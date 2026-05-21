# HBM's TATARIN Edition

Репозиторий для подготовки Minecraft-сборки вокруг `HBM's Nuclear Tech Mod: Community Edition` с отдельными клиентским и серверным профилями.

Главная цель: сначала получить стабильный dedicated server на Ubuntu без GUI, затем постепенно добавлять QoL, аддоны, серверные инструменты и плагинный слой.

## Базовая платформа

| Component | Version / Target | Status | Notes |
| --- | --- | --- | --- |
| Minecraft | `1.12.2` | fixed | Базовая версия сборки. |
| Forge | `14.23.5.2860` | fixed | Основное серверное ядро и mod loader. |
| Java | `8` / `1.8.x` | fixed | Для Ubuntu: `openjdk-8-jre-headless`. |
| Server OS | `Ubuntu Server 22.04 LTS` | fixed | Headless, без GUI. |
| HBM line | `HBM's Nuclear Tech Mod: Community Edition` | fixed for boot-test | Основная HBM-линия. |
| Plugin layer | `SpongeForge` | later profile | Не включать в первый boot-test. |

## Первый Boot-Profile

Первый запуск делаем минимальным:

| Side | Component | Status | Notes |
| --- | --- | --- | --- |
| client + server | `HBM's Nuclear Tech Mod: Community Edition` | required | Единственная HBM-база. Не смешивать с Extended, Reloaded, Hamster, Waldemar или official 1.7.10. |
| client + server | HBM CE required dependencies | required if present | Проверить на странице конкретного релиза перед скачиванием. |

На первом запуске не добавляем:

- SpongeForge
- CE Space
- Leafia addon
- Galacticraft Companion
- structure addons
- JEI и клиентские QoL-моды
- FoamFix, Phosphor, BetterFps и другие оптимизаторы
- крупные технические моды

Подробности: [docs/BOOT_PROFILE.md](docs/BOOT_PROFILE.md).

## Основные Моды

| Mod | Side | Status | Notes |
| --- | --- | --- | --- |
| `HBM's Nuclear Tech Mod: Community Edition` | client + server | required | Основной мод сборки. |
| `Just Enough Items` | client | required after boot-test | Рецепты и просмотр предметов. Не нужен для первого server boot. |
| `The One Probe` | client + server | recommended | Информация о блоках и сущностях. |
| `Applied Energistics 2` | client + server | recommended | Хранение и автоматизация. |
| `Storage Drawers` | client + server | recommended | Массовое хранение ресурсов. |
| `Iron Chests` | client + server | recommended | Простое расширение сундуков. |
| `Immersive Engineering` | client + server | recommended | Индустриальная техника, требует проверки баланса с HBM. |
| `FoamFix` | client + server | recommended after boot-test | Оптимизация памяти, конфиг тестировать отдельно. |
| `Chunk-Pregenerator` | server | recommended | Предгенерация мира перед публичным запуском. |
| `Spark` | server | recommended | Профилирование TPS, heap и лагов. |

## Клиентские QoL-Моды

| Mod | Side | Status | Notes |
| --- | --- | --- | --- |
| `JourneyMap` | client | recommended | Карта. Cave/radar-настройки нужно согласовать с правилами сервера. |
| `AppleSkin` | client | recommended | Отображение насыщения и еды. |
| `Mouse Tweaks` | client | recommended | Удобство инвентаря. |
| `Controlling` | client | recommended | Поиск конфликтов клавиш. |

## Кандидаты На Технический Стек

Эти моды не входят в первый профиль. Их добавляем только после стабильного HBM CE boot-test.

| Mod | Side | Status | Notes |
| --- | --- | --- | --- |
| `Thermal Foundation` | client + server | candidate | Библиотека/материалы для Thermal stack. |
| `Thermal Expansion` | client + server | candidate | Машины. Может перетянуть прогрессию на себя. |
| `Thermal Dynamics` | client + server | candidate | Трубы и логистика. Проверить баланс с HBM. |
| `Ender IO` | client + server | candidate | Сильные conduits и машины. Проверить баланс. |
| `Mekanism` | client + server | candidate | Крупный tech stack, высокий риск конфликта по прогрессии. |
| `Galacticraft` | client + server | candidate | Космос. Имеет смысл только вместе с отдельной проверкой HBM-интеграций. |

## HBM Аддоны

| Addon | Target | Side | Status | Notes |
| --- | --- | --- | --- | --- |
| `HBM's NTM CE: Space` | NTM:CE | client + server | high candidate | Space addon для CE. Требует `MixinBooter`. Не включать в первый boot-test. |
| `HBM's Nuclear Tech - Leafia's Cursed Addon` | NTM:CE | client + server | optional / risky | Быстро обновляется, но стабильность ниже. |
| `HBM Galacticraft Companion` | HBM + Galacticraft Legacy | client + server | optional | Только если добавляем Galacticraft. |
| `HBM Fixes` | HBM 1.12.2 legacy ports | client + server | candidate for legacy ports | Не ставить поверх CE без проверки необходимости. |
| `Potatoo's Custom Structure For HBM's Nuclear Tech Mod` | HBM 1.12.2 / Reloaded | client + server | optional | Worldgen. Выбрать до старта публичного мира. |
| `HBM/NTM structure` | NTM Extended | client + server | optional | Ориентирован на Extended, не считать совместимым с CE без теста. |
| `HBM Ruins Pack` | HBM 1.12.x | client + server | low confidence | Проверить формат установки и совместимость. |
| `MSFH More structures for hbm` | HBM Reloaded | client + server | low confidence | Маленький structure addon, требует ручной проверки источника. |
| `More Stuff for Minecraft` | HBM + Creative Items | client + server | pack-dev only | Полезно только для кастомных рецептов. |
| `HBM NTM Lucky blocks` | HBM Extended | client + server | rejected for main server | Ломает баланс и прогрессию. |

## Библиотеки И Зависимости

| Library / Dependency | Required For | Status | Notes |
| --- | --- | --- | --- |
| `Forge 14.23.5.2860` | all mods | fixed | Основной loader. |
| `Java 8` | Forge 1.12.2 server | fixed | На Ubuntu использовать headless JRE. |
| `MixinBooter` | `HBM's NTM CE: Space` | conditional | Нужен только если включаем CE Space или другой addon с mixins. |
| `CodeChicken Lib` | selected legacy mods | conditional | Добавлять только если конкретный выбранный мод потребует. |
| `Thermal Foundation` | Thermal stack | candidate | Одновременно библиотека и контентная база Thermal-модов. |

## Серверные Плагины

Плагины возможны только в отдельном профиле `Forge + SpongeForge`. Bukkit/Spigot/Paper-плагины в обычный Forge-сервер не подходят.

| Plugin | Platform | Status | Notes |
| --- | --- | --- | --- |
| `SpongeForge` | SpongeForge | later required | Нужен только для plugin-enabled профиля. Тестировать отдельно от чистого Forge. |
| `LuckPerms` | Sponge | recommended | Права и группы. |
| `Nucleus` | Sponge | recommended | Essentials/admin-команды. |
| `GriefPrevention` | Sponge | recommended | Приваты. Обязательно тестировать HBM-взрывы и радиацию. |
| `Spark` | Sponge or Forge | recommended | Не ставить одновременно Forge- и Sponge-вариант без причины. |
| `UltimateChat` | Sponge | optional | Каналы и форматирование чата. |
| `Plan` | Sponge | optional | Аналитика игроков. |
| `EconomyLite` | Sponge | optional | Только если нужна экономика. |
| `WorldEdit` | Sponge | candidate | Осторожно с модовыми блоками. |

## Разделение Клиента И Сервера

| Profile | Contents |
| --- | --- |
| `profiles/client/` | Клиентские моды, клиентские конфиги, resourcepacks. |
| `profiles/server/` | Dedicated server, server configs, server-only mods, Sponge plugins. |
| `profiles/common/` | Конфиги, которые должны совпадать у клиента и сервера. |

Правило: если мод регистрирует блоки, предметы, жидкости, рецепты, измерения или worldgen, он должен быть одинаковым на клиенте и сервере.

## Структура Репозитория

```text
docs/
  BOOT_PROFILE.md
  DECISIONS.md
  FIRST_DEPLOY_CHECKLIST.md
  HBM_ECOSYSTEM.md
  MODLIST.md
  PLUGINLIST.md
  SERVER_CLIENT_SPLIT.md
  UBUNTU22_SERVER.md
manifests/
  hbm-addons.csv
  hbm-modpacks.csv
  hbm-variants.csv
  mods.csv
  plugins.csv
profiles/
  client/
  common/
  server/
scripts/
```

## Repository Policy

В git храним документацию, манифесты, шаблоны конфигов и скрипты.

Не коммитим:

- `.jar`
- `.zip`
- миры
- логи
- crash-reports
- runtime-конфиги с секретами
- локальные клиентские настройки

Точные `.jar` и версии файлов фиксируем после скачивания и успешного тестового запуска.
