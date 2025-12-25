---
title: 2.2.3. Модель ~ Расчёта Сомнения
description: IDEMO ~ Ontology of Dynamic Systems. __description__
published: true
date: 2025-12-25T17:16:58.651Z
tags: 
editor: markdown
dateCreated: 2025-12-25T17:16:58.651Z
---

## 2.2.3.1. Основное {#2-2-3-1}
Документ описывает модель расчёта Сомнения как метрики множественности альтернатив в Viewpoint.

> *Версия: doc.2.2.3.v.1.0.0.1 ∙ декабрь 2025*<br/><br class="hidden-wiki"/>
> *Текущий LifeCycle:* `Draft` → Candidate → Stable → Canonical<br class="hidden-wiki"/>
> *Фаза:*. `Birth` → Develop → Climax → Degrade → Turn → End( death | transform )<br/><br class="hidden-wiki"/>
> *Текущий ChangeFlow:* #1<br class="hidden-wiki"/>
> *Фаза:* `collect` → analyze → forecast → decide → implement → evaluate<br/><br class="hidden-wiki"/>
> <a href="/ru/2-applied/4-examples/1-common/doc-lifecycle.md" target="_blank"><small>Подробно о LifeCycle документа</small></a>

## 2.2.3.2. Связанные документы {#2-2-3-2}
### 2.2.3.2.1. Исходящие *(ссылается этот документ)*
- [1.3.8 Определение~Сомнение](/ru/1-core/3-definitions/doubt.md)
- [1.3.1 Определение~Viewpoint](/ru/1-core/3-definitions/viewpoint.md)
- [1.1.4 Спецификация~ChangeOperators](/ru/1-core/1-specifictions/change-operators.md)

### 2.2.3.2.2. Входящие *(ссылаются на этот документ)*
- (пока нет)

## 2.2.3.3. Описание модели {#2-2-3-3}
Модель вычисляет Сомнение как функцию от количества/значимости альтернатив и ёмкости доступных ChangeOperators.

### Формула
$$
Doubt = C \cdot \frac{A}{A + A_0} \cdot \sigma\left(\alpha (T - T_0)\right)
$$
где:
- $A = \sum_j v_j$ — взвешенная сумма альтернатив,
- $T = \sum_i W_i Q_i$ — агрегированная ёмкость инструментов,
- $C \geq 1$ — цена ошибки,
- $A_0 > 0$ — полунасыщение по альтернативам,
- $\alpha > 0$ — крутизна сигмоиды,
- $T_0$ — порог ёмкости инструментов,
- $\sigma(x) = \frac{1}{1 + e^{-x}}$ — сигмоида.

### Параметры
| Параметр | Интерпретация                  | Примерные значения |
|----------|--------------------------------|-------------------|
| $A_0$    | Полунасыщение по альтернативам | 2–5               |
| $\alpha$ | Крутизна перехода              | 1–5               |
| $T_0$    | Порог ёмкости инструментов     | 0.5–1.5           |
| $C$      | Цена ошибки                    | 1–3               |

### Интерпретация значений
- Doubt ≈ 0: ложная уверенность (аналог Dunning-Kruger).
- Doubt ≈ 1: максимальное сомнение (аналог imposter syndrome).

## 2.2.3.4. Динамическая настройка параметров {#2-2-3-4}
Параметры корректируются на основе графа опыта:
- +1 ассоциации → снижение $A_0$, $T_0$.
- -1 ассоциации → рост $C$.
- Динамичные контексты → рост $\alpha$.

## 2.2.3.5. Триггер MetaChangeFlow {#2-2-3-5}
При Doubt > θ (θ ≈ 0.7) запускается MetaChangeFlow для пересмотра Viewpoint и операторов.

## 2.2.3.6. Следствия модели {#2-2-3-6}
- Сомнение — адаптивный механизм предотвращения локальных оптимумов.
- Автоматическая настройка усиливает самоулучшение системы.
- Полюса модели объясняют системные аналоги Dunning-Kruger и imposter syndrome.
- Триггер MetaChangeFlow обеспечивает мета-адаптацию при высоком сомнении.

> **Онлайн-версия:** https://ods.idemo.ru/ru/2-applied/2-models/doubt-calculation.md
> **GitHub-версия:** https://github.com/idemo-ru/ods/blob/main/ru/2-applied/2-models/doubt-calculation.md