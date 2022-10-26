---
## Front matter
title: "Шаблон отчёта по лабораторной работе"
subtitle: "Простейший вариант"
author: "Уханаева Сансара Зоригтуевна"

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

Целью работы является освоение процедуры оформления отчетов с помощью легковесного языка разметки Markdown.

# Задание

1. Откройте терминал
2. Перейдите в каталог курса сформированный при выполнении лаборатор-
ной работы No3:
38 Демидова А. В.
Архитектура ЭВМ
cd ~/work/study/2022-2023/"Архитектура компьютера"/arch-pc/
Обновите локальный репозиторий, скачав изменения из удаленного репози-
тория с помощью команды
git pull
3. Перейдите в каталог с шаблоном отчета по лабораторной работе No 4
cd ~/work/study/2022-2023/"Архитектура
компьютера"/arch-pc/labs/lab04/report↪
4. Проведите компиляцию шаблона с использованием Makefile. Для этого
введите команду
make
При успешной компиляции должны сгенерироваться файлы report.pdf и
report.docx. Откройте и проверьте корректность полученных файлов.
5. Удалите полученный файлы с использованием Makefile. Для этого введите
команду
make clean
Проверьте, что после этой команды файлы report.pdf и report.docx были
удалены.
6. Откройте файл report.md c помощью любого текстового редактора, на-
пример gedit
gedit report.md
Внимательно изучите структуру этого файла.
Демидова А. В. 39
Архитектура ЭВМ
7. Заполните отчет и скомпилируйте отчет с использованием Makefile. Про-
верьте корректность полученных файлов. (Обратите внимание, для кор-
ректного отображения скриншотов они должны быть размещены в ката-
логе image)
8. Загрузите файлы на Github.
cd ~/work/study/2022-2023/"Архитектура компьютера"/arch-pc
git add .
git commit -am 'feat(main): add files lab-4'
git push
3.5. Задание для самостоятельной работы
1. В соответствующем каталоге сделайте отчёт по лабораторной работе No 3
в формате Markdown. В качестве отчёта необходимо предоставить отчёты
в 3 форматах: pdf, docx и md.
2. Загрузите файлы на github.

# Теоретическое введение

3.2.1. Базовые сведения о Markdown
Чтобы создать заголовок, используйте знак #, например:
# This is heading 1
## This is heading 2
### This is heading 3
#### This is heading 4
Чтобы задать для текста полужирное начертание, заключите его в двойные
звездочки:
This text is **bold**.
Чтобы задать для текста курсивное начертание, заключите его в одинарные
звездочки:
This text is *italic*.
33 Демидова А. В.
Архитектура ЭВМ
Чтобы задать для текста полужирное и курсивное начертание, заключите его
в тройные звездочки:
This is text is both ***bold and italic***.
Блоки цитирования создаются с помощью символа >:
> The drought had lasted now for ten million years, and the reign of
the terrible lizards had long since ended. Here on the Equator,
in the continent which would one day be known as Africa, the
battle for existence had reached a new climax of ferocity, and
the victor was not yet in sight. In this barren and desiccated
land, only the small or the swift or the fierce could flourish,
or even hope to survive.
↪
↪
↪
↪
↪
↪
Упорядоченный список можно отформатировать с помощью соответствую-
щих цифр:
1. First instruction
1. Sub-instruction
1. Sub-instruction
1. Second instruction
Чтобы вложить один список в другой, добавьте отступ для элементов дочер-
него списка:
1. First instruction
1. Second instruction
1. Third instruction
Неупорядоченный (маркированный) список можно отформатировать с помо-
щью звездочек или тире:
* List item 1
* List item 2
* List item 3
34 Демидова А. В.
Архитектура ЭВМ
Чтобы вложить один список в другой, добавьте отступ для элементов дочер-
него списка:
- List item 1
- List item A
- List item B
- List item 2
Синтаксис Markdown для встроенной ссылки состоит из части [link text],
представляющей текст гиперссылки, и части (file-name.md) – URL-адреса или
имени файла, на который дается ссылка:
[link text](file-name.md)
или
[link text](http://example.com/ "Необязательная подсказка")
Markdown поддерживает как встраивание фрагментов кода в предложение,
так и их размещение между предложениями в виде отдельных огражденных
блоков. Огражденные блоки кода — это простой способ выделить синтаксис для
фрагментов кода. Общий формат огражденных блоков кода:
``` language
your code goes in here
```
3.2.2. Оформление формул в Markdown
Внутритекстовые формулы делаются аналогично формулам LaTeX. Например,
формула sin2(𝑥) + cos2(𝑥) = 1 запишется как
$\sin^2 (x) + \cos^2 (x) = 1$
Демидова А. В. 35
Архитектура ЭВМ
Выключение формулы:
sin2(𝑥) + cos2(𝑥) = 1 (3.1)
со ссылкой в тексте «Смотри формулу ({-eq. 3.1}).» записывается как
$$
\sin^2 (x) + \cos^2 (x) = 1
$$ {#eq:eq1}
Смотри формулу (`[-@eq:eq1]`).
3.2.3. Оформление изображений в Markdown
В Markdown вставить изображение в документ можно с помощью непосред-
ственного указания адреса изображения. Синтаксис данной команды выглядит
следующим образом:
![Подпись к рисунку](/путь/к/изображению.jpg "Необязательная
подсказка"){ #fig:fig1 width=70% }↪
Здесь:
• в квадратных скобках указывается подпись к изображению;
• в круглых скобках указывается URL-адрес или относительный путь изоб-
ражения, а также (необязательно) всплывающую подсказку, заключённую
в двойные или одиночные кавычки.
• в фигурных скобках указывается идентификатор изображения (#fig:fig1)
для ссылки на него по тексту и размер изображения относительно ширины
страницы (width=90%)
Ссылка на изображение (рис. 3.1) может быть оформлена следующим образом
(рис. [-@fig:fig1])
36 Демидова А. В.
Архитектура ЭВМ
Рис. 3.1. Подпись к рисунку
3.2.4. Обработка файлов в формате Markdown
Преобразовать файл README.md можно следующим образом:
pandoc README.md -o README.pdf
или так
pandoc README.md -o README.docx
Для компиляции отчетов по лабораторным работам предлагается использо-
вать следующий Makefile
FILES = $(patsubst %.md, %.docx, $(wildcard *.md))
FILES += $(patsubst %.md, %.pdf, $(wildcard *.md))
LATEX_FORMAT =
FILTER = --filter pandoc-crossref
%.docx: %.md
Демидова А. В. 37
Архитектура ЭВМ
-pandoc "$<" $(FILTER) -o "$@"
%.pdf: %.md
-pandoc "$<" $(LATEX_FORMAT) $(FILTER) -o "$@"
all: $(FILES)
@echo $(FILES)
clean:
-rm $(FILES) *~
3.3. Техническое обеспечение
При выполнении лабораторной работы на своей технике необходимо устано-
вить следующее ПО:
• TeX Live (https://www.tug.org/texlive/) последней версии.
• Pandoc (https://pandoc.org/) версии v2.18
• Pandoc-crossref (https://github.com/lierdakil/pandoc-crossref/releases)
версии v0.3.13.0
На компьютерах в дисплейных классах факультета физико-математических
и естественных наук РУДН все необходимое ПО установлено

# Выполнение лабораторной работы

1. Откроем терминал
2. Перейдем в каталог курса сформированный при выполнении лабораторной работы №3:
(/afs/.dk.sci.pfu.edu.ru/home/s/z/szukhanaeva/Изображения/Снимки экрана/Снимок экрана от 2022-10-26 15-09-58.png)
Обновим локальный репозиторий, скачав изменения из удаленного репозитория с помощью команды git pull
(/afs/.dk.sci.pfu.edu.ru/home/s/z/szukhanaeva/Изображения/Снимки экрана/Снимок экрана от 2022-10-26 15-16-21.png)

3. Перейдем в каталог с шаблоном отчета по лабораторной работе № 4
(/afs/.dk.sci.pfu.edu.ru/home/s/z/szukhanaeva/Изображения/Снимки экрана/Снимок экрана от 2022-10-26 15-17-33.png)

4. Проведем компиляцию шаблона с использованием Makefile. Для этого введем команду make
(/afs/.dk.sci.pfu.edu.ru/home/s/z/szukhanaeva/Изображения/Снимки экрана/Снимок экрана от 2022-10-26 15-18-09.png)
Сгенерировались файлы report.pdf и report.docx. Откроем и проверим корректность полученных файлов.
(/afs/.dk.sci.pfu.edu.ru/home/s/z/szukhanaeva/Изображения/Снимки экрана/Снимок экрана от 2022-10-26 15-23-04.png)

5. Удалим полученный файлы с использованием Makefile. Для этого введем команду make clean
(/afs/.dk.sci.pfu.edu.ru/home/s/z/szukhanaeva/Изображения/Снимки экрана/Снимок экрана от 2022-10-26 15-30-35.png)
Проверим, что после этой команды файлы report.pdf и report.docx были удалены.
(/afs/.dk.sci.pfu.edu.ru/home/s/z/szukhanaeva/Изображения/Снимки экрана/Снимок экрана от 2022-10-26 15-30-49.png)
(/afs/.dk.sci.pfu.edu.ru/home/s/z/szukhanaeva/Изображения/Снимки экрана/Снимок экрана от 2022-10-26 15-34-55.png)

6. Откроем файл report.md c помощью текстового редактора gedit и внимательно изучим структуру этого файла.
(/afs/.dk.sci.pfu.edu.ru/home/s/z/szukhanaeva/Изображения/Снимки экрана/Снимок экрана от 2022-10-26 15-31-44.png)
(/afs/.dk.sci.pfu.edu.ru/home/s/z/szukhanaeva/Изображения/Снимки экрана/Снимок экрана от 2022-10-26 15-32-17.png)

7. Заполним отчет и скомпилируем отчет с использованием Makefile и проверим корректность полученных файлов. (Для корректного отображения скриншотов они должны быть размещены в каталоге image)
(/afs/.dk.sci.pfu.edu.ru/home/s/z/szukhanaeva/Изображения/Снимки экрана/Снимок экрана от 2022-10-26 15-57-43.png)

8. Загрузим файлы на Github.

# Выводы
Я освоила процедуры оформления отчетов с помощью легковесного языка разметки Markdown

# Список литературы{.unnumbered}

::: {#refs}
:::
