# Plugin List

Плагины предполагают серверный профиль с `SpongeForge` для Minecraft `1.12.2`. Bukkit/Spigot/Paper-плагины в обычный Forge-сервер не подходят.

## Required For Public Server

| Plugin | Platform | Role | Notes |
| --- | --- | --- | --- |
| LuckPerms | Sponge | Permissions | База прав и групп. |
| Nucleus | Sponge | Essentials/admin commands | Команды, homes, warps, mute, jail и админские инструменты. |
| GriefPrevention | Sponge | Claims/protection | Приваты для модового сервера. Нужно тестировать с HBM взрывами и радиацией. |
| Spark | Sponge or Forge | Profiling | Профилирование TPS, tick entities, heap. |

## Recommended

| Plugin | Platform | Role | Notes |
| --- | --- | --- | --- |
| UltimateChat | Sponge | Chat channels | Каналы чата и форматирование. |
| NuVotifier | Sponge | Voting integration | Только если нужен vote rewards. |
| Plan | Sponge | Player analytics | Полезно для публичного сервера, требует БД/веб. |
| EconomyLite | Sponge | Economy | Только если нужна экономика. |

## Candidate / Test First

| Plugin | Platform | Role | Notes |
| --- | --- | --- | --- |
| WorldEdit Sponge | Sponge | Admin editing | Использовать осторожно с модовыми блоками. |
| CatClearLag alternatives | Sponge | Cleanup | Проверить, чтобы не удалял нужные модовые entities/items. |

