---
title: 1.1.6. Спецификация ~ Осмысленность Intent
description: IDEMO ~ Ontology of Dynamic Systems. __description__
published: true
date: 2025-12-26T08:40:27.269Z
tags: 
editor: markdown
dateCreated: 2025-12-26T08:40:23.538Z
---

## 1.1.6.1. Основное {#1-1-6-1}
Документ специфицирует осмысленность Intent как обязательный критерий валидности потенциала действия.

> *Версия: doc.1.1.6.v.1.0.0.1 ∙ декабрь 2025*<br/><br class="hidden-wiki"/>
> *Текущий LifeCycle:* `Draft` → Candidate → Stable → Canonical<br class="hidden-wiki"/>
> *Фаза:*. `Birth` → Develop → Climax → Degrade → Turn → End( death | transform )<br/><br class="hidden-wiki"/>
> *Текущий ChangeFlow:* #1<br class="hidden-wiki"/>
> *Фаза:* `collect` → analyze → forecast → decide → implement → evaluate<br/><br class="hidden-wiki"/>
> <a href="/ru/2-applied/4-examples/1-common/doc-lifecycle.md" target="_blank"><small>Подробно о LifeCycle документа</small></a>

## 1.1.6.2. Связанные документы {#1-1-6-2}
### 1.1.6.2.1. Исходящие *(ссылается этот документ)*
- [1.1.5 Спецификация~Intent](/ru/1-core/1-specifictions/intent.md)
- [1.3.7 Определение~Опыт](/ru/1-core/3-definitions/experience.md)
- [1.3.8 Определение~Сомнение](/ru/1-core/3-definitions/doubt.md)

### 1.1.6.2.2. Входящие *(ссылаются на этот документ)*
- (пока нет)

## 1.1.6.3. Термины и определения {#1-1-6-3}
**Осмысленность Intent** — структурная валидность потенциала действия по 10 критериям.

## 1.1.6.4. Область применения {#1-1-6-4}
Обязательна для всех Intent в ODS. Не применима к психологическим или феноменологическим интерпретациям.

## 1.1.6.5. Критерии осмысленности {#1-1-6-5}
| № | Критерий                          | Описание                                                                 |
|---|-----------------------------------|--------------------------------------------------------------------------|
| 1 | Context-Coherence                | Соответствие текущему контексту                                          |
| 2 | Dissonance-Resolution Capacity   | Способность разрешить рассинхронизацию/конфликт                          |
| 3 | Ontological Soundness            | Совместимость с онтологией системы                                       |
| 4 | Flow-Integrability               | Встраиваемость в ChangeFlow                                              |
| 5 | Resource Feasibility             | Доступность необходимых ресурсов                                         |
| 6 | Predictive Determinacy           | Предсказуемость диапазона результатов                                    |
| 7 | Meta-Goal Alignment              | Согласованность с мета-целями/инвариантами                                |
| 8 | Complexity Sufficiency           | Достаточная, но не избыточная сложность                                  |
| 9 | Internal Coherence               | Логическая непротиворечивость                                            |
|10 | Outcome Verifiability            | Проверяемость результата                                                 |

## 1.1.6.6. Формула валидности {#1-1-6-6}
Бинарная:  
$$ M = \prod_{i=1}^{10} m_i $$  
где \( m_i = 1 \) если критерий выполнен, иначе 0.  
M=1 → осмысленно; M=0 → отвергнуть Intent.

Градуированная (опционально):  
$$ M = \sum_{i=1}^{10} w_i m_i $$  
\( m_i, w_i \in [0,1] \), нормировка весов.

## 1.1.6.7. Аналогия с λ-исчислением {#1-1-6-7}
Intent ≡ λ-абстракция (потенциальная трансформация).  
Осмысленность ≡ type checking (валидность перед β-редукцией/действием).  
M=0 ≡ ill-typed (редукция невозможна).

## 1.1.6.8. Заключение {#1-1-6-8}
Осмысленность — онтологический firewall Intent, обеспечивающий валидность перед ChangeFlow.

> **Онлайн-версия:** https://ods.idemo.ru/ru/1-core/1-specifictions/intent-meaningfulness.md
> **GitHub-версия:** https://github.com/idemo-ru/ods/blob/main/ru/1-core/1-specifictions/intent-meaningfulness.md