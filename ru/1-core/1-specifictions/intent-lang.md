---
title: 1.1.5. Спецификация ~ Intent Lang - iLang
description: IDEMO ~ Ontology of Dynamic Systems. __description__
published: true
date: 2025-12-10T16:00:02.920Z
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
- **LC-6:** LifeCycle-6 *(см. связанные документы)*;
- **CF-6:** ChengeFlow-6 *(см. связанные документы)*;
- **CO:** ChangeOperators *(см. связанные документы)*;
- **Intent:** Единственный хранимый артефакт *. Реализация (код) всегда эфемерна.

## 1.1.5.4. Область применения {#1-2-5-4}
Структурная конструкция LC-6 и CF-6.

## 1.1.5.5. Корневые топологические Intent - примитивы {#1-1-5-5}
Примитивы связанные с фазами LC-6, CF-6, осушествляющие фазовые переходы.
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
| `^`    | decide       | Разрешить неопределённость, выбрать вариант (коллапс неопределённости)     | decide                         |
| `>`    | implement    | Реализовать | implement                      |
| `_`    | evaluate     | Зафиксировать результат (записать новое состояние)     | evaluate                       |

## 1.1.5.6. Корневые процессные Intent - примитивы {#1-1-5-6}
| Символ | Имя          | Смысл                                   | Связь с процессом |
|--------|--------------|-----------------------------------------|---------------------------------|
| `/`    | split        | Разделить поток / сущность              | ветвление                      |
| `*`    | merge        | Объединить потоки / сущности            | слияние                        |
| `!`    | reflect      | Рефлексия                               | обучение                       |
| `<>`   | wait         | Ожидать условия                         | синхронизация                  |
| `**`   | repeat       | Повторить с условием/счётчиком          | циклы                          |

## 1.1.5.7. Контекст и пространства имён {#1-1-5-7}

```yaml
#iLang.context
@domain.subdomains_path.entity:inner_path          		# полный путь
import domain.subdomains_path.entity as alias      		# импорт
@alias:path                                   				# короткая запись
@path!                                        				# строгое подключение 
																											# (ошибка, если недоступно)
@path?                                        				# опциональное (продолжить без него)
@path:timeout=5s                              				# с таймаутом
/cond > @alias_1:path, @alias_1:path									# подклбчение по условию в теле flow
/cond > (/cond > @alias_1:path, @alias_1:path), @alias_3:path
```

> **Онлайн-версия:** https://ods.idemo.ru/ru/1-core/1-specifictions/intent-lang.md
> **GitHub-версия:** https://github.com/idemo-ru/ods/blob/main/ru/1-core/1-specifictions/intent-lang.md