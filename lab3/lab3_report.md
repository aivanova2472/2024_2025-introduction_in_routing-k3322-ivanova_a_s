University: ITMO University

Faculty: FICT

Course: Introduction in routing

Year: 2024/2025

Group: K3322

Author: Ivanova Anna Sergeevna

Lab: Lab3

Date of create: 18.12.2024

Date of finished: 

# Лабораторная работa №3 "Эмуляция распределенной корпоративной сети связи, настройка OSPF и MPLS, организация первого EoMPLS"

## Цель работы

Изучить протоколы OSPF и MPLS, механизмы организации EoMPLS.

## Ход работы ##

Развернем нашу сеть, используя файл lab3.clab.yaml:

```
name: lab3

mgmt:
    network: Net3
    ipv4_subnet: 192.30.31.0/24

topology:
    nodes:
        R01.NY:
            kind: vr-ros
            image: vrnetlab/vr-routeros:6.47.9
            mgmt_ipv4: 192.30.31.11
        R01.LND:
            kind: vr-ros
            image: vrnetlab/vr-routeros:6.47.9
            mgmt_ipv4: 192.30.31.12
        R01.LBN:
            kind: vr-ros
            image: vrnetlab/vr-routeros:6.47.9
            mgmt_ipv4: 192.30.31.13
        R01.HKI:
            kind: vr-ros
            image: vrnetlab/vr-routeros:6.47.9
            mgmt_ipv4: 192.30.31.14
        R01.MSK:
            kind: vr-ros
            image: vrnetlab/vr-routeros:6.47.9
            mgmt_ipv4: 192.30.31.15
        R01.SPB:
            kind: vr-ros
            image: vrnetlab/vr-routeros:6.47.9
            mgmt_ipv4: 192.30.31.16
        SGI_Prism:
            kind: vr-ros
            image: vrnetlab/vr-routeros:6.47.9
            mgmt_ipv4: 192.30.31.17
        PC1:
            kind: vr-ros
            image: vrnetlab/vr-routeros:6.47.9
            mgmt_ipv4: 192.30.31.18
    links:
        - endpoints: ["R01.NY:eth2", "SGI_Prism:eth2"]
        - endpoints: ["R01.NY:eth3", "R01.LND:eth2"]
        - endpoints: ["R01.NY:eth4", "R01.LBN:eth2"]
        - endpoints: ["R01.LND:eth3", "R01.HKI:eth2"]
        - endpoints: ["R01.LBN:eth3", "R01.MSK:eth2"]
        - endpoints: ["R01.LBN:eth4", "R01.HKI:eth4"]
        - endpoints: ["R01.HKI:eth3", "R01.SPB:eth3"]
        - endpoints: ["R01.MSK:eth3", "R01.SPB:eth2"]
        - endpoints: ["R01.SPB:eth4", "PC1:eth2"]
```

#### 2. Разворачиваем контейнер 

![image](https://github.com/user-attachments/assets/825ee380-9f78-4dba-9535-9f0a37d663e7)

#### 3. Прописываем параметры каждому устройству
Текст конфигураций сетевых устройств:
- Роутер R01.NY

![image](https://github.com/user-attachments/assets/597ba72a-125e-4968-94d0-047a913e0e1b)


- Роутер R01.LND

![image](https://github.com/user-attachments/assets/4f30faf1-c122-4cf0-b307-313a28308a79)


- Роутер R01.LBN

![image](https://github.com/user-attachments/assets/7174a5a3-83ab-420b-81c7-59fcf5433c56)


- Роутер R01.HKI

![image](https://github.com/user-attachments/assets/43ce805d-1917-432f-9428-b2f6c4a79e81)


- Роутер R01.MSK

![image](https://github.com/user-attachments/assets/214047c2-88c4-445c-a736-efdbdd0cdbf7)


- Роутер R01.SPB

![image](https://github.com/user-attachments/assets/ac9cf5da-25ad-48ae-b278-591e01856f46)


- SGI-Prism

![image](https://github.com/user-attachments/assets/9a85c694-b824-47e7-b347-d481ecad23ad)


- PC1

![image](https://github.com/user-attachments/assets/e866bbc9-2a12-465b-934a-c54cc26fb1d6)


#### 4. Таблицы маршрутизации для каждого роутера:
![image](https://github.com/user-attachments/assets/24836d69-8b82-4989-9bd6-4e44e8aa1ff9)

![image](https://github.com/user-attachments/assets/20ddcc00-2a86-49e1-85df-57f07325b826)

![image](https://github.com/user-attachments/assets/0e6ae57b-18d7-4834-8b17-ba1bb453b408)

![image](https://github.com/user-attachments/assets/5d995869-6d01-4305-88b8-b8c74b53c30f)

![image](https://github.com/user-attachments/assets/67744064-1d36-44d5-85ba-11fd309075d5)

![image](https://github.com/user-attachments/assets/fbd3bf14-c647-4da5-8f4d-5703cacf71e3)


#### 5. Информация об MPLS метках:
![image](https://github.com/user-attachments/assets/79a8af0b-4f43-4c7c-9077-59f53d76fa66)


#### 6. Схема сети
![image](https://github.com/user-attachments/assets/08ff8dad-a884-480c-9605-5eb8f68e8ad1)

#### 7. Проверка пинга ПК и сервера
![image](https://github.com/user-attachments/assets/2169b616-2cdf-4458-92cc-0f972ef30eca)

![image](https://github.com/user-attachments/assets/d8f07a2c-b095-4382-b119-72766f54fd91)


#### 8. Вывод
В результате выполения данной лабораторной работы были изучены протоколы OSPF и MPLS, а также механизмы организации EoMPLS.
