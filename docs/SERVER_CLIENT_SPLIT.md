# Server And Client Split

## Common

Моды из общей части должны стоять и на клиенте, и на сервере. Обычно это контентные, технические и библиотечные моды: HBM, JEI-зависимые интеграции, хранение предметов, трубы, генерация руд, машины.

Файлы:

- `profiles/client/mods/`
- `profiles/server/mods/`
- `profiles/common/config/`

## Client Only

Клиентские моды не кладем на сервер. Типичные признаки:

- миникарта
- интерфейс инвентаря
- HUD
- шейдеры
- оптимизация рендера
- тултипы
- ресурспаки

Примеры:

- JourneyMap
- AppleSkin
- BetterFps
- FoamFix client-side настройки
- Inventory Tweaks
- The One Probe client display

## Server Only

Серверные моды и плагины не кладем в клиентский профиль. Типичные задачи:

- права
- приваты
- экономика
- мониторинг TPS
- бэкапы
- pregen мира
- админские команды

Примеры:

- SpongeForge
- LuckPerms Sponge
- Nucleus
- GriefPrevention Sponge
- Spark
- Chunk-Pregenerator

## Config Policy

Конфиги делим так:

- `profiles/common/config/` - одинаковые для клиента и сервера
- `profiles/server/config/` - серверные лимиты, генерация мира, баланс, защита
- `profiles/client/config/` - интерфейс, HUD, графика, клавиши

Если конфиг влияет на регистрацию блоков, предметов, биомов, измерений или рецептов, он должен быть общим и совпадать у клиента и сервера.

