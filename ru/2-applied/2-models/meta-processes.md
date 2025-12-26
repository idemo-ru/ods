---
title: 2.2.11. Модель ~ Мета-процессы (MetaChangeFlow)
description: IDEMO ~ Ontology of Dynamic Systems. __description__
published: true
date: 2025-12-26T16:10:39.844Z
tags: 
editor: markdown
dateCreated: 2025-12-26T15:52:27.916Z
---

## 2.2.11.1. Основное {#2-2-11-1}
Документ описывает мета-процессы как рефлексивные циклы над ChangeFlow/Viewpoint/Intent.

> *Версия: doc.2.2.11.v.1.0.0.1 ∙ декабрь 2025*<br/><br class="hidden-wiki"/>
> *Текущий LifeCycle:* `Draft` → Candidate → Stable → Canonical<br class="hidden-wiki"/>
> *Фаза:*. `Birth` → Develop → Climax → Degrade → Turn → End( death | transform )<br/><br class="hidden-wiki"/>
> *Текущий ChangeFlow:* #1<br class="hidden-wiki"/>
> *Фаза:* `collect` → analyze → forecast → decide → implement → evaluate<br/><br class="hidden-wiki"/>
> <a href="/ru/2-applied/4-examples/1-common/doc-lifecycle.md" target="_blank"><small>Подробно о LifeCycle документа</small></a>

## 2.2.11.2. Связанные документы {#2-2-11-2}
### 2.2.11.2.1. Исходящие *(ссылается этот документ)*
- [2.2.4 Модель~MetaChangeFlow](/ru/2-applied/2-models/meta-change-flow.md)
- [1.3.1 Определение~Viewpoint](/ru/1-core/3-definitions/viewpoint.md)
- [1.3.7 Определение~Опыт](/ru/1-core/3-definitions/experience.md)

### 2.2.11.2.2. Входящие *(ссылается на этот документ)*
- (пока нет)

## 2.2.11.3. Описание модели {#2-2-11-3}
Мета-процессы — рекурсивные циклы рефлексии над элементами ODS (Viewpoint, Intent, Doubt, параметры).

### Фазы
1. **Триггер → collect**: условие (Doubt > θ, низкая M).
2. **Рефлексия → analyze**: создание MetaViewpoint.
3. **Генерация → forecast**: альтернативы via MetaOperators (Split/Merge/Rotate/Invent/Prune/Adjust).
4. **Оценка → decide**: прогноз Doubt/EV/M.
5. **Применение → implement**: фиксация нового состояния; архивация старого.
6. **Архивация/обновление → evaluate**: запись в граф опыта, superseded_by связи.

Рекурсия: глубина ≤ 3.

### Интеграция с графом опыта
- Реюз успешных конфигураций.
- Контрфактическая симуляция.
- Обновление: superseded_by связи.

## 2.2.11.4. Универсальность
Требуют полный ChangeFlow + рефлексию (analyze/forecast/decide над собой).

По классам систем:
- Класс 0–1 (детерминированные): нет (только implement, нет decide/recurse).
- Класс 2–3: зародышевые (ограниченная рефлексия над инстинктами).
- Класс 4: базовые (рефлексия над опытом).
- Класс 5: полные (MetaChangeFlow над Viewpoint/Intent).
- Класс 6: множественные вложенные (самоэволюция).

## 2.2.11.5. Примеры мета-процессов {#2-2-11-5}
- MetaChangeFlow: адаптация Viewpoint при Doubt.
- Мета-валидация Intent: повышение M.
- Мета-управление Doubt: корректировка параметров.

## 2.2.11.6. Следствия модели {#2-2-11-6}
- Универсальный механизм самоулучшения ODS.
- Предотвращает застревание/паралич.
- Ускоряет эволюцию архитектуры.

> **Онлайн-версия:** https://ods.idemo.ru/ru/2-applied/2-models/meta-processes.md
> **GitHub-версия:** https://github.com/idemo-ru/ods/blob/main/ru/2-applied/2-models/meta-processes.md