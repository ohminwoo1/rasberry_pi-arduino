# rasberry_pi-arduino

## Rasberry_pi Initial Settings
```
sudo apt update
sudo apt upgrade
```

  - Broken Korean
```
sudo apt-get install fonts-unfonts-core -y
sudo apt-get install ibus-hangul -y
sudo reboot
```

## Install InfluxDB
  - InfluxDB download key using wget
```
wget -q https://repos.influxdata.com/influxdata-archive_compat.key
echo '393e8779c89ac8d958f81f942f9ad7fb82a25e133faddaf92e15b16e6ac9ce4c influxdata-archive_compat.key' | sha256sum -c && cat influxdata-archive_compat.key | gpg --dearmor | sudo tee /etc/apt/trusted.gpg.d/influxdata-archive_compat.gpg > /dev/null
echo 'deb [signed-by=/etc/apt/trusted.gpg.d/influxdata-archive_compat.gpg] https://repos.influxdata.com/debian stable main' | sudo tee /etc/apt/sources.list.d/influxdata.list
```
  - Packages are up to date && install Influxdb
```
 sudo apt-get update && sudo apt-get install influxdb -y

```
  -InfluxDB as a background service on startup
```
sudo service influxdb start
```
  -InfluxDB is status (service)
```
sudo service influxdb statuse
```

## Make InfluxDB DataBase

```
$ influx

>create database <Name of Database>
Check : show databases
```

# Grafana Installation

## 1. Install the prerequisite packages
```
sudo apt-get install -y apt-transport-https software-properties-common wget
```

## 2. Import the GPG key:
```
sudo mkdir -p /etv/apt/keyrings/
wget -q -O - https://apt.grafana.com/gpg.key | gpg --dearmor | sudo tee /etc/apt/keyrings/grafana.gpg > /dev/null
```

## 3. To add a repository for stable releases, run the following command:
```
echo "deb [signed-by=etc/apt/keyrings/grafana.gpg] https://apt.grafa.com stable main" | sudo tee -a /etc/apt/sources.list.d/grafana.list
```

## 4. Run the following command to update the list of available packages:
```
sudo apt-get update && sudo apt-get install grafana -y

```

## 5. Run the following command to server start
```
sudo systemctl start grafana-server
```
## influxdb import with python
```
pip install influxdb
```
  - hint: See PEP 668 for the detailed specification
```
  sudo rm /usr/lib/python3.11/EXTERNALLY-MANAGED
```

# TelegramBot
```
  pip install python-telegram-bot --upgrade
  git clone https://github.com/python-telegram-bot/python-telegram-bot
  pip install python-telegram-bot[job-queue] --pre
```
