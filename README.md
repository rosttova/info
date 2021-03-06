1) Клиент-серверная архитектура - сетевая нагрузка на языке SQL, распределенная между сервером и клиентом. Сервером является софт, предоставляющий услугу, а клиентом - веб-приложние\десктоп\и тд. 

Может быть:
1. Одноуровневая (клиент-сервер) - простые сайты
2. Двухуровневая (клиент-сервер через API) - более сложные сайты
3. Трехуровневая (клиент-сервер-база данных) - ресурсы, которые обладают высокой безопасностью для клиентов, гибкость услуг, большой базой данных и целостностью данных для клиентов (крупные онлайн-магазины).

Характеристики архитектуры:
- обмен данных на основе сообщений
- сервер сам решает, как обрабатывать запрос
- защищены данные клиента (если используется HTTPs протокол)
- можно сделать сервера более мощными, если добавить балансировщики
- можно подключить к одному ресурсу несколько серверов для постоянной работы при отказе сайта
- масштабируемость
- сервер предоставляет услугу сразу же нескольким клиентам одновременно

Также в клиент-серверной архитектуре существует несколько уровней: уровень представления (интерфейс), уровень бизнес-логики (сервер), уровень данных (БД).


2) HTTP (hyper text transfer protocol) - протокол прикладного уровня передачи данных (в виде гипертекстовый документов) в формате HTML. Клиент посылает запрос серверу и получает от него ответ. 

Особенности HTTP протокола: 
- не защищенный
- можно сохранять информацию клиента (cookie, сессии на сервере)
- в запросе\ответе указывается способ представления ресурса (язык, формат и тд через HTTP-заголовок)

HTTPS - защищенный HTTP протокол, шифрование информации происходит через протокол SSL (устарел) и TLS (новая версия SSL).

TSL протокол шифрует информацию через ассиметричную схему. То есть для шифровки данных у клиента и сервера существует один общий ключ, а для расшифровки создается уже другой. Также TLS обеспечивает сохранность и целостность данных, их приватность и позволяет выполнят аутентификацию пользователя (доступ к ресурсу получают только авторизованные пользователи).

3) HTTP методы показывают основную операцию, производную над ресурсом. Находятся в основной части запроса на сервер.

Основные методы:
- get - запрос на получение информации
- post - отправка данных на сервер
- put - загрузка данных, обновление или замена информации
- delete - удаление 
- connect - преобразование данных в туннель TCP\IP для их шифрования
- head - информация о ресурсе: можно узнать, существует ли файл, когда его меняли и другую информацию.
- options - получить с сервера настройки\параметры
- trace - возвращает запрос с информацией, какую информацию добавляют или меняют промежуточные серверы.
- patch - заменяет часть информации на сервере.

4) HTTP статус коды сервера - показывают статус операции, производимой на сервере.

100 - информационные (100 - все в порядке, клиент должен продолжать запрос, 101 - указан протокол, на какой сервер переключился клиент)

200 - успешная обработка запроса клиента (201 - ресурс создан, 202 - запрос закончен, но не обработан, 203 - OK, но нагрузка изменена с помощью прокси, 205 - вид документа изменился)

300 - перенаправление клиента - для успешного выполнения нужен другой запрос (301 - страница перемещена по другому URI, 304 - данные в кэше, нет необходимости повторно создавать данные, 308 - страница перемещена для post)

400 - ошибка клиента (400 - сервер не понял запрос из-за ошибки в синтаксисе, 401 - ошибка в авторизации, 402 - ошибка в оплате (нужно оплатить), 403 - у пользователя не хватает прав для доступа, 404 - сервер не может найти ресурс, 405 - метод нельзя использовать)

500 - ошибка сервера (501 - сервер не поддерживает метод запроса, 503 - сервер не может получить ответ вовремя, 505 - версия HTTP не поддерживается сервером)

5) Что такое ядро браузера 
Ядро браузера - программа, которая интерактивно отображает данные веб-страниц для пользователя. Ядро загружает данные, обрабатывает и отрисовывает их, а также производит маличные расчеты. 

Ядро облегчает поиск и устранение ошибок кода, упрощает создание новых программ разработчика\пользователя, дает возможность улучшить отдельный компонент сразу в нескольких программа. 

6) Какие браузеры какие ядра используют
1. Internet Explorer - Trident (Edge HTML)
2. Mozilla - Gecko
3. Safari - WebKit
4. Opera - Presto

7) API - технология между двумя программами для их взаимодействия (авторизация через соц.сети, плашка погоды и тд).
	
8. Что такое ендпоинты
Endpoint - конечная точка сайта, обращение к маршруту отдельным HTTP методом. Адрес, на который посылаются запросы.

9) URL - адрес уникального ресурса в Интернете - https://github.com

URI - имя + адрес ресурса - URL+URN - https://github.com/rosttova/hw_git

URN - имя ресурса, может содержать path (адрес ресурса на сайте) и query (дополнительные) параметры. rosttova/hw_git

10) Идемпотентные HTTP методы - если повторный единичный запрос дает один и тот же результат (Get, head, put, delete, options, trace)

11) Безопасные HTTP методы - если один запрос не меняет состояние сервера («только для чтения») - get, head, options, trace.

12) Авторизация - система авторизует пользователя, пропускает на ресурс и определяет его роль. И в последующем предоставляет доступ к данным, исходя из прав клиента.

Идентификация - система определяет пользователя по его логину

Аутентификация - система определяет по паролю в базе данных - выявление подлинности.

13) Что такое IP - Internet protocol - идентификатор (локального устройства, доступность для связи). IP адрес - уникальный сетевой адрес, построенный по протоколу IP - 4 числа от 0-255

Виды IP:
- статический, частный (в локальной сети) - 192.168….
- динамический, публичный (при выходе в Интернет) 

14) Что такое октеты в DNS 
DNS - domain name system, система имен доменов, которая преобразует символьное имя IP в адрес и наоборот. 
Октет - цифра в 8-битных байта (всего в IP-адресе таких 4 цифры. Разделенные точкой)
Октет не должен превышать превышать 255 и составляет 32 бита.

15) Что такое порт, сколько портов у Linux сервера
Порт - номер программы\приложения на компьютере, число от 0 до 65 535, пишется после IP : номер порта. 
Порт необходим для того, чтобы принимать и передавать данные, а также устранять ошибки. 

У Linux сервера может быть 65 535 портов:
- от 0-1023- порты для системных процессов (права администратора)
- от 1024 - 49151 - пользовательские порты
- от 49 152 - 65 5 35 - порты для частных услуг.

16) Уровни OSI
1. Физический - передача битов, радиоканал
2. Канальный - целостность передачи данных по надежной линии связи (изернет)
3. Сетевой (IP) - операции подсети через роутер
4. Транспортный - разбивает и передает данные с гарантией доставки 
5. Сеансовый - устанавливает сеансы связи (RPC, PAP)
6. Уровень представления - преобразовывает форматы данных и шифрование (jpg, gif)
7. Прикладной - уровень приложений (HTTP, FTP)

17) Хедеры http запросов
1. General (основные) - Информация о методе, статус код, откуда пришел клиент, какой URL запрос. Относится как запросам, так и к ответам.
2. Request (запрос) - информация о клиенте или ресурсе, который нужно получить. Можно установить параметры - нужна ли авторизация, в каком виде нужно получить ответ
3. Response (ответ) - дополнительная информация об ответе сервера - user agent, какие типы контента готовы получить
4. Entity (сущности) - информация о теле ресурса (длина содержимого)
5. Custom - собственные заголовки разработчика ( ____ : х - _____)
6. Cookie 
