# Разработка веб-интерфейса для взаимодействия с устройством.

Связь осуществляется посредством Ethernet, а значит  надо определится и с протоколом.

HTTP REST-модель не подходит. Кроме двустороней связи, нужна и односторонняя, где инициатором может как клиент, так и сервер,
к примеру для отправки уведомления, манипуляции устройством из клиентской части.

Протоколы, которые следует рассмотреть в первую очередь:
1. использование websocket
2. MQTT-протокол

Нужно определится с сервером, который будет крутится на устройстве, есть библиотеки, которые облегчают эту задачу.
Я рассмотрела mongoose, много простых и понятных примеров, как для http, websocket и MQTT.

Веб-приложение, которое открывается в браузере, будет обмениваться с устройством сообщениями. Надо определиться с форматом этих сообщений. 
JSON - отличный кандидат на эту роль. 

Следующий пункт касается веб-приложения. Разберемся, какие технологии веб-разработки подойдут для встраиваемых систем.
Требования этих систем:
1. ограничение по занимаемой на sd-карте памяти.
2. минимизация нагрузки на процессор.

Самый дешевый и простой подход - использование чистых httml, css и javascript. Но, если хочется визуально приятного и современного интерфейса, то
стоит обратить внимание на некоторые библиотечки и фреймворки.
В этой статье есть ссылки на подходящие из них с точки зрения разработки интерфейса для встраиваемых систем: https://www.netburner.com/learn/web-development-for-embedded-systems-engineers/

С них и начнем:


## Flutter

Это уже не js и html, но при сборке он конвертируется в них, чтобы исполняться в браузере. То есть на выходе при развертываниии
своего приложения мы имеем структуру файлов с *.js и *.html

Интерфейс знакомый из iOS и Android. Как сделать что-то отличное, надо поразбираться, если остановимся на этом варианте.
В галерее много интересного https://gallery.flutter.dev/#/

Используется язык Dart для написания приложения. На первый взгляд подходит, тем более, когда ты в начале пути, и в любом случае учить новый язык, будь то JS или Dart.
Но в случае с Dart не надо учить подробно верстку.

Отлично подходит для приложений с большим количеством элементов управления, что нам и нужно. Не подходит для статичных, страниц с большими объемами текстовой информации.

Надо проверить на деле, как будет работать на устройстве. Заявлено, что собранное веб-приложение можно развернуть на любом сервере.
