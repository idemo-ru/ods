---
title: 2.2.6. Модель ~ Валидация Intent
description: IDEMO ~ Ontology of Dynamic Systems. __description__
published: true
date: 2025-12-26T08:48:24.242Z
tags: 
editor: markdown
dateCreated: 2025-12-26T08:42:46.431Z
---

## 2.2.6.1. Основное {#2-2-6-1}
Документ описывает модель валидации Intent через метрику осмысленности и её интеграцию с Doubt/MetaChangeFlow.

> *Версия: doc.2.2.6.v.1.0.0.1 ∙ декабрь 2025*<br/><br class="hidden-wiki"/>
> *Текущий LifeCycle:* `Draft` → Candidate → Stable → Canonical<br class="hidden-wiki"/>
> *Фаза:*. `Birth` → Develop → Climax → Degrade → Turn → End( death | transform )<br/><br class="hidden-wiki"/>
> *Текущий ChangeFlow:* #1<br class="hidden-wiki"/>
> *Фаза:* `collect` → analyze → forecast → decide → implement → evaluate<br/><br class="hidden-wiki"/>
> <a href="/ru/2-applied/4-examples/1-common/doc-lifecycle.md" target="_blank"><small>Подробно о LifeCycle документа</small></a>

## 2.2.6.2. Связанные документы {#2-2-6-2}
### 2.2.6.2.1. Исходящие *(ссылается этот документ)*
- [1.1.5 Спецификация~Intent](/ru/1-core/1-specifictions/intent.md)
- [1.1.6 Спецификация~Осмысленность Intent](/ru/1-core/1-specifictions/intent-meaningfulness.md)
- [1.3.8 Определение~Сомнение](/ru/1-core/3-definitions/doubt.md)
- [2.2.4 Модель~MetaChangeFlow](/ru/2-applied/2-models/meta-change-flow.md)

### 2.2.6.2.2. Входящие *(ссылается на этот документ)*
- (пока нет)

## 2.2.6.3. Описание модели {#2-2-6-3}
Модель валидирует Intent перед ChangeFlow по метрике осмысленности M.

### Метрика осмысленности
Бинарная:  
$$ M = \prod_{i=1}^{10} m_i $$  
(критерии из 1.1.6).

Градуированная:  
$$ M = \sum_{i=1}^{10} w_i m_i $$  
\( m_i, w_i \in [0,1] \).

M=0 → Intent отвергается (не запускает ChangeFlow).

## 2.2.6.4. Интеграция с Doubt {#2-2-6-4}
- M=0 → высокий Doubt (бессмысленное Intent усиливает множественность/неопределённость).
- M<θ_m → триггер повышения Doubt и запуска MetaChangeFlow.

## 2.2.6.5. Интеграция с MetaChangeFlow {#2-2-6-5}
- При M=0 или низком M: MetaChangeFlow синтезирует/корректирует Intent для повышения M.
- Граф опыта: -1 для Intent с M=0; +1 усиливает осмысленные.

## 2.2.6.6. Следствия модели {#2-2-6-6}
- Фильтрация бессмысленных Intent на входе ChangeFlow.
- Усиление адаптации via связь с Doubt/MetaChangeFlow.
- Обеспечение онтологической чистоты и устойчивости ODS.

> **Онлайн-версия:** https://ods.idemo.ru/ru/2-applied/2-models/intent-validation.md
> **GitHub-версия:** https://github.com/idemo-ru/ods/blob/main/ru/2-applied/2-models/intent-validation.md