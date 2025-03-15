---
## Front matter
title: "Лабораторная работа 6"
subtitle: "Модель хищник-жертва"
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

Реализовать модель хищник-жертва в xcos и OpenModelica.

# Задание

1. Реализовать модель хищник-жертва в xcos;
2. Реализовать модель хищник-жертва в xcos с помощью блока Modelica;
3. Реализовать модель хищник-жертва в OpenModelica.

# Теоретическое введение

Модель «хищник–жертва» (модель Лотки — Вольтерры) представляет собой модель межвидовой конкуренции. В математической форме модель имеет вид:

$$
\begin{cases}
  \dot x = ax - bxy;
  \dot y = cxy - dy,
\end{cases}
$$

где $x$ — количество жертв; $y$ — количество хищников; $a, b, c, d$ — коэффициен-ты, отражающие взаимодействия между видами: $a$ — коэффициент рождаемости жертв; $b$ — коэффициент убыли жертв; $c$ — коэффициент рождения хищников; $d$ — коэффициент убыли хищников.

# Выполнение лабораторной работы

## Реализация модели в xcos

Зафиксируем начальные данные: $a = 2, b = 1, c = 0, 3, d = 1, x(0) = 2, y(0) = 1$. В меню Моделирование, Задать переменные окружения зададим значения коэф-
фициентов $a, b, c, d$ (рис. [-@fig:001]).

![Задание переменных окружения](image/1.png){#fig:001 width=70%}

Для реализации модели в дополнение к блокам `CLOCK_c`, `CSCOPE`, `TEXT_f`, `MUX`, `INTEGRAL_m`, `GAINBLK_f`, `SUMMATION`, `PROD_f` потребуется блок `CSCOPX` — регистрирующее устройство для построения фазового портрета.

Реализованная модель хищник-жертва предствлена на рис. [-@fig:002].

![Модель хищник-жертва в xcos](image/model.png){#fig:002 width=70%}

В меню Моделирование, Установка необходимо задать конечное время интегрирования, равным времени моделирования: 30 (рис. [-@fig:003]).

![Конечное время интегрирования](image/2.png){#fig:003 width=70%}


В параметрах блоков интегрирования зададим начальные значения $x(0) = 2, y(0) = 1$ (рис. [-@fig:004], [-@fig:005]).

![Начальные значения для верхнего блока интегрирования](image/3.png){#fig:004 width=70%}

![Начальные значения для нижнего блока интегрирования](image/4.png){#fig:005 width=70%}

Результат моделирования представлен на рис. [-@fig:006]. Черной линией обозначен график $x(t)$ (динамика численности жертв), зеленая линия определяет $y(t)$ — динамику численности хищников.

![Результат моделирования](image/6.png){#fig:006 width=70%}

На рис. [-@fig:007] приведён фазовый портрет модели.

![Фазовый портрет модели](image/5.png){#fig:007 width=70%}

## Реализация модели с помощью блока Modelica

Для реализации модели с помощью языка Modelica потребуются следующие блоки xcos: `CLOCK_c`, `CSCOPE`, `CSCOPXY`, `TEXT_f`, `MUX`, `CONST_m` и `MBLOCK` (Modelica generic).

Как и ранее, задаём значения коэффициентов a, b, c, d (рис. [-@fig:008]).

![Задание переменных окружения](image/7.png){#fig:008 width=70%}

Готовая модель хищник–жертва представлена на рис. [-@fig:009].

![Модель хищник-жертва с применением блока Modelica](image/model-modelica.png){#fig:009 width=70%}

Параметры блока Modelica представлены на рис. [-@fig:010]. Переменные на входе (“a”, “b”, “c”, “d”) и выходе (“x”, “y”) блока заданы как внешние (“E”).

![Параметры блока Modelica](image/9.png){#fig:010 width=70%}

Результат моделирования получаем следующие графики (рис. [-@fig:011], [-@fig:012]).

![Результат моделирования с применением блока Modelica](image/10.png){#fig:011 width=70%}


![Фазовый портрет модели с применением блока Modelica](image/11.png){#fig:012 width=70%}

## Упражнение

Реализуем модель «хищник – жертва» в OpenModelica. Построим
графики изменения численности популяций и фазовый портрет.

```
  parameter Real a = 2;
  parameter Real b = 1;
  parameter Real c = 0.3;
  parameter Real d = 1;
  parameter Real x0 = 2;
  parameter Real y0 = 1;

  Real x(start=x0);
  Real y(start=y0);
equation
  der(x) = a*x - b*x*y;
  der(y) = c*x*y - d*y;
```

В результате выполнения симуляции получим график изменения численности хищников и жертв (рис. [-@fig:013]).

![Динамика численности особей модели хищник-жертва в OpenModelica](image/12.png){#fig:013 width=70%}

Также получим фазовый портрет для модели (рис. [-@fig:014]).

![Фазовый портрет модели хищник-жертва в OpenModelica](image/14.png){#fig:014 width=70%}

# Выводы

В результате выполнения лабораторной работы реализована модель хищник-жертва в xcos, с помощью блока Modelica и OpenModelica.

# Список литературы{.unnumbered}

::: {#refs}
:::
