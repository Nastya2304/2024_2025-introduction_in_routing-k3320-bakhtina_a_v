University: [ITMO University](https://itmo.ru/ru/)

Faculty: [FICT](https://fict.itmo.ru)

Course: [Introduction in routing](https://github.com/itmo-ict-faculty/introduction-in-routing)

Year: 2024/2025

Group: K3320

Author: Bakhtina Anastasia Viacheslavovna

Lab: Lab3

Date of create: 05.11.2024

Date of finished: 05.11.2024

# Отчёт по лабораторной работе №3 "Эмуляция распределенной корпоративной сети связи, настройка OSPF и MPLS, организация первого EoMPLS"

 ***Цель:*** Изучить протоколы OSPF и MPLS, механизмы организации EoMPLS.


## Ход работы

### Схема работы: 

В начале лабораторной работы №3 была построена следующая схема IP/MPLS сети связи для "RogaIKopita Games". Были созданы все устройства указанные на схеме и соединения между ними.

<img src="./images/diagram.png" style="width:500px; height: auto; background: white">

В yaml-файле была задана топология сети, указанная на схеме:

<img src="./images/net.png" style="width:500px; height: auto; background: white">

## Конфигурация
#### R01.NY
<img src="./images/R01.NY_export.png" style="display: block;width:500px; height: auto; background: white; margin-bottom: 10px">

#### R01.LND
<img src="./images/R01.LND_export.png" style="display: block;width:500px; height: auto; background: white; margin-bottom: 10px">

#### R01.HKI
<img src="./images/R01.HKI_export.png" style="display: block;width:500px; height: auto; background: white; margin-bottom: 10px">

#### R01.SPB
<img src="./images/R01.SPB_export.png" style="display: block;width:500px; height: auto; background: white; margin-bottom: 10px">

#### R01.MSK
<img src="./images/R01.MSK_export.png" style="display: block;width:500px; height: auto; background: white; margin-bottom: 10px">

#### R01.LBN
<img src="./images/R01.LBN_export.png" style="display: block;width:500px; height: auto; background: white; margin-bottom: 10px">

### RO1.NY:
<img src="./images/R01.NY.png" style="display: block;width:500px; height: auto; background: white; margin-bottom: 10px">

### RO1.LND:
<img src="./images/R01.LND.png" style="display: block;width:500px; height: auto; background: white; margin-bottom: 10px">

### RO1.HKI:
<img src="./images/R01.HKI.png" style="display: block;width:500px; height: auto; background: white; margin-bottom: 10px">

### RO1.SPB:
<img src="./images/R01.SPB.png" style="display: block;width:500px; height: auto; background: white; margin-bottom: 10px">

### RO1.MSK:
<img src="./images/R01.MSK.png" style="display: block;width:500px; height: auto; background: white; margin-bottom: 10px">

### RO1.LBN:
<img src="./images/R01.LBN.png" style="display: block;width:500px; height: auto; background: white; margin-bottom: 10px">

## Проверка работоспособности (PC1 -> SGI_PRISM, SGI_PRISM -> PC1):

<img src="./images/ping_1.png" style="display: block;width:500px; height: auto; background: white; margin-bottom: 10px">
<img src="./images/ping_2.png" style="display: block;width:500px; height: auto; background: white; margin-bottom: 10px">

##  Трассировка между роутерами

#### R01.SPB -> R01.NY

<img src="./images/2.png" style="display: block;width:500px; height: auto; background: white; margin-bottom: 10px">

#### R01.NY -> R01.SPB

<img src="./images/1.png" style="display: block;width:500px; height: auto; background: white; margin-bottom: 10px">

###  Вывод

В данной лабораторной работе №3 была построена схема сети связи для "RogaIKopita Games". А также были изучены протоколы OSPF и MPLS, механизмы организации EoMPLS.
