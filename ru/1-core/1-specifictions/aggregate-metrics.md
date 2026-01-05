---
title: 1.1.3. Спецификация ~ DegradeScore
description: IDEMO ~ Ontology of Dynamic Systems. DegradeScore — универсальная метрика деградации любой системы (от частиц до цивилизаций), единственная координата, определяющая текущую из шести фаз жизненного цикла.
published: true
date: 2026-01-05T19:14:25.003Z
tags: 
editor: markdown
dateCreated: 2025-12-08T11:58:25.184Z
---

## 1.1.3.1. Основное {#1-1-3-1}
Документ описывает единый реестр агрегатных скалярных метрик, являющихся координатами состояния системы.

> *Версия: doc.1.1.3.v.1.31.6 ∙ июнь 2025*<br/><br class="hidden-wiki"/>
> *Текущий LifeCycle:* `Draft` → Candidate → Stable → Canonical<br class="hidden-wiki"/>
> *Фаза:*. `Birth` → Develop → Climax → Degrade → Turn → End( death | transform )<br/><br class="hidden-wiki"/>
> *Текущий ChangeFlow:* #31<br  class="hidden-wiki"/>
> *Фаза:*  `collect` → analyze → forecast → decide → implement → evaluate<br/><br class="hidden-wiki"/>
> <a href="/ru/2-applied/4-examples/1-common/doc-lifecycle.md" target="_blank"><small>Подробно о LifeCycle документа</small></a>

## 1.1.3.2. Связанные документы {#1-1-3-2}
### 1.1.3.2.1. Исходящие *(ссылается этот документ)*
- [1.2.1 Постулат~ Об исключении антропоморфности](/ru/1-core/2-postulates/no-anthropomorphism.md)
- [1.3.10 Определение~ Идентичность системы](/ru/1-core/3-definitions/identity.md)

### 1.1.3.2.2. Входящие *(ссылаются на этот документ)*
- [1.1.1 Спецификация~ LifeCycle-6](/ru/1-core/1-specifications/life-cycle-6.md)
- [1.3.0 Определение~ Система](/ru/1-core/3-definitions/0-system.md)

## 1.1.3.3. Иерархия метрик {#1-1-3-3}
| Уровень | Метрика | Размерность | Назначение |
+|---------|---------|-------------|------------|
| 0 | **DegradeVector** | 4-мерный ⟨DS, Δt_s, Δt_p, Tag⟩ | вход в фазовую аксиому |
| 1 | **DegradeScore** (DS) | [0,1] | координата «износ / усталость» |
| 2 | **ResilienceRatio** (RR) | [0,1] | 1 − DS, исходная координата |
| 3+ | **доменные** (CI, RM…) | опц. | эмерджентность, ресурсы |

&gt; Уровень 0 обязателен для всех систем; уровни 2+ фиксируются классом-наследником.

## 1.1.3.4. Формула свертки DegradeScore {#1-1-3-4}
DS(t) = 1 – RR(t)  
RR(t) = σ( Σᵢ ωᵢ · rrᵢ(t) )  
где  
- rrᵢ(t) ∈ [0,1] — нормализованная частная метрика,  
- ωᵢ ≥ 0, Σωᵢ = 1 — веса класса (Прил. A),  
- σ(x) = clamp(x, 0, 1).

## 1.1.3.5. Реестр доменных метрик-доноров (прил. B) {#1-1-3-5}
| ID | Доменная метрика | Домен | Нормализация |
|----|-----------------|--------|--------------|
| rr_bio | % живых клеток | био | live/total |
| rr_code | % успешных CI/CD | IT | success/total |
| rr_star | % водорода | звезды | H_now/H_init |
| rr_corp | % удержания сотрудников | компания | 1–(увол./штат) |

&gt; Список rrᵢ и веса ωᵢ жёстко фиксируются для каждого ClassTag и версионируются совместно с документом.

## 1.1.3.6. DegradeVector и фазовая аксиома {#1-1-3-6}
**DegradeVector**(S, t) = ⟨DS(t), Δt_stable(t), Δt_phase(t), ClassTag⟩  
**Фазовая аксиома** — таблица Phase : DegradeVector → {birth, develop, climax, degrade, turn, end} (Прил. X).  
Наблюдатель вычисляет вектор и читает фазу; интерпретации нет.

## 1.1.3.7. Практика наблюдателя {#1-1-3-7}
1. Собрать rrᵢ → RR → DS.  
2. Измерить Δt_stable, Δt_phase, прочитать ClassTag.  
3. Подать DegradeVector в таблицу-аксиому → получить фазу.  
4. (Опц.) Дополнительные метрики логируются, но фазу не меняют.

## 1.1.3.8. Заключение
DegradeScore остаётся единой фундаментальной скалярной координатой, но не единственным элементом вывода фазы.  
Любая претензия на «субъективизм» снимается векторной аксиомой, жёстко привязанной к ClassTag.

> **Онлайн-версия:** https://ods.idemo.ru/ru/1-core/1-specifications/aggregate-metrics.md 
> **GitHub-версия:** https://github.com/idemo-ru/ods/blob/main/ru/1-core/1-specifications/aggregate-metrics.md