---
## Front matter
title: "Отчёт по лабораторной работе №3"
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

Основной целью работы является знакомство с инструментом для измерения
пропускной способности сети в режиме реального времени — iPerf3, а также
получение навыков проведения воспроизводимого эксперимента по измерению
пропускной способности моделируемой сети в среде Mininet.

# Выполнение лабораторной работы

Создаем необходимые папки и копируем emptynet.py (рис. [-@fig:001]).

![in dir lab_iperf3_topo](image/1.png){#fig:001 width=70%}

Запускаем файл (рис. [-@fig:002]).

![Выводится консоль iperf3](image/2.png){#fig:002 width=70%}

Смотрим все элементы топологии (рис. [-@fig:003]).

![net links dump](image/3.png){#fig:003 width=70%}

В коде выводим IP&MAC адрес (рис. [-@fig:004]).

![via print](image/4.png){#fig:004 width=70%}

Запускаем отредактированную программу (рис. [-@fig:005]).

![наблюдаем корректное отображение для 1 хоста](image/5.png){#fig:005 width=70%}

Добавляем такое же отображение для 2 хоста (рис. [-@fig:006]).

![тот же код только для h2](image/6.png){#fig:006 width=70%}

Запускаем отредактированную программу (рис. [-@fig:007]).

![наблюдаем корректное отображение для 2 хоста](image/7.png){#fig:007 width=70%}

Добавляем импорты CPULimitHost & TCLink (рис. [-@fig:008]).

![CPULimitHost & TCLink](image/8.png){#fig:008 width=70%}

Расширяем net импортированными модулями (рис. [-@fig:009]).

![в вызове Mininet](image/9.png){#fig:009 width=70%}

Добавляем ограничение CPU на хосты (рис. [-@fig:010]).

![ура! добавили](image/10.png){#fig:010 width=70%}

Запускаем код (рис. [-@fig:011]).

![наблюдаем ограничение cpu](image/11.png){#fig:011 width=70%}

Изменяем структуру (рис. [-@fig:012]).

![переименовали / перенесли / etc](image/12.png){#fig:012 width=70%}

Выполняем iperf команды прямо в коде(рис. [-@fig:013]).

![так же для h1 добавляем вывод в отчёт](image/13.png){#fig:013 width=70%}

Запускаем измененный код (рис. [-@fig:014]).

![так же видим отключенный cli](image/14.png){#fig:014 width=70%}

Создаем Мэйкфайл и настраиваем его (рис. [-@fig:015]).

![для автоматизации](image/15.png){#fig:015 width=70%}

Пробуем наш Мэйкфайл(рис. [-@fig:016]).

![ура! получилось](image/16.png){#fig:016 width=70%}

# Выводы

Познакомились с инструментом для измерения
пропускной способности сети в режиме реального времени — iPerf3, а также
получили навыки проведения воспроизводимого эксперимента по измерению
пропускной способности моделируемой сети в среде Mininet

# Список литературы{.unnumbered}

::: {#refs}
:::
