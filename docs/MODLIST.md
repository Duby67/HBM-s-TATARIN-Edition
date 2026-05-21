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
| Mekanism | common | Tech | Кандидат: возможен конфликт по балансу с HBM. |
| Immersive Engineering | common | Tech/energy | Хорошо ложится в индустриальную тематику. |
| Storage Drawers | common | Storage | Удобно для массовых ресурсов. |
| Iron Chests | common | Storage | Низкий риск, полезно в ранней игре. |
| Controlling | client | Keybind search | Клиентский QoL. |
| Mouse Tweaks | client | Inventory QoL | Клиентский QoL. |
| Inventory Tweaks | client | Inventory QoL | Проверить стабильность на `1.12.2`. |
| AppleSkin | client | Food HUD | Клиентский QoL. |
| JourneyMap | client | Map | Сервер может запретить cave/radar настройки правилами. |

## Performance And Admin

| Mod | Side | Role | Notes |
| --- | --- | --- | --- |
| FoamFix | common | Memory optimization | Проверить настройки отдельно для клиента и сервера. |
| BetterFps | client | Client performance | Только клиент. |
| Phosphor | common | Lighting performance | Кандидат, тестировать с HBM worldgen/tiles. |
| VanillaFix | client | Crash handling/performance | Обычно клиентский. |
| Chunk-Pregenerator | server | World pregen | Важно для сервера с тяжелой генерацией. |
| Spark | server | Profiler | Использовать для диагностики TPS и лагов. |

## Later Candidates

| Mod | Side | Role | Notes |
| --- | --- | --- | --- |
| Galacticraft | common | Space | Тематически подходит, но требует отдельного совместимого набора аддонов. |
| OpenComputers | common | Automation | Хорош для продвинутой автоматизации. |
| ComputerCraft/CC:Tweaked | common | Automation | Альтернатива OpenComputers. |
| NuclearCraft | common | Nuclear tech | Под вопросом: может дублировать роль HBM. |
