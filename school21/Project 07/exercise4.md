
### FA 001. Activities - Получить ответ на запрос методом GET

**URL:** {{baseUrl}}/api/v1/Activities

**Ожидаемый результат:** В теле ответа содержится массив структур с ключами "id", "title", "dueDate", "completed" и их значениями. Тип данных значений ключей соответствует требованиям: id - INT, title - string, dueDate - string, completed - boolean. Статус код ответа 200.

**Заголовки запроса:** 
User-Agent:PostmanRuntime/7.36.0; 
Accept-Encoding: gzip, deflate, br;
 Connection: keep-alive; 
 Accept: text/plain; v=1.0

**Тело запроса:** none

**Заголовки ответа:** 
Content-Type: application/json; charset=utf-8; v=1.0;
Date: Fri, 29 Dec 2023 12:19:08 GMT;
Server: Kestrel;
Transfer-Encoding: chunked;
api-supported-versions: 1.0

**Тело ответа:** 
```
    {
        "id": 1,
        "title": "Activity 1",
        "dueDate": "2023-12-29T13:19:09.0703823+00:00",
        "completed": false
    },
    {
        "id": 2,
        "title": "Activity 2",
        "dueDate": "2023-12-29T14:19:09.0703851+00:00",
        "completed": true
    },
    {
        "id": 3,
        "title": "Activity 3",
        "dueDate": "2023-12-29T15:19:09.0703855+00:00",
        "completed": false
    },
```  

### FA 002. Activities - Отправка запроса методом POST с валидным Id - 50

**URL:** {{baseUrl}}/api/v1/Activities

**Ожидаемый результат:** В теле ответа содержится структура(словарь) с ключами "id", "title", "dueDate", "completed" и их занчениями. Тип данных значений ключей соответствует требованиям: id - INT, title - string, dueDate - string, completed - boolean. Статус код ответа 201.

**Заголовки запроса:** 
Content-Type: application/json;
Content-Length: ```<calculated when request is sent>```
Host: ```<calculated when request is sent>```
User-Agent: PostmanRuntime/7.36.0; 
Accept-Encoding: gzip, deflate, br;
 Connection: keep-alive; 
 Accept: text/plain; v=1.0

**Тело запроса:** 

```
{
  "id": {{id_50}},
  "title": "string",
  "dueDate": "2023-12-26T07:43:51.447Z",
  "completed": true
}
```

**Заголовки ответа:** 
Content-Type: application/json; charset=utf-8; v=1.0;
Date: Fri, 29 Dec 2023 13:28:42 GMT;
Server: Kestrel;
Transfer-Encoding: chunked;
api-supported-versions: 1.0

**Тело ответа:** 

```
{
    "id": 50,
    "title": "string",
    "dueDate": "2023-12-26T07:43:51.447Z",
    "completed": true
}
```

### FA 003. Activities - Отправка запроса методом POST с невалидным Id - 99999999999

**URL:** {{baseUrl}}/api/v1/Activities

**Ожидаемый результат:** В теле ответа содержится структура(словарь) с ключами "type", "title", "status", "traceId", "errors" и их занчениями. Статус код ответа 400, в значении ключа "errors" описана ошибка: "The JSON value could not be converted to System.Int32". 

**Заголовки запроса:** 
Content-Type: application/json;
Content-Length: ```<calculated when request is sent>```
Host: ```<calculated when request is sent>```
User-Agent: PostmanRuntime/7.36.0; 
Accept-Encoding: gzip, deflate, br;
 Connection: keep-alive; 
 Accept: text/plain; v=1.0

**Тело запроса:** 

```
{
  "id": {{id_99999999999}},
  "title": "string",
  "dueDate": "2023-12-29T17:48:51.447Z",
  "completed": true
}
```

**Заголовки ответа:** 
Content-Type: application/json; charset=utf-8; v=1.0;
Date: Fri, 29 Dec 2023 13:49:18 GMT;
Server: Kestrel;
Transfer-Encoding: chunked;

**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-01e816c921f54f45b77ee5f26660443a-9363e37a77384945-00",
    "errors": {
        "$.id": [
            "The JSON value could not be converted to System.Int32. Path: $.id | LineNumber: 1 | BytePositionInLine: 19."
        ]
    }
}
```

### FA 004. Activities - Отправка запроса методом POST с пустым Id  

**URL:** {{baseUrl}}/api/v1/Activities

**Ожидаемый результат:** В теле ответа содержится структура(словарь) с ключами "type", "title", "status", "traceId", "errors" и их значениями. Статус код ответа 400, в значении ключа "errors" описана ошибка: "The JSON value could not be converted to System.Int32".

**Заголовки запроса:**   

Content-Type: application/json
User-Agent: PostmanRuntime/7.36.0
Accept-Encoding: gzip, deflate, br
Accept: text/plain; v=1.0

**Тело запроса:** 

```
{
  "id": "string",
  "title": "string",
  "dueDate": "2023-12-26T07:43:51.447Z",
  "completed": true
}
```

**Заголовки ответа:** 



**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-70922b152455084b98bf81f1e7a811f6-037120801d0cfb43-00",
    "errors": {
        "$.id": [
            "The JSON value could not be converted to System.Int32. Path: $.id | LineNumber: 1 | BytePositionInLine: 16."
        ]
    }
}
```
### FA 005. Activities - Отправка запроса методом POST без JSON
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Activities

**Ожидаемый результат:** В теле ответа содержится структура(словарь) с ключами "type", "title", "status", "traceId", "errors" и их значениями. Статус код ответа 400, в значении ключа "errors" описана ошибка: "A non-empty request body is required.".

**Заголовки запроса:** 
Accept text/plain; v=1.0
Content-Type application/json; v=1.0

**Тело запроса:** none

**Заголовки ответа:** 
Content-Type application/problem+json; charset=utf-8
Date Fri, 05 Jan 2024 13:04:21 GMT
Server Kestrel
Transfer-Encoding chunked
**Тело ответа:** 

```
{"type":"https://tools.ietf.org/html/rfc7231#section-6.5.1",
"title":"One or more validation errors occurred.",
"status":400,
"traceId":"00-b1fb7aecfdd84743b349799656064ef4-a806dbf646653e4a-00",
"errors":{"":["A non-empty request body is required."]}}
```
### FA 006. Activities - Отправка запроса методом POST без строки id  
**URL:**  https://fakerestapi.azurewebsites.net//api/v1/Activities

**Ожидаемый результат:** В теле ответа содержится структура(словарь) с ключами "type", "title", "status", "traceId", "errors" и их значениями. Статус код ответа 400, в значении ключа "errors" описана ошибка: "The JSON value could not be converted to System.Int32". 
 
**Заголовки запроса:** 
Accept -H "accept: */*

**Тело запроса:** 

```
{
  "title": "string",
  "dueDate": "2023-12-26T07:43:51.447Z",
  "completed": true
}
```

**Заголовки ответа:** 
Content-Type application/json; charset=utf-8; v=1.0
Date Fri, 05 Jan 2024 13:13:11 GMT
Server Kestrel
Transfer-Encoding chunked
api-supported-versions - 1.0


**Тело ответа:** 

```
{
    "id": 0,
    "title": "string",
    "dueDate": "2023-12-26T07:43:51.447Z",
    "completed": true
}
```
### FA 007. Activities - Отправка запроса методом POST с спецсимволом  вместо id
**URL:**  https://fakerestapi.azurewebsites.net//api/v1/Activities

**Ожидаемый результат:** В теле ответа содержится структура(словарь) с ключами "type", "title", "status", "traceId", "errors" и их значениями. Статус код ответа 400, в значении ключа "errors" описана ошибка: "The JSON value could not be converted to System.Int32".

**Заголовки запроса:** 
Accept  text/plain; v=1.0
Content-Type application/json; v=1.0

**Тело запроса:** 

```
{
  "id": "+-",
  "title": "string",
  "dueDate": "2023-12-26T08:00:24.145Z",
  "completed": true
}
```

**Заголовки ответа:**   
Content-Type - application/problem+json; charset=utf-8
Date - Fri, 05 Jan 2024 13:17:23 GMT
Server Kestrel
Transfer-Encoding - chunked


**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-cf37cfbc4d426246bf35978b999536b4-a17045b9b6914d49-00",
    "errors": {
        "$.id": [
            "The JSON value could not be converted to System.Int32. Path: $.id | LineNumber: 1 | BytePositionInLine: 12."
        ]
    }
}
``` 
### FA 008. Activities - Отправка запроса методом POST с вводом "w8" в поле id  
**URL:**  https://fakerestapi.azurewebsites.net//api/v1/Activities

**Ожидаемый результат:** В теле ответа содержится структура(словарь) с ключами "type", "title", "status", "traceId", "errors" и их значениями. Статус код ответа 400, в значении ключа "errors" описана ошибка: "The JSON value could not be converted to System.Int32".

**Заголовки запроса:** 
Accept text/plain; v=1.0
Content-Type application/json; v=1.0

**Тело запроса:** 

```
{
  "id": "w8",
  "title": "string",
  "dueDate": "2023-12-26T08:00:24.145Z",
  "completed": true
}
```

**Заголовки ответа:** 
Content-Type - application/problem+json; charset=utf-8
Date - Fri, 05 Jan 2024 13:19:34 GMT
Server Kestrel
Transfer-Encoding - chunked


**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-e7a7ee20b602eb46b8d07df66cd3b504-3ad8c3f68d34ac4b-00",
    "errors": {
        "$.id": [
            "The JSON value could not be converted to System.Int32. Path: $.id | LineNumber: 1 | BytePositionInLine: 12."
        ]
    }
}
```
### FA 009. Activities - Отправка запроса методом POST с вводом "аб" в поле id  
**URL:**  https://fakerestapi.azurewebsites.net//api/v1/Activities

**Ожидаемый результат:** В теле ответа содержится структура(словарь) с ключами "type", "title", "status", "traceId", "errors" и их значениями. Статус код ответа 400, в значении ключа "errors" описана ошибка: "The JSON value could not be converted to System.Int32".

**Заголовки запроса:** 
Accept text/plain; v=1.0
Content-Type application/json; v=1.0

**Тело запроса:** 

```
{
  "id": "аб",
  "title": "string",
  "dueDate": "2023-12-26T08:00:24.145Z",
  "completed": true
}
```

**Заголовки ответа:** 
Content-Type - application/problem+json; charset=utf-8
Date - Fri, 05 Jan 2024 13:19:51 GMT
Server Kestrel
Transfer-Encoding - chunked

**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-b22cbf414a803449aef7190e6979f2fb-33dfdefb3c9e1f47-00",
    "errors": {
        "$.id": [
            "The JSON value could not be converted to System.Int32. Path: $.id | LineNumber: 1 | BytePositionInLine: 14."
        ]
    }
}
```
### FA 010. Activities - Отправка запроса методом POST с вводом  отрицательного числа "-1" в поле id  
**URL:**  https://fakerestapi.azurewebsites.net//api/v1/Activities

**Ожидаемый результат:** В теле ответа содержится структура(словарь) с ключами "id", "title", "dueDate", "completed" и их значениями. Статус код ответа 400, в значении ключа "errors" описана ошибка: "The JSON value could not be converted to System.Int32".

**Заголовки запроса:** 
Accept text/plain; v=1.0
Content-Type application/json; v=1.0

**Тело запроса:** 

```
{
  "id": "-1",
  "title": "string",
  "dueDate": "2023-12-26T08:00:24.145Z",
  "completed": true
}
```

**Заголовки ответа:** 
Content-Type - application/json; charset=utf-8; v=1.0
Date - Fri, 05 Jan 2024 13:20:13 GMT
Server Kestrel
Transfer-Encoding - chunked
api-supported-versions - 1.0

**Тело ответа:** 

```
{
    "id": -1,
    "title": "string",
    "dueDate": "2023-12-26T08:00:24.145Z",
    "completed": true
}
```
### FA 011. Activities - Отправка запроса методом POST с вводом "1" в поле id с удалением строки title  
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Activities

**Ожидаемый результат:** В теле ответа содержится структура(словарь) с ключами "id", "title", "dueDate", "completed" и их значениями. Статус код ответа 200. 

**Заголовки запроса:** 
Accept text/plain; v=1.0
Content-Type application/json; v=1.0

**Тело запроса:** 
```
{
  "id": "1",
  "dueDate": "2023-12-26T08:00:24.145Z",
  "completed": true
}
```

**Заголовки ответа:** 
Content-Type - application/json; charset=utf-8; v=1.0
Date - Fri, 05 Jan 2024 13:20:39 GMT
Server Kestrel
Transfer-Encoding - chunked
api-supported-versions - 1.0

**Тело ответа:** 

```
{
    "id": 1,
    "title": null,
    "dueDate": "2023-12-26T08:00:24.145Z",
    "completed": true
}
```
### FA 012. Activities - Отправка запроса методом POST с вводом "1" в поле id с удалением строки completed  
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Activities

**Ожидаемый результат:** В теле ответа содержится структура(словарь) с ключами "type", "title", "status", "traceId", "errors" и их значениями. Статус код ответа 400, в значении ключа "errors" описана ошибка: "The JSON object contains a trailing comma at the end which is not supported in this mode. Change the reader options. Path: $ | LineNumber: 4 | BytePositionInLine: 0." 

**Заголовки запроса:** 
Accept text/plain; v=1.0
Content-Type application/json; v=1.0

**Тело запроса:** 

```
{
  "id": "1",
  "title": "string",
  "dueDate": "2023-12-26T08:00:24.145Z",
}
```

**Заголовки ответа:** 
Content-Type - application/json; charset=utf-8; v=1.0
Date - Fri, 05 Jan 2024 13:20:13 GMT
Server Kestrel
Transfer-Encoding - chunked

**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-3365c503ed5d27438fface55d427e9de-ef61c5387ca21840-00",
    "errors": {
        "$": [
            "The JSON object contains a trailing comma at the end which is not supported in this mode. Change the reader options. Path: $ | LineNumber: 4 | BytePositionInLine: 0."
        ]
    }
}
```
### FA 013. Activities - Отправка запроса методом GET с вводом "1" в поле id   
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Activities/1

**Ожидаемый результат:** В теле ответа содержится структура(словарь) с ключами "id", "title", "dueDate", "completed" и их значениями. Тип данных значений ключей соответствует требованиям: id - INT, title - string, dueDate - string, completed - boolean. Статус код ответа 200.

**Заголовки запроса:** 
Host - <calculated when request is sent>
User-Agent - PostmanRuntime/7.36.0
Accept - */*
Accept-Encoding - gzip, deflate, br
Connection - keep-alive

**Тело запроса:** none


**Заголовки ответа:** 
Content-Type - application/json; charset=utf-8; v=1.0
Date - Fri, 05 Jan 2024 13:21:18 GMT
Server Kestrel
Transfer-Encoding - chunked
api-supported-versions - 1.0

**Тело ответа:** 

```
{
    "id": 1,
    "title": "Activity 1",
    "dueDate": "2024-01-05T14:21:18.4874492+00:00",
    "completed": false
}
```
### FA 014. Activities - Отправка запроса методом GET с вводом "-1" в поле id  
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Activities/-1

**Ожидаемый результат:** В теле ответа содержится структура(словарь) с ключами "type", "title", "status", "traceId" и их значениями. Статус код ответа 404. 

**Заголовки запроса:** 
Host - <calculated when request is sent>
User-Agent - PostmanRuntime/7.36.0
Accept - */*
Accept-Encoding - gzip, deflate, br
Connection - keep-alive

**Тело запроса:** none

**Заголовки ответа:** 
Content-Type - application/json; charset=utf-8; v=1.0
Date - Fri, 05 Jan 2024 13:21:37 GMT
Server Kestrel
Transfer-Encoding - chunked
api-supported-versions - 1.0

**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.4",
    "title": "Not Found",
    "status": 404,
    "traceId": "00-7d344cba3600694a9c8d185b8dcaf8e7-07164736f226b146-00"
}
``` 
### FA 015. Activities - Отправка запроса методом GET с вводом  9999999999 в поле id   
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Activities/9999999999

**Ожидаемый результат:** В теле ответа содержится структура(словарь) с ключами "type", "title", "status", "traceId", "errors" и их значениями. Статус код ответа 400, в значении ключа "errors" описана ошибка: "The value '99999999999' is not valid." 

**Заголовки запроса:** 
Host - <calculated when request is sent>
User-Agent - PostmanRuntime/7.36.0
Accept - */*
Accept-Encoding - gzip, deflate, br
Connection - keep-alive

**Тело запроса:** none

**Заголовки ответа:** 
Content-Type - application/json; charset=utf-8;
Date - Fri, 05 Jan 2024 13:21:57 GMT
Server Kestrel
Transfer-Encoding - chunked

**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-2f55e466fa8ee94384bd7d0b30b8ffc7-b9ec96ad85c1c742-00",
    "errors": {
        "id": [
            "The value '9999999999' is not valid."
        ]
    }
}
```
### FA 016. Activities - Отправка запроса методом PUT с вводом "1" в поле id   
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Activities/:activity_id

**Ожидаемый результат:** В теле ответа содержится структура(словарь) с ключами "id", "title", "dueDate", "completed" и их значениями. Тип данных значений ключей соответствует требованиям: id - INT, title - string, dueDate - string, completed - boolean. Статус код ответа 200. 

**Заголовки запроса:** 
Content-Type application/json; v=1.0
Accept accept: text/plain; v=1.0

**Тело запроса:** 

```
{
  "id": 1,
  "title": "string",
  "dueDate": "2023-12-26T08:21:18.690Z",
  "completed": true
}
```

**Заголовки ответа:** 
Content-Type - application/json; charset=utf-8; v=1.0
Date - Fri, 05 Jan 2024 13:22:22 GMT
Server Kestrel
Transfer-Encoding - chunked
api-supported-versions - 1.0

**Тело ответа:** 

```
{
    "id": 1,
    "title": "string",
    "dueDate": "2023-12-26T08:21:18.69Z",
    "completed": true
}
```
### FA 017. Activities - Отправка запроса методом PUT с вводом отрицательного числа "-1" в поле id   
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Activities/-1 

**Ожидаемый результат:** В теле ответа содержится структура(словарь) с ключами "id", "title", "dueDate", "completed" и их значениями. Статус код ответа 400, в значении ключа "errors" описана ошибка: "The JSON value could not be converted to System.Int32"

**Заголовки запроса:** 
Content-Type application/json; v=1.0
Accept accept: text/plain; v=1.0

**Тело запроса:** 

```
{
  "id": "-1",
  "title": "string",
  "dueDate": "2023-12-26T08:21:18.690Z",
  "completed": true
}
```

**Заголовки ответа:** 
Content-Type - application/json; charset=utf-8; v=1.0
Date - Fri, 05 Jan 2024 13:22:42 GMT
Server Kestrel
Transfer-Encoding - chunked
api-supported-versions - 1.0

**Тело ответа:** 

```
{
    "id": -1,
    "title": "string",
    "dueDate": "2023-12-26T08:21:18.69Z",
    "completed": true
}
```
### FA 018. Activities - Отправка запроса методом PUT с вводом "0" в поле id  
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Activities/0

**Ожидаемый результат:** В теле ответа содержится структура(словарь) с ключами "id", "title", "dueDate", "completed" и их значениями. Статус код ответа 400, в значении ключа "errors" описана ошибка: "The JSON value could not be converted to System.Int32"

**Заголовки запроса:** 
Content-Type application/json; v=1.0
Accept accept: text/plain; v=1.0

**Тело запроса:** 

```
{
  "id": "0",
  "title": "string",
  "dueDate": "2023-12-26T08:21:18.690Z",
  "completed": true
}
```

**Заголовки ответа:** 
Content-Type - application/json; charset=utf-8; v=1.0
Date - Fri, 05 Jan 2024 13:23:03 GMT
Server Kestrel
Transfer-Encoding - chunked
api-supported-versions - 1.0

**Тело ответа:** 

```
{
    "id": 0,
    "title": "string",
    "dueDate": "2023-12-26T08:21:18.69Z",
    "completed": true
}
```
### FA 019. Activities - Отправка запроса методом PUT с вводом "1" в поле id и удалением JSON  
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Activities/1

**Ожидаемый результат:** В теле ответа содержится структура(словарь) с ключами "type", "title", "status", "traceId", "errors" и их значениями. Статус код ответа 400, в значении ключа "errors" описана ошибка: "A non-empty request body is required."

**Заголовки запроса:** 
Content-Type application/json; v=1.0
Accept accept: text/plain; v=1.0

**Тело запроса:** 

```

```

**Заголовки ответа:** 
Content-Type - application/json; charset=utf-8; v=1.0
Date - Fri, 05 Jan 2024 13:23:23 GMT
Server Kestrel
Transfer-Encoding - chunked

**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-115c1a5ddf7e5d408eb8a01bef5ffcda-5f9814e79c7d7f43-00",
    "errors": {
        "": [
            "A non-empty request body is required."
        ]
    }
}
```
### FA 020. Activities - Отправка запроса методом PUT с вводом "1" в поле id и удалением строки id в JSON  
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Activities/1 

**Ожидаемый результат:** В теле ответа содержится структура(словарь) с ключами "type", "title", "status", "traceId", "errors" и их значениями. Статус код ответа 400, в значении ключа "errors" описана ошибка: "The JSON value could not be converted to System.Int32".

**Заголовки запроса:** 
Content-Type application/json; v=1.0
Accept accept: text/plain; v=1.0

**Тело запроса:** 

```
{
  "title": "string",
  "dueDate": "2023-12-26T08:21:18.690Z",
  "completed": true
}
```

**Заголовки ответа:** 
Content-Type - application/json; charset=utf-8; 
Date - Fri, 05 Jan 2024 13:23:53 GMT
Server Kestrel
Transfer-Encoding - chunked

**Тело ответа:** 

```
{
    "id": 0,
    "title": "string",
    "dueDate": "2023-12-26T08:21:18.69Z",
    "completed": true
}
```
### FA 021. Activities - Отправка запроса методом PUT с вводом "1" в поле Completed и удалением строки id в JSON  
**URL:**  https://fakerestapi.azurewebsites.net//api/v1/Activities/1 

**Ожидаемый результат:** В теле ответа содержится структура(словарь) с ключами "type", "title", "status", "traceId", "errors" и их значениями. Статус код ответа 400, в значении ключа "errors" описана ошибка: "The JSON value could not be converted to System.Boolean."

**Заголовки запроса:** 
Content-Type  application/json; v=1.0
Accept accept: text/plain; v=1.0

**Тело запроса:** 

```
{
  "title": "string",
  "dueDate": "2023-12-26T08:21:18.690Z",
  "completed": 1
}
```

**Заголовки ответа:** 
Content-Type - application/json; charset=utf-8; 
Date - Fri, 05 Jan 2024 13:24:30 GMT
Server Kestrel
Transfer-Encoding - chunked

**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-b6814b27092d734990e02c8fd92b77c0-5d44cea04c16d34c-00",
    "errors": {
        "$.completed": [
            "The JSON value could not be converted to System.Boolean. Path: $.completed | LineNumber: 3 | BytePositionInLine: 16."
        ]
    }
}
```
### FA 022. Activities - Отправка запроса методом PUT с вводом "99999999999"   
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Activities/99999999999

**Ожидаемый результат:** В теле ответа содержится структура(словарь) с ключами "type", "title", "status", "traceId", "errors" и их значениями. Статус код ответа 400, в значениях ключа "errors" описаны ошибки: "The value '99999999999' is not valid."
**Заголовки запроса:** 
Content-Type application/json; v=1.0
Accept accept: text/plain; v=1.0

**Тело запроса:** 

```
{
  "id": "99999999999",
  "title": "string",
  "dueDate": "2023-12-26T08:21:18.690Z",
  "completed": true
}
```

**Заголовки ответа:** 
Content-Type - application/json; charset=utf-8; 
Date - Fri, 05 Jan 2024 14:49:29 GMT
Server Kestrel
Transfer-Encoding - chunked

**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-98e74d2aa4fea0408b135114d0ff4e24-91555a1127ecac45-00",
    "errors": {
        "id": [
            "The value '99999999999' is not valid."
        ],
        "$.id": [
            "The JSON value could not be converted to System.Int32. Path: $.id | LineNumber: 1 | BytePositionInLine: 21."
        ]
    }
}
```
### FA 023. Activities - Удаление методом DELETE валидного значения id - 1  
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Activities/1

**Ожидаемый результат:** 

**Заголовки запроса:** 

Content-Type - application/json; v=1.0
Accept accept: text/plain; v=1.0  

**Тело запроса:** none

**Заголовки ответа:** 
Content-Length - 0
Date - Fri, 05 Jan 2024 14:51:45 GMT
Server Kestrel
api-supported-versions - 1.0


**Тело ответа:** none

### FA 024. Activities - Удаление методом DELETE несуществующего значения id 58965  
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Activities/58965

**Ожидаемый результат:** Тело ответа отсутствует. Статус код ответа 404, в значении ключа "errors" описана ошибка: "The value '58965' is not valid."

**Заголовки запроса:** 
Content-Type application/json; v=1.0
Accept accept: text/plain; v=1.0

**Тело запроса:** none

**Заголовки ответа:** 
Content-Length - 0
Date - Fri, 05 Jan 2024 14:54:53 GMT
Server Kestrel
api-supported-versions - 1.0

**Тело ответа:** none

### FA 025. Activities - Отправка запроса методом DELETE с вводом  9999999999 в поле id   
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Activities/9999999999

**Ожидаемый результат:** 

**Заголовки запроса:** 
Content-Type application/json; v=1.0
Accept accept: text/plain; v=1.0

**Тело запроса:** none

**Заголовки ответа:** 
Content-Length - application/problem+json; charset=utf-8
Date - Fri, 05 Jan 2024 14:56:04 GMT
Server Kestrel
Transfer-Encoding - chunked

**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-0a1fb9b8543c4d44817b4859bc404a17-df36e1b71de79748-00",
    "errors": {
        "id": [
            "The value '9999999999' is not valid."
        ]
    }
}
```
### FA 026. Authors - Получить ответ на запрос методом GET   
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Authors

**Ожидаемый результат:** 

**Заголовки запроса:** 
Accept text/plain; v=1.0

**Тело запроса:** none

**Заголовки ответа:** 
Content-Type - application/json; charset=utf-8; v=1.0
Date - Fri, 05 Jan 2024 14:59:26 GMT
Server Kestrel
Transfer-Encoding - chunked
api-supported-versions - 1.0

**Тело ответа:** 

```
[
    {
        "id": 1,
        "idBook": 1,
        "firstName": "First Name 1",
        "lastName": "Last Name 1"
    },
    {
        "id": 2,
        "idBook": 1,
        "firstName": "First Name 2",
        "lastName": "Last Name 2"
    },
    {
        "id": 3,
        "idBook": 1,
        "firstName": "First Name 3",
        "lastName": "Last Name 3"
    }
]
```
### FA 027. Authors -  Отправка запроса методом POST с валидным Id - 50  
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Authors

**Ожидаемый результат:** В теле ответа содержится структура (словарь) с ключами "id", "idBook", "firstName", "lastName" и их значениями. Тип данных значений ключей соответствует требованиям: id - INT, idBook - INT, firstName - string, lastName - string. Статус код ответа 200.

**Заголовки запроса:** 
Accept text/plain; v=1.0
Content-Type text/json; v=1.0

**Тело запроса:** 

```
{
  "id": 50,
  "idBook": 0,
  "firstName": "string",
  "lastName": "string"
}
```

**Заголовки ответа:** 
Content-Type - application/json; charset=utf-8; v=1.0
Date - Fri, 05 Jan 2024 15:04:10 GMT
Server Kestrel
Transfer-Encoding - chunked
api-supported-versions - 1.0

**Тело ответа:** 

```
{
    "id": 50,
    "idBook": 0,
    "firstName": "string",
    "lastName": "string"
}
```
### FA 028. Authors - Отправка запроса методом POST с невалидным Id - 99999999999  
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Authors

**Ожидаемый результат:** В теле ответа содержится структура(словарь) с ключами "type", "title", "status", "traceId", "errors" и их значениями. Статус код ответа 400. В значении ключа "errors" описана ошибка: "The JSON value could not be converted to System.Int32"

**Заголовки запроса:** 
Accept: text/plain; v=1.0 
Content-Type: text/json; v=1.0 
User-Agent: PostmanRuntime/7.36.0 
Host: fakerestapi.azurewebsites.net 
Accept-Encoding: gzip, deflate, br 
Connection: keep-alive


**Тело запроса:** 

```
{
  "id": "99999999999",
  "idBook": "99999999999",
  "firstName": "string",
  "lastName": "string"
}
```

**Заголовки ответа:** 
Content-Type: application/problem+json; charset=utf-8 
Date: Sun, 07 Jan 2024 16:58:36 GMT 
Server: Kestrel 
Transfer-Encoding: chunked

**Тело ответа:** 
``` 
{    "type": "https://tools.ie tf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",    
    "status": 400,
    "traceId": "00-ae08864291709f4c98d8661cf78c92f9-1e851c2cc2e4964b-00",    
    "errors": {
        "$.id": [            "The JSON value could not be converted to System.Int32. Path: $.id | LineNumber: 1 | BytePositionInLine: 21."
        ]    }
}
```

### FA 029. Authors - Отправка запроса методом POST с пустым Id   
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Authors

**Ожидаемый результат:** В теле ответа содержится структура(словарь) с ключами "type", "title", "status", "traceId", "errors" и их значениями. Статус код ответа 400. В значении ключа "errors" описана ошибка: "',' is an invalid start of a value"

**Заголовки запроса:** 
Accept: text/plain; v=1.0 
Content-Type: application/json; v=1.0 
User-Agent: PostmanRuntime/7.36.0 
Host: fakerestapi.azurewebsites.net 
Accept-Encoding: gzip, deflate, br 
Connection: keep-alive

**Тело запроса:** 

```
{
  "id": ,
  "idBook": 0,
  "firstName": "string",
  "lastName": "string"
}
```

**Заголовки ответа:** 
Content-Type: application/problem+json; charset=utf-8 
Date: Sun, 07 Jan 2024 17:15:36 GMT 
Server: Kestrel 
Transfer-Encoding: chunked

**Тело ответа:** 
```
{    "type": "https://tools.ietf .org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",    
    "status": 400,
    "traceId": "00-0e6ea9c58078234681ec0f8250cf7e15-7a8ad6368234784b-00",    
    "errors": {
        "$.id": [            "',' is an invalid start of a value. Path: $.id | LineNumber: 1 | BytePositionInLine: 8."
        ]    }
}
```

### FA 030. Authors - Отправка запроса методом POST без JSON  
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Authors

**Ожидаемый результат:** В теле ответа содержится структура(словарь) с ключами "type", "title", "status", "traceId", "errors" и их значениями. Статус код ответа 400. В значении ключа "errors" описана ошибка: "A non-empty request body is required."

**Заголовки запроса:** 
Cache-Control: no-cache
Postman-Token: <calculated when request is sent>
Accept: text/plain; v=1.0
Content-Type: text/json; v=1.0
User-Agent: PostmanRuntime/7.36.0
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive

**Тело запроса:** 

```

```

**Заголовки ответа:** 
Content-Type - application/problem+json; charset=utf-8
Date - Fri, 05 Jan 2024 15:10:35 GMT
Server Kestrel
Transfer-Encoding - chunked


**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-4639895bdb2add4c9adaf71fd056eb5f-ea6419d8eacdc548-00",
    "errors": {
        "": [
            "A non-empty request body is required."
        ]
    }
}
```
### FA 031. Authors - Отправка запроса методом POST без строки id  
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Authors

**Ожидаемый результат:** В теле ответа содержится структура(словарь) с ключами "type", "title", "status", "traceId", "errors" и их значениями. Статус код ответа 400, в значении ключа "errors" описана ошибка: "The JSON value could not be converted to System.Int32".

**Заголовки запроса:** 
Accept text/plain; v=1.0
Content-Type text/json; v=1.0

**Тело запроса:** 

```
{

  "idBook": 0,
  "firstName": "string",
  "lastName": "string"
}
```

**Заголовки ответа:** 
Content-Type - application/json; charset=utf-8; v=1.0
Date - Fri, 05 Jan 2024 15:14:25 GMT
Server Kestrel
Transfer-Encoding - chunked
api-supported-versions - 1.0

**Тело ответа:** 

```
{
    "id": 0,
    "idBook": 0,
    "firstName": "string",
    "lastName": "string"
}
```
### FA 032. Authors - Отправка запроса методом POST с спецсимволом вместо id  
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Authors

**Ожидаемый результат:** В теле ответа содержится структура(словарь) с ключами "type", "title", "status", "traceId", "errors" и их значениями. Статус код ответа 400, в значении ключа "errors" описана ошибка: "'+' is invalid within a number, immediately after a sign character ('+' or '-'). Expected a digit ('0'-'9').

**Заголовки запроса:** 
Accept text/plain; v=1.0
Content-Type text/json; v=1.0

**Тело запроса:** 

```
{
  "id": 50,
  "idBook": 0,
  "firstName": "string",
  "lastName": "string"
}
```

**Заголовки ответа:** 
Content-Type - application/json; charset=utf-8; v=1.0
Date - Fri, 05 Jan 2024 15:16:06 GMT
Server Kestrel
Transfer-Encoding - chunked
api-supported-versions - 1.0

**Тело ответа:** 

```
{
    "id": 50,
    "idBook": 0,
    "firstName": "string",
    "lastName": "string"
}
```

### FA 033. Authors - Отправка запроса методом POST с вводом "a5" в поле id  
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Authors

**Ожидаемый результат:** В теле ответа содержится структура(словарь) с ключами "type", "title", "status", "traceId", "errors" и их значениями. Статус код ответа 400, в значении ключа "errors" описана ошибка: "'w' is an invalid start of a value.

**Заголовки запроса:** 
Accept text/plain; v=1.0
Content-Type text/json; v=1.0

**Тело запроса:** 

```
{
  "id": w8,
  "idBook": 0,
  "firstName": "string",
  "lastName": "string"
}
```

**Заголовки ответа:** 
Content-Type - application/problem+json; charset=utf-8
Date - Fri, 05 Jan 2024 15:16:57 GMT
Server Kestrel
Transfer-Encoding - chunked

**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-a7b42f1e15926b4dad29fa7e8ca9985e-75b82b278eb0114c-00",
    "errors": {
        "$.id": [
            "'w' is an invalid start of a value. Path: $.id | LineNumber: 1 | BytePositionInLine: 8."
        ]
    }
}
```
### FA 034. Authors - Отправка запроса методом POST с вводом "абв" в поле id  
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Authors

**Ожидаемый результат:** В теле ответа содержится структура(словарь) с ключами "type", "title", "status", "traceId", "errors" и их значениями. Статус код ответа 400, в значении ключа "errors" описана ошибка: "'0xD0' is an invalid start of a value.

**Заголовки запроса:** 
Accept text/plain; v=1.0
Content-Type text/json; v=1.0

**Тело запроса:** 

```
{
  "id": {{id_kir}},
  "idBook": 0,
  "firstName": "string",
  "lastName": "string"
}
```

**Заголовки ответа:** 
Content-Type - application/problem+json; charset=utf-8
Date - Fri, 05 Jan 2024 15:18:52 GMT
Server Kestrel
Transfer-Encoding - chunked

**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-d577db41203a094eab0c08f133f50cab-1852e24ea5553d46-00",
    "errors": {
        "$.id": [
            "'0xD0' is an invalid start of a value. Path: $.id | LineNumber: 1 | BytePositionInLine: 8."
        ]
    }
}
```
### FA 035. Authors -  Отправка запроса методом POST с вводом  отрицательного числа "-1" в поле id  
**URL:**  https://fakerestapi.azurewebsites.net//api/v1/Authors

**Ожидаемый результат:** В теле ответа содержится структура(словарь) с ключами "id", "title", "dueDate", "completed" и их значениями. Статус код ответа 400, в значении ключа "errors" описана ошибка: "The JSON value could not be converted to System.Int32". 

**Заголовки запроса:** 
Accept text/plain; v=1.0
Content-Type text/json; v=1.0

**Тело запроса:** 

```
{
  "id": {{id_neg}},
  "idBook": 0,
  "firstName": "string",
  "lastName": "string"
}
```

**Заголовки ответа:** 
Content-Type - application/json; charset=utf-8; v=1.0
Date - Fri, 05 Jan 2024 15:20:07 GMT
Server Kestrel
Transfer-Encoding - chunked
api-supported-versions - 1.0  

**Тело ответа:** 

```
{
    "id": -1,
    "idBook": 0,
    "firstName": "string",
    "lastName": "string"
}
```
### FA 036. Authors - Отправка запроса методом POST с валидным idBook 1  
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Authors

**Ожидаемый результат:** В теле ответа содержится структура (словарь) с ключами "id", "idBook", "firstName", "lastName" и их значениями. Тип данных значений ключей соответствует требованиям: id - INT, idBook - INT, firstName - string, lastName - string. Статус код ответа 201

**Заголовки запроса:** 
Accept text/plain; v=1.0
Content-Type text/json; v=1.0

**Тело запроса:** 

```
{
  "id": 0,
  "idBook": 1,
  "firstName": "string",
  "lastName": "string"
}
```

**Заголовки ответа:** 

Content-Type - application/json; charset=utf-8; v=1.0
Date - Fri, 05 Jan 2024 15:22:00 GMT
Server Kestrel
Transfer-Encoding - chunked
api-supported-versions - 1.0  

**Тело ответа:** 

```
{
    "id": 0,
    "idBook": 1,
    "firstName": "string",
    "lastName": "string"
}
```

### FA 037. Authors - Отправка запроса методом POST с невалидным IdBook 9999999999  
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Authors

**Ожидаемый результат:** В теле ответа содержится структура(словарь) с ключами "type", "title", "status", "traceId", "errors" и их значениями. Статус код ответа 400. В значении ключа "errors" описана ошибка: "The JSON value could not be converted to System.Int32.

**Заголовки запроса:** 
Accept text/plain; v=1.0
Content-Type text/json; v=1.0

**Тело запроса:** 

```
{
  "id": 0,
  "idBook": {{id_99999999999}},
  "firstName": "string",
  "lastName": "string"
}
```

**Заголовки ответа:** 
Content-Type - application/json; charset=utf-8
Date - Fri, 05 Jan 2024 15:23:06 GMT
Server Kestrel
Transfer-Encoding - chunked

**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-bcc6b0205e29834c9609448eb4717fa5-e0ce598c1b7c1f46-00",
    "errors": {
        "$.idBook": [
            "The JSON value could not be converted to System.Int32. Path: $.idBook | LineNumber: 2 | BytePositionInLine: 23."
        ]
    }
}
```
### FA 038. Authors - Отправка запроса методом POST с пустым idBook  
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Authors

**Ожидаемый результат:** В теле ответа содержится структура(словарь) с ключами "type", "title", "status", "traceId", "errors" и их значениями. Статус код ответа 400. В значении ключа "errors" описана ошибка: "',' is an invalid start of a value.

**Заголовки запроса:** 
Accept text/plain; v=1.0
Content-Type text/json; v=1.0
 
**Тело запроса:** 

```
{
  "id": 0,
  "idBook": 99999999999,
  "firstName": "string",
  "lastName": "string"
}
```

**Заголовки ответа:** 
Content-Type - application/json; charset=utf-8
Date - Fri, 05 Jan 2024 15:25:27 GMT
Server Kestrel
Transfer-Encoding - chunked

**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-7c9ab38ffce77147af7c0fc43c8c9b40-7342489e60b5a845-00",
    "errors": {
        "$.idBook": [
            "',' is an invalid start of a value. Path: $.idBook | LineNumber: 2 | BytePositionInLine: 12."
        ]
    }
}
```
### FA 039. Authors - Отправка запроса методом POST без строки idBook  
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Authors

**Ожидаемый результат:** В теле ответа содержится структура (словарь) с ключами "id", "idBook", "firstName", "lastName" и их значениями. Тип данных значений ключей соответствует требованиям: id - INT, idBook - INT, firstName - string, lastName - string. Статус код ответа 200.

**Заголовки запроса:** 
Cache-Control no-cache
Postman-Token <calculated when request is sent>
Content-Type application/json
Content-Length <calculated when request is sent>
Host <calculated when request is sent>
User-Agent PostmanRuntime/7.32.1
Accept */*
Accept-Encoding gzip, deflate, br
Connection keep-alive
Accept text/plain; v=1.0

**Тело запроса:** 

```
{
  "id": 0,

  "firstName": "string",
  "lastName": "string"
}
```

**Заголовки ответа:** 
Content-Length - 0
Connection - close
Date - Fri, 05 Jan 2024 15:26:30 GMT

**Тело ответа:** none

### FA 040. Authors - Отправка запроса методом POST с вводом  отрицательного числа "-1" в поле idBook  
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Authors

**Ожидаемый результат:** В теле ответа содержится структура (словарь) с ключами "id", "idBook", "firstName", "lastName" и их значениями. Тип данных значений ключей соответствует требованиям: id - INT, idBook - INT, firstName - string, lastName - string. Статус код ответа 200.

**Заголовки запроса:** 
Cache-Control no-cache
Postman-Token <calculated when request is sent>
Content-Type application/json
Content-Length <calculated when request is sent>
Host <calculated when request is sent>
User-Agent PostmanRuntime/7.32.1
Accept */*
Accept-Encoding gzip, deflate, br
Connection keep-alive
Accept text/plain; v=1.0

**Тело запроса:** 

```
{
  "id": 0,
  "idBook": {{id_neg}},
  "firstName": "string",
  "lastName": "string"
}
```

**Заголовки ответа:** 
Content-Length - 0
Connection - close
Date - Fri, 05 Jan 2024 15:28:42 GMT

**Тело ответа:** none

### FA 041. Authors - Отправка запроса методом GET с вводом "1" в поле id   
**URL:** https://fakerestapi.azurewebsites.net/api/v1/Authors/authors/books/:id

**Ожидаемый результат:** В теле ответа содержится структура (словарь) с ключами "id", "idBook", "firstName", "lastName" и их значениями. Тип данных значений ключей соответствует требованиям: id - INT, idBook - INT, firstName - string, lastName - string. Статус код ответа 200.

**Заголовки запроса:** 
Accept text/plain; v=1.0

**Тело запроса:**  none

**Заголовки ответа:** 
Content-Type - application/json; charset=utf-8; v=1.0
Date - Fri, 05 Jan 2024 15:29:37 GMT
Server Kestrel
Transfer-Encoding - chunked
api-supported-versions - 1.0 

**Тело ответа:** 

```
[
    {
        "id": 1,
        "idBook": 1,
        "firstName": "First Name 1",
        "lastName": "Last Name 1"
    },
    {
        "id": 2,
        "idBook": 1,
        "firstName": "First Name 2",
        "lastName": "Last Name 2"
    },
    {
        "id": 3,
        "idBook": 1,
        "firstName": "First Name 3",
        "lastName": "Last Name 3"
    }
]
```
### FA 042. Authors - Отправка запроса методом GET с вводом "-1" в поле id   
**URL:** https://fakerestapi.azurewebsites.net/api/v1/Authors/authors/books/:id

**Ожидаемый результат:** В теле ответа содержится структура(словарь) с ключами "type", "title", "status", "traceId", "errors" и их значениями. Статус код ответа 400. В значении ключа "errors" описана ошибка: "The JSON value could not be converted to System.Int32"

**Заголовки запроса:** 
Accept text/plain; v=1.0

**Тело запроса:** none


**Заголовки ответа:** 
Content-Type - application/json; charset=utf-8; v=1.0
Date - Fri, 05 Jan 2024 15:31:48 GMT
Server Kestrel
Transfer-Encoding - chunked
api-supported-versions - 1.0 

**Тело ответа:** 

```
[]
```
### FA 043. Authors -  Отправка запроса методом GET с вводом  9999999999 в поле id   
**URL:** https://fakerestapi.azurewebsites.net/api/v1/Authors/authors/books/:id

**Ожидаемый результат:** В теле ответа содержится структура(словарь) с ключами "type", "title", "status", "traceId", "errors" и их значениями. Статус код ответа 400. В значении ключа "errors" описана ошибка: "The value '99999999999' is not valid."

**Заголовки запроса:** 
Accept text/plain; v=1.0

**Тело запроса:**  none

**Заголовки ответа:** 

Content-Type - application/json; charset=utf-8
Date - Fri, 05 Jan 2024 15:34:48 GMT
Server Kestrel
Transfer-Encoding - chunked

**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-7908ab6aef8c3342b39fc367af700eca-2fff507dd44afa4d-00",
    "errors": {
        "idBook": [
            "The value '99999999999' is not valid."
        ]
    }
}
```
### FA 044. Authors - Отправка запроса методом GET с вводом "1" в поле id   
**URL:** https://fakerestapi.azurewebsites.net/api/v1/Authors/authors/books/:id

**Ожидаемый результат:** В теле ответа содержится структура (словарь) с ключами "id", "idBook", "firstName", "lastName" и их значениями. Тип данных значений ключей соответствует требованиям: id - INT, idBook - INT, firstName - string, lastName - string. Статус код ответа 200.

**Заголовки запроса:** 
Accept: text/plain; v=1.0
User-Agent: PostmanRuntime/7.36.0
Postman-Token: 76ec82aa-bc50-40a3-bf71-69c7b51d3492
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive

**Тело запроса:** none

**Заголовки ответа:** 
Content-Type: application/json; charset=utf-8; v=1.0
Date: Sun, 07 Jan 2024 20:52:33 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0

**Тело ответа:** 

```
[
    {
    "id":1,
    "idBook":1,
    "firstName":"First Name 1",
    "lastName":"Last Name 1"
    }
]
```
### FA 045. Authors - Отправка запроса методом GET с вводом "-1" в поле id   
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Authors/:id

**Ожидаемый результат:** В теле ответа содержится структура(словарь) с ключами "type", "title", "status", "traceId" и их значениями. Статус код ответа 404.

**Заголовки запроса:** 
Accept text/plain; v=1.0  

**Тело запроса:** none

**Заголовки ответа:** 
Content-Type - application/json; charset=utf-8; v=1.0
Date - Fri, 05 Jan 2024 15:38:33 GMT
Server Kestrel
Transfer-Encoding - chunked
api-supported-versions - 1.0 

**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.4",
    "title": "Not Found",
    "status": 404,
    "traceId": "00-9c9d485d947b88458e9dd68bfdaecbe3-8471bc5a94d39047-00"
}
```
### FA 046. Authors - Отправка запроса методом GET с вводом  "9999999999" в поле id   
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Authors/:id

**Ожидаемый результат:** В теле ответа содержится структура(словарь) с ключами "type", "title", "status", "traceId", "errors" и их значениями. Статус код ответа 400. В значении ключа "errors" описана ошибка: "The value '99999999999' is not valid."

**Заголовки запроса:** 
Accept text/plain; v=1.0

**Тело запроса:** none

**Заголовки ответа:** 
Content-Type - application/problem+json; charset=utf-8
Date - Fri, 05 Jan 2024 15:39:45 GMT
Server Kestrel
Transfer-Encoding - chunked

**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-58023f66c277394ea6ca17e3b87c0d4e-69c9febf2e0b4f45-00",
    "errors": {
        "id": [
            "The value '99999999999' is not valid."
        ]
    }
}
```
### FA 047. Authors - Отправка запроса методом GET с вводом  "0" в поле id   
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Authors/:id

**Ожидаемый результат:** В теле ответа содержится структура(словарь) с ключами "type", "title", "status", "traceId" и их значениями. Статус код ответа 404.

**Заголовки запроса:** 
Accept text/plain; v=1.0

**Тело запроса:** none

**Заголовки ответа:** 
Content-Type - application/problem+json; charset=utf-8; v=1.0
Date - Fri, 05 Jan 2024 15:41:15 GMT
Server Kestrel
Transfer-Encoding - chunked
api-supported-versions - 1.0

**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.4",
    "title": "Not Found",
    "status": 404,
    "traceId": "00-b37a6db48b546947b1b88a33bd8bdc93-6fd576b80bf8244a-00"
}
```
### FA 048. Authors - Отправка запроса методом PUT с вводом "1" в поле id   
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Authors/:id

**Ожидаемый результат:** В теле ответа содержится структура (словарь) с ключами "id", "idBook", "firstName", "lastName" и их значениями. Тип данных значений ключей соответствует требованиям: id - INT, idBook - INT, firstName - string, lastName - string. Статус код ответа 200.


**Заголовки запроса:** 
Accept text/plain; v=1.0
Content-Type application/json; v=1.0

**Тело запроса:** 

```
{
  "id": {{id_1}},
  "idBook": 0,
  "firstName": "string",
  "lastName": "string"
}
```

**Заголовки ответа:** 
Content-Type - application/problem+json; charset=utf-8; v=1.0
Date - Fri, 05 Jan 2024 15:43:32 GMT
Server Kestrel
Transfer-Encoding - chunked
api-supported-versions - 1.0

**Тело ответа:** 

```
{
    "id": 1,
    "idBook": 0,
    "firstName": "string",
    "lastName": "string"
}
```
### FA 049. Authors - Отправка запроса методом PUT с вводом отрицательного числа "-1" в поле id   
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Authors/:id

**Ожидаемый результат:** В теле ответа содержится структура(словарь) с ключами "id", "title", "dueDate", "completed" и их значениями. Статус код ответа 400, в значении ключа "errors" описана ошибка: "The JSON value could not be converted to System.Int32".

**Заголовки запроса:** 
Accept text/plain; v=1.0
Content-Type  application/json; v=1.0

**Тело запроса:** 

```
{
  "id": {{id_neg}},
  "idBook": 0,
  "firstName": "string",
  "lastName": "string"
}
```

**Заголовки ответа:** 
Content-Type - application/problem+json; charset=utf-8; v=1.0
Date - Fri, 05 Jan 2024 15:44:47 GMT
Server Kestrel
Transfer-Encoding - chunked
api-supported-versions - 1.0

**Тело ответа:** 

```
{
    "id": -1,
    "idBook": 0,
    "firstName": "string",
    "lastName": "string"
}
```
### FA 050. Authors - Отправка запроса методом PUT с вводом "0" в поле id   
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Authors/:id

**Ожидаемый результат:** В теле ответа содержится структура(словарь) с ключами "id", "title", "dueDate", "completed" и их значениями. Статус код ответа 400, в значении ключа "errors" описана ошибка: "The JSON value could not be converted to System.Int32"

**Заголовки запроса:** 
Accept text/plain; v=1.0
Content-Type application/json; v=1.0

**Тело запроса:** 

```
{
  "id": {{id_0}},
  "idBook": 0,
  "firstName": "string",
  "lastName": "string"
}
```

**Заголовки ответа:** 
Content-Type - application/problem+json; charset=utf-8; v=1.0
Date - Fri, 05 Jan 2024 15:45:54 GMT
Server Kestrel
Transfer-Encoding - chunked
api-supported-versions - 1.0

**Тело ответа:** 

```
{
    "id": 0,
    "idBook": 0,
    "firstName": "string",
    "lastName": "string"
}
```
### FA 051. Authors - Отправка запроса методом PUT с вводом "1" в поле id и удалением JSON  
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Authors/:id

**Ожидаемый результат:** В теле ответа содержится структура(словарь) с ключами "type", "title", "status", "traceId", "errors" и их значениями. Статус код ответа 400. В значении ключа "errors" описана ошибка: "A non-empty request body is required."

**Заголовки запроса:** 
Accept text/plain; v=1.0
Content-Type application/json; v=1.0

**Тело запроса:** 

```

```

**Заголовки ответа:** 
Content-Type - application/problem+json; charset=utf-8
Date - Fri, 05 Jan 2024 15:46:54 GMT
Server Kestrel
Transfer-Encoding - chunked

**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-e5c56cd300e97845aa75f943f2f71a9f-9be826d303efc347-00",
    "errors": {
        "": [
            "A non-empty request body is required."
        ]
    }
}
```
### FA 052. Authors - Отправка запроса методом PUT с вводом "1" в поле id и удалением строки id в JSON  
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Authors/1

**Ожидаемый результат:** В теле ответа содержится структура(словарь) с ключами "type", "title", "status", "traceId", "errors" и их значениями. Статус код ответа 400. В значении ключа "errors" описана ошибка: "A non-empty request body is required."

**Заголовки запроса:** 
Cache-Control no-cache
Postman-Token <calculated when request is sent>
Content-Type application/json
Content-Length <calculated when request is sent>
Host <calculated when request is sent>
User-Agent PostmanRuntime/7.32.1
Accept */*
Accept-Encoding gzip, deflate, br
Connection keep-alive
Accept text/plain; v=1.0
Content-Type application/json; v=1.0

**Тело запроса:** 

```
{

  "idBook": 1,
  "firstName": "string",
  "lastName": "string"
}
```

**Заголовки ответа:** 
Content-Type - application/json; charset=utf-8; v=1.0
Date - Fri, 05 Jan 2024 15:53:07 GMT
Server Kestrel
Transfer-Encoding - chunked
api-supported-versions 1.0

**Тело ответа:** 

```
{
    "id": 0,
    "idBook": 1,
    "firstName": "string",
    "lastName": "string"
}
```
### FA 053. Authors - Отправка запроса методом PUT с вводом "1" в поле id и удалением строки idBook в JSON  
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Authors/:id

**Ожидаемый результат:** В теле ответа содержится структура(словарь) с ключами "type", "title", "status", "traceId", "errors" и их значениями. Статус код ответа 400. В значении ключа "errors" описана ошибка: "A non-empty request body is required."

**Заголовки запроса:** 
Cache-Control no-cache
Postman-Token <calculated when request is sent>
Content-Type application/json
Content-Length <calculated when request is sent>
Host <calculated when request is sent>
User-Agent PostmanRuntime/7.32.1
Accept */*
Accept-Encoding gzip, deflate, br
Connection keep-alive
Accept text/plain; v=1.0
Content-Type text/json; v=1.0

**Тело запроса:** 

```
{
  "id": 0,

  "firstName": "string",
  "lastName": "string"
}
```

**Заголовки ответа:** 
Content-Length - 0
Connection - Close
Date - Fri, 05 Jan 2024 15:55:46 GMT

**Тело ответа:** none

### FA 054. Authors - Отправка запроса методом PUT с вводом "9999999999"   
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Authors/1

**Ожидаемый результат:** В теле ответа содержится структура(словарь) с ключами "type", "title", "status", "traceId", "errors" и их значениями. Статус код ответа 400. В значении ключа "errors" описана ошибка: "The value '99999999999' is not valid." 

**Заголовки запроса:** 
Cache-Control no-cache
Postman-Token <calculated when request is sent>
Content-Type application/json
Content-Length <calculated when request is sent>
Host <calculated when request is sent>
User-Agent PostmanRuntime/7.32.1
Accept */*
Accept-Encoding gzip, deflate, br
Connection keep-alive
Accept text/plain; v=1.0
Content-Type text/json; v=1.0

**Тело запроса:** 

```
{
  "id": {{id_99999999999}},
  "idBook": 0,
  "firstName": "string",
  "lastName": "string"
}
```

**Заголовки ответа:** 
Content-Type - application/json; charset=utf-8
Date - Fri, 05 Jan 2024 15:57:33 GMT
Server Kestrel
Transfer-Encoding - chunked

**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-feef10bc296db845a123230802834216-d970575a18d3e144-00",
    "errors": {
        "id": [
            "The value '99999999999' is not valid."
        ],
        "$.id": [
            "The JSON value could not be converted to System.Int32. Path: $.id | LineNumber: 1 | BytePositionInLine: 19."
        ]
    }
}
```
### FA 055. Authors - Удаление методом DELETE валидного значения id - 1  
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Authors/1

**Ожидаемый результат:** Тело ответа отсутствует. Статус код ответа 200.

**Заголовки запроса:** 
Cache-Control no-cache
Postman-Token <calculated when request is sent>
Host <calculated when request is sent>
User-Agent PostmanRuntime/7.32.1
Accept */* 
Accept-Encoding gzip, deflate, br
Connection keep-alive

**Тело запроса:** none

**Заголовки ответа:** 
Content-Length - 0
Date - Fri, 05 Jan 2024 15:58:52 GMT
Server Kestrel
api-supported-versions 1.0

**Тело ответа:** none

### FA 056. Authors - Удаление методом DELETE несуществующего значения id 58965   
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Authors/58965 

**Ожидаемый результат:** Тело ответа отсутствует. Статус код ответа 404, в значении ключа "errors" описана ошибка: "The value '58965' is not valid."
 

**Заголовки запроса:** 
Cache-Control no-cache
Postman-Token <calculated when request is sent>
Host <calculated when request is sent>
User-Agent PostmanRuntime/7.32.1
Accept */* 
Accept-Encoding gzip, deflate, br
Connection keep-alive

**Тело запроса:**  none

**Заголовки ответа:** 
Content-Length - 0
Date - Fri, 05 Jan 2024 16:00:48 GMT
Server Kestrel
api-supported-versions 1.0

**Тело ответа:**  none

### FA 057. Authors - Отправка запроса методом DELETE с вводом  9999999999 в поле id   
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Authors/:id

**Ожидаемый результат:** Тело ответа отсутствует. Статус код ответа 400, в значении ключа "errors" описана ошибка: "The value '9999999999' is not valid."

**Заголовки запроса:** 
Cache-Control no-cache
Postman-Token <calculated when request is sent>
Host <calculated when request is sent>
User-Agent PostmanRuntime/7.32.1
Accept */* 
Accept-Encoding gzip, deflate, br
Connection keep-alive

**Тело запроса:** none

**Заголовки ответа:** 

Content-Length - 0
Date - Fri, 05 Jan 2024 16:02:28 GMT
Server Kestrel
api-supported-versions 1.0
**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-41a3533511ccc441b05c0bba39552cb7-8680d9106de04845-00",
    "errors": {
        "id": [
            "The value '99999999999' is not valid."
        ]
    }
}
```
### FA 058. Books - Получить ответ на запрос методом GET   
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Books

**Ожидаемый результат:** В теле ответа содержится массив структур с ключами "id", "title", "description", "pageCount", "excerpt" и "publishDate" и их значениями. Тип данных значений ключей соответствует требованиям: id - INT, title - string, description - string, pageCount - INT, excerpt - string, publishDate - string. Статус код ответа 200.

**Заголовки запроса:** 

User-Agent PostmanRuntime/7.32.1
Accept */*
Accept-Encoding gzip, deflate, br
Connection keep-alive
Accept  text/plain; v=1.0

**Тело запроса:** none

**Заголовки ответа:** 
Content-Type - application/json; charset=utf-8; v=1.0
Date - Fri, 05 Jan 2024 16:49:02 GMT
Server Kestrel
Transfer-Encoding - chunked
api-supported-versions 1.0

**Тело ответа:** 

```
[
    {
        "id": 1,
        "title": "Book 1",
        "description": "Lorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\n",
        "pageCount": 100,
        "excerpt": "Lorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\nLorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\nLorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\nLorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\nLorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\n",
        "publishDate": "2024-01-04T16:49:03.8563989+00:00"
    }
]
```
### FA 059. Books - Отправка запроса методом POST с валидным Id - 50  
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Books

**Ожидаемый результат:**  В теле ответа содержится структура(словарь) с ключами "id", "title", "description", "pageCount", "excerpt" и "publishDate" и их значениями. Тип данных значений ключей соответствует требованиям: id - INT, title - string, description - string, pageCount - INT, excerpt - string, publishDate - string. Статус код ответа 200.

**Заголовки запроса:** 
Accept -H "accept: */*

**Тело запроса:** 

```
{
  "id": {{id_50}},
  "title": "string",
  "description": "string",
  "pageCount": {{id_50}},
  "excerpt": "string",
  "publishDate": "2023-12-26T08:30:50.626Z"
}
```

**Заголовки ответа:** 

Content-Type - application/json; charset=utf-8; v=1.0
Date - Fri, 05 Jan 2024 16:53:20 GMT
Server Kestrel
Transfer-Encoding - chunked
api-supported-versions 1.0
**Тело ответа:** 

```
{
    "id": 50,
    "title": "string",
    "description": "string",
    "pageCount": 50,
    "excerpt": "string",
    "publishDate": "2023-12-26T08:30:50.626Z"
}
```
### FA 060. Books - Отправка запроса методом POST с невалидным Id - 99999999999  
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Books/

**Ожидаемый результат:** Система не сможет обработать невалидный id и вернёт ошибку с кодом статуса 400 Bad Request, сообщив о проблеме с id.

**Заголовки запроса:** 

Content-Length <calculated when request is sent>
Host <calculated when request is sent>
User-Agent PostmanRuntime/7.32.1
Accept */*
Accept-Encoding gzip, deflate, br
Connection keep-alive
Content-Type application/json; v=1.0

**Тело запроса:** 

```
{
  "id":  "{{id_99999999999}}",
  "title": "Название книги",
  "description": "Описание книги",
  "pageCount": "50",
  "excerpt": "Отрывок из книги",
  "publishDate": "2023-12-25T12:19:52.130Z"
}
```

**Заголовки ответа:** 
Content-Type - application/problem+json; charset=utf-8
Date - FFri, 05 Jan 2024 17:02:30 GMT
Server - Kestrel
Transfer-Encoding - chunked

**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-00976306a00fe6439a689397136236ec-f45153912030f64a-00",
    "errors": {
        "$.id": [
            "The JSON value could not be converted to System.Int32. Path: $.id | LineNumber: 1 | BytePositionInLine: 22."
        ]
    }
}
```
### FA 061. Books - Отправка запроса методом POST с пустым Id   
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Books/

**Ожидаемый результат:** Поскольку id является обязательным и не может быть пустым, система вернет ошибку валидации с кодом статуса 400 Bad Request, указав на отсутствие значения id.

**Заголовки запроса:** 
Accept */*
Accept-Encoding gzip, deflate, br
Content-Type application/json; v=1.0
Content-Length <calculated when request is sent>
Host <calculated when request is sent>
User-Agent PostmanRuntime/7.32.1
Connection keep-alive
Accept text/json; v=1.0

**Тело запроса:** 

```
{
  "id":,
  "title": "Название книги",
  "description": "Описание книги",
  "pageCount": "0",
  "excerpt": "Отрывок из книги",
  "publishDate": "2023-12-25T12:19:52.130Z"
}
```

**Заголовки ответа:** 

Content-Type - application/problem+json; charset=utf-8
Date - Fri, 05 Jan 2024 17:13:43 GMT
Server Kestrel
Transfer-Encoding - chunked

**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-e4a5729606b10a44961bdc71393068d4-cf2511b087723c43-00",
    "errors": {
        "$.id": [
            "',' is an invalid start of a value. Path: $.id | LineNumber: 1 | BytePositionInLine: 7."
        ]
    }
}
```
### FA 062. Books - Отправка запроса методом POST без JSON  
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Books/

**Ожидаемый результат:** 

**Заголовки запроса:** 

Content-Length 0
Host <calculated when request is sent>
User-Agent PostmanRuntime/7.32.1
Accept */*
Accept-Encoding gzip, deflate, br
Connection keep-alive
Accept text/json; v=1.0
Content-Type application/json; v=1.0
**Тело запроса:** 

```

```

**Заголовки ответа:** 
Content-Type - application/problem+json; charset=utf-8
Date - Fri, 05 Jan 2024 17:18:30 GMT
Server Kestrel
Transfer-Encoding - chunked

**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-1b9e4653b7066d498119368b488d630e-292407f82d64204d-00",
    "errors": {
        "": [
            "A non-empty request body is required."
        ]
    }
}
```
### FA 063. Books - Отправка запроса методом POST без строки id  
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Books/

**Ожидаемый результат:** Сервер ожидает тело запроса в формате JSON и, не обнаружив его, вернет ошибку с кодом статуса 400 Bad Request, сообщив о необходимости передать тело запроса.

**Заголовки запроса:** 

Content-Type - application/json; v=1.0
Content-Length <calculated when request is sent>
Host <calculated when request is sent>
User-Agent PostmanRuntime/7.32.1
Accept */*
Accept-Encoding gzip, deflate, br
Connection keep-alive

**Тело запроса:** 

```
{
  "title": "Название книги",
  "description": "Описание книги",
  "pageCount": "0",
  "excerpt": "Отрывок из книги",
  "publishDate": "2023-12-25T12:19:52.130Z"
}
```

**Заголовки ответа:** 
Content-Type - application/json; charset=utf-8; v=1.0
Date - Fri, 05 Jan 2024 17:23:11 GMT
Server Kestrel
Transfer-Encoding - chunked
api-supported-versions - 1.0

**Тело ответа:** 

```
{
    "id": 0,
    "title": "Название книги",
    "description": "Описание книги",
    "pageCount": 0,
    "excerpt": "Отрывок из книги",
    "publishDate": "2023-12-25T12:19:52.13Z"
}
```
### FA 064. Books - Отправка запроса методом POST с спецсимволом вместо id 

**URL:** https://fakerestapi.azurewebsites.net//api/v1/Books/

**Ожидаемый результат:**  Система не сможет обработать id с спецсимволом и вернёт ошибку с кодом статуса 400 Bad Request, сообщив о проблеме с id.

**Заголовки запроса:** 

Content-Type application/json
Content-Length <calculated when request is sent>
Host <calculated when request is sent>
User-Agent PostmanRuntime/7.32.1
Accept */*
Accept-Encoding gzip, deflate, br
Connection keep-alive

**Тело запроса:** 

```
{
  "id": {{id_symbol}},
  "title": "string",
  "description": "string",
  "pageCount": 0,
  "excerpt": "string",
  "publishDate": "2023-12-25T12:19:52.130Z"
}
  
```

**Заголовки ответа:** 
Content-Type - application/json; charset=utf-8
Date - Sat, 06 Jan 2024 09:13:51 GMT
Server Kestrel
Transfer-Encoding - chunked

**Тело ответа:** 

```
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-8fd7cd992d2e2542a3a38f640092d655-b27b434597e6d245-00",
    "errors": {
        "$": 
        [
            "'' is an invalid start of a property name. Expected a '\"'. Path: $ | LineNumber: 0 | BytePositionInLine: 1."
        ]
}
```

### FA 065. Books - Отправка запроса методом POST с вводом "w8" в поле id  
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Books/

**Ожидаемый результат:** Система не сможет интерпретировать строковое значение "w8" как целочисленный id и вернёт ошибку с кодом статуса 400 Bad Request, сообщив о некорректном формате поля id.

**Заголовки запроса:** 
Content-Type application/json
Content-Length <calculated when request is sent>
Host <calculated when request is sent>
User-Agent PostmanRuntime/7.32.1
Accept */*
Accept-Encoding gzip, deflate, br
Connection keep-alive
Accept application/json; v=1.0
Accept text/json; v=1.0

**Тело запроса:** 

```
{
  "id":  {{id_w8}},
  "title": "string",
  "description": "string",
  "pageCount": 0,
  "excerpt": "string",
  "publishDate": "2023-12-25T12:19:52.130Z"
}
```

**Заголовки ответа:** 
Content-Type - application/json; charset=utf-8
Date - Sat, 06 Jan 2024 09:13:51 GMT
Server Kestrel
Transfer-Encoding - chunked

**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-c59388b260f69b439918918a6fd94730-953089bf70228642-00",
    "errors": {
        "$.id": [
            "'w' is an invalid start of a value. Path: $.id | LineNumber: 1 | BytePositionInLine: 8."
        ]
    }
}
```
### FA 066. Books -  Отправка запроса методом POST с вводом "аб" в поле id   
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Books/

**Ожидаемый результат:**  Система не сможет интерпретировать кириллические символы "аб" как целочисленный id и вернёт ошибку с кодом статуса 400 Bad Request, указав на неправильный формат поля id.

**Заголовки запроса:** 

Content-Type application/json
Content-Length <calculated when request is sent>
Host <calculated when request is sent>
User-Agent PostmanRuntime/7.32.1
Accept */*
Accept-Encoding gzip, deflate, br
Connection keep-alive


**Тело запроса:** 

```
{
  "id": {{id_kir}},
  "title": "Название книги",
  "description": "Описание книги",
  "pageCount": 50,
  "excerpt": "Отрывок из книги",
  "publishDate": "2023-12-25T12:19:52.130Z"
}
```

**Заголовки ответа:** 
Content-Type - application/json; charset=utf-8
Date - Sat, 06 Jan 2024 09:29:13 GMT
Server Kestrel
Transfer-Encoding - chunked

**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-835e017f66acbf43b8ae0832ffbaa619-5872b55cb87b614b-00",
    "errors": {
        "$.id": [
            "'0xD0' is an invalid start of a value. Path: $.id | LineNumber: 1 | BytePositionInLine: 8."
        ]
    }
}
```

### FA 067. Books - Отправка запроса методом POST с вводом  отрицательного числа "-1" в поле id  
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Books/

**Ожидаемый результат:** В теле ответа содержится структура(словарь) с ключами "id", "title", "description", "pageCount", "excerpt" и "publishDate" и их значениями. Тип данных значений ключей соответствует требованиям: id - INT, title - string, description - string, pageCount - INT, excerpt - string, publishDate - string. Статус код ответа 200.

**Заголовки запроса:** 
Accept application/json; v=1.0

**Тело запроса:** 

```
{
  "id": {{id_neg}},
  "title": "string",
  "description": "string",
  "pageCount": 50,
  "excerpt": "string",
  "publishDate": "2023-12-25T12:19:52.130Z"
}
```

**Заголовки ответа:** 
Content-Type - application/json; charset=utf-8; v=1.0
Date - Sat, 06 Jan 2024 09:3:59 GMT
Server Kestrel
Transfer-Encoding - chunked
api-supported-versions - 1.0

**Тело ответа:** 

```
{
    "id": -1,
    "title": "string",
    "description": "string",
    "pageCount": 0,
    "excerpt": "string",
    "publishDate": "2024-01-06T09:16:48.168Z"
}
```
### FA 068. Books - Отправка запроса методом POST с вводом "1" в поле id с удалением строки title 

**URL:** https://fakerestapi.azurewebsites.net//api/v1/Books/

**Ожидаемый результат:**  Система обрабатывает запрос и создает запись даже без поля title, возвращая успешный ответ с кодом статуса 200 OK и результатом содержащим null вместо title, поле title не является обязательным.


**Заголовки запроса:** 
Content-Type application/json
Content-Length <calculated when request is sent>
Host <calculated when request is sent>
User-Agent PostmanRuntime/7.32.1
Accept */*
Accept-Encoding gzip, deflate, br
Connection keep-alive
Accept application/json; v=1.0
Accept text/json; v=1.0

**Тело запроса:** 

```
{
  "id": {{id_1}},
  "description": "string",
  "pageCount": 0,
  "excerpt": "string",
  "publishDate": "2023-12-25T12:19:52.130Z"
}
```

**Заголовки ответа:** 
Content-Type - application/json; charset=utf-8; v=1.0
Date - Sat, 06 Jan 2024 16:35:41 GMT
Server Kestrel
Transfer-Encoding - chunked
api-supported-versions - 1.0

**Тело ответа:** 

```
{
    "id": 1,
    "title": null,
    "description": "string",
    "pageCount": 0,
    "excerpt": "string",
    "publishDate": "2023-12-25T12:19:52.13Z"
}
```

### FA 069. Books - Отправка запроса методом POST с вводом "1" в поле id с удалением строки discription  
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Books/

**Ожидаемый результат:** 

**Заголовки запроса:** 

Content-Type application/json
Content-Length <calculated when request is sent>
Host <calculated when request is sent>
User-Agent PostmanRuntime/7.32.1
Accept */*
Accept-Encoding gzip, deflate, br
Connection keep-alive
Accept application/json; v=1.0


**Тело запроса:** 

```
{
  "id": {{id_1}},
   "title": "string",
  "pageCount": 0,
  "excerpt": "string",
  "publishDate": "2023-12-25T12:19:52.130Z"
}
```

**Заголовки ответа:** 

Content-Type - application/json; charset=utf-8; v=1.0
Date - Sat, 06 Jan 2024 16:39:48 GMT
Server Kestrel
Transfer-Encoding - chunked
api-supported-versions - 1.0  

**Тело ответа:** 

```
{
    "id": 1,
    "title": "string",
    "description": null,
    "pageCount": 0,
    "excerpt": "string",
    "publishDate": "2023-12-25T12:19:52.13Z"
}
```
### FA 070. Books - Отправка запроса методом GET с вводом "1" в поле id   
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Books/1

**Ожидаемый результат:** Система возвращает информацию о книге с id равным 1. Статус ответа 200 OK, и тело ответа содержит информацию о книге, соответствующую запрошенному id.

**Заголовки запроса:** 
Accept accept: text/plain; v=1.0

**Тело запроса:** none

**Заголовки ответа:** 

Content-Type - application/json; charset=utf-8; v=1.0
Date - Sat, 06 Jan 2024 16:42:30 GMT
Server Kestrel
Transfer-Encoding - chunked
api-supported-versions - 1.0   

**Тело ответа:** 

```
{
    "id": 1,
    "title": "Book 1",
    "description": "Lorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\n",
    "pageCount": 100,
    "excerpt": "Lorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\nLorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\nLorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\nLorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\nLorem lorem lorem. Lorem lorem lorem. Lorem lorem lorem.\n",
    "publishDate": "2024-01-05T16:42:31.0953176+00:00"
}
```
### FA 071. Books - Отправка запроса методом GET с вводом "-1" в поле id   
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Books/-1

**Ожидаемый результат:**  Статус код ответа 404. В теле ответа содержится структура(словарь) с ключами "type", "title", "status", "traceId". 

**Заголовки запроса:** 
Accept
accept: text/plain; v=1.0

**Тело запроса:** none

**Заголовки ответа:** 
Content-Type - application/json; charset=utf-8; v=1.0
Date - Sat, 06 Jan 2024 16:46:45 GMT
Server Kestrel
Transfer-Encoding - chunked
api-supported-versions - 1.0 

**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.4",
    "title": "Not Found",
    "status": 404,
    "traceId": "00-c938218a85dfb340bcb0b4808a9fd245-3abbc8b4ae5bc440-00"
}
```
### FA 072. Books - Отправка запроса методом GET с вводом  9999999999 в поле id 
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Books/9999999999

**Ожидаемый результат:** Статус код ответа 400. В теле ответа содержится структура(словарь) с ключами "type", "title", "status", "traceId", "errors" и в нём описана ошибка "The value '9999999999' is not valid."

**Заголовки запроса:** 
Accept accept: text/plain; v=1.0

**Тело запроса:** none

**Заголовки ответа:** 
Content-Type - application/problem+json; charset=utf-8
Date - Sat, 06 Jan 2024 16:49:08 GMT
Server Kestrel
Transfer-Encoding - chunked

**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-f85a38fcc29da84b91362f84fcf94cc1-c20648fb497d3b43-00",
    "errors": {
        "id": [
            "The value '9999999999' is not valid."
        ]
    }
}
``` 
### FA 073. Books - Отправка запроса методом PUT с вводом "1" в поле id   
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Books/1

**Ожидаемый результат:** Статус код ответа 200. В теле ответа отражена обновлённая информация о книге, соответствующая отправленным данным в теле запроса. 

**Заголовки запроса:** 

Accept */*

**Тело запроса:** 

```
{
  "id": {{id_1}},
  "title": "string",
  "description": "string",
  "pageCount": 0,
  "excerpt": "string",
  "publishDate": "2023-12-25T13:55:00.207Z"
}
```

**Заголовки ответа:** 

Content-Type - application/json; charset=utf-8; v=1.0
Date - Sat, 06 Jan 2024 16:53:46 GMT
Server Kestrel
Transfer-Encoding - chunked
api-supported-versions - 1.0   

**Тело ответа:** 

```
{
    "id": 1,
    "title": "string",
    "description": "string",
    "pageCount": 0,
    "excerpt": "string",
    "publishDate": "2023-12-25T13:55:00.207Z"
}
```
### FA 074. Books - Отправка запроса методом PUT с вводом отрицательного числа "-1" в поле id  
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Books/-1

**Ожидаемый результат:** Статус код ответа 400. В теле ответа содержится ошибка, указывающая на отсутствие объекта с таким id.

**Заголовки запроса:** 
Content-Type application/json
Content-Length <calculated when request is sent>
Host <calculated when request is sent>
User-Agent PostmanRuntime/7.32.1
Accept */*
Accept-Encoding gzip, deflate, br
Connection keep-alive

**Тело запроса:** 

```
{
  "id": {{id_neg}},
  "title": "string",
  "description": "string",
  "pageCount": 0,
  "excerpt": "string",
  "publishDate": "2023-12-25T13:55:00.207Z"
}
```

**Заголовки ответа:** 
Content-Type - application/json; charset=utf-8; v=1.0
Date - Sat, 06 Jan 2024 17:11:17 GMT
Server Kestrel
Transfer-Encoding - chunked
api-supported-versions - 1.0  

**Тело ответа:** 

```
{
    "id": -1,
    "title": "string",
    "description": "string",
    "pageCount": 0,
    "excerpt": "string",
    "publishDate": "2023-12-25T13:55:00.207Z"
}
``` 
### FA 075. Books - Отправка запроса методом PUT с вводом "0" в поле id   
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Books/0

**Ожидаемый результат:** Статус код ответа 400.  В теле ответа содержится ошибка, указывающая на отсутствие объекта с таким id.

**Заголовки запроса:** 

Content-Type application/json
Content-Length <calculated when request is sent>
Host <calculated when request is sent>
User-Agent PostmanRuntime/7.32.1
Accept */*
Accept-Encoding gzip, deflate, br
Connection keep-alive

**Тело запроса:** 

```
{
  "id": {{id_0}},
  "title": "string",
  "description": "string",
  "pageCount": 0,
  "excerpt": "string",
  "publishDate": "2023-12-25T13:55:00.207Z"
}
```

**Заголовки ответа:** 
Content-Type - application/json; charset=utf-8; v=1.0
Date - Sat, 06 Jan 2024 17:14:01 GMT
Server Kestrel
Transfer-Encoding - chunked
api-supported-versions - 1.0 

**Тело ответа:** 

```
{
    "id": 0,
    "title": "string",
    "description": "string",
    "pageCount": 0,
    "excerpt": "string",
    "publishDate": "2023-12-25T13:55:00.207Z"
}
```
### FA 076. Books - Отправка запроса методом PUT с вводом "1" в поле id и удалением JSON  
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Books/1

**Ожидаемый результат:** Статус код ответа 400. В теле ответа содержится ошибка, указывающая на необходимость предоставления тела запроса для операции PUT.

**Заголовки запроса:** 

Content-Type application/json; v=1.0
Content-Length 0
Host <calculated when request is sent>
User-Agent PostmanRuntime/7.32.1
Accept */*
Accept-Encoding gzip, deflate, br
Connection keep-alive


**Тело запроса:** 

```

```

**Заголовки ответа:** 

Content-Type - application/json; charset=utf-8
Date - Sat, 06 Jan 2024 17:20:19 GMT
Server Kestrel
Transfer-Encoding - chunked

**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-b4ac4ac4bcff154e84f0b068493cf83e-ac4a48d48ef4c240-00",
    "errors": {
        "": [
            "A non-empty request body is required."
        ]
    }
}
```
### FA 077. Books - Отправка запроса методом PUT с вводом "1" в поле id и удалением строки id в JSON  
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Books/1

**Ожидаемый результат:** Статус код ответа 400 с соответствующим сообщением об отсутствии поля id в запросе.

**Заголовки запроса:** 
Accept: */*
Content-Type: application/json
User-Agent: PostmanRuntime/7.36.0
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive

**Тело запроса:** 

```
{

  "title": "string",
  "description": "string",
  "pageCount": 0,
  "excerpt": "string",
  "publishDate": "2023-12-25T13:55:00.207Z"
}
```

**Заголовки ответа:** 
Content-Type: application/json; charset=utf-8; v=1.0
Date: Sun, 07 Jan 2024 13:22:50 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0

**Тело ответа:** 

```
{"id":0,"title":"string","description":"string","pageCount":0,"excerpt":"string","publishDate":"2023-12-25T13:55:00.207Z"}
```
### FA 078. Books - Отправка запроса методом PUT с вводом "999999999"   
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Books/9999999999

**Ожидаемый результат:** Система должна валидировать входные данные и корректно обрабатывать сценарии с невалидным "id". Поскольку предполагается, что максимально допустимое значение "id" должно укладываться в диапазон значений типа данных System.Int32, ожидается, что запрос с "id" = 9999999999 выявит ошибку валидации, поскольку данное значение превышает максимально допустимое значение для типа System.Int32. Сервер должен вернуть статус-код "400 Bad Request" с информацией о типе ошибки.

**Заголовки запроса:** 
Accept: */*
Content-Type: application/json
User-Agent: PostmanRuntime/7.36.0
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive

**Тело запроса:** 

```
{
  "id": {{id_99999999999}},
  "title": "string",
  "description": "string",
  "pageCount": 0,
  "excerpt": "string",
  "publishDate": "2023-12-25T13:55:00.207Z"
}
```

**Заголовки ответа:** 
Content-Type: application/problem+json; charset=utf-8
Date: Sun, 07 Jan 2024 13:28:04 GMT
Server: Kestrel
Transfer-Encoding: chunked

**Тело ответа:** 

```
{"type":"https://tools.ietf.org/html/rfc7231#section-6.5.1","title":"One or more validation errors occurred.","status":400,"traceId":"00-2e54b8d7b5ade047ba9536d45d183109-51cb8c7918094146-00","errors":{"id":["The value '99999999999' is not valid."],"$.id":["The JSON value could not be converted to System.Int32. Path: $.id | LineNumber: 1 | BytePositionInLine: 9."]}}
```
### FA 079. Books - Удаление методом DELETE валидного значения id - 1  
**URL:** https://fakerestapi.azurewebsites.net///api/v1/Books/1

**Ожидаемый результат:** При отправке DELETE запроса с валидным "id" ожидается, что ресурс с указанным идентификатором будет успешно удалён из системы. Ожидается статус-код "200 OK". При этом не предполагается наличие тела в ответе (payload).

**Заголовки запроса:** 
User-Agent: PostmanRuntime/7.36.0
Accept: */*
Accept-Encoding: gzip, deflate, br

**Тело запроса:**  none

**Заголовки ответа:** 
Content-Length: 0
Date: Sun, 07 Jan 2024 13:31:35 GMT
Server: Kestrel
api-supported-versions: 1.0

**Тело ответа:** none

### FA 080. Books - Удаление методом DELETE несуществующего значения id 58965   
**URL:** https://fakerestapi.azurewebsites.net///api/v1/Books/58965

**Ожидаемый результат:**  ответ сервера со статус-кодом "404 Not Found" как индикатор отсутствующего ресурса. Это соответствует протоколу HTTP, который предписывает возвращение данного статуса в случае запроса на удаление несуществующего объекта.

**Заголовки запроса:** 
User-Agent: PostmanRuntime/7.36.0
Accept: */*
Accept-Encoding: gzip, deflate, br

**Тело запроса:** none


**Заголовки ответа:** 

Content-Length: 0
Date: Sun, 07 Jan 2024 13:32:52 GMT
Server: Kestrel
api-supported-versions: 1.0  

**Тело ответа:**  none

### FA 081. Books - Отправка запроса методом DELETE с вводом  9999999999 в поле id  
**URL:** https://fakerestapi.azurewebsites.net///api/v1/Books/9999999999

**Ожидаемый результат:** Так как значение id 9999999999 превышает максимально допустимое значение для типа данных System.Int32, следует ожидать ошибку валидации с возвратом статус-кода "400 Bad Request". Это сообщение будет указывать на ограничения типа данных параметра id и неспособность системы обработать запрос.

**Заголовки запроса:** 

User-Agent: PostmanRuntime/7.36.0
Accept: */*
Accept-Encoding: gzip, deflate, br  

**Тело запроса:** none

**Заголовки ответа:** 
Content-Type: application/problem+json; charset=utf-8
Date: Sun, 07 Jan 2024 13:34:00 GMT
Server: Kestrel
Transfer-Encoding: chunked

**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-8b2410558c78554ab031f4676ba870f7-89d6bb070131444b-00",
    "errors": {
        "id": [
            "The value '9999999999' is not valid."
        ]
    }
}
``` 
### FA 082. CoverPhotos - Получить ответ на запрос методом GET   
**URL:** https://fakerestapi.azurewebsites.net//api/v1/CoverPhotos

**Ожидаемый результат:**  статус-код "200 OK" с массивом объектов JSON, каждый из которых представляет собой обложку книги. Ожидается, что каждый объект в массиве содержит ключи "id", "idBook" и "url" и корректные значения, соответствующие указанному формату данных.

**Заголовки запроса:** 
Accept: -H  "accept: text/plain; v=1.0"
User-Agent: PostmanRuntime/7.36.0
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive

**Тело запроса:**  none

**Заголовки ответа:** 

Content-Type: application/json; charset=utf-8; v=1.0
Date: Sun, 07 Jan 2024 13:35:27 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0  

**Тело ответа:** 

```
[
    {
        "id": 1,
        "idBook": 1,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 1&w=250&h=350"
    },
    {
        "id": 2,
        "idBook": 2,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 2&w=250&h=350"
    }
]
```
### FA 083. CoverPhotos - Отправка запроса методом POST с валидным Id - 50  
**URL:** https://fakerestapi.azurewebsites.net//api/v1/CoverPhotos

**Ожидаемый результат:** успешное создание ресурса и возврат HTTP-статуса 200 ок с телом ответа, содержащим данные созданной сущности. Структура ответа должна совпадать с телом запроса, подтверждая запись данных.

**Заголовки запроса:** 
AAccept: -H  "accept: */*
Content-Type: application/json
User-Agent: PostmanRuntime/7.36.0
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive

**Тело запроса:** 

```
{
  "id": "1",
  "idBook": "0",
  "url": "string"
}
```

**Заголовки ответа:** 
Content-Type: application/json; charset=utf-8; v=1.0
Date: Sun, 07 Jan 2024 13:37:03 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0

**Тело ответа:** 

```
{
    "id": 1,
    "idBook": 0,
    "url": "string"
}
```
### FA 084. CoverPhotos - Отправка запроса методом POST с невалидным Id - 99999999999  
**URL:** https://fakerestapi.azurewebsites.net//api/v1/CoverPhotos

**Ожидаемый результат:** Значение id превышает максимальный доступный размер для типа данных System.Int32, следовательно, ожидается возвращение ошибки валидации с HTTP-статусом 400 Bad Request, включающей описание ошибки, которое указывает на невозможность приведения значения к ожидаемому типу.

**Заголовки запроса:** 
Accept: -H  "accept: */*
Content-Type: application/json
User-Agent: PostmanRuntime/7.36.0
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive

**Тело запроса:** 

```
{
  "id": "99999999999",
  "idBook": "0",
  "url": "string"
}
```

**Заголовки ответа:** 
Content-Type: application/problem+json; charset=utf-8
Date: Sun, 07 Jan 2024 13:38:10 GMT
Server: Kestrel
Transfer-Encoding: chunked

**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-714b503680e84b41b91335c8c991ab39-e5a3f95b19d14743-00",
    "errors": {
        "$.id": [
            "The JSON value could not be converted to System.Int32. Path: $.id | LineNumber: 1 | BytePositionInLine: 21."
        ]
    }
}
```
### FA 085. CoverPhotos - Отправка запроса методом POST с пустым Id   
**URL:** https://fakerestapi.azurewebsites.net//api/v1/CoverPhotos

**Ожидаемый результат:** Отсутствие значения id в теле запроса приводит к возвращению ошибки валидации. Следует ожидать HTTP-статус 400 Bad Request с информацией, что в поле id поступило пустое значение, что нарушает ожидаемую структуру JSON и требования к данным.

**Заголовки запроса:** 
Accept: -H  "accept: */*
Content-Type: application/json
User-Agent: PostmanRuntime/7.36.0
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive

**Тело запроса:** 

```
{
  "id": ,
  "idBook": "0",
  "url": "string"
}
```

**Заголовки ответа:** 
Content-Type: application/problem+json; charset=utf-8
Date: Sun, 07 Jan 2024 13:39:16 GMT
Server: Kestrel
Transfer-Encoding: chunked

**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-0f68ff9bb533a54d844c4d1619607f63-3c9b55915d885f4e-00",
    "errors": {
        "$.id": [
            "',' is an invalid start of a value. Path: $.id | LineNumber: 1 | BytePositionInLine: 8."
        ]
    }
}
```
### FA 086. CoverPhotos - Отправка запроса методом POST без JSON  
**URL:** https://fakerestapi.azurewebsites.net//api/v1/CoverPhotos

**Ожидаемый результат:** Отсутствие тела запроса для метода POST, который подразумевает создание ресурса, приведёт к ошибке о невозможности обработать пустое тело запроса. Будет возвращён HTTP-статус 400 Bad Request с сообщением о необходимости предоставления непустого тела запроса для успешного исполнения операции.

**Заголовки запроса:** 
Accept: text/plain; v=1.0
Content-Type: application/json; v=1.0
User-Agent: PostmanRuntime/7.36.0
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive

**Тело запроса:** 

```

```

**Заголовки ответа:** 
Content-Type: application/problem+json; charset=utf-8
Date: Sun, 07 Jan 2024 13:40:08 GMT
Server: Kestrel
Transfer-Encoding: chunked

**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-2f225a29f7d7854592c75cbc653305b5-3abdffdc65576e42-00",
    "errors": {
        "": [
            "A non-empty request body is required."
        ]
    }
}
```
### FA 087. CoverPhotos - Отправка запроса методом POST без строки id  
**URL:** https://fakerestapi.azurewebsites.net//api/v1/CoverPhotos

**Ожидаемый результат:** Предполагается, что поле "id" является обязательным, и API не генерирует "id" автоматически. Будет возвращён HTTP-статус 400 Bad Request с сообщением о необходимости предоставления "id".

**Заголовки запроса:** 

Accept: -H  "accept: */*
Content-Type: application/json
User-Agent: PostmanRuntime/7.36.0
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive
**Тело запроса:** 

```
{
  "idBook": "0",
  "url": "string"
}
```

**Заголовки ответа:** 
Content-Type: application/json; charset=utf-8; v=1.0
Date: Sun, 07 Jan 2024 13:41:03 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0

**Тело ответа:** 

```
{
    "id": 0,
    "idBook": 0,
    "url": "string"
}
```
### FA 088. CoverPhotos - Отправка запроса методом POST с спецсимволом вместо id  
**URL:** https://fakerestapi.azurewebsites.net//api/v1/CoverPhotos

**Ожидаемый результат:** В теле ответа содержится структура(словарь) с ключами "type", "title", "status", "traceId", "errors" и их значениями. Статус код ответа 400. В значении ключа "errors" описана ошибка: "The JSON value could not be converted to System.Int32.

**Заголовки запроса:** 

Accept: -H  "accept: */*
Content-Type: application/json
User-Agent: PostmanRuntime/7.36.0
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive
**Тело запроса:** 

```
{
  "id": "+-",
  "idBook": "0",
  "url": "string"
}
```

**Заголовки ответа:** 

Content-Type: application/problem+json; charset=utf-8
Date: Sun, 07 Jan 2024 13:41:55 GMT
Server: Kestrel
Transfer-Encoding: chunked
**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-f1da6ae19cac0b4880f0ca1b38f7e7d7-de4a375ba7806f46-00",
    "errors": {
        "$.id": [
            "The JSON value could not be converted to System.Int32. Path: $.id | LineNumber: 1 | BytePositionInLine: 12."
        ]
    }
}
```
### FA 089. CoverPhotos - Отправка запроса методом POST с вводом "w8" в поле id  
**URL:** https://fakerestapi.azurewebsites.net//api/v1/CoverPhotos

**Ожидаемый результат:** В теле ответа содержится структура(словарь) с ключами "type", "title", "status", "traceId", "errors" и их значениями. Статус код ответа 400. В значении ключа "errors" описана ошибка: "The JSON value could not be converted to System.Int32. 

**Заголовки запроса:** 

Accept: -H  "accept: */*
Content-Type: application/json
User-Agent: PostmanRuntime/7.36.0
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive  

**Тело запроса:** 

```
{
  "id": "w8",
  "idBook": "0",
  "url": "string"
}
```

**Заголовки ответа:** 

Content-Type: application/problem+json; charset=utf-8
Date: Sun, 07 Jan 2024 13:42:44 GMT
Server: Kestrel
Transfer-Encoding: chunked  

**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-955f2986a2eee44aaab56f43ecd3a7b4-f2d37ddebdf46345-00",
    "errors": {
        "$.id": [
            "The JSON value could not be converted to System.Int32. Path: $.id | LineNumber: 1 | BytePositionInLine: 12."
        ]
    }
}
```
### FA 090. CoverPhotos - Отправка запроса методом POST с вводом "аб" в поле id  
**URL:** https://fakerestapi.azurewebsites.net//api/v1/CoverPhotos

**Ожидаемый результат:** В теле ответа содержится структура(словарь) с ключами "type", "title", "status", "traceId", "errors" и их значениями. Статус код ответа 400. В значении ключа "errors" описана ошибка: "The JSON value could not be converted to System.Int32.

**Заголовки запроса:** 

Accept: -H  "accept: */*
Content-Type: application/json
User-Agent: PostmanRuntime/7.36.0
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive  

**Тело запроса:** 

```
{
  "id": "аб",
  "idBook": "0",
  "url": "string"
}
```

**Заголовки ответа:** 
Content-Type: application/problem+json; charset=utf-8
Date: Sun, 07 Jan 2024 13:43:35 GMT
Server: Kestrel
Transfer-Encoding: chunked

**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-77aad5533411ff4998616c8a3f518762-a32252eb666f8949-00",
    "errors": {
        "$.id": [
            "The JSON value could not be converted to System.Int32. Path: $.id | LineNumber: 1 | BytePositionInLine: 14."
        ]
    }
}
```
### FA 091. CoverPhotos - Отправка запроса методом POST с вводом  отрицательного числа "-1" в поле id  
**URL:** https://fakerestapi.azurewebsites.net//api/v1/CoverPhotos

**Ожидаемый результат:** В теле ответа содержится структура(словарь) с ключами "type", "title", "status", "traceId", "errors" и их значениями. Статус код ответа 400. В значении ключа "errors" описана ошибка: "The JSON value could not be converted to System.Int32.

**Заголовки запроса:** 
Accept: -H  "accept: */*
Content-Type: application/json
User-Agent: PostmanRuntime/7.36.0
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive

**Тело запроса:** 

```
{
  "id": "-1",
  "idBook": "0",
  "url": "string"
}
```

**Заголовки ответа:** 

Content-Type: application/json; charset=utf-8; v=1.0
Date: Sun, 07 Jan 2024 13:44:24 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0
**Тело ответа:** 

```
{
    "id": -1,
    "idBook": 0,
    "url": "string"
}
```
### FA 092. CoverPhotos - Отправка запроса методом GET с вводом "1" в поле idBook  
**URL:** 

**Ожидаемый результат:** В теле ответа содержится структура (словарь) с ключами "id", "idBook", "url" и их значениями. Тип данных значений ключей соответствует требованиям: id - INT, idBook - INT, url - string. Статус код ответа 200.

**Заголовки запроса:** 

User-Agent: PostmanRuntime/7.36.0
Accept: */*
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive  

**Тело запроса:**  none

**Заголовки ответа:** 
Content-Type: application/json; charset=utf-8; v=1.0
Date: Sun, 07 Jan 2024 13:45:09 GMT
Server: Kestrel
Transfer-Encoding: chunked

**Тело ответа:** 

```
[
    {
        "id": 1,
        "idBook": 1,
        "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 1&w=250&h=350"
    }
]
```
### FA 093. CoverPhotos - Отправка запроса методом GET с вводом "-1" в поле idBook  
**URL:** 

**Ожидаемый результат:** Сервер вернёт HTTP статус 200 OK и пустой массив в теле ответа

**Заголовки запроса:** 
User-Agent: PostmanRuntime/7.36.0
Accept: */*
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive

**Тело запроса:** none

**Заголовки ответа:** 
Content-Type: application/json; charset=utf-8; v=1.0
Date: Sun, 07 Jan 2024 13:46:07 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0

**Тело ответа:** 

```
[]
```
### FA 094. CoverPhotos - Отправка запроса методом GET с вводом  9999999999 в поле id   
**URL:** 

**Ожидаемый результат:** Сервер вернёт HTTP статус 400 Bad Request с информацией об ошибке, в том числе указывая, что значение '99999999999' недопустимо. 

**Заголовки запроса:** 
User-Agent: PostmanRuntime/7.36.0
Accept: */*
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive

**Тело запроса:**  none

**Заголовки ответа:** 
Content-Type: application/problem+json; charset=utf-8
Date: Sun, 07 Jan 2024 13:47:21 GMT
Server: Kestrel
Transfer-Encoding: chunked

**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-69c7b52d784fb84ab144dd7777078fea-7a134e145c246848-00",
    "errors": {
        "id": [
            "The value '99999999999' is not valid."
        ]
    }
}
```
### FA 095. CoverPhotos - Отправка запроса методом GET с вводом "1" в поле id   
**URL:** 

**Ожидаемый результат:**  Запрос GET должен вернуть информацию о CoverPhoto с id 1. Если такой элемент существует, сервер вернёт HTTP статус 200 OK и в теле ответа будет содержаться JSON-объект с полной информацией о CoverPhoto, включая поля "id", "idBook", и "url", с указанными значениями. 

**Заголовки запроса:** 
User-Agent: PostmanRuntime/7.36.0
Accept: */*
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive

**Тело запроса:**  none


**Заголовки ответа:** 
Content-Type: application/json; charset=utf-8; v=1.0
Date: Sun, 07 Jan 2024 13:48:38 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0

**Тело ответа:** 

```
{
    "id": 1,
    "idBook": 1,
    "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 1&w=250&h=350"
}
```
### FA 096. CoverPhotos - Отправка запроса методом GET с вводом "-1" в   поле id   
**URL:** 

**Ожидаемый результат:** Сервер вернёт HTTP статус 404 Not Found с информацией о том, что запрашиваемый ресурс не найден. В теле ответа будет содержаться информация об ошибке запроса. 

**Заголовки запроса:** 
User-Agent: PostmanRuntime/7.36.0
Accept: */*
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive

**Тело запроса:** none

**Заголовки ответа:** 

Content-Type: application/problem+json; charset=utf-8; v=1.0
Date: Sun, 07 Jan 2024 13:49:32 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0  

**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.4",
    "title": "Not Found",
    "status": 404,
    "traceId": "00-edbce836918ae94f87029655eb74e428-f065d9015f209940-00"
}
```
### FA 097. CoverPhotos - Отправка запроса методом GET с вводом  9999999999 в поле id   
**URL:** 

**Ожидаемый результат:** Система вернёт HTTP статус 400 Bad Request из-за несоответствия типа данных (слишком большое число для предполагаемого целочисленного идентификатора). В теле ответа будет содержаться информация о ошибке, указывая, что предоставленное значение '9999999999' для id недопустимо.

**Заголовки запроса:** 
User-Agent: PostmanRuntime/7.36.0
Accept: */*
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive

**Тело запроса:**  none

**Заголовки ответа:** 

Content-Type: application/problem+json; charset=utf-8
Date: Sun, 07 Jan 2024 13:50:42 GMT
Server: Kestrel
Transfer-Encoding: chunked  

**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-0d9a9a90db9ce64c99e7ea14ff592f10-3a7e6fb80e79f346-00",
    "errors": {
        "id": [
            "The value '9999999999' is not valid."
        ]
    }
}
```
### FA 098. CoverPhotos - Отправка запроса методом PUT с вводом "1" в поле id  
**URL:** 

**Ожидаемый результат:** Система обновит данные и вернёт HTTP статус 200 OK вместе с обновлённым телом ответа, содержащим новые значения полей "id", "idBook", и "url".  

**Заголовки запроса:** 
Accept: text/plain; v=1.0
Content-Type: application/json; v=1.0
User-Agent: PostmanRuntime/7.36.0
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive

**Тело запроса:** 

```
{
  "id": "1",
  "idBook": "0",
  "url": "string"
}
```

**Заголовки ответа:** 

Content-Type: application/json; charset=utf-8; v=1.0
Date: Sun, 07 Jan 2024 13:59:29 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0
**Тело ответа:** 

```
{
    "id": 1,
    "idBook": 0,
    "url": "string"
}
``` 

### FA 099. CoverPhotos - Отправка запроса методом PUT с вводом отрицательного числа "-1" в поле id   
**URL:** 

**Ожидаемый результат:** Вернётся HTTP статус 400 Bad Request с сообщением о несоответствии типа id.  

**Заголовки запроса:** 
Content-Type: application/json; v=1.0
Accept: accept: text/plain; v=1.0
User-Agent: PostmanRuntime/7.36.0
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive

**Тело запроса:** 

```
{
  "id": -1,
  "idBook": 0,
  "url": "string"
}
```

**Заголовки ответа:** 

Content-Type: application/json; charset=utf-8; v=1.0
Date: Sun, 07 Jan 2024 14:06:21 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0
**Тело ответа:** 

```
{
    "id": -1,
    "idBook": 0,
    "url": "string"
}
```
### FA 100. CoverPhotos - Отправка запроса методом PUT с вводом "0" в поле id   
**URL:** 

**Ожидаемый результат:** Сервер не допускает id "0" или такой записи нет, вернётся HTTP статус 400 Bad Request. 

**Заголовки запроса:** 

Content-Type: application/json
User-Agent: PostmanRuntime/7.36.0
Accept: */*
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive
**Тело запроса:** 

```
{
  "id": 0,
  "idBook": 0,
  "url": "string"
}
```

**Заголовки ответа:** 
Content-Type: application/json; charset=utf-8; v=1.0
Date: Sun, 07 Jan 2024 14:09:03 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0

**Тело ответа:** 

```
{
    "id": 0,
    "idBook": 0,
    "url": "string"
}
```
### FA 101. CoverPhotos - Отправка запроса методом PUT с вводом "1" в поле id и удалением JSON  
**URL:** 

**Ожидаемый результат:** Ошибка с кодом состояния HTTP 400 Bad Request из-за отсутствия JSON в теле запроса.

**Заголовки запроса:** 

User-Agent: PostmanRuntime/7.36.0
Accept: */*
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive
**Тело запроса:** 

```

```

**Заголовки ответа:** 
Content-Type: application/problem+json; charset=utf-8
Date: Sun, 07 Jan 2024 14:10:09 GMT
Server: Kestrel
Transfer-Encoding: chunked

**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.13",
    "title": "Unsupported Media Type",
    "status": 415,
    "traceId": "00-84fecbba9e41e548b610ad012de30de2-26653162e83d6046-00"
}
```
### FA 102. CoverPhotos - Отправка запроса методом PUT с вводом "1" в поле id и удалением строки id в JSON  
**URL:** 

**Ожидаемый результат:** Система обновит данные и вернёт HTTP статус 200 OK вместе с обновлённым телом ответа, содержащим новые значения полей "id", "idBook", и "url".  

**Заголовки запроса:** 

Content-Type: application/json
User-Agent: PostmanRuntime/7.36.0
Accept: */*
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive
**Тело запроса:** 

```
{
  "idBook": 0,
  "url": "string"
}
```

**Заголовки ответа:** 

Content-Type: application/json; charset=utf-8; v=1.0
Date: Sun, 07 Jan 2024 14:11:26 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0
**Тело ответа:** 

```
{
    "id": 0,
    "idBook": 0,
    "url": "string"
}
```
### FA 103. CoverPhotos - Отправка запроса методом PUT с вводом "999999999"   
**URL:** 

**Ожидаемый результат:** Ошибка с кодом состояния HTTP 400 Bad Request из-за того, что значение id превышает допустимый диапазон для целочисленного типа данных. "The value '9999999999' is not valid."

**Заголовки запроса:** 
Content-Type: application/json
User-Agent: PostmanRuntime/7.36.0
Accept: */*
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive

**Тело запроса:** 

```
{
  "id": 99999999999,
  "idBook": 0,
  "url": "string"
}
```

**Заголовки ответа:** 

Content-Type: application/problem+json; charset=utf-8
Date: Sun, 07 Jan 2024 14:12:42 GMT
Server: Kestrel
Transfer-Encoding: chunked  

**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-395a7a3c0d5af74f9d7845b20ace36e3-a4d85566d7a47144-00",
    "errors": {
        "id": [
            "The value '9999999999' is not valid."
        ],
        "$.id": [
            "The JSON value could not be converted to System.Int32. Path: $.id | LineNumber: 1 | BytePositionInLine: 19."
        ]
    }
}
```
### FA 104. CoverPhotos - Удаление методом DELETE валидного значения id - 1 

**URL:**  

**Ожидаемый результат:** Запись с номером id удаляется. Возвращается пустой ответ с кодом состояния HTTP 200 OK.

**Заголовки запроса:** 

User-Agent: PostmanRuntime/7.36.0
Accept: */*
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive

**Тело запроса:**  none

**Заголовки ответа:** 
Content-Length: 0
Date: Sun, 07 Jan 2024 14:13:43 GMT
Server: Kestrel
api-supported-versions: 1.0

**Тело ответа:** none

### FA 105. CoverPhotos - Удаление методом DELETE несуществующего значения id 58965   
**URL:** 

**Ожидаемый результат:** Ответ сервера со статус-кодом "404 Not Found" как индикатор отсутствующего ресурса. Это соответствует протоколу HTTP, который предписывает возвращение данного статуса в случае запроса на удаление несуществующего объекта. 

**Заголовки запроса:** 
User-Agent: PostmanRuntime/7.36.0
Accept: */*
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive

**Тело запроса:**  none

**Заголовки ответа:** 
Content-Length: 0
Date: Sun, 07 Jan 2024 14:16:07 GMT
Server: Kestrel
api-supported-versions: 1.0

**Тело ответа:**  none

### FA 106. CoverPhotos - Отправка запроса методом DELETE с вводом  9999999999 в поле id   
**URL:** 

**Ожидаемый результат:** Ошибка с кодом состояния HTTP 400 Bad Request из-за того, что значение id вне допустимого диапазона для типа данных id в системе. "The value '9999999999' is not valid." 

**Заголовки запроса:** 

User-Agent: PostmanRuntime/7.36.0
Accept: */*
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive  

**Тело запроса:**   none

**Заголовки ответа:** 

Content-Type: application/problem+json; charset=utf-8
Date: Sun, 07 Jan 2024 14:17:02 GMT
Server: Kestrel
Transfer-Encoding: chunked 

**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-5eb1b1df2608c040be28cdb4e5d2fb2b-6d5dcac50855574b-00",
    "errors": {
        "id": [
            "The value '99999999999' is not valid."
        ]
    }
}
```
### FA 107. Users - Получить ответ на запрос методом GET   
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Users

**Ожидаемый результат:** Сервер вернёт список пользователей в формате JSON с их id, именами пользователей (userName) и паролями (password), например, пользователя с id 1, userName "User 1" и password "Password1", и так далее для других записей в этом списке, с кодом статуса 200 OK.

**Заголовки запроса:** 
Accept: -H  "accept: text/plain; v=1.0"
User-Agent: PostmanRuntime/7.36.0
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive

**Тело запроса:** none

**Заголовки ответа:** 

Content-Type: application/json; charset=utf-8; v=1.0
Date: Sun, 07 Jan 2024 14:22:11 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0  

**Тело ответа:** 

```
 {
        "id": 1,
        "userName": "User 1",
        "password": "Password1"
    },
    {
        "id": 2,
        "userName": "User 2",
        "password": "Password2"
    },
    {
        "id": 3,
        "userName": "User 3",
        "password": "Password3"
    }
```
### FA 108. Users - Отправка запроса методом POST с валидным Id - 50  
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Users

**Ожидаемый результат:**  Успешное создание нового пользователя с id 50. СТАТУС-КОД ОТВЕТА 200.


**Заголовки запроса:** 
Accept: -H  "accept: */*
Content-Type: application/json
User-Agent: PostmanRuntime/7.36.0
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive

**Тело запроса:** 

```
{
  "id": 50,
  "userName": "string",
  "password": "string"
}
```

**Заголовки ответа:** 

Content-Type: application/json; charset=utf-8; v=1.0
Date: Sun, 07 Jan 2024 14:24:08 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0 

**Тело ответа:** 

```
{
    "id": 50,
    "userName": "string",
    "password": "string"
}
```
### FA 109. Users - Отправка запроса методом POST с невалидным Id - 999 99999999  
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Users

**Ожидаемый результат:** Ошибка валидации, так как значение id превышает допустимый диапазон для целочисленного типа данных. Сервер возвращает ответ с кодом ошибки 400 Bad Request и сообщением об ошибке валидации id.

**Заголовки запроса:** 
Accept: -H  "accept: */*
Content-Type: application/json
User-Agent: PostmanRuntime/7.36.0
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive

**Тело запроса:** 

```
{
  "id": 99999999999,
  "userName": "string",
  "password": "string"
}
```

**Заголовки ответа:** 

Content-Type: application/problem+json; charset=utf-8
Date: Sun, 07 Jan 2024 14:25:02 GMT
Server: Kestrel
Transfer-Encoding: chunked  

**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-f3c680393604a74c9dae8b4a9b70669b-b8ad32dbdd475c48-00",
    "errors": {
        "$.id": [
            "The JSON value could not be converted to System.Int32. Path: $.id | LineNumber: 1 | BytePositionInLine: 19."
        ]
    }
}
```
### FA 110. Users - Отправка запроса методом POST с пустым Id   
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Users

**Ожидаемый результат:**  Ошибка валидации из-за отсутствующего значения id. Сервер возвращает ответ с кодом ошибки 400 Bad Request и сообщением о том, что в теле запроса обнаружена ошибка.

**Заголовки запроса:** 
Accept: -H  "accept: */*
Content-Type: application/json
User-Agent: PostmanRuntime/7.36.0
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive

**Тело запроса:** 

```
{
  "id":,
  "userName": "string",
  "password": "string"
}
```

**Заголовки ответа:** 

Content-Type: application/problem+json; charset=utf-8
Date: Sun, 07 Jan 2024 14:25:48 GMT
Server: Kestrel
Transfer-Encoding: chunked  

**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-634598c944c0bf4cbbd15840425a5b18-0a23e58879f7d14c-00",
    "errors": {
        "$.id": [
            "',' is an invalid start of a value. Path: $.id | LineNumber: 1 | BytePositionInLine: 7."
        ]
    }
}
```
### FA 111. Users - Отправка запроса методом POST без JSON  
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Users/

**Ожидаемый результат:** Ошибка валидации, так как тело запроса не содержит данных. Сервер возвращает ответ с кодом ошибки 400 Bad Request и сообщением о необходимости предоставления непустого тела запроса.

**Заголовки запроса:** 
Accept: "accept: */*
Content-Type: application/json; v=1.0
User-Agent: PostmanRuntime/7.36.0
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive

**Тело запроса:** 

```

```

**Заголовки ответа:** 

Content-Type: application/problem+json; charset=utf-8
Date: Sun, 07 Jan 2024 14:29:15 GMT
Server: Kestrel
Transfer-Encoding: chunked  

**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-83e5a1df5adfbb40b3b274e6ecb34012-b85f97bcac92a645-00",
    "errors": {
        "": [
            "A non-empty request body is required."
        ]
    }
}
```
### FA 112. Users - Отправка запроса методом POST без строки id  
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Users

**Ожидаемый результат:** Создание пользователя без предоставления ID не выполняется, сервер автоматически не генерирует ID для пользователя. Статус код ответа 400. Ошибка - отсутствие обязательного поля id.


**Заголовки запроса:** 

Accept: -H  "accept: */*
Content-Type: application/json
User-Agent: PostmanRuntime/7.36.0
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive  

**Тело запроса:** 

```
{
  "userName": "string",
  "password": "string"
}
```

**Заголовки ответа:** 
Content-Type: application/json; charset=utf-8; v=1.0
Date: Sun, 07 Jan 2024 14:30:34 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0

**Тело ответа:** 

```
{
    "id": 0,
    "userName": "string",
    "password": "string"
}
```
### FA 113. Users - Отправка запроса методом POST с спецсимволом вместо id   
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Users

**Ожидаемый результат:**  В запросе на создание пользователя присутствует неверный формат ID, что приводит к ошибке валидации. Сервер возвращает ошибку с кодом 400 - Bad Request.

**Заголовки запроса:** 

Accept: -H  "accept: */*
Content-Type: application/json
User-Agent: PostmanRuntime/7.36.0
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive  

**Тело запроса:** 

```
{
  "id": +-,
  "userName": "string",
  "password": "string"
}
```

**Заголовки ответа:** 

Content-Type: application/problem+json; charset=utf-8
Date: Sun, 07 Jan 2024 14:31:29 GMT
Server: Kestrel
Transfer-Encoding: chunked  

**Тело ответа:** 

```
{"type":"https://tools.ietf.org/html/rfc7231#section-6.5.1","title":"One or more validation errors occurred.","status":400,"traceId":"00-ebdddefc58bd4c42b85f33b2603f79b2-0a21028299283540-00","errors":{"$.id":["'+' is an invalid start of a value. Path: $.id | LineNumber: 1 | BytePositionInLine: 8."]}}
```
### FA 114. Users - Отправка запроса методом POST с вводом "w8" в поле id   
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Users

**Ожидаемый результат:** В запросе на создание пользователя используется некорректное значение для ID - строка "w8", что недопустимо по правилам валидации API и вызывает ошибку с кодом 400 - Bad Request.
 

**Заголовки запроса:** 
Accept: -H  "accept: */*
Content-Type: application/json
User-Agent: PostmanRuntime/7.36.0
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive

**Тело запроса:** 

```
{
  "id": w8,
  "userName": "string",
  "password": "string"
}
```

**Заголовки ответа:** 
Content-Type: application/problem+json; charset=utf-8
Date: Sun, 07 Jan 2024 14:32:26 GMT
Server: Kestrel
Transfer-Encoding: chunked

**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-c7edfa4ecadcb545b855eef2df533c95-843fd8346f5c3c4d-00",
    "errors": {
        "$.id": [
            "'w' is an invalid start of a value. Path: $.id | LineNumber: 1 | BytePositionInLine: 8."
        ]
    }
}
```
### FA 115. Users - Отправка запроса методом POST с вводом "аб" в поле id  
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Users

**Ожидаемый результат:** Попытка создать пользователя с использованием некорректных символов "аб" в поле ID приведёт к ошибке валидации. Сервер вернёт ответ с ошибкой и кодом состояния 400 - Bad Request.

**Заголовки запроса:** 
Accept: "accept: */*
Content-Type: application/json
User-Agent: PostmanRuntime/7.36.0
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive

**Тело запроса:** 

```
{
  "id": аб,
  "userName": "string",
  "password": "string"
}
```

**Заголовки ответа:** 
Content-Type: application/problem+json; charset=utf-8
Date: Sun, 07 Jan 2024 14:35:14 GMT
Server: Kestrel
Transfer-Encoding: chunked

**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-d97b1ca5520e094c8f6d29716de8f5d0-165e223fe55b194a-00",
    "errors": {
        "$.id": [
            "'0xD0' is an invalid start of a value. Path: $.id | LineNumber: 1 | BytePositionInLine: 8."
        ]
    }
}
```
### FA 116. Users - Отправка запроса методом POST с вводом  отрицательного числа "-1" в поле id  
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Users

**Ожидаемый результат:** Сервер вернёт HTTP статус 200 OK и тело ответа, содержащее поля "id", "userName" и "password" с присвоенными им значениями -1, "string" и "string" соответственно.

**Заголовки запроса:** 

Accept: "accept: */*
Content-Type: application/json
User-Agent: PostmanRuntime/7.36.0
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive  

**Тело запроса:** 

```
{
  "id": -1,
  "userName": "string",
  "password": "string"
}
```

**Заголовки ответа:** 
Content-Type: application/json; charset=utf-8; v=1.0
Date: Sun, 07 Jan 2024 14:37:16 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0

**Тело ответа:** 

```
{
    "id": -1,
    "userName": "string",
    "password": "string"
}
```
### FA 117. Users - Отправка запроса методом POST с вводом "1" в поле id с удалением строки password  
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Users

**Ожидаемый результат:** сервер вернёт HTTP статус 400 Bad Request с сообщением о невалидном запросе, указывающем на ошибку что поле "password" отсутствует, если оно обязательно для создания ресурса.

**Заголовки запроса:** 

Accept: "accept: */*
Content-Type: application/json
User-Agent: PostmanRuntime/7.36.0
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive
**Тело запроса:** 

```
{
  "id": {{"id_1"}},
  "userName": "string",
}
```

**Заголовки ответа:** 

Content-Type: application/problem+json; charset=utf-8
Date: Sun, 07 Jan 2024 14:39:54 GMT
Server: Kestrel
Transfer-Encoding: chunked  

**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-fdbf229db253a043a8391bf22700f095-7e7c7309d5dd644b-00",
    "errors": {
        "$": [
            "The JSON object contains a trailing comma at the end which is not supported in this mode. Change the reader options. Path: $ | LineNumber: 3 | BytePositionInLine: 0."
        ]
    }
}
```
### FA 118. Users - Отправка запроса методом GET с вводом "1" в поле id   
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Users/1

**Ожидаемый результат:** Сервер вернёт HTTP статус 200 OK и тело ответа с полями "id", "userName" и "password", содержащее информацию о пользователе с id равным 1. Данные будут соответствовать информации о ресурсе, хранящейся на сервере.

**Заголовки запроса:** 
Accept: -H  "accept: text/plain; v=1.0"
User-Agent: PostmanRuntime/7.36.0
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive

**Тело запроса:**  none

**Заголовки ответа:** 
Content-Type: application/json; charset=utf-8; v=1.0
Date: Sun, 07 Jan 2024 14:40:59 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0

**Тело ответа:** 

```
{
    "id": 1,
    "userName": "User 1",
    "password": "Password1"
}
```
### FA 119. Users - Отправка запроса методом GET с вводом "-1" в поле id   
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Users/-1

**Ожидаемый результат:** сервер вернёт HTTP статус 404 Not Found с сообщением об отсутствии ресурса с таким id. Сообщение будет содержать информацию о типе ошибки и HTTP статусе.

**Заголовки запроса:** 
Accept: -H  "accept: text/plain; v=1.0"
User-Agent: PostmanRuntime/7.36.0
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive

**Тело запроса:** none

**Заголовки ответа:** 

Content-Type: application/problem+json; charset=utf-8; v=1.0
Date: Sun, 07 Jan 2024 14:41:58 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0  

**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.4",
    "title": "Not Found",
    "status": 404,
    "traceId": "00-2659374190de844fb3c7fda29c1f761e-76ccef91d763d04b-00"
}
```
### FA 120. Users - Отправка запроса методом GET с вводом  9999999999 в поле id   
**URL:** https://fakerestapi.azurewebsites.net//api/v1/Users/9999999999

**Ожидаемый результат:** Сервер вернёт ответ с HTTP статусом 400 Bad Request, указывая на невалидное значение поля id. Тело ответа будет содержать словарь с информацией об ошибке, в том числе с указанием невалидного значения id.

**Заголовки запроса:** 
Accept: -H  "accept: text/plain; v=1.0"
User-Agent: PostmanRuntime/7.36.0
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive

**Тело запроса:** none

**Заголовки ответа:** 
Content-Type: application/problem+json; charset=utf-8
Date: Sun, 07 Jan 2024 14:43:09 GMT
Server: Kestrel
Transfer-Encoding: chunked

**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-fa7d2a451efbb340bd9c281fe9da863e-c440c801e27b7a47-00",
    "errors": {
        "id": [
            "The value '9999999999' is not valid."
        ]
    }
}
```
### FA 121. Users - Отправка запроса методом PUT с вводом "1" в поле id   
**URL:** https://fakerestapi.azurewebsites.net///api/v1/Users/1

**Ожидаемый результат:** Сервер примет запрос и вернёт ответ с HTTP статусом 200 OK. В теле ответа содержится структура с обновлённой информацией пользователя, включая ключи "id", "userName", "password" с соответствующими значениями.


**Заголовки запроса:** 
Accept: text/json; v=1.0
Content-Type: application/json
User-Agent: PostmanRuntime/7.36.0
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive

**Тело запроса:** 

```
{
  "id": "1",
  "userName": "string",
  "password": "string"
}
```

**Заголовки ответа:** 

Content-Type: application/json; charset=utf-8; v=1.0
Date: Sun, 07 Jan 2024 14:44:12 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0  

**Тело ответа:** 

```
{
    "id": 1,
    "userName": "string",
    "password": "string"
}
```
### FA 122. Users - Отправка запроса методом PUT с вводом отрицательного числа "-1" в поле id   
**URL:** https://fakerestapi.azurewebsites.net///api/v1/Users/-1

**Ожидаемый результат:** Сервер вернёт ответ с HTTP статусом 400 Bad Request, так как такого объекта не существует. Тело ответа будет содержать словарь с информацией об ошибке.

**Заголовки запроса:** 

Accept: */*
Content-Type: text/json; v=1.0
User-Agent: PostmanRuntime/7.36.0
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive
**Тело запроса:** 

```
{
  "id": "-1",
  "userName": "string",
  "password": "string"
}
```

**Заголовки ответа:** 
Content-Type: application/json; charset=utf-8; v=1.0
Date: Sun, 07 Jan 2024 14:45:12 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0

**Тело ответа:** 

```
{
    "id": -1,
    "userName": "string",
    "password": "string"
}
```
### FA 123. Users - Отправка запроса методом PUT с вводом "0" в поле id   
**URL:** https://fakerestapi.azurewebsites.net///api/v1/Users/0

**Ожидаемый результат:** Сервер вернёт ответ с HTTP статусом 400 Bad Request, так как такого объекта не существует. Тело ответа будет содержать словарь с информацией об ошибке.

**Заголовки запроса:** 
Accept: */*
Content-Type: text/json; v=1.0
User-Agent: PostmanRuntime/7.36.0
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive

**Тело запроса:** 

```
    {
  "id": "0",
  "userName": "string",
  "password": "string"
}
```

**Заголовки ответа:** 
Content-Type: application/json; charset=utf-8; v=1.0
Date: Sun, 07 Jan 2024 14:45:55 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0

**Тело ответа:** 

```
{
    "id": 0,
    "userName": "string",
    "password": "string"
}
```
### FA 124. Users - Отправка запроса методом PUT с вводом "1" в поле id и удалением JSON  
**URL:** https://fakerestapi.azurewebsites.net///api/v1/Users/1

**Ожидаемый результат:** При попытке выполнить PUT запрос без тела (пустое тело запроса), сервер вернет HTTP-статус код 400 Bad Request. Ответ будет содержать информацию о том, что для выполнения запроса требуется непустое тело запроса.

**Заголовки запроса:** 
Accept: */*
Content-Type: text/json; v=1.0
User-Agent: PostmanRuntime/7.36.0
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive

**Тело запроса:** 

```

```

**Заголовки ответа:** 

Content-Type: application/problem+json; charset=utf-8
Date: Sun, 07 Jan 2024 14:47:15 GMT
Server: Kestrel
Transfer-Encoding: chunked
**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-8368db9d2b5c734abf802793ff1fffcd-01c5965a923b1f42-00",
    "errors": {
        "": [
            "A non-empty request body is required."
        ]
    }
}
```
### FA 125. Users - Отправка запроса методом PUT с вводом "1" в поле id и удалением строки id в JSON  
**URL:** https://fakerestapi.azurewebsites.net///api/v1/Users/1

**Ожидаемый результат:** PUT запрос с указанием id "1" в URL и данными пользователя без ключа id в теле запроса должен быть обработан сервером, который вернет HTTP-статус код 200 OK. В теле ответа сервер должен вернуть обновленные данные пользователя, со структурой JSON, включая id.

**Заголовки запроса:** 
Accept: */*
Content-Type: text/json; v=1.0
User-Agent: PostmanRuntime/7.36.0
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive

**Тело запроса:** 

```
{
  "userName": "string",
  "password": "string"
}
```

**Заголовки ответа:** 

Content-Type: application/json; charset=utf-8; v=1.0
Date: Sun, 07 Jan 2024 14:48:04 GMT
Server: Kestrel
Transfer-Encoding: chunked
api-supported-versions: 1.0  

**Тело ответа:** 

```
{
    "id": 0,
    "userName": "string",
    "password": "string"
}
```
### FA 126. Users - Отправка запроса методом PUT с вводом "999999999"   
**URL:** https://fakerestapi.azurewebsites.net///api/v1/Users/9999999999"

**Ожидаемый результат:** При отправке PUT запроса с некорректным значением для id клиент получит HTTP-статус указывающий на ошибку - 400 Bad Request. Ответ содержит детализированное описание проблем с указанием, что значение id невалидно, и дополнительное сообщение об ошибке конвертации значения в ожидаемый тип System.Int32.

**Заголовки запроса:** 
Accept: text/json; v=1.0
Content-Type: application/json
User-Agent: PostmanRuntime/7.36.0
Host: fakerestapi.azurewebsites.net
Accept-Encoding: gzip, deflate, br
Connection: keep-alive

**Тело запроса:** 

```
{
  "id": "9999999999"",
  "userName": "string",
  "password": "string"
}
```

**Заголовки ответа:** 

Content-Type: application/problem+json; charset=utf-8
Date: Sun, 07 Jan 2024 14:49:13 GMT
Server: Kestrel
Transfer-Encoding: chunked 

**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-eeffa1c20c35cd46bbb6b3a8ed717470-c5b4238ca97dfd48-00",
    "errors": {
        "id": [
            "The value '9999999999\"' is not valid."
        ],
        "$.id": [
            "The JSON value could not be converted to System.Int32. Path: $.id | LineNumber: 1 | BytePositionInLine: 20."
        ]
    }
}
```
### FA 127. Users - Удаление методом DELETE валидного значения id - 1  
**URL:** https://fakerestapi.azurewebsites.net///api/v1/Users/1

**Ожидаемый результат:**  Запрос на удаление пользователя с валидным id 1 успешно выполнен, HTTP-статус код 200 OK. Тело ответа отсутствует, т.к. это операция удаления.

**Заголовки запроса:** 

User-Agent: PostmanRuntime/7.36.0
Accept: */*
Accept-Encoding: gzip, deflate, br  

**Тело запроса:** none

**Заголовки ответа:** 
Content-Length: 0
Date: Sun, 07 Jan 2024 14:50:05 GMT
Server: Kestrel
api-supported-versions: 1.0

**Тело ответа:**  none

### FA 128. Users - Удаление методом DELETE несуществующего значения id 58965   
**URL:** https://fakerestapi.azurewebsites.net///api/v1/Users/58965

**Ожидаемый результат:**  Запрос на удаление пользователя с несуществующим id 58965 обработан, HTTP-статус код 404 Not Found, так как пользователь с данным id отсутствует в системе. Тело ответа также отсутствует.

**Заголовки запроса:** 
User-Agent: PostmanRuntime/7.36.0
Accept: */*
Accept-Encoding: gzip, deflate, br

**Тело запроса:**  none

**Заголовки ответа:** 

Content-Length: 0
Date: Sun, 07 Jan 2024 14:51:26 GMT
Server: Kestrel
api-supported-versions: 1.0  

**Тело ответа:** none

### FA 129. Users - Отправка запроса методом DELETE с вводом  9999999999 в поле id   
**URL:** https://fakerestapi.azurewebsites.net///api/v1/Users/99999999999

**Ожидаемый результат:** Запрос на удаление пользователя с некорректным id 9999999999 обработан, HTTP-статус код 400 Bad Request, указывающий на то, что предоставленный id невалиден для данной операции. В теле ответа предоставляется информация о конкретной ошибке валидации.

**Заголовки запроса:** 
User-Agent: PostmanRuntime/7.36.0
Accept: */*
Accept-Encoding: gzip, deflate, br

**Тело запроса:**  none

**Заголовки ответа:** 
Content-Type: application/problem+json; charset=utf-8
Date: Sun, 07 Jan 2024 14:52:15 GMT
Server: Kestrel
Transfer-Encoding: chunked

**Тело ответа:** 

```
{
    "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
    "title": "One or more validation errors occurred.",
    "status": 400,
    "traceId": "00-44462ea2dafe9c4d884dc89fa8bd2cb4-635ec1cccb4bab48-00",
    "errors": {
        "id": [
            "The value '99999999999' is not valid."
        ]
    }
}
```
### FA 130. Users - Отправка запроса методом DELETE с вводом  0 в поле id   
**URL:** https://fakerestapi.azurewebsites.net///api/v1/Users/0

**Ожидаемый результат:**  HTTP-статус 404 Not Found, в системе нет пользователя с таким id. Тело ответа отсутствует.

**Заголовки запроса:** 
User-Agent: PostmanRuntime/7.36.0
Accept: */*
Accept-Encoding: gzip, deflate, br

**Тело запроса:**   none

**Заголовки ответа:** 
Content-Length: 0
Date: Sun, 07 Jan 2024 14:53:12 GMT
Server: Kestrel
api-supported-versions: 1.0

**Тело ответа:**  none
