---
## Front matter
title: "Отчёт по лабораторной работе №1"
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

# Цель работы

Установка инструмента моделирования конфигурации сети Cisco Packet
Tracer [3], знакомство с его интерфейсом.


# Выполнение лабораторной работы

Заходим на networkAcademy (рис. [-@fig:001]).

![регистрируемся и получаем продукт](image/1.png){#fig:001 width=70%}

Строим схему с концентратором (рис. [-@fig:002]).

![порядок соединения портов неважен](image/2.png){#fig:002 width=70%}

Указываем статические адреса на устройствах (рис. [-@fig:003]).

![делаем для каждого](image/3.png){#fig:003 width=70%}

Запускаем симуляцию и отправляем с PC0 на PC4 (рис. [-@fig:004]).

![ожидаемый результат](image/4.png){#fig:004 width=70%}

Информация о PDU: уровень OSI (рис. [-@fig:005]).

![OSI](image/5.png){#fig:005 width=70%}

Информация о PDU: форматы пакетов (рис. [-@fig:006]).

![форматы](image/6.png){#fig:006 width=70%}

Как нас и попросили проверяем себя в тесте (рис. [-@fig:007]).

![ответил неправильно](image/7.png){#fig:007 width=70%}

Отправляем с двух сторон пакеты (рис. [-@fig:008]).

![призываем коллизию](image/8.png){#fig:008 width=70%}

Отслеживаем пакеты (рис. [-@fig:009]).

![отследили](image/9.png){#fig:009 width=70%}

Размещаем коммутатор  (рис. [-@fig:010]).

![разместили](image/10.png){#fig:010 width=70%}

Запустив пакеты замечаем разницу в передаче  (рис. [-@fig:011]).

![разница в передаче](image/11.png){#fig:011 width=70%}

Рассматриваем пакеты  (рис. [-@fig:012]).

![ура](image/12.png){#fig:012 width=70%}

Соединяем наши схемы   (рис. [-@fig:013]).

![витым кабелем](image/13.png){#fig:013 width=70%}

Отправляем пакет от устройства левой схемы на устройство правой   (рис. [-@fig:014]).

![успешно](image/14.png){#fig:014 width=70%}

Добавляем маршрутизатор (рис. [-@fig:015]).

![прямым кабелем тк устройства одного типа](image/15.png){#fig:015 width=70%}

Прописываем статический адрес  (рис. [-@fig:016]).

![config](image/16.png){#fig:016 width=70%}

Устанавливаем тоггл в On на открытие портов  (рис. [-@fig:017]).

![ура](image/17.png){#fig:017 width=70%}


# Выводы

Поставили инструмент моделирования конфигурации сети Cisco Packet
Tracer [3], ознакомились

# Список литературы{.unnumbered}

::: {#refs}
:::
