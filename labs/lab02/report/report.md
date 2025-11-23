---
## Front matter
title: "Доклад на тему: Настройка сетевых сервисов на сетевом оборудовании. DNS"
subtitle: "НПИбд-02-22"
author: "Чесноков Артемий Павлович"

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

# Цель Доклада

Изучить принципы работы службы DNS и продемонстрировать процесс её настройки на сетевом оборудовании с использованием среды моделирования Cisco Packet Tracer.


# Определение и введение

DNS (Domain Name System) — система доменных имён, обеспечивающая преобразование доменных имён в IP-адреса.
DNS выполняет критически важную функцию — абстрагирование пользователя от необходимости оперировать числовыми идентификаторами (IP-адресами) сетевых ресурсов, что существенно повышает удобство и гибкость доступа к сервисам. 

# Подробно про теорию

Domain Name System (DNS) — это протокол прикладного уровня модели OSI (или уровня Application в модели TCP/IP), предназначенный для разрешения символьных доменных имён в соответствующие им IP-адреса (рис. [-@fig:101]). Система реализована в виде распределённой базы данных, поддерживаемой иерархически организованной структурой серверов: корневые серверы (Root Servers), серверы доменов верхнего уровня (TLD), авторитетные серверы доменов второго и последующих уровней.

![OSI](image/OSI.png){#fig:101 width=70%}

Ключевые функции DNS:

1. Forward Lookup — преобразование доменного имени в IP-адрес (наиболее распространённый случай);

2. Reverse Lookup — получение доменного имени по IP-адресу;

3. Роутинг и делегирование зон — обеспечение отказоустойчивости и масштабируемости;

4. Кэширование — снижение задержек и нагрузок за счёт хранения временных результатов запросов.

# Виды записей

| Тип записи | Назначение                                      |
| ---------- | ----------------------------------------------- |
| A          | IPv4-адрес хоста                                |
| AAAA       | IPv6-адрес хоста                                |
| CNAME      | Каноническое имя (псевдоним)                    |
| MX         | Почтовый сервер домена                          |
| PTR        | Обратная запись (используется для rDNS)         |
| NS         | Указание авторитетного DNS-сервера              |
| SOA        | Начало зоны, определяет основные параметры зоны |


# Пример для Cisco Packet Tracer

Разместим все необходимые устройства. Нам понадобятся Компьютер, Сервер, коммутатор. Второй компьютер использовался для тестов, в повторении эксперимента читатем он никакой роли не играет (можно игнорировать)  (рис. [-@fig:001]).

![Размещаемся в логическом view](image/1.png){#fig:001 width=70%}

Соединяем прямыми кабелями, т.к. мы соединяем устройства разного типа (рис. [-@fig:002]).

![В сетях Ethernet тип соединительного кабеля зависит от того, передают ли устройства сигнал на одни и те же контакты](image/2.png){#fig:002 width=70%}

На сервере открываем вкладку "IP configuration" (рис. [-@fig:003]).

![в этой вкладке мы настраиваем ](image/3.png){#fig:003 width=70%}

Указываем IP-адрес и адрем DNS сервера (рис. [-@fig:004]).

![Пример настройки для сервера](image/4.png){#fig:004 width=70%}

Теперь в разделе HTTP в html разметке запишем некоторые приветственные слова (рис. [-@fig:005]).

![Всё что написано - чистая правда](image/5.png){#fig:005 width=70%}

Настроим компьютер (рис. [-@fig:006]).

![Настройки для компьютера](image/6.png){#fig:006 width=70%}

Самое важное - запишем доменное в разделе SERVICES во вкладке DNS (рис. [-@fig:007]).

![Указал - chesnokovap](image/7.png){#fig:007 width=70%}

Открываем в браузере с нашего заранее настроенного компьютера  (рис. [-@fig:008]) (рис. [-@fig:009]).

![С использованием доменного имени](image/8.png){#fig:008 width=70%}

![С использованием IP-адреса](image/9.png){#fig:009 width=70%}

# Выводы

DNS является ключевым сетевым сервисом, обеспечивающим преобразование доменных имён в IP-адреса. 
Его корректная настройка критически важна для функционирования сетевой инфраструктуры. 
Использование Cisco Packet Tracer позволяет **наглядно** отработать конфигурацию DNS.


# Список литературы{.unnumbered}

::: {#refs}

:::
