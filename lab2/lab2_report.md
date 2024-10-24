University: ITMO University

Faculty: FICT

Course: Introduction in routing

Year: 2024/2025

Group: K3322

Author: Ivanova Anna Sergeevna

Lab: Lab2

Date of create: 22.10.2024

Date of finished:

# Лабораторная работ №2 "Эмуляция распределенной корпоративной сети связи, настройка статической маршрутизации между филиалами"

### Цель работы
Ознакомиться с принципами планирования IP адресов, настройке статической маршрутизации и сетевыми функциями устройств.
### Ход работы
#### Создадим топологию в ContainerLab, конфигурации для каждого устройства и проверим правильность их настроек:

Роутер MSK:

![](https://github.com/aivanova2472/2024_2025-introduction_in_routing-k3322-ivanova_a_s/blob/main/lab2/screenshots/R01_MSK.jpg "R01_MSK")

Роутер FRT:

![](https://github.com/aivanova2472/2024_2025-introduction_in_routing-k3322-ivanova_a_s/blob/main/lab2/screenshots/R01_FRT.jpg "R01_FRT")


Роутер BRL:

![](https://github.com/aivanova2472/2024_2025-introduction_in_routing-k3322-ivanova_a_s/blob/main/lab2/screenshots/R01_BRL.jpg "R01_BRL")

PC1

![](https://github.com/aivanova2472/2024_2025-introduction_in_routing-k3322-ivanova_a_s/blob/main/lab2/screenshots/pc1.jpg "pc1")

PC2

![](https://github.com/aivanova2472/2024_2025-introduction_in_routing-k3322-ivanova_a_s/blob/main/lab2/screenshots/pc2.jpg "pc2")

PC3

![](https://github.com/aivanova2472/2024_2025-introduction_in_routing-k3322-ivanova_a_s/blob/main/lab2/screenshots/pc3.jpg "pc3")

Узнаем ip каждого из компьютеров:

![](https://github.com/aivanova2472/2024_2025-introduction_in_routing-k3322-ivanova_a_s/blob/main/lab2/screenshots/ip_pc1.jpg "ip1")
![](https://github.com/aivanova2472/2024_2025-introduction_in_routing-k3322-ivanova_a_s/blob/main/lab2/screenshots/ip_pc2.jpg "ip2")
![](https://github.com/aivanova2472/2024_2025-introduction_in_routing-k3322-ivanova_a_s/blob/main/lab2/screenshots/ip_pc3.jpg "ip3")

#### Пропингуем компьютеры
![](https://github.com/aivanova2472/2024_2025-introduction_in_routing-k3322-ivanova_a_s/blob/main/lab2/screenshots/ping1.jpg "ping1")
![](https://github.com/aivanova2472/2024_2025-introduction_in_routing-k3322-ivanova_a_s/blob/main/lab2/screenshots/ping2.jpg "ping2")
![](https://github.com/aivanova2472/2024_2025-introduction_in_routing-k3322-ivanova_a_s/blob/main/lab2/screenshots/ping3.jpg "ping3")


Поменяем логин и пароль у одного из компьютеров:
![](https://github.com/aivanova2472/2024_2025-introduction_in_routing-k3322-ivanova_a_s/blob/main/lab2/screenshots/log.jpg "log")

#### Диаграмма топологии:
![](https://github.com/aivanova2472/2024_2025-introduction_in_routing-k3322-ivanova_a_s/blob/main/lab2/screenshots/graph.jpg "graph")


## Вывод ##
В ходе выполнения лабораторной работы была создана связь трёх геораспределенных офисов, настроены IP адреса на интерфейсах, созданы DHCP сервера на роутерах, настроена статическая маршрутизация.



