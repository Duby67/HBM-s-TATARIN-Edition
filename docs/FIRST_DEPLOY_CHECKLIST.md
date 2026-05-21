# First Deploy Checklist

Цель: первый headless запуск `HBM NTM: Community Edition` на Ubuntu Server 22.04.

## Before Upload

1. Скачать Forge installer/server для `1.12.2-14.23.5.2860`.
2. Скачать выбранный build `HBM's Nuclear Tech Mod: Community Edition`.
3. Проверить страницу релиза HBM CE на обязательные зависимости.
4. Не скачивать и не добавлять дополнительные моды.

## Server Files

На Ubuntu в `/opt/hbm-server/server` должны оказаться:

```text
forge-1.12.2-14.23.5.2860.jar
minecraft_server.1.12.2.jar
server.properties
eula.txt
start.sh
mods/
config/
```

В `mods/`:

```text
HBM CE jar
required dependency jars, if any
```

## Commands

```bash
sudo apt update
sudo apt install -y openjdk-8-jre-headless screen curl unzip
sudo useradd -r -m -U -d /opt/hbm-server -s /bin/bash minecraft
sudo mkdir -p /opt/hbm-server/server
sudo chown -R minecraft:minecraft /opt/hbm-server
```

После загрузки файлов:

```bash
cd /opt/hbm-server/server
chmod +x start.sh
java -version
./start.sh
```

## First Start Expected Failure

Первый запуск может остановиться из-за EULA. Это нормально.

После чтения EULA:

```text
eula=true
```

Затем запустить сервер снова.

## Pass Criteria

1. В консоли есть строка `Done`.
2. Нет crash-report.
3. Клиент с тем же HBM CE build подключается к серверу.
4. Сервер штатно останавливается командой `stop`.
5. Повторный запуск открывает тот же мир без ошибок.

