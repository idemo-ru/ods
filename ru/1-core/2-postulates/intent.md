---
title: 1.2.1. Постулат  ~  Intent как атомарная единица смысла
description: IDEMO ~ Ontology of Dynamic Systems. __description__
published: true
date: 2025-12-12T02:35:31.630Z
tags: 
editor: markdown
dateCreated: 2025-12-12T01:53:07.161Z
---

## 1.2.1.1. Основное {#1-2-1-1}
Документ постулирует Intent (намерение) как Intent — онтологически первичную, недекомпозируемую единицц вычислительного смысла в ODS.

> *Версия: doc.1.2.1.v.1.2.8.5 ∙ декабрь 2025*<br/><br class="hidden-wiki"/>
> *Текущий LifeCycle:* ~~Draft~~ → `Candidate` → Stable → Canonical<br class="hidden-wiki"/>
> *Фаза:*. ~~Birth~~ → ~~Develop~~ → `Climax` → Degrade → Turn → End( death | transform )<br/><br class="hidden-wiki"/>
> *Текущий ChangeFlow:* #5<br  class="hidden-wiki"/>
> *Фаза:*  ~~collect~~ → ~~analyze~~ → ~~forecast~~ → ~~decide~~ → ~~implement~~ → `evaluate`<br/><br class="hidden-wiki"/>
> <a href="/ru/2-applied/4-examples/1-common/doc-lifecycle.md" target="_blank"><small>Подробно о LifeCycle документа</small></a>

## 1.2.1.2. Связанные документы {#1-2-1-2}
### 1.2.1.2.1. Исходящие *(ссылается этот документ)*
- (пока нет)
### 1.2.1.2.2. Входящие *(ссылаются на этот документ)*
- (пока нет)

## 1.2.1.3. Термины и определения {#1-2-__id__-3}
**Intent** — чистое, реализационно-независимое описание того, что должно быть достигнуто системой в одном полном цикле изменения.

Intent делится на два канонических класса:  
- **Primitive Intent** — атомарный смысл одной фазы (неделимый квант)  
- **Composite Intent** — валидная композиция Primitive Intent’ов, соответствующая контракту ChangeFlow-6

## 1.2.1.4. Формулировка постулата {#1-2-1-4}
1. Каждый ChangeFlow-6 есть композиция Intent’ов  
2. Каждый Composite Intent есть один полный ChangeFlow-6 в чистом виде  
3. Primitive Intent не содержит смысл ровно одной фазы и не подлежит дальнейшему разложению  
4. Реализация любого Intent всегда вторична и эфемерна  
5. Смысл системы полностью исчерпывается последовательностью её Composite Intent’ов

## 1.2.1.5. Обновлённое определение системы {#1-2-1-5}
System(Y) = A⟨ChangeOperators⟩ ( S-Layer, LifeCycle ⊕ **Sequence⟨CompositeIntent⟩** | C-Layer ≠ ∅ )

## 1.2.1.6. Следствия для правил декомпозиции {#1-2-1-6}
- RLC/CC: X — дочерняя LifeCycle ⇔ X обладает хотя бы одним Composite Intent, не наследуемым от родителя  
- ROS: декомпозиция останавливается, когда все нижние ChangeFlow реализуют один и тот же Composite Intent разными ChangeOperator’ами

## 1.2.1.7. Связи с другими терминами {#1-2-1-7}
- Родительские: 1.3.0.1 Система, 1.1.01 RLC/CC, 1.1.02 ROS
- Дочерние: ChangeFlow-6 (переопределён), decide(), implement()
- Связанные: Primitive Intent, Composite Intent, ChangeOperator

## 1.2.1.10. Заключение {#1-2-1-10}
Постулат Intent закрывает микроуровень динамики систем а иак же онтологическую дыру между смыслом и реализацией.  
Отныне в ODS есть только Intent’ы и их временные актуализации через ChangeOperators. (под сомнением)