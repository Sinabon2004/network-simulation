---
## Front matter
title: "Отчёт по лабораторной работе №4"
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

Основной целью работы является знакомство с NETEM — инструментом для
тестирования производительности приложений в виртуальной сети, а также
получение навыков проведения интерактивного и воспроизводимого экспериментов по измерению задержки и её дрожания (jitter) в моделируемой сети
в среде Mininet.


# Выполнение лабораторной работы

Задаем простейшую топологию (рис. [-@fig:001]).

![mn --topo=single, 2 x](image/1.png){#fig:001 width=70%}

Проверяем автоматическое выставление ip (рис. [-@fig:002]).

![host-1 ](image/2.png){#fig:002 width=70%}

Проверяем автоматическое выставление ip (рис. [-@fig:003]).

![host-2](image/3.png){#fig:003 width=70%}

Проверяем соединение (рис. [-@fig:004]).

![ping](image/4.png){#fig:004 width=70%}

Задаем задержку на первый хост 100мс (рис. [-@fig:005]).

![cli = tc](image/5.png){#fig:005 width=70%}

Задаем задержку на второй хост (рис. [-@fig:006]).

![cli = tc](image/6.png){#fig:006 width=70%}

Проверяем задержку (рис. [-@fig:007]).

![заметна задержка](image/7.png){#fig:007 width=70%}

Убираем задержку (рис. [-@fig:008]).

![результат пинга](image/8.png){#fig:008 width=70%}

Задержка убирается опцией del (рис. [-@fig:009]).

![опция в деле](image/9.png){#fig:009 width=70%}

Добавляем случайное отклонение 10мс

![после delay вторым параметром](image/10.png){#fig:010 width=70%}

Добавляем корреляцию

![третий параметр после delay](image/11.png){#fig:011 width=70%}

Добавляем распределение

![distribution normal](image/12.png){#fig:012 width=70%}

Обновляем пакеты, ставим geequi

![ждем....](image/13.png){#fig:013 width=70%}

Организовываем папочки

![для наших воспроизводимых экспов](image/14.png){#fig:014 width=70%}

Создали скрипт mininet топологии

![на питоне](image/15.png){#fig:015 width=70%}

Написали скрипт для gnu plot

![несложно](image/16.png){#fig:016 width=70%}

написали makefile 

![несложно](image/17.png){#fig:017 width=70%}

Протестировали

![test](image/18.png){#fig:018 width=70%}

Посмотрели график

![красивый](image/19.png){#fig:019 width=70%}

Смотрим график при убранном из входных первого пакета

![видим отступ в начале](image/20.png){#fig:020 width=70%}

Скрипт для подсчёта метрик rtt

![на питоне](image/21.png){#fig:021 width=70%}

Обновляем makefile

![добавили rtt.py](image/22.png){#fig:022 width=70%}

Протестили

![test](image/23.png){#fig:023 width=70%}

Сделали папки для СР

![4шт](image/24.png){#fig:024 width=70%}

Для демонстрации изменения задержки в дисц.очередей - делаем два прогона ping'а

![сделали](image/25.png){#fig:025 width=70%}

запуск

![change](image/26.png){#fig:026 width=70%}

график

![change](image/27.png){#fig:027 width=70%}

Прогон с отклонением

![dev](image/28.png){#fig:028 width=70%}

запуск с отклонением

![dev](image/29.png){#fig:029 width=70%}

график

![dev](image/30.png){#fig:030 width=70%}

прогон с корреляцией

![cor](image/31.png){#fig:031 width=70%}

запуск топологии

![cor](image/32.png){#fig:032 width=70%}

plot

![cor](image/33.png){#fig:033 width=70%}

Прогон с паретовским распределением

![pareto](image/34.png){#fig:034 width=70%}

execution

![pareto](image/35.png){#fig:035 width=70%}

plot

![pareto](image/36.png){#fig:036 width=70%}


# Выводы

Познакомились с NETEM, а также
получили навыки проведения интерактивного и воспроизводимого экспериментов по измерению задержки и её дрожания (jitter) в моделируемой сети
в среде Mininet.

# Список литературы{.unnumbered}

::: {#refs}
:::
