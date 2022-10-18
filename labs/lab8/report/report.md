---
## Front matter
title: "Отчёт по лабораторной работе №8"
subtitle: "Дисциплина: Основы информационной безопасности"
author: "Полиенко Анастасия Николаевна, НПМбд-01-19"

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

Освоить на практике применение однократного гаммирования при работе с различными текстами на одном ключе.

# Теоретическое введение

Гаммирование представляет собой наложение (снятие) на открытые (зашифрованные) данные последовательности элементов других данных, полученной с помощью некоторого криптографического алгоритма, для получения зашифрованных (открытых) данных. Иными словами, наложение
гаммы — это сложение её элементов с элементами открытого (закрытого)
текста по некоторому фиксированному модулю, значение которого представляет собой известную часть алгоритма шифрования.

В соответствии с теорией криптоанализа, если в методе шифрования используется однократная вероятностная гамма (однократное гаммирование)
той же длины, что и подлежащий сокрытию текст, то текст нельзя раскрыть.
Даже при раскрытии части последовательности гаммы нельзя получить информацию о всём скрываемом тексте.
Наложение гаммы по сути представляет собой выполнение операции
сложения по модулю 2 (XOR) (обозначаемая знаком ⊕) между элементами
гаммы и элементами подлежащего сокрытию текста.

# Выполнение лабораторной работы

Cоздаём функцию, которая осуществляет однократное гаммирование посредством побитового XOR (рис. [-@fig:001])

![Функция шифрования](image/Screenshot_1.jpg){ #fig:001 width=70% }

Задаём две равные по длине текстовые строки и создаём случайный символьный ключ такой же длины (рис. [-@fig:002])

![Исходные данные](image/Screenshot_2.jpg){ #fig:002 width=70% }

Осуществляем шифрование двух текстов по ключу с помощью написанной функции (рис. [-@fig:003])

![Шифрование данных](image/Screenshot_3.jpg){ #fig:003 width=70% }

Создаём переменную, которая, прогнав два шифрованных текста через побитовый XOR, поможет злоумышленнику
получить один текст, зная другой, без ключа (рис. [-@fig:004])

![Получение данных без ключа](image/Screenshot_4.jpg){ #fig:004 width=70% }

Таким же способом можно получить часть данных (рис. [-@fig:005])

![Получение части данных](image/Screenshot_5.jpg){ #fig:005 width=70% }

# Выводы

Я освоила на практике применение режима однократного гаммирования при работе с несколькими текстами.

# Список литературы{.unnumbered}

::: {#refs}
:::
