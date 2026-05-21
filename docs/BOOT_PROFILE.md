# Boot Profile: HBM CE Minimal

Цель профиля: проверить, что выбранная HBM-линия запускается на dedicated server и что клиент может подключиться без лишних модов, Sponge, оптимизаторов и QoL-слоя.

## Fixed Line

- HBM line: `HBM's Nuclear Tech Mod: Community Edition`
- Minecraft: `1.12.2`
- Loader / server core: `Forge 14.23.5.2860`
- Java: `8`
- OS target: `Ubuntu Server 22.04 LTS`, headless, без GUI

## Minimal Server Mods

В `profiles/server/mods/` для первого boot-test кладем только:

1. `HBM's Nuclear Tech Mod: Community Edition`
2. Обязательные зависимости HBM CE, если они указаны на странице релиза

Не добавлять на первом запуске:

- SpongeForge
- CE Space
- Leafia addon
- Galacticraft Companion
- HBM structure addons
- JEI, JourneyMap, AppleSkin и другие клиентские QoL-моды
- FoamFix, Phosphor, BetterFps и другие оптимизаторы

## Minimal Client Mods

В `profiles/client/mods/` для первого подключения кладем:

1. `HBM's Nuclear Tech Mod: Community Edition`
2. Те же обязательные зависимости HBM CE, что и на сервере

Клиентский профиль должен совпадать с сервером по модам, которые регистрируют блоки, предметы, жидкости, измерения, рецепты или worldgen.

## First Boot Checklist

1. Сервер запускается до строки `Done`.
2. Сервер создает новый мир без crash-report.
3. Клиент с тем же HBM CE build подключается к серверу.
4. В логах нет registry mismatch.
5. В новом мире генерируются HBM-руды и структуры, если они включены в самой CE-базе.
6. Можно поставить и сломать базовые HBM-блоки.
7. Сервер корректно останавливается командой `stop`.
8. После повторного запуска мир открывается без ошибок.

## Success Criteria

Профиль считается пройденным, если:

- dedicated server работает 30 минут без crash-report;
- один клиент подключается, двигается по миру и взаимодействует с HBM-блоками;
- restart сервера не ломает мир;
- в логах нет повторяющихся ошибок уровня `ERROR` по HBM, registry, missing mappings или world save.

## Next Profile After Success

После успешного минимального boot-profile можно создавать следующий профиль:

`HBM CE + required client QoL + server diagnostics`

Только после этого тестировать:

- SpongeForge
- CE Space
- Leafia addon
- structure addons
- крупные технические моды

