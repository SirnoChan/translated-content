---
title: Как работает Веб
slug: Learn_web_development/Getting_started/Web_standards/How_the_web_works
---

{{LearnSidebar}}{{PreviousMenu("Learn/Getting_started_with_the_web/Publishing_your_website", "Learn/Getting_started_with_the_web")}}

_Как работает Веб_ даст упрощённое представление о том, что происходит при просмотре веб-страницы в браузере на вашем компьютере или телефоне.

Эта теория не так важна для написания веб-кода в краткосрочной перспективе, но в скором времени вы действительно начнёте извлекать выгоду из понимания того, что происходит в фоновом режиме.

## Клиенты и серверы

Компьютеры, подключённые к сети, называются клиентами и серверами. Упрощённая схема того, как они взаимодействуют, может выглядеть следующим образом:

![](client-server.jpg)

- Клиенты являются обычными пользователями, подключёнными к Интернету посредством устройств (например, компьютер подключён к Wi-Fi, или ваш телефон подключён к мобильной сети) и программного обеспечения, доступного на этих устройствах (как правило, браузер, например, Firefox или Chrome).
- Серверы - это компьютеры, которые хранят веб-страницы, сайты или приложения. Когда клиентское устройство пытается получить доступ к веб-странице, копия страницы загружается с сервера на клиентский компьютер для отображения в браузере пользователя.

## Остальные части панели инструментов

Клиент и сервер, о которых мы рассказали выше, не раскрывают всю суть. Есть много других компонентов, и мы опишем их ниже.

А сейчас давайте представим, что Веб - это дорога. Одна сторона дороги является клиентом, который представляет собой ваш дом. Другая сторона дороги является сервером, который представляет собой магазин. Вы хотите что-то купить в нём.

![](road.jpg)

Помимо клиента и сервера, мы также должны уделить внимание:

- **Ваше Интернет-подключение**: Позволяет отправлять и принимать данные по сети. Оно подобно улице между домом и магазином.
- **TCP/IP**: Протокол Управления Передачей и Интернет Протокол являются коммуникационными протоколами, которые определяют, каким образом данные должны передаваться по сети. Они как транспортные средства, которые позволяют сделать заказ, пойти в магазин и купить ваши товары. В нашем примере, это как автомобиль или велосипед (или собственные ноги).
- **DNS**: Система Доменных Имён напоминает записную книжку для веб-сайтов. Когда вы вводите веб-адрес в своём браузере, браузер обращается к DNS, чтобы найти реальный адрес веб-сайта, прежде чем он сможет его получить. Браузеру необходимо выяснить, на каком сервере живёт сайт, поэтому он может отправлять HTTP-сообщения в нужное место (см. Ниже). Это похоже на поиск адреса магазина, чтобы вы могли попасть в него.
- **HTTP**: Протокол Передачи Гипертекста - это {{Glossary("Protocol", "протокол")}}, который определяет язык для клиентов и серверов, чтобы общаться друг с другом. Он, как язык, который вы используете, чтобы заказать ваш товар.
- **Файлы компонентов**: сайт состоит из нескольких различных файлов, которые подобны различным отделам с товарами в магазине. Эти файлы бывают двух основных типов:
  - **Файлы кода**: сайты построены преимущественно на HTML, CSS и JavaScript, хотя вы познакомитесь с другими технологиями чуть позже.
  - **Материалы**: это собирательное название для всех других вещей, составляющих сайт, такие как изображения, музыка, видео, документы Word и PDF.

## Что же на самом деле происходит?

Когда вы вводите веб-адрес в свой браузер (для нашей аналогии - посещаете магазин):

1. Браузер обращается к DNS серверу и находит реальный адрес сервера, на котором "живёт" сайт (Вы находите адрес магазина).
2. Браузер посылает HTTP запрос к серверу, запрашивая его отправить копию сайта для клиента (Вы идёте в магазин и заказываете товар). Это сообщение и все остальные данные, передаваемые между клиентом и сервером, передаются по интернет-соединению с использованием протокола TCP/IP.
3. Если сервер одобряет запрос клиента, сервер отправляет клиенту статус "200 ОК", который означает: "Конечно, вы можете посмотреть на этот сайт! Вот он", а затем начинает отправку файлов сайта в браузер в виде небольших порций, называемых пакетными данными (магазин выдаёт вам ваш товар или вам привозят его домой).
4. Браузер собирает маленькие куски в полноценный сайт и показывает его вам (товар прибывает к вашей двери — новые вещи, потрясающе!).

## DNS

Реальные веб-адреса - неудобные, незапоминающиеся строки, которые вы вводите в адресную строку, чтобы найти ваши любимые веб-сайты. Эти строки состоят из чисел, например: `63.245.215.20`.

Такой набор чисел называется {{Glossary("IP Address", "IP-адресом")}} и представляет собой уникальное местоположение в Интернете. Впрочем, его не очень легко запомнить, правда? Вот почему изобрели DNS. Это специальные сервера, которые связывают веб-адрес, который вы вводите в браузере (например, "mozilla.org"), с реальным IP-адресом сайта.

Сайты можно найти непосредственно через их IP-адреса. Вы можете найти IP-адрес веб-сайта, введя его домен в инструмент, как [IP Checker](https://www.nslookup.io/website-to-ip-lookup/).

## Пакеты

Ранее мы использовали термин "пакеты", чтобы описать формат, в котором данные передаются от сервера к клиенту. Что мы имеем в виду? В основном, когда данные передаются через Интернет, они отправляются в виде тысячи мелких кусочков, так что множество разных пользователей могут скачивать один и тот же сайт одновременно. Если бы сайты отправлялись одним большим куском, тогда бы только один пользователь мог скачать его за один раз, и это, очевидно, сделало бы пользование интернетом не эффективным и не очень радостным.

## Смотрите также

- [Как работает Интернет](/ru/docs/Learn_web_development/Howto/Web_mechanics/How_does_the_Internet_work)
- [HTTP — Протокол уровня приложений](https://dev.opera.com/articles/http-basic-introduction/)
- [HTTP: Давайте изучим его!](https://dev.opera.com/articles/http-lets-get-it-on/)
- [HTTP: Коды ответов](https://dev.opera.com/articles/http-response-codes/)

## Благодарность

Фото улицы: [Street composing](https://www.flickr.com/photos/kdigga/9110990882/in/photolist-cXrKFs-c1j6hQ-mKrPUT-oRTUK4-7jSQQq-eT7daG-cZEZrh-5xT9L6-bUnkip-9jAbvr-5hVkHn-pMfobT-dm8JuZ-gjwYYM-pREaSM-822JRW-5hhMf9-9RVQNn-bnDMSZ-pL2z3y-k7FRM4-pzd8Y7-822upY-8bFN4Y-kedD87-pzaATg-nrF8ft-5anP2x-mpVky9-ceKc9W-dG75mD-pY62sp-gZmXVZ-7vVJL9-h7r9AQ-gagPYh-jvo5aM-J32rC-ibP2zY-a4JBcH-ndxM5Y-iFHsde-dtJ15p-8nYRgp-93uCB1-o6N5Bh-nBPUny-dNJ66P-9XWmVP-efXhxJ), [Kevin D](https://www.flickr.com/photos/kdigga/).

{{PreviousMenu("Learn/Getting_started_with_the_web/Publishing_your_website", "Learn/Getting_started_with_the_web")}}
