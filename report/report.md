---
## Front matter
title: "Отчёт по лабораторной работе 4"
subtitle: "Работа с программными пакетами"
author: "Вишняков Родион Сергеевич"

## Generic otions
lang: ru-RU
toc-title: "Содержание"

## Bibliography
bibliography: bib/cite.bib
csl: pandoc/csl/gost-r-7-0-5-2008-numeric.csl

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
biblatex: true
biblio-style: "gost-numeric"
biblatexoptions:
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

Получить навыки работы с репозиториями и менеджерами пакетов.

# Выполнение лабораторной работы

Открываем консоль и переходим в режим суперпользователя

![Режим суперпользователя](image/1.png){ #fig:001 width=70% height=70% }

Изучаем содержание каталогов и файлов репозиториев

![Изучение файлов и каталогов](image/2.png){ #fig:002 width=70% height=70% }

Выводим на экран список репозиториев

![Список репозиториев](image/3.png){ #fig:003 width=70% height=70% }

Выводим на экран список пакетов('user')

![Список пакетов 'user'](image/4.png){ #fig:004 width=70% height=70% }

Устанавливаем nmap и изучаем информацию по имеющимся пакетам

![Установка nmap](image/5.png){ #fig:005 width=70% height=70% }

Устанавливаем nmap и изучаем информацию по имеющимся пакетам

![Установка nmap](image/6.png){ #fig:005 width=70% height=70% }

Устанавливаем nmap и изучаем информацию по имеющимся пакетам

![Установка nmap](image/7.png){ #fig:005 width=70% height=70% }

Удаляем nmap

![Удаление nmap](image/8.jpg){ #fig:006 width=70% height=70% }

Удаляем nmap

![Удаление nmap](image/9.jpg){ #fig:006 width=70% height=70% }

Получаем список имеющихся групп пакетов, затем устанавливаем группу пакетов
RPM Development Tools:

![Установка пакетов](image/10.png){ #fig:007 width=70% height=70% }

Получаем список имеющихся групп пакетов, затем устанавливаем группу пакетов
RPM Development Tools:

![Установка пакетов](image/11.png){ #fig:007 width=70% height=70% }

Получаем список имеющихся групп пакетов, затем устанавливаем группу пакетов
RPM Development Tools:

![Установка пакетов](image/12.png){ #fig:007 width=70% height=70% }

Удаляем группу пакетов

![Удаление пакетов](image/13.png){ #fig:008 width=70% height=70% }

Просматриваем историю использования команды dnf

![История команды dnf](image/14.png){ #fig:009 width=70% height=70% }
 
Отменяем последнее действие

![Отмена последнего действия](image/14.png){ #fig:010 width=70% height=70% }
 
Скачиваем rmp-пакет lynx

![Установка пакета](image/15.png){ #fig:011 width=70% height=70% }

Ищем каталог

![Каталог](image/16.png){ #fig:012 width=70% height=70% }

Переходим в каталог и устанавливаем пакет

![Установка пакета](image/17.png){ #fig:013 width=70% height=70% }
 
Определяем расположение исполняемого файла

![Исполняемый файл](image/18.png){ #fig:014 width=70% height=70% }

Определяем к какому пакету принадлежит новый файл и получаем дополнительную информацию

![Расположение файла и дополнительная информация](image/19.png){ #fig:015 width=70% height=70% }

Получаем список всех файлов в пакете

![Получение списка файлов](image/20.png){ #fig:015 width=70% height=70% }

Получаем список всех файлов в пакете

![Получение списка файлов](image/21.png){ #fig:015 width=70% height=70% }

Смотрим файлы документации

![Просмотр файлов документации](image/22.png){ #fig:015 width=70% height=70% }

Выводим на экран перечень и месторасположение конфигурационных файлов пакета

![Перечень и месторасположение файлов](image/23.png){ #fig:016 width=70% height=70% }

Выводим на экран расположение и содержание скриптов

![Расположение и содержание скриптов](image/24.png){ #fig:015 width=70% height=70% }

Запускаем текстовый браузер lynx в отдельном терминале

![Тектовый браузер lynx](image/25.png){ #fig:015 width=70% height=70% }

Удаляем пакет

![Удаление пакета](image/26.png){ #fig:015 width=70% height=70% }

Скачиваем пакет dnsmasq и определяеи расположение исполняемого файла

![Установка пакета](image/27.png){ #fig:011 width=70% height=70% }

Определяем к какому пакету принадлежит новый файл и получаем дополнительную информацию

![Расположение файла и дополнительная информация](image/28.png){ #fig:015 width=70% height=70% }

Получаем список всех файлов в пакете

![Получение списка файлов](image/29.png){ #fig:015 width=70% height=70% }

Выводим на экран перечень и месторасположение конфигурационных файлов пакета

![Перечень и месторасположение файлов](image/30.png){ #fig:016 width=70% height=70% }

Выводим на экран расположение и содержание скриптов

![Расположение и содержание скриптов](image/31.png){ #fig:015 width=70% height=70% }

Удаляем пакет

![Удаление пакета](image/32.png){ #fig:015 width=70% height=70% }


# Вывод

Мы получили навыки работы с репозиториями и менеджерами пакетов

# Контрольные вопросы

1. Команда dnf provides ищет пакет по файлу.

2. Команды dnf group list и dnf group info показывают группы пакетов и их состав.

3. Команда dnf install устанавливает локальный rpm-файл.

4. Команда rpm -qp --scripts показывает скрипты в пакете.

5. Команда rpm -qd показывает документацию пакета.

6. Команда rpm -qf определяет пакет-владелец файла.
