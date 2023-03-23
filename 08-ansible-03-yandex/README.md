# Домашнее задание к занятию "08.03 Использование Yandex Cloud"

## Подготовка к выполнению

1. (Необязательно) Познакомтесь с [lighthouse](https://youtu.be/ymlrNlaHzIY?t=929)
2. Подготовьте в Yandex Cloud три хоста: для `clickhouse`, для `vector` и для `lighthouse`.
![img_1.png](img_1.png)
Ссылка на репозиторий LightHouse: https://github.com/VKCOM/lighthouse

## Основная часть

1. Допишите playbook: нужно сделать ещё один play, который устанавливает и настраивает lighthouse.
2. При создании tasks рекомендую использовать модули: `get_url`, `template`, `yum`, `apt`.
3. Tasks должны: скачать статику lighthouse, установить nginx или любой другой webserver, настроить его конфиг для открытия lighthouse, запустить webserver.
4. Приготовьте свой собственный inventory файл `prod.yml`.
![img_2.png](img_2.png)
5. Запустите `ansible-lint site.yml` и исправьте ошибки, если они есть.
![img_3.png](img_3.png)
6. Попробуйте запустить playbook на этом окружении с флагом `--check`.
![img_5.png](img_5.png)
7. Запустите playbook на `prod.yml` окружении с флагом `--diff`. Убедитесь, что изменения на системе произведены.
![img_7.png](img_7.png)
8. Повторно запустите playbook с флагом `--diff` и убедитесь, что playbook идемпотентен.
![img_8.png](img_8.png)
9. Подготовьте README.md файл по своему playbook. В нём должно быть описано: что делает playbook, какие у него есть параметры и теги.
```html
Подготовленные ВМ:    

| Hostname          | Public IP     | Software           |
|-------------------|---------------|--------------------|
| clickhouse-01     | 51.250.78.123 | Clickhouse         |
| vector-01         | 51.250.70.13  | Vector             |
| lighthouse-01     | 51.250.88.196 | Lighthouse & Nginx | 

Каталог playbook/inventory/prod содержит описание среды prod.

В каталоге playbook/inventory/prod расположен каталог group_vars, в котором содержится описание переменных для среды prod.

В каталоге playbook/inventory/prod расположен файл hosts.yml, в котором описаны хосты, к которым будет применен playbook.

В каталоге playbook/template распложены jinja-файлы шаблонов для настройки разворачиваемых сервисов в процессе выполнения playbook.

Теги:
- clickhouse (установка clickhouse)
- vector (установка vector)
- nginx (установка nginx)
- lighthouse (установка lighthouse) 
```
10. Готовый playbook выложите в свой репозиторий, поставьте тег `08-ansible-03-yandex` на фиксирующий коммит, в ответ предоставьте ссылку на него.
https://github.com/apriemysheva/mnt-homeworks2/tree/main/08-ansible-03-yandex/playbook
---

### Как оформить ДЗ?

Выполненное домашнее задание пришлите ссылкой на .md-файл в вашем репозитории.

---
