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
| `Pam's HarvestCraft` | client + server | recommended | Фермерство, новые культуры и еда. Хорошая база для survival-сервера. |
| `Cooking for Blockheads` | client + server | recommended | Кухонные блоки и удобная готовка, хорошо дополняет Pam's HarvestCraft. |
| `Spice of Life: Carrot Edition` | client + server | recommended | Увеличивает максимальное HP за поедание разнообразной еды. |

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
| `Mekanism` | client + server | recommended | Оставляем в плане сборки. Совместимость с HBM подтверждена отдельным изучением. |
| `Galacticraft` | client + server | candidate | Космос. Имеет смысл только вместе с отдельной проверкой HBM-интеграций. |

## Фермерство, Еда И HP

| Mod | Side | Status | Notes |
| --- | --- | --- | --- |
| `Pam's HarvestCraft` | client + server | recommended | Основной мод на фермерство и кулинарию для `1.12.2`. Не конфликтует с HBM по тематике и дает мирную прогрессию для маленького сервера. |
| `Cooking for Blockheads` | client + server | recommended | Кухонная инфраструктура и удобный доступ к рецептам еды. Особенно полезен вместе с Pam's HarvestCraft. |
| `Spice of Life: Carrot Edition` | client + server | recommended | Дает постоянные дополнительные сердца за уникальные съеденные блюда. Хорошо мотивирует использовать кулинарный контент. |

## Карта В Браузере

| Tool | Side | Status | Notes |
| --- | --- | --- | --- |
| `DynmapForge` | server | primary candidate | Web-карта прямо из Forge-сервера. Настраивать низкую частоту рендера, отключать агрессивные live-triggers и делать fullrender вручную или по расписанию. |
| `Minecraft Overviewer` | external | candidate for low load | Внешний генератор статической изометрической карты. Можно запускать cron-раз в час, почти не трогает tick-thread сервера. Минус: модовые блоки HBM/Pam нужно проверять отдельно. |
| `BlueMap` | server / standalone | candidate | Красивая 3D web-карта, но для `1.12.2` путь установки менее прямой и может требовать Sponge или standalone-процесс. |

Предпочтение сейчас: начать с `DynmapForge`, а если нагрузка будет заметной - перейти к внешнему `Minecraft Overviewer` с hourly render.

## Оптимизация

Оптимизаторы добавляем после чистого HBM CE boot-test. Coremod-оптимизации нельзя ставить пачкой без проверки: они часто пересекаются по зонам ответственности.

| Mod | Side | Status | Notes |
| --- | --- | --- | --- |
| `Spark` | server | recommended | Профилирование перед оптимизацией. Сначала измеряем TPS, entities, tile entities и heap. |
| `Chunk-Pregenerator` | server | recommended | Предгенерация мира снижает лаги exploration на публичном запуске. |
| `AI Improvements` | server | recommended | Снижает нагрузку от mob AI. |
| `FastWorkbench` | client + server | recommended | Оптимизирует crafting lookup. |
| `FastFurnace` | client + server | recommended | Оптимизирует furnace lookup. |
| `Clumps` | client + server | recommended | Объединяет XP orbs и уменьшает entity load. |
| `VintageFix` | client + server | candidate | Современная оптимизация для `1.12.2`; тестировать как альтернативу FoamFix, не ставить вслепую вместе. |
| `FoamFix` | client + server | candidate | Старый проверенный оптимизатор памяти. Использовать только если VintageFix не подходит или тесты показывают пользу. |
| `Phosphor` | client + server | candidate | Оптимизация освещения. Проверить с HBM worldgen, структурами и tile entities. |
| `Surge` | client + server | candidate | Оптимизации старта и runtime. Проверить на совместимость с HBM CE и другими coremods. |
| `VanillaFix` | client | recommended | Клиентские фиксы крашей и производительности. |
| `TexFix` | client | candidate | Снижение расхода видеопамяти на текстуры. Полезно для слабых клиентов. |
| `BetterFps` | client | candidate | Клиентский FPS-тюнинг. Тестировать после основного набора, потому что эффект зависит от железа. |

## HBM CE Source

Основной HBM-мод, на который опирается сборка: `HBM's Nuclear Tech Mod: Community Edition`.

Source repository: `Warfactory-Official/Hbm-s-Nuclear-Tech-CE`.

Это именно выбранная CE-линия для Minecraft `1.12.2`: в исходниках проекта указан `modName = HBM's Nuclear Tech Mod: Community Edition`, `modId = hbm`, `minecraftVersion = 1.12.2`, а release archive формируется как `NTM-CE-1.12.2`.

Для сервера берем опубликованный release `.jar`, а не случайную сборку из `master`. Важный нюанс: исходники могут собираться современным JDK через downgrader, но runtime-цель для Minecraft `1.12.2` остается Java 8.

## HBM Аддоны

| Addon | Target | Side | Status | Notes |
| --- | --- | --- | --- | --- |
| `HBM's NTM CE: Space` | NTM:CE | client + server | CE-compatible candidate | Space addon для CE. Требует `MixinBooter`. Не включать в первый boot-test. |
| `HBM's Nuclear Tech - Leafia's Cursed Addon` | NTM:CE | client + server | CE-compatible risky | Явно заявлен как CE addon, но стабильность ниже. Тестировать отдельным профилем. |
| `HBM Galacticraft Companion` | HBM + Galacticraft Legacy | client + server | conditional / unknown with CE | Только если добавляем Galacticraft и подтверждаем совместимость именно с CE. |
| `HBM Fixes` | HBM 1.12.2 legacy ports | client + server | not for CE unless proven | Не ставить поверх CE без конкретной причины. |
| `Potatoo's Custom Structure For HBM's Nuclear Tech Mod` | HBM 1.12.2 / Reloaded | client + server | not for CE unless proven | Target не подтвержден для CE, worldgen-риск. |
| `HBM/NTM structure` | NTM Extended | client + server | not compatible with CE plan | Ориентирован на Extended, не на CE. |
| `HBM Ruins Pack` | HBM 1.12.x | client + server | not for CE unless proven | Неясная совместимость. |
| `MSFH More structures for hbm` | HBM Reloaded | client + server | not compatible with CE plan | Ориентирован на Reloaded, не на CE. |
| `More Stuff for Minecraft` | HBM + Creative Items | client + server | pack-dev only | Полезно только для кастомных рецептов. |
| `HBM NTM Lucky blocks` | HBM Extended | client + server | rejected for main server | Ломает баланс и прогрессию. |

Правило для HBM-аддонов: в CE-сборку допускаются только аддоны, где target явно указан как `NTM:CE` или `Community Edition`. Extended/Reloaded structure addons не считаем совместимыми.

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
| `SpongeForge` | SpongeForge | optional later | Нужен только если позже понадобится plugin-enabled профиль. Для маленького сервера стартуем без него. |
| `LuckPerms` | Sponge | optional | Только если понадобятся группы прав. |
| `Spark` | Sponge or Forge | recommended | Для текущего плана предпочтительнее Forge-вариант без Sponge. |
| `UltimateChat` | Sponge | optional | Каналы и форматирование чата. |
| `Plan` | Sponge | optional | Аналитика игроков. |

Не добавляем для текущего маленького сервера:

- `WorldEdit`
- `EconomyLite`
- `GriefPrevention`
- `Nucleus`

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
