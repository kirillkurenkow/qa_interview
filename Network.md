# Network

## Модель OSI
**Модель OSI (Open System Interconnection)** — 7-уровневая логическая модель работы сети. 

Реализуется группой протоколов и правил связи, организованных в несколько уровней:
* На физическом уровне определяются физические (механические, электрические, оптические) характеристики линий связи;
* На канальном уровне определяются правила использования физического уровня узлами сети;
* Сетевой уровень отвечает за адресацию и доставку сообщений;
* Транспортный уровень контролирует очередность прохождения компонентов сообщения;
* Сеансовый уровень координирует связь между двумя прикладными программами, работающими на разных рабочих станциях;
* Уровень представления служит для преобразования данных из внутреннего формата компьютера в формат передачи;
* Прикладной уровень является пограничным между прикладной программой и другими уровнями, обеспечивая удобный интерфейс 
связи для сетевых программ пользователя.

## Протоколы
**Протокол передачи данных** — набор соглашений интерфейса логического уровня, которые определяют обмен данными между 
различными программами. 
Эти соглашения задают единообразный способ передачи сообщений и обработки ошибок при взаимодействии программного 
обеспечения разнесённой в пространстве аппаратуры, соединённой тем или иным интерфейсом.

### HTTP
**HTTP** — широко распространённый протокол передачи данных, изначально предназначенный для передачи гипертекстовых 
документов (то есть документов, которые могут содержать ссылки, позволяющие организовать переход к другим документам).

Аббревиатура HTTP расшифровывается как HyperText Transfer Protocol.

#### Методы HTTP запросов
##### GET
Метод `GET` запрашивает представление ресурса. Запросы с использованием этого метода могут только извлекать данные.

##### POST
`POST` используется для отправки сущностей к определённому ресурсу. 
Часто вызывает изменение состояния или какие-то побочные эффекты на сервере.

##### DELETE
`DELETE` удаляет указанный ресурс

##### HEAD
`HEAD` запрашивает ресурс так же, как и метод `GET`, но без тела ответа.

##### PUT
`PUT` заменяет все текущие представления ресурса данными запроса.

##### CONNECT
`CONNECT` устанавливает "туннель" к серверу, определённому по ресурсу.

##### OPTIONS
`OPTIONS` используется для описания параметров соединения с ресурсом.

##### TRACE
`TRACE` выполняет вызов возвращаемого тестового сообщения с ресурса.

##### PATCH
`PATCH` используется для частичного изменения ресурса.

#### Коды ответа HTTP
Код ответа (состояния) HTTP показывает, был ли успешно выполнен определённый HTTP запрос. Коды сгруппированы в 5 классов:
1. Информационные `100 - 199`
2. Успешные `200 - 299`
3. Перенаправления `300 - 399`
4. Клиентские ошибки `400 - 499`
5. Серверные ошибки `500 - 599`

##### Описание некоторых кодов ответа HTTP
| Код |       Название        | Описание                                                                                                                                                                   |
|:---:|:---------------------:|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| 100 |       Continue        | Этот промежуточный ответ указывает, что запрос успешно принят и клиент может продолжать присылать запросы либо проигнорировать этот ответ, если запрос был завершён.       |
| 101 |  Switching Protocol   | Этот код присылается в ответ на запрос клиента, содержащий заголовок `Upgrade`, и указывает, что сервер переключился на протокол, который был указан в заголовке.          |
| 200 |          OK           | Запрос успешно обработан                                                                                                                                                   |
| 201 |        Created        | Запрос успешно выполнен и в результате был создан ресурс.                                                                                                                  |
| 202 |       Accepted        | Запрос принят, но ещё не обработан. Не поддерживаемо, т.е., нет способа с помощью HTTP отправить асинхронный ответ позже, который будет показывать итог обработки запроса. |
| 300 |    Multiple Choice    | Этот код ответа присылается, когда запрос имеет более чем один из возможных ответов. И User-agent или пользователь должен выбрать один из ответов.                         |
| 301 |   Moved Permanently   | Этот код ответа значит, что URI запрашиваемого ресурса был изменён.                                                                                                        |
| 302 |         Found         | Этот код ответа значит, что запрошенный ресурс временно изменён.                                                                                                           |
| 400 |      Bad Request      | Этот ответ означает, что сервер не понимает запрос из-за неверного синтаксиса.                                                                                             |
| 401 |     Unauthorized      | Для получения запрашиваемого ответа нужна аутентификация. Статус похож на статус 403, но,в этом случае, аутентификация возможна.                                           |
| 403 |       Forbidden       | У клиента нет прав доступа к содержимому, поэтому сервер отказывается дать надлежащий ответ.                                                                               |
| 404 |       Not Found       | Сервер не может найти запрашиваемый ресурс.                                                                                                                                |
| 500 | Internal Server Error | Сервер столкнулся с ситуацией, которую он не знает как обработать.                                                                                                         |
| 502 |      Bad Gateway      | Эта ошибка означает что сервер, во время работы в качестве шлюза для получения ответа, нужного для обработки запроса, получил недействительный (недопустимый) ответ.       |
| 503 |  Service Unavailable  | Сервер не готов обрабатывать запрос. Зачастую причинами являются отключение сервера или то, что он перегружен.                                                             |
| 504 |    Gateway Timeout    | Этот ответ об ошибке предоставляется, когда сервер действует как шлюз и не может получить ответ вовремя.                                                                   |

### TCP и TCP/IP
**TCP** — это протокол управления передачей (Transmission Control Protocol). 
Его задача — управлять отправкой данных и следить за тем, чтобы они были гарантированно приняты получателем.

**IP** — протокол, который отвечает за адресацию: чтобы нужные данные долетели до нужного компьютера. 
Его основная задача — логически соединить компьютеры между собой, чтобы можно было отправлять данные от одного к другому. 
Для этого он выделяет IP-адреса, строит маршруты доставки пакетов, а главное — умеет организовать передачу данных с 
помощью пакетов.

**TCP/IP** — общее стандартное название двух протоколов, `TCP` и `IP`. 
Они стоят рядом потому, что протокол `TCP` работает поверх `IP`, а вместе эти протоколы образуют универсальный стек 
протоколов передачи данных.

### DHCP
**DHCP (Dynamic Host Configuration Protocol)** — сетевой протокол, позволяющий сетевым устройствам автоматически 
получать IP-адрес и другие параметры, необходимые для работы в сети `TCP/IP`.

### DNS
**DNS (Domain Name System)** — компьютерная распределённая система для получения информации о доменах. 
Чаще всего используется для получения IP-адреса по имени хоста

---

## API
Интерфейс прикладного программирования (API) определяет правила, которым необходимо следовать для связи с другими 
программными системами.

### REST
**REpresentational State Transfer (REST)** — это программная архитектура, которая определяет условия работы API.

Отличительной особенностью сервисов REST является то, что они позволяют наилучшим образом использовать протокол HTTP.

#### Основные принципы REST
* Единый интерфейс
* Разграничение клиента и сервера
* Нет сохранения состояния
* Кэширование всегда разрешено
* Многоуровневая система
* Код предоставляется по запросу

### RPC
У семейства протоколов RPC (Remote Procedure Call) свой отличительный подход — удаленный вызов процедур. 
В отличие от REST, одна точка входа, и телом запроса определяется, какой ресурс или какое действие будет выполнено. 
Реализаций подхода не так много. Главным образом они различаются форматом передачи данных — XML, JSON или бинарный.

#### XML-RPC и SOAP
**XML-RPC** изначально был разработан Microsoft в конце 90-х годов. 
Это текстовый протокол, в изначальном виде довольно прост в освоении. 
Единственная проблема этого формата — это сам XML (eXtensible Markup Language). XML, 
как формат передачи данных, довольно избыточен. В первую очередь, из-за открывающих и закрывающих тегов. 
У HTML в каком-то смысле та же проблема, но ничего другого для верстки не существует.

Позже Microsoft разработали еще один протокол, который стал расширением XML-RPC — SOAP (Simple Object Access Protocol). 
У него более строгая структура, много ограничений и требований. Сам протокол может работать поверх множества 
сетевых протоколов – SMTP, FTP и тд.

#### JSON-RPC
**JSON-RPC** — это протокол семейства RPC, у которого в качестве формата передачи данных используется JSON. 

Типичный запрос выглядит так: 
```
POST /rpc 

{
  "method": "getSomeData",
  "params": ["list", "of", "params"],
  "id": 1
}
```

#### gRPC
**gRPC** — это бинарный протокол, т.е. данные передаются в бинарном виде, а не в виде текста.

Для кодирования и декодирования сообщений используется собственный протокол сериализации **Protobuf (Protocol Buffers)**. 
Максимально похожий на структуры из языка Си.

---

## Сокеты
**Сетевые сокеты** — способ взаимодействия любого приложения с системой на которой оно работает. 

**Сокет** — это интерфейс, который по сути представляет собой совокупность адреса в сети и используемого порта.
