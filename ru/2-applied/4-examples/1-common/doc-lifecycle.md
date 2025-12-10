---
title: 2.4.1.1. Пример  ~  Вечный жизненный цикл документа IDEMO ~ ODS
description: IDEMO ~ Ontology of Dynamic Systems. __description__
published: true
date: 2025-12-10T09:18:14.239Z
tags: 
editor: markdown
dateCreated: 2025-12-08T16:36:01.426Z
---

## 2.4.1.1.1. Основное {#2-4-1-1-1}
Статус: | `Draft` | Candidate | Stable | Canonical |

Версия: doc.v.0.1 ∙ декабрь 202*

> Документ описывает применение IDEMO ~ ODS к документу текушей документации как системе
{.is-info}


## 2.4.1.1.2. Связанные документы {#2-4-1-1-2}
### 2.4.1.1.2.1. Исходящие *(ссылается этот документ)*
- [1.2.6. Постулат ~ О фазовой полноте (6 фаз)](/ru/1-core/2-postulates/life_cycle-6-phase.md)
- [1.3.7. Спецификация ~ DegradeScore](/ru/1-core/2-specifications/DegradeScore.md)
- [1.0.0. Манифест ~ IDEMO](/ru/1-core/0-eternal/manifesto.md)
### 2.4.1.1.2.2. Входящие *(ссылаются на этот документ)*
→ все документы /ru/1-core/, /ru/2-appied/ (автоматическая обратная связь)

## 2.4.1.1.3. Правило версионирования {#2-4-1-1-3}
**prefix**: doc.v
**lvl_1**: индекс текущего LifeCycle (трансформацим, инкарнации)
**lvl_2**: индекст текушего ChangeFlow
**lvl_3**: индекст текущей фазы текушего ChangeFlow

- Шаблон версии: doc.v.__lvl_1__.__lvl_2__.__lvl_3__

## 2.4.1.1.4. Граф LC-6 {#2-4-1-1-4}
```yaml
	# ODS Eternal Lifecycle Metadata v1.0 — КАНОНИЧЕСКИЙ ПРИМЕР
  
id: "2.4.1.1"
title: "Пример ~ Вечный жизненный цикл документа ODS"
incarnation: 3
version: doc.v.3.158.0

lifecycle:
  name: Canonical
  started_at: 2025-12-08
  phase: 
  	climax
  	started_at: 2025-12-08
  degrade_score: 0.07
  changeflows:
    current: 
    	id: "cf-2025-12-08-158"
      phase: collect
    	index: 158
    last_evaluated_at: 2025-12-08
    stats:
      total:   157
      success: 142
      neutral:  13
      failure:   2

expirience:
  incarnations:
    -  incarnation: 0
      name: Draft
      started_at: 2025-12-08
      ended_at: 2025-12-08
      final_ds: 0.94
      changeflows: 27
    -  incarnation: 1
      name: Candidate
      started_at: 2025-12-08
      ended_at: 2025-12-08
      final_ds: 0.61
      changeflows: 79
    -  incarnation: 2
      name: Stable
      started_at: 2025-12-08
      ended_at: 2025-12-08
      final_ds: 0.19
      changeflows: 51
 ```

## 1.2.__id__.__n__. Заключение {#1-2-__id__-__n__}
Каждый документ IDEMO ~ ODS — это бессмертная сущность с вечным `id`,  
проходящая цепочку воплощений Draft → Candidate → Stable → Canonical  
через те же самые 6 фаз и DegradeScore, что и любая другая система во Вселенной.

> Ссылка на этот канон обязательна в каждом документе /1-core/ и /2-applied/
{.is-success}


**Файл:** /ru/1-core/4-examples/1-common/doc-lifecycle
