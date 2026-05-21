# Server Profile

Этот профиль предназначен для dedicated server на Ubuntu Server 22.04 без GUI.

## Boot Profile

Текущая тестовая линия:

- Minecraft `1.12.2`
- Forge `14.23.5.2860`
- Java `8`
- HBM base: `HBM's Nuclear Tech Mod: Community Edition`
- GUI: no, запуск только с `nogui`

## Template Files

- `server.properties.example` - шаблон настроек сервера.
- `eula.txt.example` - EULA не принимается автоматически.
- `start.sh.example` - шаблон headless запуска.
- `hbm-server.service.example` - пример systemd unit.

Перед запуском на Ubuntu:

```bash
cp server.properties.example server.properties
cp eula.txt.example eula.txt
cp start.sh.example start.sh
chmod +x start.sh
```

После прочтения EULA изменить:

```text
eula=true
```

## First Test Rule

На первом запуске в `mods/` должен лежать только HBM CE и его обязательные зависимости. Все остальные моды добавляются позже отдельными тестовыми шагами.

