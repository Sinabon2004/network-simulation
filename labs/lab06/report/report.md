---
## Front matter
title: "Отчёт по лабораторной работе №6
subtitle: "Командная оболочка Midnight Commander"
author: "Чесноков Артерий Павлович"

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
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase,Scale=0.9
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

Основной целью работы является знакомство с принципами работы дисциплины очереди Token Bucket Filter, которая формирует входящий/исходящий
трафик для ограничения пропускной способности, а также получение навыков
моделирования и исследования поведения трафика посредством проведения
интерактивного и воспроизводимого экспериментов в Mininet.

# Выполнение лабораторной работы

1. Создаем линейную топологию (рис. @fig:001).

![два коммутатора & два хоста](image/1.png){#fig:001 width=70%}

2. Сталкиваемся с x11 проблемой (рис. @fig:002).

![тк запускаем мининет под судо](image/2.png){#fig:002 width=70%}

3. Обновляем куку (рис. @fig:003).

![берем из mininet пользователя](image/3.png){#fig:003 width=70%}

4. Проверяем адреса (рис. @fig:004).

![и другие назначенные автоматически конфигурации](image/4.png){#fig:004 width=70%}

5. Проверяем соединение  (рис. @fig:005).

![от h1 в h2](image/5.png){#fig:005 width=70%}

6. Фиксируем текущий битрейт (рис. @fig:006).

![пропускная способность ~22Gb/s](image/6.png){#fig:006 width=70%}

7. Создаем tbf правило (рис. @fig:007).

![обращаем внимание на такт процессора](image/7.png){#fig:007 width=70%}

8. Проверяем пропускную способность (рис. @fig:008).

![Фиксируем примененные нами ограничения](image/8.png){#fig:008 width=70%}

9. Удаляем созданное нами правило (рис. @fig:009).

![на хосте размещать ограничивающие политики = плохая практика](image/9.png){#fig:009 width=70%}

10. Поэтому разместим правило на сетевом устройстве (рис. @fig:010).

![видим тот же битрейт](image/10.png){#fig:010 width=70%}

11. Удаляем правило (рис. @fig:011).

![с коммутатора](image/11.png){#fig:011 width=70%}

12. Создаем сложные правила  (рис. @fig:012).

![на одно правило накладываем другое](image/12.png){#fig:012 width=70%}

13. Создаем окружение для воспроизводимого эксперимента (рис. @fig:013).

![берем за основу наши наработки из 3 лабораторной работы](image/13.png){#fig:013 width=70%}

14. Демонстрирую процесс поиска нужного шаблона (рис. @fig:014).

![через grep ищу упоминания](image/14.png){#fig:014 width=70%}

15. Импровизируем и редактируем скрипт запуска топологии (рис. @fig:015).

![так же делаем линейную топологию](image/15.png){#fig:015 width=70%}

16. Редактируем скрипт отвечающий за отрисовку графика (рис. @fig:016).

![делаем две кривые](image/16.png){#fig:016 width=70%}

17. Восхищаемся графиком (рис. @fig:017).

![разница в битрейте колоссальна](image/17.png){#fig:017 width=70%}


# Выводы

В ходе выполнения лабораторной работы мы с алгоритмом TBF, научились ограничивать пропускную способность в сети, а так же строить сложные правила в дисциплине очередей (netem + tbf).

