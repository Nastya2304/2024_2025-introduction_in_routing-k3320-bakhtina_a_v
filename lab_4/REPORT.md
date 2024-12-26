University: [ITMO University](https://itmo.ru/ru/)

Faculty: [FICT](https://fict.itmo.ru)

Course: [Introduction in routing](https://github.com/itmo-ict-faculty/introduction-in-routing)

Year: 2024/2025

Group: K3320

Author: Bakhtina Anastasia Viacheslavovna

Lab: Lab4

Date of create: 23.12.2024

Date of finished: 26.12.2024

# Отчёт по лабораторной работе №4 "Эмуляция распределенной корпоративной сети связи, настройка iBGP, организация L3VPN, VPLS"

 ***Цель:*** Изучить протоколы BGP, MPLS и правила организации L3VPN и VPLS.
 

 ## Ход работы

### Схема работы: 
В начале лабораторной работы №4 была построена следующая схема IP/MPLS сети связи для "RogaIKopita Games". Были созданы все устройства указанные на схеме и соединения между ними.

<img src="./images/diagram.png" style="width:500px; height: auto; background: white">

В yaml-файле была задана топология сети, указанная на схеме:

<img src="./images/net.png" style="width:500px; height: auto; background: white">

## Конфигурация
#### R01.NY
<img src="./images/R01.NY.png" style="display: block;width:500px; height: auto; background: white; margin-bottom: 10px">

#### R01.LND
<img src="./images/R01.LND.png" style="display: block;width:500px; height: auto; background: white; margin-bottom: 10px">

#### R01.HKI
<img src="./images/R01_HKI.png" style="display: block;width:500px; height: auto; background: white; margin-bottom: 10px">

#### R01.SVL
<img src="./images/R01.SVL.png" style="display: block;width:500px; height: auto; background: white; margin-bottom: 10px">

#### R01.LBN
<img src="./images/R01.LBN.png" style="display: block;width:500px; height: auto; background: white; margin-bottom: 10px">

## Часть 1
### PING: R01.NY -> R01.SPB, R01.SVL:
<img src="./images/R01.NY_ping.png" style="display: block;width:auto; height: auto; background: white; margin-bottom: 10px">

### PING: R01.SPB -> R01.NY, R01.SVL:
<img src="./images/R01.SPB_ping.png" style="display: block;width:auto; height: auto; background: white; margin-bottom: 10px">

### PING: R01.SVL -> R01.SPB, R01.NY:
<img src="./images/R01.SVL_ping.png" style="display: block;width:auto; height: auto; background: white; margin-bottom: 10px">

## Часть 2
### PING: PC1 -> PC2, PC3:
<img src="./images/PC1.png" style="display: block;width:auto; height: auto; background: white; margin-bottom: 10px">

### PING: PC2 -> PC1, PC3:
<img src="./images/PC2.png" style="display: block;width:auto; height: auto; background: white; margin-bottom: 10px">

### PING: PC3 -> PC1, PC2:
<img src="./images/PC3.png" style="display: block;width:auto; height: auto; background: white; margin-bottom: 10px">


###  Вывод

В данной лабораторной работе №4 была построена схема сети связи для "RogaIKopita Games". А также были изучены протоколы BGP, MPLS и правила организации L3VPN и VPLS.
