University: [ITMO University](https://itmo.ru/ru/)

Faculty: [FICT](https://fict.itmo.ru)

Course: [Introduction in routing](https://github.com/itmo-ict-faculty/introduction-in-routing)

Year: 2024/2025

Group: K3320

Author: Bakhtina Anastasia Viacheslavovna

Lab: Lab1

Date of create: 04.10.2024

Date of finished: 09.10.2024

# Отчёт по лабораторной работе №1 "Установка ContainerLab и развертывание тестовой сети связи"

***Цель:***  Ознакомиться с инструментом ContainerLab и методами работы с ним, изучить работу VLAN, IP адресации и т.д.


## Ход работы

В начале лабораторной работы №1 была построена следующая трехуровневая сеть связи классического предприятия:

<img src="./images/diagram.png" style="width:500px; height: auto; background: white">

Затем при попытке сделать данную лабораторную работу в виртуальной машине (Ubuntu) были замечены сложности с развертыванием контейнера и подключением к устройствам. На ноутбук был установлен Linux второй ОС. После таких манипуляций все было реализовано успешно.

В yaml-файле была задана топология сети, указанная на схеме:

<img src="./images/net.png" style="width:500px; height: auto; background: white">

## Конфигурация

<img src="./images/R01.png" style="display: block;width:720px; height: auto; background: white; margin-bottom: 10px">
<img src="./images/SWO1.01.png" style="display: block;width:690px; height: auto; background: white; margin-bottom: 10px">
<img src="./images/SWO2.01.png" style="display: block;width:689px; height: auto; background: white; margin-bottom: 10px">
<img src="./images/SWO2.02.png" style="display: block;width:688px; height: auto; background: white; margin-bottom: 10px">

### После задания конфигураций нод, проверим работоспособность:

<img src="./images/SWO1.01-ping.png" style="display: block;width:731px; height: auto; background: white; margin-bottom: 10px">
<img src="./images/SWO2.01-ping.png" style="display: block;width:735px; height: auto; background: white; margin-bottom: 10px">
<img src="./images/SWO2.02-ping.png" style="display: block;width:757px; height: auto; background: white; margin-bottom: 10px">

###  Вывод

В данной лабораторной работе №1 была построена трехуровневая сеть классического предприятия. А также в ходе работы была ознакомлена с инструментом ContainerLab и методами работы с ним, была изучена работа VLAN, IP адресации.
