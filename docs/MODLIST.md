# Mod List

Черновой список для Minecraft `1.12.2` + Forge `14.23.5.2860`.

HBM-ветка пока не финализирована. После проверки экосистемы основной кандидат для теста - `HBM's Nuclear Tech Mod: Community Edition`; ранее выбранный `Extended Edition` остается fallback-кандидатом. Подробности: `docs/HBM_ECOSYSTEM.md`.

## Required

| Mod | Side | Role | Notes |
| --- | --- | --- | --- |
| HBM's Nuclear Tech Mod: Community Edition | common | Nuclear tech core | Главный кандидат для теста на `1.12.2`. |
| Hbm's Nuclear Tech Mod Extended Edition | common | Nuclear tech core fallback | Запасной кандидат: `NTM-Extended-1.12.2-3.0.3.jar`. Не ставить вместе с CE. |
| Just Enough Items | client | Recipes/UI | Нужен игрокам для рецептов и изучения цепочек производства. |
| The One Probe | common | Block/entity inspection | Удобнее WAILA/HWYLA для технических сборок. |
| CodeChicken Lib | common | Library | Только если потребуется выбранными модами. |

## Recommended Technical Mods

| Mod | Side | Role | Notes |
| --- | --- | --- | --- |
| Applied Energistics 2 | common | Storage/logistics | Хорошая база для поздней игры. |
| Thermal Foundation | common | Materials/library | Брать только если добавляем Thermal stack. |
| Thermal Expansion | common | Machines | Не должен перетягивать прогрессию HBM на себя. |
| Thermal Dynamics | common | Pipes/logistics | Проверить баланс с HBM трубами. |
| Ender IO | common | Machines/conduits | Кандидат, может сильно упростить логистику. |
| Mekanism | common | Tech | Оставляем в плане: совместимость с HBM подтверждена отдельным изучением. |
| Immersive Engineering | common | Tech/energy | Хорошо ложится в индустриальную тематику. |
| Storage Drawers | common | Storage | Удобно для массовых ресурсов. |
| Iron Chests | common | Storage | Низкий риск, полезно в ранней игре. |
| Controlling | client | Keybind search | Клиентский QoL. |
| Mouse Tweaks | client | Inventory QoL | Клиентский QoL. |
| Inventory Tweaks | client | Inventory QoL | Проверить стабильность на `1.12.2`. |
| AppleSkin | client | Food HUD | Клиентский QoL. |
| JourneyMap | client | Map | Сервер может запретить cave/radar настройки правилами. |

## Quests And Progression

| Mod | Side | Role | Notes |
| --- | --- | --- | --- |
| FTB Quests | common | Quest book | Основная система квестов для HBM-прогрессии. |
| FTB Library | common | Library | Зависимость FTB Quests. |
| Item Filters | common | Quest dependency | Фильтры предметов для FTB Quests. |
| CraftTweaker | common | Recipe scripting | Добавлять после стабилизации base modlist. |
| ModTweaker | common | Modded machine scripting | Кандидат для интеграции CraftTweaker с машинами. |
## Farming And Food

| Mod | Side | Role | Notes |
| --- | --- | --- | --- |
| Pam's HarvestCraft | common | Farming/cooking | Основной кандидат на фермерство и кулинарию. |
| Cooking for Blockheads | common | Kitchen UX | Хорошо дополняет Pam's HarvestCraft. |
| Spice of Life: Carrot Edition | common | Food variety HP rewards | Увеличивает максимальное HP за разнообразную еду. |

## Browser Map

| Tool | Side | Role | Notes |
| --- | --- | --- | --- |
| DynmapForge | server | Browser map | Основной кандидат. Настроить низкую частоту рендера и отключить агрессивные live-triggers. |
| Minecraft Overviewer | external | Static isometric map | Кандидат для hourly cron-рендера с минимальной нагрузкой на сервер. Проверить HBM/Pam блоки. |
| BlueMap | server/external | 3D browser map | Красиво, но путь для `1.12.2` требует отдельной проверки. |

## Performance And Admin

| Mod | Side | Role | Notes |
| --- | --- | --- | --- |
| FoamFix | common | Memory optimization | Проверить настройки отдельно для клиента и сервера. |
| BetterFps | client | Client performance | Только клиент. |
| Phosphor | common | Lighting performance | Кандидат, тестировать с HBM worldgen/tiles. |
| VanillaFix | client | Crash handling/performance | Обычно клиентский. |
| Chunk-Pregenerator | server | World pregen | Важно для сервера с тяжелой генерацией. |
| Spark | server | Profiler | Использовать для диагностики TPS и лагов. |
| AI Improvements | server | Mob AI optimization | Снижает нагрузку от мобов. |
| FastWorkbench | common | Crafting optimization | Уменьшает нагрузку от crafting lookup. |
| FastFurnace | common | Furnace optimization | Уменьшает нагрузку от furnace lookup. |
| Clumps | common | XP orb optimization | Объединяет XP orbs. |
| VintageFix | common | Modern 1.12.2 optimization | Кандидат вместо FoamFix, не ставить вместе без теста. |
| Surge | common | Startup/runtime optimization | Кандидат, проверить coremod-совместимость. |
| TexFix | client | Texture memory optimization | Полезно для слабых клиентов. |

## Later Candidates

| Mod | Side | Role | Notes |
| --- | --- | --- | --- |
| Galacticraft | common | Space | Тематически подходит, но требует отдельного совместимого набора аддонов. |
| OpenComputers | common | Automation | Хорош для продвинутой автоматизации. |
| Super Factory Manager | common | Automation | Кандидат из NTM Standard Pack. |
| Chisel | common | Building | Декор, низкий gameplay-риск. |
| MCHeliCE | common | Vehicles/combat | Только если нужна техника/авиация. |
| Warforge Remaintained | common | Warfare | Поздний optional-кандидат. |
| ComputerCraft/CC:Tweaked | common | Automation | Альтернатива OpenComputers. |
| IC2 | common | Tech | Deferred: еще одна полная tech-прогрессия. |
| NuclearCraft | common | Nuclear tech | Deferred: дублирует роль HBM. |
| Draconic Evolution | common | Power creep | Rejected for now: слишком сильный скачок мощности. |
| Uncrafting Table | common | Utility | Rejected for now: dupe/balance risk. |
