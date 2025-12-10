---
title: 2.4.1.1. Пример  ~  Вечный жизненный цикл документа IDEMO ~ ODS
description: IDEMO ~ Ontology of Dynamic Systems. __description__
published: true
date: 2025-12-10T11:20:55.446Z
tags: 
editor: markdown
dateCreated: 2025-12-08T16:36:01.426Z
---

## 2.4.1.1.1. Основное {#2-4-1-1-1}
Документ описывает применение IDEMO ~ ODS к крнкпетному документу текушей документации и определяет все документы системами с LifeCycle-6 & ChangeFlow-6 & Intent

> *Версия: doc.v.1.2.3.3 ∙ __месяц__ 2025*<br/><br class="hidden-wiki"/>
> *Текущий LifeCycle:*.  ~~Draft~~ → `Candidate` → Stable → Canonical<br class="hidden-wiki"/>
> *Фаза:*. ~~Birth~~ → ~~Develop~~ → `Climax` → Degrade → Turn → End<br/><br class="hidden-wiki"/>
> *Текущий ChangeFlow:* #3<br  class="hidden-wiki"/>
> *Фаза:*  ~~collect~~ → ~~analyze~~ → `forecast` → decide → implement → evaluate<br/><br class="hidden-wiki"/>
> <a href="/ru/2-applied/4-examples/1-common/doc-lifecycle.md" target="_blank"><small>Подробно о LifeCycle документа /ссылается сам на себя</small></a>

## 2.4.1.1.2. Связанные документы {#2-4-1-1-2}
### 2.4.1.1.2.1. Исходящие *(ссылается этот документ)*
- [1.2.6. Постулат ~ О фазовой полноте (6 фаз)](/ru/1-core/2-postulates/life_cycle-6-phase.md)
- [1.3.7. Спецификация ~ DegradeScore](/ru/1-core/2-specifications/DegradeScore.md)
- [1.0.0. Манифест ~ IDEMO](/ru/1-core/0-eternal/manifesto.md)
### 2.4.1.1.2.2. Входящие *(ссылаются на этот документ)*
→ все документы /ru/1-core/, /ru/2-appied/ (автоматическая обратная связь)

## 2.4.1.1.3. Правило версионирования {#2-4-1-1-3}
|---|
| Сегмент | Источник или шаблон |
| **prefix** | doc.v |
| **lvl_1** | индекс текущего LifeCycle (трансформацим, инкарнации) |
| **lvl_2** | индекс текущей фазы текущего LifeCycle |
| **lvl_3** | индекст текушего ChangeFlow |
| **lvl_4** | индекст текущей фазы текущего ChangeFlow |

> **Шаблон версии:** doc.v.__lvl_1__.__lvl_2__.__lvl_3__.__lvl_4__
{.is-info}


## 2.4.1.1.4. Граф LC-6 {#2-4-1-1-4}
```yaml
	# ODS Eternal Lifecycle Metadata v1.0 — КАНОНИЧЕСКИЙ ПРИМЕР (псевдокод)
  
id: "2.4.1.1" # Сквозной порядковый номер документа
title: "Пример ~ Вечный жизненный цикл документа ODS"
incarnation: 3 # Индекс текущей инкарнации
version: doc.v.3.158.0 # версия по шаблону

lifecycle: # Граф текущей инкарнации
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

expirience: # Граф опыта системы
  incarnations:
    -  incarnation: 0
      name: Draft
      started_at: 2025-12-08
      ended_at: 2025-12-08
      final_ds: 0.94
      changeflows: 
      	count: 27
        ids: ***
    -  incarnation: 1
      name: Candidate
      started_at: 2025-12-08
      ended_at: 2025-12-08
      final_ds: 0.61
      changeflows: 
      	count: 79
        ids ***
    -  incarnation: 2
      name: Stable
      started_at: 2025-12-08
      ended_at: 2025-12-08
      final_ds: 0.19
      changeflows: 
      	count: 51
        ids: ***
 ```

## 1.2.__id__.__n__. Заключение {#1-2-__id__-__n__}
Каждый документ IDEMO ~ ODS — это бессмертная сущность с вечным `id`,  
проходящая цепочку воплощений Draft → Candidate → Stable → Canonical  
через те же самые 6 фаз и DegradeScore, что и любая другая система во Вселенной.

> Ссылка на этот канон обязательна в каждом документе /1-core/ и /2-applied/
{.is-success}


**Файл:** /ru/1-core/4-examples/1-common/doc-lifecycle
