# Ubuntu 22.04 Headless Server

Целевая среда: Ubuntu Server 22.04 LTS без GUI.

## System Packages

Minecraft Forge `1.12.2` требует Java 8.

```bash
sudo apt update
sudo apt install -y openjdk-8-jre-headless screen curl unzip
```

Проверка:

```bash
java -version
```

Ожидаем Java `1.8.x`. Если на сервере установлено несколько Java, выбрать Java 8:

```bash
sudo update-alternatives --config java
```

## User And Directory

Рекомендуемый отдельный пользователь:

```bash
sudo useradd -r -m -U -d /opt/hbm-server -s /bin/bash minecraft
sudo mkdir -p /opt/hbm-server/server
sudo chown -R minecraft:minecraft /opt/hbm-server
```

Рабочая директория сервера:

```text
/opt/hbm-server/server
```

## Files To Place

Минимальный набор после установки Forge:

```text
/opt/hbm-server/server/
  forge-1.12.2-14.23.5.2860.jar
  minecraft_server.1.12.2.jar
  eula.txt
  server.properties
  mods/
    HBM-CE build jar
  config/
  start.sh
```

Точные имена `.jar` фиксируются после скачивания и тестового запуска.

## Headless Start

Для ручного запуска:

```bash
cd /opt/hbm-server/server
./start.sh
```

Для запуска в `screen`:

```bash
screen -S hbm
cd /opt/hbm-server/server
./start.sh
```

Выйти из screen без остановки сервера:

```text
Ctrl+A, затем D
```

Вернуться:

```bash
screen -r hbm
```

## Memory Baseline

Для первого boot-test:

```text
Xms: 2G
Xmx: 4G
```

Для публичного сервера HBM это почти наверняка придется поднять после профилирования. Начинать с завышенных значений не нужно: сначала важно увидеть реальное поведение boot-profile.

## Firewall

Если используется `ufw`:

```bash
sudo ufw allow 25565/tcp
```

RCON не открывать наружу. Если RCON понадобится, ограничить доступ firewall-правилами или VPN.

