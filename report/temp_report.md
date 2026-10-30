---
## Front matter
title: "Отчёт по лабораторной работе 9"
subtitle: "Настройка POP3/IMAP сервера"
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

Приобретение практических навыков по установке и простейшему конфигурированию POP3/IMAP-сервера.

# Выполнение лабораторной работы

Установка пакетов telnet и dovecot на виртуальной машине server с помощью пакетного менеджера dnf. Процесс загрузки и установки завершен успешно.

![1](image/1.jpg){ #fig:001 width=70% height=70% }

Редактирование конфигурационных файлов Dovecot. В dovecot.conf включены протоколы imap и pop3. В 10-auth.conf задан метод аутентификации plain. В auth-system.conf.ext проверено использование драйверов pam и passwd. В 10-mail.conf настроено расположение почтовых ящиков maildir:~/Maildir. Postfix также настроен на использование каталога Maildir/.

![2](image/2.jpg){ #fig:002 width=70% height=70% }

Настройка межсетевого экрана (firewalld). Добавлены разрешающие правила для протоколов pop3, pop3s, imap и imaps на постоянной основе (--permanent). После этого контекст безопасности SELinux восстановлен командой restorecon, и служба Dovecot успешно запущена.

![3](image/3.jpg){ #fig:002 width=70% height=70% }

Мониторинг логов почтовой службы (tail -n 20 /var/log/maillog) и просмотр тестового письма локально с помощью утилиты mail. Также показан успешный вывод команды doveadm mailbox list, отображающий папку INBOX после перезапуска службы Dovecot.

![4](image/4.jpg){ #fig:003 width=70% height=70% }

Проверка работы POP3 сервера через утилиту telnet. Выполнено подключение к порту 110 сервера mail.rsvishnyakov.net, успешная авторизация пользователя rsvishnyakov и просмотр содержимого первого письма командой retr 1.
 
![5](image/5.jpg){ #fig:001 width=70% height=70% }

Окно настройки "Account Summary" в графическом почтовом клиенте Evolution на клиентской машине. Заданы параметры для приема (IMAP, сервер mail.rsvishnyakov.net, STARTTLS) и отправки (SMTP) почты для пользователя rsvishnyakov.

![6](image/6.jpg){ #fig:002 width=70% height=70% }

Интерфейс почтового клиента Evolution на клиентской машине. В папке "Входящие" (Inbox) отображается успешно полученное тестовое письмо с темой "lab9", что подтверждает корректную работу связки Postfix и Dovecot.

![7](image/7.jpg){ #fig:003 width=70% height=70% }

 Внесение изменений в скрипт mail.sh на сервере для автоматизации развертывания. Копируются конфигурационные файлы Dovecot, добавляются команды для установки пакетов, настройки брандмауэра для POP3/IMAP, настройки Postfix для использования Maildir, а также перезапуска служб.
 
![8](image/8.jpg){ #fig:001 width=70% height=70% }

Редактирование скрипта инициализации mail.sh на клиентской машине. Добавлены команды для автоматической установки репозитория epel-release и почтового клиента evolution при развертывании виртуальной машины client.

![9](image/9.jpg){ #fig:001 width=70% height=70% }

# Вывод

Мы приобрели практические навыки по установке и простейшему конфигурированию POP3/IMAP-сервера.


