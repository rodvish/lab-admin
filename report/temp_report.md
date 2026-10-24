---
## Front matter
title: "Отчёт по лабораторной работе 4"
subtitle: "Адресация IPv4 и IPv6. Двойной стека"
author: "Вишняков Родион Сергеевич"

## Generic otions
lang: ru-RU
toc-title: "Содержание"

## Bibliography

## Pdf output format
toc: true # Table of contents
toc-depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4
documentclass: scrreprt
## I18n polyglossia
polyglossia-lang:
  name: russian
  options:
	- spelling=modern
	- babelshorthands=true
polyglossia-otherlangs:
  name: english
## I18n babel
babel-lang: russian
babel-otherlangs: english
## Fonts
mainfont: IBM Plex Serif
romanfont: IBM Plex Serif
sansfont: IBM Plex Sans
monofont: IBM Plex Mono
mathfont: STIX Two Math
mainfontoptions: Ligatures=Common,Ligatures=TeX,Scale=0.94
romanfontoptions: Ligatures=Common,Ligatures=TeX,Scale=0.94
sansfontoptions: Ligatures=Common,Ligatures=TeX,Scale=MatchLowercase,Scale=0.94
monofontoptions: Scale=MatchLowercase,Scale=0.94,FakeStretch=0.9
mathfontoptions:
## Biblatex
  - parentracker=true
  - backend=biber
  - hyperref=auto
  - language=auto
  - autolang=other*
  - citestyle=gost-numeric
## Pandoc-crossref LaTeX customization
figureTitle: "Рис."
tableTitle: "Таблица"
listingTitle: "Листинг"
lofTitle: "Список иллюстраций"
lotTitle: "Список таблиц"
lolTitle: "Листинги"
## Misc options
indent: true
header-includes:
  - \usepackage{indentfirst}
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

Изучение принципов распределения и настройки адресного пространства на устройствах сети.

# Выполнение лабораторной работы

Рабочая область эмулятора GNS3 с собранной топологией сети с двойным стеком протоколов. В левой части реализована подсеть IPv4 с маршрутизатором FRR, в правой — подсеть IPv6 с маршрутизатором VyOS, а в центре находится сервер с двойным стеком. В нижней части окна запущен процесс захвата трафика Wireshark.

![1](image/1.jpg){ #fig:001 width=70% height=70% }

Консоли терминалов виртуальных компьютеров PC1 и PC2. Продемонстрирован процесс назначения IPv4-адресов и шлюзов по умолчанию с помощью команды `ip`, а также проверка примененных сетевых настроек командами `show ip` и `show ipv6`.

![2](image/2.jpg){ #fig:002 width=70% height=70% }

Консоль центрального сервера (VPCS). Выполнена настройка IPv4-адреса и шлюза по умолчанию для подсети 64.100.1.0/24. Успешность настройки подтверждена выводом команды `show ip`.

![3](image/3.jpg){ #fig:002 width=70% height=70% }

Консоль маршрутизатора FRR (`msk-rodvish-gw-01`). Показан процесс конфигурации интерфейсов `eth0`, `eth1` и `eth2`: назначение им соответствующих IPv4-адресов, включение портов командой `no shutdown` и сохранение конфигурации в память.

![4](image/4.jpg){ #fig:003 width=70% height=70% }

Проверка текущей конфигурации маршрутизатора FRR (`msk-rodvish-gw-01`). С помощью команды `show interface brief` подтверждается, что настроенные интерфейсы `eth0`, `eth1` и `eth2` находятся в активном состоянии (up) и имеют верные IPv4-адреса.
 
![5](image/5.jpg){ #fig:001 width=70% height=70% }

Проверка связности узлов в подсети IPv4. В консолях PC1 и PC2 успешно выполняются команды `ping` и `trace` до соседних компьютеров и сервера. Также на фоне виден перехваченный ICMP-трафик в Wireshark.

![6](image/6.jpg){ #fig:002 width=70% height=70% }

Консоли виртуальных компьютеров PC3, PC4 и сервера. На данных узлах выполнена настройка глобальных IPv6-адресов (2001:db8:c0de...). Корректность применения адресов проверена командой `show ipv6`.

![7](image/7.jpg){ #fig:003 width=70% height=70% }

Консоль маршрутизатора VyOS. Выполнена конфигурация интерфейсов `eth0`, `eth1` и `eth2`: назначены IPv6-адреса и настроена служба Router Advert (рассылка префиксов) для каждой подсети. Настройки успешно применены командой `commit`, сохранены и проверены через `show interfaces`.

![8](image/8.jpg){ #fig:001 width=70% height=70% }

# Вывод

Мы изучили принципы распределения и настройки адресного пространства на устройствах сети.


