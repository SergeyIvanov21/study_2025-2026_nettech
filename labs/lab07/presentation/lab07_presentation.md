---
## Front matter
lang: ru-RU
title: Лабораторная работа №7
subtitle: Сетевые технологии
author:
  - Иванов Сергей Владимирович, НПИбд-01-23
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 02 декабря 2025

## i18n babel
babel-lang: russian
babel-otherlangs: english

## Formatting pdf
toc: false
slide_level: 2
aspectratio: 169
section-titles: true
theme: metropolis
header-includes:
 - \metroset{progressbar=frametitle,sectionpage=progressbar,numbering=fraction}
 - '\makeatletter'
 - '\beamer@ignorenonframefalse'
 - '\makeatother'

 ## Fonts
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase,Scale=0.9
---

## Цель

Получение навыков настройки службы DHCP на сетевом оборудовании для
распределения адресов IPv4 и IPv6.

## Настройка DHCP в случае IPv4

![Создание сети](image/1.png){#fig:001 width=70%}

## Настройка DHCP в случае IPv4

![Запуск маршрутизатора](image/2.png){#fig:002 width=70%}

## Настройка DHCP в случае IPv4

На маршрутизаторе изменим имя устройства и доменное имя, заменим системного пользователя.

![Настройка маршрутизатора](image/3.png){#fig:003 width=70%}

## Настройка DHCP в случае IPv4

![Настройка маршрутизатора](image/4.png){#fig:004 width=70%}

## Настройка DHCP в случае IPv4

Настроим адресацию IPv4: 

![Настройка адресации IPv4](image/5.png){#fig:005 width=70%}
 
## Настройка DHCP в случае IPv4

Добавим конфигурацию DHCP-сервера на маршрутизаторе:

![Конфигурация dhcp](image/6.png){#fig:006 width=70%}

## Настройка DHCP в случае IPv4

![Просмотр статистики](image/7.png){#fig:007 width=70%}

## Настройка DHCP в случае IPv4

![Настройка PC1](image/8.png){#fig:008 width=70%}

## Настройка DHCP в случае IPv4

![Настройка PC1](image/9.png){#fig:009 width=70%}

## Настройка DHCP в случае IPv4

![Проверка конфигурации и пропинговка](image/10.png){#fig:010 width=70%}

## Настройка DHCP в случае IPv4

![Просмотр статистики](image/11.png){#fig:011 width=70%}

## Настройка DHCP в случае IPv4

На маршрутизаторе посмотрим журнал работы DHCP-сервера:

![Просмотр журнала DHCP-сервера](image/12.png){#fig:012 width=70%}

## Настройка DHCP в случае IPv4

![Анализ пакетов](image/13.png){#fig:013 width=70%}

## Настройка DHCP в случае IPv6

![Настройка Server](image/14.png){#fig:014 width=70%}

## Настройка DHCP в случае IPv6

![Настройка маршрутизации IPv6](image/15.png){#fig:015 width=70%}

## Настройка DHCP в случае IPv6

На маршрутизаторе настроим DHCPv6 без отслеживания состояния:

![Настройка DHCPv6](image/16.png){#fig:016 width=70%}

## Настройка DHCP в случае IPv6

Добавление конфигурации DHCP-сервера:

![Настройка DHCPv6](image/17.png){#fig:017 width=70%}

## Настройка DHCP в случае IPv6

![Проверка настроек PC2](image/18.png){#fig:018 width=70%}

## Настройка DHCP в случае IPv6

![Пооверка связи](image/19.png){#fig:019 width=70%}

## Настройка DHCP в случае IPv6

![Проверка настроек DNS](image/20.png){#fig:020 width=70%}

## Настройка DHCP в случае IPv6

На узле PC2 получим адрес по DHCPv6 (запрос только информации DHCPv6, но не адреса)

![Получение адреса](image/21.png){#fig:021 width=70%}

## Настройка DHCP в случае IPv6

Пропингуем от PC2 маршрутизатор

![Проверка связи](image/22.png){#fig:022 width=70%}

## Настройка DHCP в случае IPv6

Проверим настройки DNS

![Проверка DNS](image/23.png){#fig:023 width=70%}

## Настройка DHCP в случае IPv6

![Статистика и выданные адреса](image/24.png){#fig:024 width=70%}

## Настройка DHCP в случае IPv6

![Захваченый трафик и анализ информации](image/25.png){#fig:025 width=70%}

## Настройка DHCP в случае IPv6

На маршрутизаторе настроим DHCPv6 с отслеживанием состояния 

![Настройка DHCPv6 с отслеживаем информации](image/26.png){#fig:026 width=70%}

## Настройка DHCP в случае IPv6

Добавим конфигурацию DHCP-сервера на маршрутизаторе:

![Конфигурация DHCP сервера](image/27.png){#fig:027 width=70%}

## Настройка DHCP в случае IPv6

На маршрутизаторе посмотрим выданные адреса: 

![Просмотр выданных адресов](image/28.png){#fig:028 width=70%}

## Настройка DHCP в случае IPv6

![Настройки PC3](image/29.png){#fig:029 width=70%}

## Настройка DHCP в случае IPv6

На узле PC3 проверим настройки DNS:

![Настройки DNS](image/30.png){#fig:030 width=70%}

## Настройка DHCP в случае IPv6

На узле PC3 получим адрес по DHCPv6:

![Получение адреса](image/31.png){#fig:031 width=70%}

## Настройка DHCP в случае IPv6

![Проверка настроек сети](image/32.png){#fig:032 width=70%}

## Настройка DHCP в случае IPv6

![Пинг и проверка DNS](image/33.png){#fig:033 width=70%}

## Настройка DHCP в случае IPv6

![Выданные адреса](image/34.png){#fig:034 width=70%}

## Настройка DHCP в случае IPv6

![Захваченный трафик](image/35.png){#fig:035 width=70%}

# Вывод

## Вывод 

В ходе выполнения лабораторной работы мы получили навыки настройки службы DHCP на сетевом оборудовании для
распределения адресов IPv4 и IPv6.








 
