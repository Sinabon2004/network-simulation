---
## Front matter
lang: ru-RU
title: Защита по лабораторной работе №4
subtitle: pf
author:
  - Чесноков Артемий Павлович
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 15 марта 2025

## i18n babel
babel-lang: russian
babel-otherlangs: english

## Formatting pdf
toc: false
toc-title: Содержание
slide_level: 2
aspectratio: 169
section-titles: true
theme: metropolis
header-includes:
 - \metroset{progressbar=frametitle,sectionpage=progressbar,numbering=fraction}
---

# Информация


## Цель

Основной целью работы является знакомство с NETEM — инструментом для
тестирования производительности приложений в виртуальной сети, а также
получение навыков проведения интерактивного и воспроизводимого экспериментов по измерению задержки и её дрожания (jitter) в моделируемой сети
в среде Mininet.

## Задаем простейшую топологию
![mn --topo=single, 2 x](image/1.png){#fig:001 width=70%}

## Проверяем автоматическое выставление ip
![host-1](image/2.png){#fig:002 width=70%}

## Проверяем автоматическое выставление ip
![host-2](image/3.png){#fig:003 width=70%}

## Проверяем соединение
![ping](image/4.png){#fig:004 width=70%}

## Задаем задержку на первый хост 100мс
![cli = tc](image/5.png){#fig:005 width=70%}

## Задаем задержку на второй хост
![cli = tc](image/6.png){#fig:006 width=70%}

## Проверяем задержку
![заметна задержка](image/7.png){#fig:007 width=70%}

## Убираем задержку
![результат пинга](image/8.png){#fig:008 width=70%}

## Задержка убирается опцией del
![опция в деле](image/9.png){#fig:009 width=70%}

## Добавляем случайное отклонение 10мс
![после delay вторым параметром](image/10.png){#fig:010 width=70%}

## Добавляем корреляцию
![третий параметр после delay](image/11.png){#fig:011 width=70%}

## Добавляем распределение
![distribution normal](image/12.png){#fig:012 width=70%}

## Обновляем пакеты, ставим geequi
![ждем....](image/13.png){#fig:013 width=70%}

## Организовываем папочки
![для наших воспроизводимых экспов](image/14.png){#fig:014 width=70%}

## Создали скрипт mininet топологии
![на питоне](image/15.png){#fig:015 width=70%}

## Написали скрипт для gnu plot
![несложно](image/16.png){#fig:016 width=70%}

## написали makefile
![несложно](image/17.png){#fig:017 width=70%}

## Протестировали
![test](image/18.png){#fig:018 width=70%}

## Посмотрели график
![красивый](image/19.png){#fig:019 width=70%}

## Смотрим график при убранном из входных первого пакета
![видим отступ в начале](image/20.png){#fig:020 width=70%}

## Скрипт для подсчёта метрик rtt
![на питоне](image/21.png){#fig:021 width=70%}

## Обновляем makefile
![добавили rtt.py](image/22.png){#fig:022 width=70%}

## Протестили
![test](image/23.png){#fig:023 width=70%}

## Сделали папки для СР
![4шт](image/24.png){#fig:024 width=70%}

## Для демонстрации изменения задержки в дисц.очередей - делаем два прогона ping'а
![сделали](image/25.png){#fig:025 width=70%}

## запуск
![change](image/26.png){#fig:026 width=70%}

## график
![change](image/27.png){#fig:027 width=70%}

## Прогон с отклонением
![dev](image/28.png){#fig:028 width=70%}

## запуск с отклонением
![dev](image/29.png){#fig:029 width=70%}

## график
![dev](image/30.png){#fig:030 width=70%}

## прогон с корреляцией
![cor](image/31.png){#fig:031 width=70%}

## запуск топологии
![cor](image/32.png){#fig:032 width=70%}

## plot
![cor](image/33.png){#fig:033 width=70%}

## Прогон с паретовским распределением
![pareto](image/34.png){#fig:034 width=70%}

## execution
![pareto](image/35.png){#fig:035 width=70%}

## plot
![pareto](image/36.png){#fig:036 width=70%}

## Спасибо за внимание.
