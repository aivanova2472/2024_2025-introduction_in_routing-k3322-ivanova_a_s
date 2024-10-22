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
#### Создадим топологию в ContainerLab:

```

name: lab2

mgmt: 
  network: statics
  ipv4-subnet: 172.20.20.0/24


topology:

  nodes:
    R01.MSK:
      kind: vr-mikrotik_ros
      image: vrnetlab/mikrotik_routeros:6.47.9
      mgmt-ipv4: 172.20.20.2
      startup-config: /home/anna/Desktop/lab2/MSK.rsc

    R01.FRT:
      kind: vr-mikrotik_ros
      image: vrnetlab/mikrotik_routeros:6.47.9
      mgmt-ipv4: 172.20.20.3
      startup-config: /home/anna/Desktop/lab2/FRT.rsc

    R01.BRL:
      kind: vr-mikrotik_ros
      image: vrnetlab/mikrotik_routeros:6.47.9
      mgmt-ipv4: 172.20.20.4
      startup-config: /home/anna/Desktop/lab2/BRL.rsc

    PC1:
      kind: vr-mikrotik_ros
      image: vrnetlab/mikrotik_routeros:6.47.9
      mgmt-ipv4: 172.20.20.5
      startup-config: /home/anna/Desktop/lab2/PC1.rsc

    PC2:
      kind: vr-mikrotik_ros
      image: vrnetlab/mikrotik_routeros:6.47.9
      mgmt-ipv4: 172.20.20.6
      startup-config: /home/anna/Desktop/lab2/PC2.rsc

    PC3:
      kind: vr-mikrotik_ros
      image: vrnetlab/mikrotik_routeros:6.47.9
      mgmt-ipv4: 172.20.20.7
      startup-config: /home/anna/Desktop/lab2/PC3.rsc


  links:
    - endpoints: ["R01.BRL:eth3", "PC3:eth1"]
    - endpoints: ["R01.FRT:eth3", "PC2:eth1"]
    - endpoints: ["R01.MSK:eth3", "PC1:eth1"]
    - endpoints: ["R01.BRL:eth2", "R01.FRT:eth1"]
    - endpoints: ["R01.FRT:eth2", "R01.MSK:eth2"]
    - endpoints: ["R01.MSK:eth1", "R01.BRL:eth1"]
    
```

#### Создадим конфигурации для каждого устройства, проверим правильность их настроек:

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



