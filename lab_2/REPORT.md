University: [ITMO University](https://itmo.ru/ru/)

Faculty: [FICT](https://fict.itmo.ru)

Course: [Introduction in routing](https://github.com/itmo-ict-faculty/introduction-in-routing)

Year: 2024/2025

Group: K3320

Author: Bakhtina Anastasia Viacheslavovna

Lab: Lab2

Date of create: 11.10.2024

Date of finished: 16.10.2024

# Отчёт по лабораторной работе №2 "Эмуляция распределенной корпоративной сети связи, настройка статической маршрутизации между филиалами"

***Цель:*** Ознакомиться с принципами планирования IP адресов, настройке статической маршрутизации и сетевыми функциями устройств.


## Ход работы

### Схема работы: 

В начале лабораторной работы №2 была построена следующая схема сети связи в трех геораспределенных офисах "RogaIKopita Games". Были созданы все устройства указанные на схеме и соединения между ними.

<img src="./images/diagram.png" style="width:500px; height: auto; background: white">

В yaml-файле была задана топология сети, указанная на схеме:

<img src="./images/net.png" style="width:500px; height: auto; background: white">

## Конфигурация
#### R01.MSK
<img src="./images/R01.MSK.png" style="display: block;width:500px; height: auto; background: white; margin-bottom: 10px">

#### R02.BRL
<img src="./images/R02.BRL.png" style="display: block;width:500px; height: auto; background: white; margin-bottom: 10px">

#### R03.FRT
<img src="./images/R03.FRT.png" style="display: block;width:500px; height: auto; background: white; margin-bottom: 10px">

## Таблицы маршрутизации:
#### R01.MSK
<img src="./images/6.png" style="display: block;width:500px; height: auto; background: white; margin-bottom: 10px">

#### R02.BRL
<img src="./images/5.png" style="display: block;width:500px; height: auto; background: white; margin-bottom: 10px">

#### R03.FRT
<img src="./images/1.png" style="display: block;width:500px; height: auto; background: white; margin-bottom: 10px">

## Проверка работоспособности:

<img src="./images/2.png" style="display: block;width:500px; height: auto; background: white; margin-bottom: 10px">
<img src="./images/3.png" style="display: block;width:500px; height: auto; background: white; margin-bottom: 10px">
<img src="./images/4.png" style="display: block;width:500px; height: auto; background: white; margin-bottom: 10px">

###  Вывод

В данной лабораторной работе №2 была построена схема сети связи в трех геораспределенных офисах "RogaIKopita Games". Я ознакомилась с принципами планирования IP адресов, научилась настройке статической маршрутизации и сетевыми функциями устройств.
