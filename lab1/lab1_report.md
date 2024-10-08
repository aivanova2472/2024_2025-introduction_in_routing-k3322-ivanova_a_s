University: ITMO University

Faculty: FICT

Course: Introduction in routing

Year: 2024/2025

Group: K3322

Author: Ivanova Anna Sergeevna

Lab: Lab1

Date of create: 08.10.2024

Date of finished: 

# Лабораторная работ №1 "Установка ContainerLab и развертывание тестовой сети связи"

### Описание
В данной лабораторной работе вы познакомитесь с инструментом ContainerLab, развернете тестовую сеть связи, настроите оборудование на базе Linux и RouterOS.
### Цель работы
Ознакомиться с инструментом ContainerLab и методами работы с ним, изучить работу VLAN, IP адресации и т.д.
### Ход работы
###### 1. Создание топологии в ContainerLab
#

![image](https://github.com/user-attachments/assets/7f542a9f-a1a8-4079-abca-6867d39add79)

```

Конфигурции устройств можно найти в папке configs.

Проверим настройку каждого устройства в сети:

1. Router1
![image](https://github.com/user-attachments/assets/43ddd972-ce82-4432-960e-b0db9f365bc8)

2. Switch1

![image](https://github.com/user-attachments/assets/2f0a1c77-bbda-4831-9d92-aeb930b2a54e)

3. Switch2_1

![image](https://github.com/user-attachments/assets/d680892c-603d-46b3-8314-3c4a79fb3687)


4. Switch2_2

![image](https://github.com/user-attachments/assets/9e6f81d7-a24e-4ac9-b272-fc144eed20c9)


Подключимся к PC1 и PC2 используя команды

```sh
    docker exec -it clab-enterprise-lab-PC1 sh
```

```sh
    docker exec -it clab-enterprise-lab-PC2 sh
```

После подключения получим IP адреса от нашего DHCP сервера с помощью следующих команд:

```sh
apt-get update
apt-get install -y iproute2 isc-dhcp-client
dhclient eth1
ip addr show eth1
```

![image](https://github.com/user-attachments/assets/a589b354-cadf-45ee-9728-07dca5f5be07)
![image](https://github.com/user-attachments/assets/f7e42ece-45e0-4c69-9637-629e4501576c)


С помощью команды "ip address print" получим IP устройств.

```
![image](https://github.com/user-attachments/assets/6c6e0dc9-66b7-42e0-a2b5-dd7802167755)
![image](https://github.com/user-attachments/assets/f96aaeac-2246-4649-90b3-02e1df73987d)
![image](https://github.com/user-attachments/assets/fd7405b7-d2db-4d74-8f0d-9eb8331a5d78)
![image](https://github.com/user-attachments/assets/28483ba2-f949-4bce-be89-4702e25e3d81)


```

Вывод команды пинг с PC2:

![image](https://github.com/user-attachments/assets/86bea36d-66b4-4304-b605-d102d57c2268)

Вывод команды пинг с Switch2_2:

![image](https://github.com/user-attachments/assets/721d3b58-e4ac-4875-8ebc-64235ea0b316)


Добавим пользователя для первого роутера и протестируем:

![image](https://github.com/user-attachments/assets/3a3b747c-94ba-4f81-bbd9-a5d2c1748b3c)
![image](https://github.com/user-attachments/assets/aba1f576-f24a-4c56-acb7-cfbd71201afb)


Диаграмма топологии
![photo_2024-10-08_15-43-22](https://github.com/user-attachments/assets/4fdbf7fa-f5f5-477c-8096-7d64c8a0438d)

## Вывод ##
В ходе лабораторной работы с использованием файла "Конфигурация сети" была создана сеть, состоящая из роутера, трех коммутаторов и двух компьютеров. Также были изменены логины и пароли на роутере и коммутаторах, настроены VLAN и DHCP-сервер для распределения IP-адресов. Успешные пинги подтвердили, что сеть работает корректно.
