---
## Front matter
lang: ru-RU
title: Лабораторная работа 8
subtitle: Модель TCP/AQM
author:
  - Клюкин М. А.
institute:
  - Российский университет дружбы народов, Москва, Россия
  

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
 - \usepackage{fontspec}
 - \usepackage{polyglossia}
 - \setmainlanguage{russian}
 - \setotherlanguage{english}
 - \newfontfamily\cyrillicfont{Arial}
 - \newfontfamily\cyrillicfontsf{Arial}
 - \newfontfamily\cyrillicfonttt{Arial}
 - \setmainfont{Arial}
 - \setsansfont{Arial}
 
---


## Докладчик

:::::::::::::: {.columns align=center}
::: {.column width="70%"}

  * Клюкин Михаил Александрович
  * студент
  * Российский университет дружбы народов
  * [1132226431@pruf.ru](mailto:1132226431@pfur.ru)
  * <https://MaKYaro.github.io/ru/>

:::
::: {.column width="30%"}

![](./image/XjDz893-bSI.jpg)

:::
::::::::::::::

## Цель работы

Реализовать модель TCP/AQM в xcos и OpenModelica.

## Задания

1. Построить модель TCP/AQM в xcos.
2. Построить графики изменения размера TCP окна $W(t)$ и размера очереди $Q(t)$.
3. Построить модель TCP/AQM в OpenModelica.

## Реализация в xcos

![Установка контекста](image/1.png){#fig:001 width=70%}

## Реализация в xcos

![Модель TCP/AQM в xcos](image/2.png){#fig:002 width=70%}

## Реализация в xcos

![Изменение размера окна и размера очереди](image/3.png){#fig:003 width=70%}

## Реализация в xcos

![Фазовый портрет (W, Q)](image/4.png){#fig:004 width=70%}

## Реализация в xcos

![Изменение размера окна и размера очереди при $C = 0.9$](image/5.png){#fig:005 width=70%}

## Реализация в xcos

![Фазовый портрет (W, Q) при $C = 0.9$](image/6.png){#fig:006 width=70%}

## Реализация модели в OpenModelica

```
parameter Real N=1;
parameter Real R=1;
parameter Real K=5.3;
parameter Real C=1;
```

## Реализация модели в OpenModelica

```
Real W(start=0.1);
Real Q(start=1);
```

## Реализация модели в OpenModelica

```
der(W) = 1/R - W*delay(W, R)/(2*R)*K*delay(Q, R);
der(Q) = if (Q==0) then max(N*W/R-C,0) else (N*W/R-C);
```

## Реализация модели в OpenModelica

![Изменение размера окна и размера очереди в OpenModelica](image/7.png){#fig:007 width=70%}

## Реализация модели в OpenModelica

![Фазовый портрет в OpenModelica](image/8.png){#fig:008 width=70%}

## Выводы

В процессе выполнения лабораторной работы реализовали модель TCP/AQM в xcos и OpenModelica.


