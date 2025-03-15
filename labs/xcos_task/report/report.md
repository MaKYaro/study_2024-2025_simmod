---
## Front matter
title: "Отчет по выполнению упражнения. Подсистема xcos"
subtitle: "Фигуры Лиссажу"
author: "Клюкин Михаил Александрович"

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
lot: false # List of tables
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

Выполнить упражнение по ознакомлению с программой *xcos*.

# Задание

Построить с помощью xcos фигуры Лиссажу со следующими параметрами:

1) $A = B = 1, a = 2, b = 2,  \delta = 0;  \pi/4;  \pi/2;  3\pi/4;  \pi;$

2) $A = B = 1, a = 2, b = 4,  \delta = 0;  \pi/4;  \pi/2;  3\pi/4;  \pi;$

3) $A = B = 1, a = 2, b = 6,  \delta = 0;  \pi/4;  \pi/2;  3\pi/4;  \pi;$

4) $A = B = 1, a = 2, b = 3,  \delta = 0;  \pi/4;  \pi/2;  3\pi/4;  \pi.$

# Выполнение лабораторной работы

Математическое выражение для кривой Лиссажу:
$$
\begin{cases}
  x(t) = A sin(at + \delta),\\
  y(t) = B sin(bt),
\end{cases}
$$
где $A, B$ -- амплитуды колебаний, $a, b$ -- частоты, $\delta$ -- сдвиг фаз.
В модели, изображённой на рис. [-@fig:021], использованы следующие блоки xcos:
- CLOCK_c -- запуск часов модельного времени;
- GENSIN_f -- блок генератора синусоидального сигнала;
- CSOPXY -- анимированное регистрирующее устройство для построения графика
типа y = f(x);
- TEXT_f -- задаёт текст примечаний.

![Модель для построения фигур Лиссажу в xcos](image/21.png){#fig:021 width=70%}

Получим график фигуры Лиссажу для параметров $A = B = 1, a = 2, b = 2, \delta = 0$ (рис. [-@fig:001]). Меняя фазу первого генератора на $\pi/4, \pi/2,  3\pi/4, \pi$, получим соответствующие фигуры Лиссажу (рис. [-@fig:002]-[-@fig:005]).

![Фигура Лиссажу для $A = B = 1, a = 2, b = 2, \delta = 0$](image/1.png){#fig:001 width=70%}

![Фигура Лиссажу для $A = B = 1, a = 2, b = 2, \delta = \pi /4$](image/2.png){#fig:002 width=70%}

![Фигура Лиссажу для $A = B = 1, a = 2, b = 2, \delta = \pi /2$](image/3.png){#fig:003 width=70%}

![Фигура Лиссажу для $A = B = 1, a = 2, b = 2, \delta = 3\pi /4$](image/4.png){#fig:004 width=70%}

![Фигура Лиссажу для $A = B = 1, a = 2, b = 2, \delta = \pi$](image/5.png){#fig:005 width=70%}

Изменим параметр частоты на втором генераторе.

Получим график фигуры Лиссажу для параметров $A = B = 1, a = 2, b = 4, \delta = 0$ (рис. [-@fig:006]). Меняя фазу первого генератора на $\pi/4, \pi/2,  3\pi/4, \pi$, получим соответсвующие фигуры Лиссажу (рис. [-@fig:007]-[-@fig:010]).

![Фигура Лиссажу для $A = B = 1, a = 2, b = 4, \delta = 0$](image/6.png){#fig:006 width=70%}

![Фигура Лиссажу для $A = B = 1, a = 2, b = 4, \delta = \pi /4$](image/7.png){#fig:007 width=70%}

![Фигура Лиссажу для $A = B = 1, a = 2, b = 4, \delta = \pi /2$](image/8.png){#fig:008 width=70%}

![Фигура Лиссажу для $A = B = 1, a = 2, b = 4, \delta = 3\pi /4$](image/9.png){#fig:009 width=70%}

![Фигура Лиссажу для $A = B = 1, a = 2, b = 4, \delta = \pi$](image/10.png){#fig:010 width=70%}

Изменим параметр частоты на втором генераторе.

Получим график фигуры Лиссажу для параметров $A = B = 1, a = 2, b = 6, \delta = 0$ (рис. [-@fig:011]). Меняя фазу первого генератора на $\pi/4, \pi/2,  3\pi/4,  \pi$,  получим соответствующие фигуры Лиссажу (рис. [-@fig:012]-[-@fig:015]).

![Фигура Лиссажу для $A = B = 1, a = 2, b = 6, \delta = 0$](image/11.png){#fig:011 width=70%}

![Фигура Лиссажу для $A = B = 1, a = 2, b = 6, \delta = \pi /4$](image/12.png){#fig:012 width=70%}

![Фигура Лиссажу для $A = B = 1, a = 2, b = 6, \delta = \pi /2$](image/13.png){#fig:013 width=70%}

![Фигура Лиссажу для $A = B = 1, a = 2, b = 6, \delta = 3\pi /4$](image/14.png){#fig:014 width=70%}

![Фигура Лиссажу для $A = B = 1, a = 2, b = 6, \delta = \pi$](image/15.png){#fig:015 width=70%}

Изменим параметр частоты на втором генераторе.

Получим график фигуры Лиссажу для параметров $A = B = 1, a = 2, b = 4, \delta = 0$ (рис. [-@fig:016]). Меняя фазу первого генератора на $\pi/4, \pi/2, 3\pi/4, \pi$, получим соответсвующие фигуры Лиссажу (рис. [-@fig:016]-[-@fig:020]).

![Фигура Лиссажу для $A = B = 1, a = 2, b = 3, \delta = 0$](image/16.png){#fig:016 width=70%}

![Фигура Лиссажу для $A = B = 1, a = 2, b = 3, \delta = \pi /4$](image/17.png){#fig:017 width=70%}

![Фигура Лиссажу для $A = B = 1, a = 2, b = 3, \delta = \pi /2$](image/18.png){#fig:018 width=70%}

![Фигура Лиссажу для $A = B = 1, a = 2, b = 3, \delta = 3\pi /4$](image/19.png){#fig:019 width=70%}

![Фигура Лиссажу для $A = B = 1, a = 2, b = 3, \delta = \pi$](image/20.png){#fig:020 width=70%}

# Выводы

В результате данной лабораторной работы выполнено упражнение по ознакомлению с программой *xcos*.
