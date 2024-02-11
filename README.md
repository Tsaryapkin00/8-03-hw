# Домашнее задание к занятию "Система мониторинга Zabbix" - `Царяпкин Константин`


### Задание 1

Установите Zabbix Server с веб-интерфейсом.

Процесс выполнения
 1. Установите PostgreSQL. Для установки достаточна та версия, что есть в системном репозитороии Debian 11.
 2. Пользуясь конфигуратором команд с официального сайта, составьте набор команд для установки последней версии Zabbix с поддержкой PostgreSQL и Apache.
 3. Выполните все необходимые команды для установки Zabbix Server и Zabbix Web Server.
    
Требования к результаты
 1. Прикрепите в файл README.md скриншот авторизации в админке.
 2. Приложите в файл README.md текст использованных команд в GitHub.

---

### Решение 1

![img](img width="667" alt="image" src="https://github.com/Tsaryapkin00/8-03-hw/assets/117481592/682add8e-34b4-49b8-aad9-c13a600bfc63")

Код для терминала
```bash
# wget https://repo.zabbix.com/zabbix/6.0/ubuntu/pool/main/z/zabbix-release/zabbix-release_6.0-4+ubuntu22.04_all.deb
# dpkg -i zabbix-release_6.0-4+ubuntu22.04_all.deb
# apt update
# apt install zabbix-server-pgsql zabbix-frontend-php php8.1-pgsql zabbix-apache-conf zabbix-sql-scripts zabbix-agent
# sudo -u postgres createuser --pwprompt zabbix
# sudo -u postgres createdb -O zabbix zabbix
# zcat /usr/share/zabbix-sql-scripts/postgresql/server.sql.gz | sudo -u zabbix psql zabbix
# sed -i 's/# DBPassword=/DBPassword=<Пароль>/g' /etc/zabbix_server.conf
# systemctl restart zabbix-server zabbix-agent apache2
# systemctl enable zabbix-server zabbix-agent apache2
```

---

### Задание 2

Установите Zabbix Agent на два хоста.

Процесс выполнения
 1. Установите Zabbix Agent на 2 вирт.машины, одной из них может быть ваш Zabbix Server.
 2. Добавьте Zabbix Server в список разрешенных серверов ваших Zabbix Agentов.
 3. Добавьте Zabbix Agentов в раздел Configuration > Hosts вашего Zabbix Servera.
 4. Проверьте, что в разделе Latest Data начали появляться данные с добавленных агентов.
    
Требования к результаты
 1. Приложите в файл README.md скриншот раздела Configuration > Hosts, где видно, что агенты подключены к серверу
 2. Приложите в файл README.md скриншот лога zabbix agent, где видно, что он работает с сервером
 3. Приложите в файл README.md скриншот раздела Monitoring > Latest data для обоих хостов, где видны поступающие от агентов данные.
 4. Приложите в файл README.md текст использованных команд в GitHub


---

### Репшение 2

---
