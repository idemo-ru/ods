---
title: 2.3.5. Правило ~ C Frame
description: IDEMO ~ Ontology of Dynamic Systems. __description__
published: true
date: 2026-01-02T12:06:20.278Z
tags: 
editor: markdown
dateCreated: 2026-01-02T12:03:54.185Z
---

## 2.3.5.1. Основное {#2-3-5-1}
Документ формализует правило: **Context Frame (C-Frame) обязан быть построен до старта ChangeFlow и остаётся неизменным до evaluate.**

> *Версия: doc.2.3.5.v.0.1.9.1 ∙ декабрь 2025 <br class="hidden-wiki">;
> *Текущий LifeCycle:* `Draft` → Candidate → Stable → Canonical <br class="hidden-wiki">;
> *Фаза:*. `Birth` → Develop → Climax → Degrade → Turn → End( death | transform )<br class="hidden-wiki">
> *Текущий ChangeFlow:* #9 <br class="hidden-wiki">;
> *Фаза:*  `collect` → analyze → forecast → decide → implement → evaluate<br class="hidden-wiki">
> a href="/ru/2-applied/4-examples/1-common/doc-lifecycle.md" target="_blank"&gt;&lt;small&gt;Подробно о LifeCycle документа&lt;/small&gt;&lt;/a&gt;

---

## 2.3.5.2. Связанные документы {#2-3-5-2}

### 2.3.5.2.1. Исходящие *(ссылается это правило)*
- [1.1.2 Спецификация~ChangeFlow-6](/ru/1-core/1-specifications/change-flow-6.md)
- [1.1.4 Спецификация~ChangeOperators](/ru/1-core/1-specifications/change-operators.md)
- [1.3.3 Определение~TIL](/ru/1-core/3-definitions/til.md)
- [tmp.1.1.6 Спецификация~iLang](/ru/1-core/1-specifications/intent-lang.md)

### 2.3.5.2.2. Входящие *(ссылаются на это правило)*
- [2.3.1 Правило~RLC/CC](/ru/2-applied/3-rules/rlc-cc.md)
- [2.3.3 Правило~ROS](/ru/2-applied/3-rules/ros.md)
- [2.3.4 Правило~SEC/OC](/ru/2-applied/3-rules/sec-oc.md)

---

## 2.3.5.3. Термины и определения {#2-3-5-3}

- **C-Frame (Context Frame)** — формализованная структура, выделяемая системой Y внутри активного C-Layer, определяющая пространство интерпретации ChangeOperators для конкретного Intent.  
- **TIL-namespace** — иерархический адресный формат iLang: `&lt;domain&gt;.&lt;agent&gt;:&lt;entity&gt;.&lt;property&gt;`.  
- **Conditions** — операционные ограничения и требования, проецируемые из C-Layer в C-Frame синтаксисом iLang.  
- **State** — актуальное состояние системы Y в границах C-Frame (≡ S_actual).  
- **Intent** — атомарная цель, ради которой строится C-Frame.

---

## 2.3.5.4. Область применения {#2-3-5-4}

Обязательно при **любом запуске ChangeFlow-6** в системах классов 1–6.  
Не применяется к статичным объектам без LifeCycle и к системам класса 0 (детерминированный implement-only).

---

## 2.3.5.5. Формулировка правила {#2-3-5-5}

**C-Frame должен быть построен полностью до фазы collect и остаётся иммутабельным до завершения evaluate; любое изменение C-Layer во время Flow требует нового C-Frame и нового Intent.**

---

## 2.3.5.6. Обоснование и мотивация {#2-3-5-6}

- Исключает **недетерминизм** при выборе ChangeOperators.  
- Гарантирует **воспроизводимость** и **аудит** исполнения.  
- Предотвращает **runtime-изменение условий**, что могло бы нарушить каузальную цепочку CF-6.  
- Сводит **риск «ползучего контекста»** к нулю: изменения внешней среды не влияют на уже запущенный Flow.

---

## 2.3.5.7. Условия применения {#2-3-5-7}

- Intent **одобрен** и **закреплён** до старта collect.  
- Система **прошла RLC/CC** и **SEC/OC** ≤ 1 цикл назад.  
- **Новые контексты**, появившиеся после начала collect, **игнорируются до следующего Flow**.

---

## 2.3.5.8. Исключения {#2-3-5-8}

- **Критические внешние события** (фатальный сбой, исчерпание ресурса, запрет C_coord) → немедленный **форсированный переход в degrade/death** текущего Flow; новый Intent и C-Frame строятся **после** полного завершения текущего LifeCycle.  
- Системы класса 0 (implement-only) **не требуют C-Frame** — изменения полностью детерминированы родителем.

---

## 2.3.5.9. Проверяемость и критерии соблюдения {#2-3-5-9}

✓ **До collect** фиксируется **хеш C-Frame** (namespace + Conditions + доступные ChangeOperators).  
✓ **После evaluate** повторный хеш **должен совпадать**; иначе — нарушение.  
✓ **Любое изменение TIL-namespace или Conditions** во Flow фиксируется как **отдельный опыт**, но **не влияет на текущий Flow**.

---

## 2.3.5.10. Механика исполнения {#2-3-5-10}

1. Resolver получает Intent.  
2. Строит **полный TIL-namespace** и **Conditions** на основе активного C-Layer.  
3. Формирует **C-Frame** и фиксирует его хеш.  
4. **Запускает collect**; дальнейшие изменения C-Layer **игнорируются**.  
5. После evaluate хеш C-Frame **сравнивается** с исходным; несовпадение = нарушение правила.

---

## 2.3.5.11. Последствия, санкции, отклики системы {#2-3-5-11}

- **Нарушение** → Flow помечается **invalid**, результат **не записывается** в Experience, **DegradeScore увеличивается**.  
- **Соблюдение** → результат **аккумулируется**, **Experience обновляется**, **DegradeScore не изменяется**.

---

## 2.3.5.12. Примеры применения {#2-3-5-12}

**✓ Корректно:**  
```py
$order_flow(
  @(logistics.crm:order.id=42),
  => ?(collect),
  => ??(analyze),
  => ~(...),
  => ^(...),
  => >(implement),
  => _(evaluate)
)  
# C-Frame зафиксирован до ? и не меняется до _
```
✗ Возможные нарушения:
Во время implement внешний сервис изменил схему данных → namespace расширился → хеш C-Frame не совпал → Flow invalid.

## 2.3.5.13. Известные ограничения и риски {#2-3-5-13}

- Высокая волатильность C-Layer может привести к частым invalid-Flow; решается увеличением частоты новых Intent или буферизацией контекстов.
- Долгие Flow (> минуты) увеличивают окно риска; рекомендуется разбивать на цепочку коротких Intent.

## 2.3.5.14. Заключение {#2-3-5-14}

C-Frame обеспечивает детерминизм и воспроизводимость ChangeFlow, изолируя исполнение от внешних колебаний.
Правило замыкает триаду RLC/CC → ROS → SEC/OC на уровне исполнения, делая Intent-ориентированную систему предсказуемой и аудируемой.

> Онлайн-версия: https://ods.idemo.ru/ru/2-applied/3-rules/c-frame-immutability.md
> GitHub-версия: https://github.com/idemo-ru/ods/blob/main/ru/2-applied/3-rules/c-frame-immutability.md
