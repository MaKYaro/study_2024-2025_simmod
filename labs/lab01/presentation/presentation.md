---
## Front matter
lang: ru-RU
title: Лабораторная работа 1
subtitle: Простые модели компьютерной сети
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

## Цели

Приобрести навыки моделирования сетей передачи данных с помощью средства имитацинного моделирования NS-2.
А также проанализировать полученные результаты моделирования.

## Задание

1. Создать шаблон сценария для NS-2;
2. Выполнить простой пример описания топологии сети, состоящей из двух узлов и одного соединения;
3. Выполнить пример с усложненной топологией сети;
4. Выполнить пример с кольцевой топологией сети;
5. Выполнить упражнение.

# Выполнение лабораторной работы

## Шаблон сценария для NS-2

![Создание директорий и шаблона](image/1.png){#fig:001 width=70%}

## Шаблон сценария для NS-2

![Запуск шаблона сценария для NS-2](image/2.png){#fig:002 width=40%}

## Простой пример описания топологии сети, состоящей из двух узлов и одного соединения

![Визуализация простой модели сети с помощью nam](image/3.png){#fig:003 width=40%}

## Простой пример описания топологии сети, состоящей из двух узлов и одного соединения

![Передача данных в простой модели сети](image/4.png){#fig:004 width=40%}

## Пример с усложненной топологией сети

![Модель сети с усложненной топологией](image/5.png){#fig:005 width=40%}

## Пример с усложненной топологией сети

![Модель сети с усложненной топологией](image/7.png){#fig:007 width=40%}

## Пример с усложненной топологией сети

![Потеря пакетов в модели с усложненной топлогией](image/8.png){#fig:008 width=40%}

## Пример с кольцевой топологией

![Модель сети с кольцевой топологией](image/9.png){#fig:009 width=40%}

## Пример с кольцевой топологией

![Передача данных между узлами `n(0)` и `n(3)` по кратчайшему пути](image/10.png){#fig:010 width=40%}

## Пример с кольцевой топологией

![Потеря пакетов при разрыве сети](image/11.png){#fig:011 width=40%}

## Пример с кольцевой топологией

![Маршрутизация данных по сети с кольцевой топологией в случае разрыва сети](image/12.png){#fig:012 width=40%}

## Упражнение

![Измененная кольцевая топология сети](image/15.png){#fig:015 width=40%}

## Упражнение

![Передача данных между узлами `n(0)` и `n(5)` по кратчайшему пути](image/16.png){#fig:016 width=40%}

## Упражнение

![Потеря пакетов при разрыве соединения](image/17.png){#fig:017 width=40%}

## Упражнение

![Передача данных между узлами `n(0)` и `n(5)` по альтернативному пути](image/18.png){#fig:018 width=40%}

## Упражнение

![Передача данных между узлами `n(0)` и `n(3)` по кратчайшему пути посел восстановления соединения](image/19.png){#fig:019 width=40%}

## Выводы

В процессе выполнения лабораторной работы приобрели навыки моделирования сетей передачи данных с помощью средств имитационного моделирования NS-2, а также проанализировали полученные результаты моделирования.
