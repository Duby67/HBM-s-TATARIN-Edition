# HBM Ecosystem Research

Дата проверки: 2026-05-21.

Цель документа: собрать доступные ветки HBM Nuclear Tech Mod, аддоны и готовые HBM-ориентированные сборки, чтобы выбрать базу для серверной сборки.

## Shortlist

Для нашего сервера сейчас есть три реалистичные линии:

| Line | Minecraft | Recommendation | Why |
| --- | --- | --- | --- |
| HBM NTM: Community Edition | 1.12.2 | Primary candidate | Самая свежая 1.12.2-линия, позиционируется как преемник Reloaded/Extended, есть CE Space и Leafia addon. |
| HBM NTM Extended Edition | 1.12.2 | Fallback candidate | Популярная и понятная линия, но уже конкурирует с CE по актуальности и полноте. |
| Official HBM NTM | 1.7.10 | Content benchmark | Официальная и самая полная ветка, но хуже подходит под современный сервер с плагинами и QoL-модами. |

Текущий вывод: если остаемся на `1.12.2`, стоит тестировать `HBM NTM: Community Edition` первым. Extended оставляем как запасной вариант, потому что у него большая база установок и больше старых аддонов.

## Base Mod Variants

| Name | MC | Latest observed | Status | Notes |
| --- | --- | --- | --- | --- |
| Hbm's Nuclear Tech Mod | 1.7.10 | `HBM-NTM-[1.0.27_X5687].jar`, 2026-05-06 | Official / active | Главная upstream-линия. Лучший ориентир по контенту, но тяжелее для серверной инфраструктуры. |
| HBM's Nuclear Tech Mod: Community Edition | 1.12.2 | `2.5.0.2`, 2026-05-01 | Strong candidate | Активный порт на 1.12.2, заявлен как наиболее полный и актуальный порт. |
| Hbm's Nuclear Tech - Extended Edition | 1.12.2 | `NTM-Extended-1.12.2-3.0.3.jar`, 2025-11-17 | Candidate / fallback | Популярный 1.12.2-порт. Автор указывает, что это не официальная 1.12.2-версия. |
| Hbm's Nuclear Tech Mod Reloaded | 1.12.2 | `hbm-1.8.4a-G.jar`, 2023-11-22 | Legacy candidate | Старый популярный порт. Сейчас выглядит менее предпочтительно, чем CE/Extended. |
| Hbm's Nuclear Tech - Hamster Reloaded | 1.12.2 | `1.12.2-1.6.4`, 2023-12-08 | Niche fork | Отдельная ветка Reloaded. Требует ручного сравнения контента и стабильности. |
| HBM's Nuclear Tech Mod - Waldemar Edition | 1.12.2 | `1.2.3.1`, 2026-05-05 | Experimental candidate | Форк Extended 2.0.2 с фиксами, оптимизацией и собственным контентом. Маленькая аудитория. |
| HBM's Nuclear Tech Modernized | 1.20.1 | `hbm_m-0.1.2-alpha.jar`, 2026-03-04 | Not for server now | Переписывание с нуля, pre-alpha, мало контента. |
| Hbm's Nuclear Tech - Muddy Edition | 1.20.1 | `2.0.0-alpha`, 2025-11-23 | Not for server now | Alpha/early rewrite, автор предупреждает не использовать важные миры. |

## Addons And Integrations

| Name | Target | MC | Latest observed | Server relevance | Notes |
| --- | --- | --- | --- | --- | --- |
| NTM CE: Space | NTM:CE | 1.12.2 | Published 2026, Modrinth | High candidate | Space addon для Community Edition. Требует NTM:CE и MixinBooter. Подходит клиенту и серверу. |
| Leafia's Cursed Addon | NTM:CE | 1.12.2 | `v42_feature`, 2026-05-05 | Optional / risky | Быстро обновляется, но автор прямо отмечает потерю общей стабильности. |
| HBM Galacticraft Companion | HBM + Galacticraft | 1.12.2 | `hbmgccompanion-0.1.5.jar`, 2026-02-07 | Optional | Делает Galacticraft Legacy и HBM более взаимозависимыми; автор предупреждает о риске поломок с отдельными форками HBM. |
| HBM Fixes | HBM 1.12.2 | 1.12.2 | `12.1.0`, 2021-07-05 | Candidate for Reloaded/older ports | Небольшой фикс-мод. Нужно проверить, нужен ли он CE; не ставить вслепую поверх нового форка. |
| Potatoo's Custom Structure For HBM | HBM 1.12.2 / Reloaded | 1.12.2 | `1.0.3`, 2022-04-23 | Optional | Добавляет HBM-структуры. Для сервера влияет на генерацию мира, тестировать до открытия мира. |
| HBM/NTM structure | NTM Extended | 1.12.2 | `2.0`, 2025-03-18 | Optional | Постапокалиптические структуры для Extended. Не считать совместимым с CE без теста. |
| HBM Ruins Pack | HBM 1.12.2 | 1.12.x | `HBM Ruins Pack_1.12.2-5(2).zip`, 2023-11-12 | Optional / low confidence | Небольшой addon pack, мало загрузок. |
| HBM NTM Lucky blocks | HBM Extended | 1.12.2 | `v1.1`, 2024-01-07 | Not recommended for serious server | Рандомные lucky blocks ломают прогрессию и баланс PvE/PvP. |
| More Stuff for Minecraft | HBM + Creative Items | 1.12.2 | `morestuff-1.1.5.jar`, 2025-09-17 | Pack-dev only | Предметы для кастомных рецептов. Полезно только если будем делать серьезный CraftTweaker/KubeJS-подобный баланс. |
| MSFH More structures for hbm | HBM Reloaded | 1.12.2 | `1.0.6`, 2026-03-14 | Low confidence | Маленький structure addon для Reloaded. Требует ручного теста и проверки источника. |

## Known Modpacks

| Name | MC | Base | Usefulness |
| --- | --- | --- | --- |
| NTM Standard Pack | 1.12.2 | NTM:CE + NTM Space | Хороший референс для CE-сборки: квесты, QoL, AE2, OpenComputers, SFM, MCHeliCE, Warforge. Можно изучать как пример прогрессии, но не копировать вслепую. |
| Nuclear Tech: New Horizons | 1.7.10 | Official HBM NTM | Референс для обучения игроков HBM через квестбук. Не подходит напрямую, если остаемся на 1.12.2. |
| HBM's Nuclear Tech Mod 1.12.2 / Technic | 1.12.2 | Older 1.12.2 HBM | Старый Technic-пак, полезен только как исторический ориентир. |

## Compatibility Rules For Our Pack

1. Нельзя смешивать форки HBM между собой: CE, Extended, Reloaded, Hamster, Waldemar и Official являются альтернативными базами, а не модами для совместной установки.
2. Аддоны структуры надо выбирать под конкретную базу HBM и тестировать на новом мире до релиза.
3. Все worldgen-аддоны фиксируем до старта публичного мира. После генерации мира менять их нельзя без риска поломанной прогрессии и неравномерного мира.
4. CE Space и Leafia addon требуют отдельного тестового профиля, потому что они завязаны на NTM:CE и могут использовать mixins.
5. Для публичного сервера не берем lucky-block аддоны в базу: они слишком сильно ломают экономику, прогрессию и PvP-баланс.

## Current Decision Proposal

Тестовая матрица:

1. `Forge 1.12.2 + HBM NTM: Community Edition`
2. `Forge 1.12.2 + HBM NTM: Community Edition + NTM CE: Space + MixinBooter`
3. `Forge 1.12.2 + HBM NTM: Community Edition + selected server utilities`
4. Если CE падает на сервере или конфликтует с нужной экосистемой, откатиться к `Extended 3.0.3`.

