---
title: 1.1.5. Спецификация ~ Intent Lang - iLang
description: IDEMO ~ Ontology of Dynamic Systems. __description__
published: true
date: 2025-12-10T15:00:07.585Z
tags: 
editor: markdown
dateCreated: 2025-12-10T14:35:03.657Z
---

## 1.1.5.1. Основное {#1-2-5-1}
Документ описывает iLang — первый и единственный чисто смысловой язык программирования в парадигме IDEMO.

> *Версия: doc.1.1.5.v.0.1.3.1 ∙ декабрь 2025*<br/><br class="hidden-wiki"/>
> *Текущий LifeCycle:* `Draft` → Candidate → Stable → Canonical<br class="hidden-wiki"/>
> *Фаза:*. ~~Birth~~ → `Develop` → Climax → Degrade → Turn → End<br/><br class="hidden-wiki"/>
> *Текущий ChangeFlow:* #__index__<br  class="hidden-wiki"/>
> *Фаза:*  ~~collect~~ → `analyze` → forecast → decide → implement → evaluate<br/><br class="hidden-wiki"/>
> <a href="/ru/2-applied/4-examples/1-common/doc-lifecycle.md" target="_blank"><small>Подробно о LifeCycle документа</small></a>

## 1.1.5.2. Связанные документы {#1-1-5-2}
### 1.1.5.2.1. Исходящие *(ссылается этот документ)*
- [1.1.12 Манифест ~ IDEMO v1.0](/ru/1-core/1-manifesto/idemo-v1.md)
- [1.1.1 Спецификация ~ LifeCycle-6](/ru/1-core/1-specifictions/life-cycle-6.md)
- [1.1.2 Спецификация ~ ChangeFlow-6](/ru/1-core/1-specifictions/change-flow-6.md)
- [1.1.3 Спецификация ~ ChangeOperators](/ru/1-core/1-specifictions/change-operators.md)
### 1.1.5.2.2. Входящие *(ссылаются на этот документ)*
- *не определены*

## 1.1.5.3. Термины и определения {#1-1-5-3}
- *Intent:* Единственный хранимый артефакт *. Реализация (код) всегда эфемерна.

## 1.1.5.4. Область применения {#1-2-5-4}
```
Определяет контекст, где используется данная спецификациф.
Четко разграничивает, где актуально, а где нет.
```

## 1.1.5.5. 16 корневых примитивов Intent {#1-1-5-5}

| Символ | Имя          | Смысл                                   | Связь с ChangeFlow / LifeCycle |
|--------|--------------|-----------------------------------------|---------------------------------|
| `+`    | birth        | Породить новую сущность                 | Birth                          |
| `−`    | death        | Завершить существование                 | End → death                    |
| `=`    | transform    | Сохранить идентичность при смене формы  | Turn → transform               |
| `+=`   | develop      | Увеличить сложность / эффективность     | Develop → Climax               |
| `-=`   | degrade      | Уменьшить сложность / эффективность     | Degrade                        |
| `?`    | collect      | Собрать контекст / данные               | collectData                    |
| `??`   | analyze      | Осмыслить, отфильтроватьб исследовать   | analyze                        |
| `~`    | forecast     | Спрогнозировать варианты исходов        | forecast                       |
| `^`    | decide       | Разрешить неопределённость, выбрать     | decide                         |
| `>`    | implement    | Реализовать (единственный локальный)   | implement                      |
| `_`    | evaluate     | Зафиксировать результат в expMemory     | evaluate                       |
| `/`    | split        | Разделить поток / сущность              | ветвление                      |
| `*`    | merge        | Объединить потоки / сущности            | слияние                        |
| `!`    | reflect      | Рефлексия / откат при -1                | обучение                       |
| `<>`   | wait         | Ожидать условия                         | синхронизация                  |
| `**`   | repeat       | Повторить с условием/счётчиком          | циклы                          |

## 1.1.4.4. Контекст и пространства имён

```ilang
@domain.subdomain.entity:inner_path          # полный путь
import domain.subdomain.entity as alias      # импорт
@alias:path                                   # короткая запись
@path!                                        # строгое подключение (ошибка, если недоступно)
@path?                                        # опциональное (продолжить без него)
@path:timeout=5s                              # с таймаутом

## 1.1.__id__.__n__. __Свободные_блоки__ {#1-2-__id__-__n__}
```
Любые дополнительные блоки, не указанные в дланном шаблоне
```

## 1.1.__id__.__n__. Заключение {#1-2-__id__-__n__}
```
Следствия, примечания, другая резюмирующая информация.
```

> **Онлайн-версия:** https://ods.idemo.ru/ru/1-core/1-specifictions/__slug__.md
> **GitHub-версия:** https://github.com/idemo-ru/ods/blob/main/ru/1-core/1-specifictions/__slug__.md