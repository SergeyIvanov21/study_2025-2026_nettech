---
## Front matter
title: "Отчет по лабораторной работе №4"
subtitle: "Дисциплина: Сетевые технологии"
author: "Иванов Сергей Владимирович"

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
listingTitle: "Листинг"
lofTitle: "Список иллюстраций"
lolTitle: "Листинги"
## Misc options
indent: true
header-includes:
  - \usepackage{indentfirst}
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

Установка и настройка GNS3 и сопутствующего программного обеспечения.

# Задание

1. Установить GNS3-all-in-one, GNS3 VM, проверить корректность запуска (см.
раздел 4.3).
2. Импортировать в GNS3 образ маршрутизатора FRR (см. раздел 4.4).
3. Импортировать в GNS3 образ маршрутизатора VyOS (см. раздел 4.4).

# Выполнение лабораторной работы

## Установка GNS3-all-in-one

Сначала я скачал с репозитория GitHub необходимый .exe файл. Далее запускаю его, следуя указаниям, нажимая
Next, принимая соглашение по лицензии, выбирая отображение названия
каталога в стартовом меню. (рис. 1)

![Процесс установки](image/1.png){#fig:001 width=70%}

В процессе установки при выборе комплектации требуется отметить MSVC
Runtime (отмечено по умолчанию), GNS3-Desktop, GNS3-VM, Tools. (рис. 2)

![Выбор инструментов](image/2.png){#fig:002 width=70%}

Затем требуется указать расположение устанавливаемого пакета (можно оставить
выдаваемое по умолчанию). В следующем окне требуется отметить тип
виртуальной машины (VirtualBox), затем нажать Inslall  (рис. 3)

![Выбор типа ВМ](image/3.png){#fig:003 width=70%}

Началась установка. (рис. 4) 

![Установка](image/4.png){#fig:004 width=70%}

В конце процесса установки появится
окно с предложением запуска GNS3 после установки, снимаю галочку, нажимаю Finish. (рис. 5)

![Завершение установки](image/5.png){#fig:005 width=70%}

## Установка GNS3 VM для VirtualBox

Перейдем в каталог, в который скачан архив с образом виртуальной машины
GNS3.VM.VirtualBox.номер-версии.zip. Распакуем архив с образом. (рис. 6)

![Распаковка архива](image/6.png){#fig:006 width=70%}

Запустим VirtualBox. Выберем меню Файл Импорт конфигураций... Укажем
месторасположение распакованного образа GNS3 VM.ova. В следующем окне
в параметрах импорта выберем в политике MAC-адреса «Сгенерировать
новые MAC-адреса всех сетевых адаптеров». Нажмем Импорт. (рис. 7)

![Импорт машины](image/7.png){#fig:007 width=70%}

Уточним параметры настройки виртуальной машины GNS3 VM в VirtualBox. Основная память — не менее 2048 МБ, число процессоров — 2 ЦП. Далее нужно убедиться, что в VirtualBox в графическом интерфейсе флажок «Включить Nested VT-x/AMD-V» отмечен включённым (рис. 8)

![Уточнение параметров машины](image/8.png){#fig:008 width=70%}

Настроим сетевой адаптер. Для этого в VirtualBox выберем импортированную виртуальную машину и перейдем в меню Машина Настроить. Перейдем
к опции «Сеть» и во вкладке «Адаптер 1» тип подключения должен быть
установлен как «Виртуальный адаптер хоста». (рис. 9)

![Настройка сетевого адаптера](image/9.png){#fig:009 width=70%}

##  Запуск экземпляра GNS3 в VirtualBox

Запустим GNS3 VM в VirtualBox. (рис. 10)

![Запуск GNS3 VM](image/10.png){#fig:010 width=70%}

Затем в основной операционной системе запустим приложение gns3. (рис. 11)

![Запуск GNS3](image/11.png){#fig:011 width=70%}

При первом запуске приложения gns3 запускается мастер настройки, в котором следует выбрать первый способ работы с gns3 — «Run appliance in a virtual
machine», нажать Next. В следующем окне указываются настройки локального сервера. Путь к серверу
и порту оставлю без изменений. Выберем IP-адрес привязки хоста, находящегося
в подсети VirtualBox, затем нажмем Next. (рис. 12)

![Запуск GNS3](image/12.png){#fig:012 width=70%}

После успешного подсоединения должно появиться окно с итоговыми настройками, на котором следует нажать Finish. (рис. 13)

![Завершение настройки](image/13.png){#fig:013 width=70%}

Интерфейс GNS3. (рис. 14)

![Запущенный GNS3](image/14.png){#fig:014 width=70%}

## Добавление образа маршрутизатора FRR

В рабочем пространстве GNS3 на левой боковой панели выберем просмотр
маршрутизаторов (Browse Routers), затем нажмем на + New template.
В открывшемся окне укажем рекомендуемое верхнее значение, а именно,
устанавливать образ с GNS3-сервера (рис. 15)

![Добавление роутера FRR](image/15.png){#fig:015 width=70%}

В следующем окне выберем Routers и образ FRR (FRRouting), нажмем Install. (рис. 16)

![Добавление роутера FRR](image/16.png){#fig:016 width=70%}

В следующем окне укажем, что устанавливать образ следует на виртуальную
машину GNS3 VM, нажмем Next. Далее предлагается выбор эмулятора, оставлю предложенное, нажмем Next. В следующем 
окне предлагается перечень файлов для скачивания и последующей установки. Выберем наиболее актуальную версию и нажмем Download (рис. 17)

![Добавление роутера FRR](image/17.png){#fig:017 width=70%}

После окончания скачивания можно импортировать образ, затем нажать Next. (рис. 18)

![Добавление роутера FRR](image/18.png){#fig:018 width=70%}

На заключительном окне указывается краткая информация об устройстве,
просмотрим её и нажмем Finish. (рис. 19)

![Добавление роутера FRR](image/19.png){#fig:019 width=70%}

В рабочем пространстве на левой панели в списке маршрутизаторов появится
образ устройства FRR.
Далее необходимо настроить образ маршрутизатора. Правой кнопкой мыши
щёлкнем на образе устройства, в меню выберем Configure template. (рис. 20)

![Настройка роутера FRR](image/20.png){#fig:020 width=70%}

В открывшемся окне необходимо во вкладке «General settings» в поле «On close» выбрать Send the shutdown signal (ACPI) . Во вкладке «HDD» 
необходимо поставить галочку «Automatically create a config disk on HDD». (рис. 21, 22)

![Настройка роутера FRR](image/21.png){#fig:021 width=70%}

![Настройка роутера FRR](image/22.png){#fig:022 width=70%}

## Добавление образа маршрутизатора VyOS

По аналогии с установкой FRR, на левой боковой панели выберем просмотр
маршрутизаторов (Browse Routers), затем нажмем на + New template. В следующем окне выберем Routers и образ VyOS, нажмем Install (рис. 23)

![Добавление VyOS](image/23.png){#fig:023 width=70%}

Выберем версию и нажмем Download. (рис. 24)

![Добавление VyOS](image/24.png){#fig:024 width=70%}

После окончания скачивания можно импортировать образ, затем нажать Next. (рис. 25)

![Добавление VyOS](image/25.png){#fig:025 width=70%}

В рабочем пространстве на левой панели в списке маршрутизаторов появится
образ VyOS.
Далее необходимо настроить образ маршрутизатора. Правой кнопкой мыши
щёлкнем на образе устройства, в меню выберем Configure template. В открывшемся окне необходимо во вкладке «General settings» в поле «On close» выбрать Send the shutdown signal (ACPI). Во вкладке «HDD» 
необходимо поставить галочку «Automatically create a config disk on HDD». (рис. 26, 27)

![Настройка VyOS](image/26.png){#fig:026 width=70%}

![Настройка VyOS](image/27.png){#fig:027 width=70%}

# Выводы

В ходе выполнения лабораторной работы мы установили и настроили GNS3 и сопутствующее программное обеспечение.