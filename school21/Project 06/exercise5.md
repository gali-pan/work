# 1. GET ​/api​/v1​/Activities

- HTTP-метод: GET
- Полный URL запроса: https://fakerestapi.azurewebsites.net/api/v1/Activities 
- Заголовки запроса: `-H  "accept: text/plain; v=1.0"`
- Тело запроса (при наличии): 
- Статус-код ответа: 200
- Тело ответа (при наличии). Если тело большое, то только его часть:
```
[
  {
    "id": 1,
    "title": "Activity 1",
    "dueDate": "2023-12-12T08:46:53.8281936+00:00",
    "completed": false
  },
  {
    "id": 2,
    "title": "Activity 2",
    "dueDate": "2023-12-12T09:46:53.8281971+00:00",
    "completed": true
  },
  {
    "id": 3,
    "title": "Activity 3",
    "dueDate": "2023-12-12T10:46:53.8281978+00:00",
    "completed": false
  },
  {
    "id": 4,
    "title": "Activity 4",
    "dueDate": "2023-12-12T11:46:53.8281983+00:00",
    "completed": true
  }
  ]
```
***
# 2. POST ​/api​/v1​/Activities
- HTTP-метод: POST
- Полный URL запроса: https://fakerestapi.azurewebsites.net/api/v1/Activities 
- Заголовки запроса: `-H  "accept: text/plain; v=1.0" -H  "Content-Type: application/json; v=1.0" -d "`
- Тело запроса (при наличии): 
```
{
  "id": 1,
  "title": "string",
  "dueDate": "2023-12-12T07:52:59.474Z",
  "completed": true
}
```
- Статус-код ответа: 200
- Тело ответа (при наличии). Если тело большое, то только его часть:
```
	
{
  "id": 1,
  "title": "string",
  "dueDate": "2023-12-12T07:52:59.474Z",
  "completed": true
}
```
***

# 3. GET ​/api​/v1​/Activities​/2
- HTTP-метод: GET
- Полный URL запроса: https://fakerestapi.azurewebsites.net/api/v1/Activities/2
- Заголовки запроса: `-H  "accept: text/plain; v=1.0"`
- Тело запроса (при наличии): 
- Статус-код ответа: 200
- Тело ответа (при наличии). Если тело большое, то только его часть:
```
{
  "id": 2,
  "title": "Activity 2",
  "dueDate": "2023-12-12T10:06:53.3556553+00:00",
  "completed": true
}
```
***
# 4. GET ​/api​/v1​/Activities​/100
- HTTP-метод: GET
- Полный URL запроса: https://fakerestapi.azurewebsites.net/api/v1/Activities/100
- Заголовки запроса: `-H  "accept: text/plain; v=1.0"`
- Тело запроса (при наличии): 
- Статус-код ответа: 404
- Тело ответа (при наличии). Если тело большое, то только его часть:
```
{
  
  "type": "https://tools.ietf.org/html/rfc7231#section-6.5.4",
  "title": "Not Found",
  "status": 404,
  "traceId": "00-723cec815847a24fbbab3a6d9f213321-fccc9e56d9a66145-00"
}
```
***

# 5. PUT ​/api​/v1​/Activities​/13

- HTTP-метод: PUT
- Полный URL запроса: https://fakerestapi.azurewebsites.net/api/v1/Activities/13
- Заголовки запроса: `-H  "accept: text/plain; v=1.0" -H  "Content-Type: application/json; v=1.0" -d "`
- Тело запроса (при наличии): 
```
{
  "id": 0,
  "title": "string",
  "dueDate": "2023-12-12T08:13:05.188Z",
  "completed": true
}
```
- Статус-код ответа: 200
- Тело ответа (при наличии). Если тело большое, то только его часть:
```
{
  "id": 0,
  "title": "string",
  "dueDate": "2023-12-12T08:13:05.188Z",
  "completed": true
}
```
***
# 6. PUT ​/api​/v1​/Activities​/10000000000

- HTTP-метод: PUT
- Полный URL запроса: https://fakerestapi.azurewebsites.net/api/v1/Activities/10000000000
- Заголовки запроса: `-H  "accept: text/plain; v=1.0" -H  "Content-Type: application/json; v=1.0" -d "`
- Тело запроса (при наличии): 
```
{
  "id": 0,
  "title": "string",
  "dueDate": "2023-12-12T08:13:05.188Z",
  "completed": true
}
```
- Статус-код ответа: 400
- Тело ответа (при наличии). Если тело большое, то только его часть:
```
{
  "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
  "title": "One or more validation errors occurred.",
  "status": 400,
  "traceId": "00-ea4d3d67201d7b4892c5b3b141415329-0f91b426c7f2ab43-00",
  "errors": {
    "id": [
      "The value '10000000000' is not valid."
    ]
  }
}
```
***
# 7. DELETE ​/api​/v1​/Activities​/13
- HTTP-метод: DELETE
- Полный URL запроса: https://fakerestapi.azurewebsites.net/api/v1/Activities/13
- Заголовки запроса: `-H  "accept: */*"`
- Тело запроса (при наличии):
- Статус-код ответа: 200
- Тело ответа (при наличии). Если тело большое, то только его часть:
***

# 8. DELETE ​/api​/v1​/Activities​/131313131313131313
- HTTP-метод: DELETE
- Полный URL запроса: https://fakerestapi.azurewebsites.net/api/v1/Activities/131313131313131313
- Заголовки запроса: `-H  "accept: */*"`
- Тело запроса (при наличии):
- Статус-код ответа: 200
- Тело ответа (при наличии). Если тело большое, то только его часть:
```
{
  "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
  "title": "One or more validation errors occurred.",
  "status": 400,
  "traceId": "00-3a2b77d789ab08438fe84dadadf9b1e2-81ed3a0adaf6cf4e-00",
  "errors": {
    "id": [
      "The value '131313131313131313' is not valid."
    ]
  }
}
```
***
# 9. GET ​/api​/v1​/Authors
- HTTP-метод: GET
- Полный URL запроса: https://fakerestapi.azurewebsites.net/api/v1/Authors
- Заголовки запроса: `-H  "accept: text/plain; v=1.0"`
- Тело запроса (при наличии):
- Статус-код ответа: 200
- Тело ответа (при наличии). Если тело большое, то только его часть:

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
***
# 10. POST /api​/v1​/Authors
- HTTP-метод: POST
- Полный URL запроса: https://fakerestapi.azurewebsites.net/api/v1/Authors
- Заголовки запроса: `-H  "accept: text/plain; v=1.0" -H  "Content-Type: application/json; v=1.0" -d "`
- Тело ответа (при наличии). Если тело большое, то только его часть:
```
{
  "id": 0,
  "idBook": 0,
  "firstName": "string",
  "lastName": "string"
}
```
- Статус-код ответа: 200
- Тело ответа (при наличии):
```
{
  "id": 0,
  "idBook": 0,
  "firstName": "string",
  "lastName": "string"
}
```
***
# 11. GET ​/api​/v1​/Authors​/authors​/books​/2
- HTTP-метод: GET
- Полный URL запроса: https://fakerestapi.azurewebsites.net/api/v1/Authors/authors/books/2
- Заголовки запроса: `-H  "accept: text/plain; v=1.0"`
- Тело запроса (при наличии):
- Статус-код ответа: 200
- Тело ответа (при наличии). Если тело большое, то только его часть:
```
[
  {
    "id": 3,
    "idBook": 2,
    "firstName": "First Name 3",
    "lastName": "Last Name 3"
  },
  {
    "id": 4,
    "idBook": 2,
    "firstName": "First Name 4",
    "lastName": "Last Name 4"
  },
  {
    "id": 5,
    "idBook": 2,
    "firstName": "First Name 5",
    "lastName": "Last Name 5"
  },
  {
    "id": 6,
    "idBook": 2,
    "firstName": "First Name 6",
    "lastName": "Last Name 6"
  }
]
  
```
***
# 12. GET ​/api​/v1​/Authors​/authors​/books​/22222222222222222222222
- HTTP-метод: GET
- Полный URL запроса: https://fakerestapi.azurewebsites.net/api/v1/Authors/authors/books/22222222222222222222222
- Заголовки запроса: `-H  "accept: text/plain; v=1.0"`
- Тело запроса (при наличии):
- Статус-код ответа: 400
- Тело ответа (при наличии). Если тело большое, то только его часть:
```
{
  "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
  "title": "One or more validation errors occurred.",
  "status": 400,
  "traceId": "00-d49afcc810ddc6489972f2f758515cee-a5f68d6f19af494a-00",
  "errors": {
    "idBook": [
      "The value '22222222222222222222222' is not valid."
    ]
  }
}
```
***
# 13. GET ​/api​/v1​/Authors​/2

- HTTP-метод: GET
- Полный URL запроса: https://fakerestapi.azurewebsites.net/api/v1/Authors/2
- Заголовки запроса: `-H  "accept: text/plain; v=1.0"`
- Тело запроса (при наличии):
- Статус-код ответа: 200
- Тело ответа (при наличии). Если тело большое, то только его часть:
```
{
  "id": 2,
  "idBook": 1,
  "firstName": "First Name 2",
  "lastName": "Last Name 2"
}
```
***
# 14 GET ​/api​/v1​/Authors​/0

- HTTP-метод: GET
- Полный URL запроса: https://fakerestapi.azurewebsites.net/api/v1/Authors/0
- Заголовки запроса: `-H  "accept: text/plain; v=1.0"`
- Тело запроса (при наличии):
- Статус-код ответа: 404
- Тело ответа (при наличии). Если тело большое, то только его часть:
```
{
  "type": "https://tools.ietf.org/html/rfc7231#section-6.5.4",
  "title": "Not Found",
  "status": 404,
  "traceId": "00-0515a9fbde5c594b998c86879c399fbe-023696c7cf41b948-00"
}
```
***
# 15. PUT ​/api​/v1​/Authors​/1

- HTTP-метод: PUT
- Полный URL запроса: https://fakerestapi.azurewebsites.net/api/v1/Authors/1
- Заголовки запроса: `-H  "accept: text/plain; v=1.0" -H  "Content-Type: application/json; v=1.0"`
- Тело запроса (при наличии):
```
{
  "id": 0,
  "idBook": 0,
  "firstName": "string",
  "lastName": "string"
}
```
- Статус-код ответа: 200
- Тело ответа (при наличии). Если тело большое, то только его часть:
```
{
  "id": 0,
  "idBook": 0,
  "firstName": "string",
  "lastName": "string"
}
```
***
# 16. PUT ​/api​/v1​/Authors​/12121212121212
- HTTP-метод: PUT
- Полный URL запроса: https://fakerestapi.azurewebsites.net/api/v1/Authors/12121212121212
- Заголовки запроса: `-H  "accept: text/plain; v=1.0" -H  "Content-Type: application/json; v=1.0"`
- Тело запроса (при наличии):
```
{
  "id": 0,
  "idBook": 0,
  "firstName": S,
  "lastName": "string"
}
```
- Статус-код ответа: 400
- Тело ответа (при наличии). Если тело большое, то только его часть:
```
{
  "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
  "title": "One or more validation errors occurred.",
  "status": 400,
  "traceId": "00-7a0702ab6fb9df4e8d21383f3fb1cbb7-e7b57b3f22aefe42-00",
  "errors": {
    "id": [
      "The value '12121212121212' is not valid."
    ]
  }
}
```
***
# 17. DELETE ​/api​/v1​/Authors​/1

- HTTP-метод: DELETE 
- Полный URL запроса: https://fakerestapi.azurewebsites.net/api/v1/Authors/1
- Заголовки запроса: ` -H  "accept: */*"`
- Тело запроса (при наличии):
- Статус-код ответа: 200
- Тело ответа (при наличии). Если тело большое, то только его часть:

***
# 18. DELETE ​/api​/v1​/Authors​/13131313131313
- HTTP-метод: DELETE 
- Полный URL запроса: https://fakerestapi.azurewebsites.net/api/v1/Authors/13131313131313
- Заголовки запроса: `-H  "accept: */*"`
- Тело запроса (при наличии):
- Статус-код ответа: 400
- Тело ответа (при наличии). Если тело большое, то только его часть:
```
{
  "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
  "title": "One or more validation errors occurred.",
  "status": 400,
  "traceId": "00-417bd5bf36fd0949ae97c38800fc4ce4-853a2f9492d64141-00",
  "errors": {
    "id": [
      "The value '13131313131313' is not valid."
    ]
  }
}
```
***
# 19. GET /api​/v1​/Books

- HTTP-метод: GET
- Полный URL запроса: https://fakerestapi.azurewebsites.net/api/v1/Books
- Заголовки запроса:  `-H  "accept: text/plain; v=1.0"`
- Тело запроса (при наличии):
- Статус-код ответа: 200
- Тело ответа (при наличии). Если тело большое, то только его часть:
```
[
  {
    "id": 1,
    "title": "Book 1",
    "description": "Voluptua eos vel aliquyam sadipscing nulla takimata no sadipscing stet sanctus gubergren duo erat. Eirmod sanctus hendrerit eos diam facilisi takimata rebum tempor magna sit. In lorem dolore tempor takimata ea sed sanctus sadipscing takimata aliquyam sit sit ipsum elitr amet et takimata takimata. Eirmod clita ipsum dolor sadipscing volutpat wisi tation soluta consequat luptatum takimata tempor amet justo dolor. Luptatum feugiat vulputate. Diam no in sed lorem liber.\n",
    "pageCount": 100,
    "excerpt": "Gubergren nonumy est blandit consetetur labore et consetetur elitr. Dignissim erat duo dolore. Duo no sit sanctus dolore accusam dolores sed clita tempor et invidunt aliquyam invidunt aliquyam. Sea nulla vero adipiscing aliquyam tempor amet ad gubergren dolore. Eirmod erat ipsum amet erat ut sit erat diam gubergren eirmod duis in nostrud sit.\nConsetetur sanctus est magna sit et dolore accusam tincidunt voluptua esse. Voluptua et clita vero ea ea dolore est elitr exerci nulla lorem et stet sea elit eum magna. Kasd est diam dolore velit et clita vulputate accumsan et commodo praesent ut. Ea et justo et et est duo erat no stet kasd sanctus esse sit imperdiet sadipscing in takimata nobis. Aliquyam odio amet clita. Et id volutpat lorem sed et tempor erat lorem. Elitr no molestie diam gubergren accusam dolore aliquam kasd diam ut elitr stet augue ut duis aliquyam placerat elitr. Facilisi stet no consetetur eirmod stet et et clita ipsum illum ea consequat nonummy est.\nStet quis sed duo est eirmod rebum nonumy accusam. Diam option autem consequat elitr labore no tincidunt stet lorem et tempor ipsum et odio et rebum soluta. Sea lorem invidunt aliquyam erat takimata ex eos. Accusam elitr consetetur kasd sit sanctus illum aliquyam dolore ipsum tincidunt. Vero sea vel accusam lorem ut dolor ut illum voluptua vulputate clita dolore gubergren vero dolore. Amet magna facilisi magna eos no. Autem kasd justo tincidunt duis esse sed dolor dignissim lorem voluptua eos voluptua labore feugiat. Rebum nibh vel. Sit elitr vulputate sea erat diam ipsum magna et diam et. Voluptua ipsum ut kasd sit amet sanctus ea eos sadipscing nonumy est. Elit dolore doming ullamcorper accusam veniam odio et minim nonumy nonumy accusam labore esse eirmod sadipscing. Diam amet te diam et consequat sit quis at sit. Ut facilisi et et no zzril eos et in ut elit nisl odio labore vulputate nonummy.\nDignissim veniam labore. Ea no feugiat dignissim ullamcorper dolor et ea clita at takimata elitr dolore dolores. Magna minim eu sed diam et zzril ea elitr justo rebum. Gubergren gubergren no elit adipiscing sit et vel dolor sit labore kasd in justo et at. Eos vero dolores lorem sit sea erat odio duo exerci facilisis illum et sed vel. Aliquyam et et est aliquyam et eos iriure accumsan vero dolor duo ut minim. Amet consetetur gubergren amet dolore sed hendrerit mazim dolore duo. Doming qui dolor esse imperdiet diam et clita ea sed vel iusto et eros vel et. At eu diam delenit lorem est lorem et sit erat invidunt ut ea dignissim voluptua feugait tation in. Consequat consetetur sed sit lorem amet amet wisi stet qui dolor. Consetetur exerci diam ipsum clita dolores voluptua duis accumsan.\nSadipscing velit labore justo amet tempor ea dolor dolore amet sit hendrerit dolore nam consequat option kasd aliquam dolore. Ipsum vel vel tempor erat voluptua labore molestie takimata clita erat erat sed labore. Labore facilisi rebum duis sadipscing. Et amet exerci et nibh et ea diam commodo diam consequat sed accusam at vero euismod. Dolor consequat velit ut lorem option. Amet autem magna eum vero et vel vel dolor odio. Magna et tincidunt. Hendrerit ipsum takimata dolore sed lorem. Quis illum lorem justo vero tation quis illum sadipscing sadipscing clita et adipiscing vel tempor ea clita vel. At consequat lorem.\n",
    "publishDate": "2023-12-11T10:33:55.6508376+00:00"
  },
  {
    "id": 2,
    "title": "Book 2",
    "description": "Magna enim tempor ipsum et dolore ut dolores praesent vero et. Rebum nonumy diam et ut ipsum dolor ut dolor et takimata. Nulla minim tincidunt diam dolor kasd imperdiet lorem erat qui et takimata eleifend feugait sea zzril option invidunt. Dolor diam aliquyam et nobis gubergren magna sadipscing eos consectetuer dolores lorem eum dolore labore no rebum. Nobis vulputate consetetur dolor et voluptua erat esse tempor vel sed velit lorem elitr ad no stet. Dolor dolor aliquyam gubergren sea adipiscing stet. Quis nostrud vero lorem lorem eirmod takimata ea justo. Ut accusam voluptua nibh rebum eirmod dolore. Est invidunt nibh sit vel invidunt vero.\n",
    "pageCount": 200,
    "excerpt": "Justo magna quis takimata est consequat sed justo vero. Elitr iriure vel et duo clita amet. Sea ut consetetur et ipsum in illum invidunt erat iusto elitr commodo hendrerit zzril.\nClita lorem amet sit suscipit labore dolor sea et voluptua. No kasd suscipit. Velit ipsum labore molestie sed dolore clita no sed et amet dolore. Sanctus eirmod dolore vero kasd sanctus aliquam. Dolor feugiat diam stet et no kasd rebum amet clita et sanctus lorem justo delenit. Sanctus magna eros dolor eirmod consequat nonumy et sadipscing et lorem ipsum mazim ut. Rebum erat veniam consequat. Amet est qui clita no sanctus lorem.\nEt sanctus minim takimata ad sed takimata eirmod iusto ea dolor facilisis erat duis sit diam luptatum facilisis. Ut qui ea ea dolor et dolor eos et et. Sed kasd amet sit tincidunt vero lobortis et in. Praesent erat labore. Consetetur possim labore no. Sanctus justo in sea duo wisi ullamcorper soluta vel stet diam sadipscing dolor sea ut facilisis. Dolore nulla dolor no illum aliquyam stet vulputate sea et kasd aliquyam at quis dolores. Ea amet ea gubergren magna takimata nonumy praesent. Tincidunt takimata amet et aliquyam ut et clita et accumsan sed accusam duis sadipscing hendrerit labore elitr imperdiet vel. Adipiscing accumsan rebum invidunt et voluptua aliquyam sadipscing invidunt takimata nibh labore commodo et eirmod vero sit. Sed amet magna tempor nonumy ipsum suscipit ex ipsum labore nostrud invidunt feugiat lorem dolor et dolore est. Dolor dolores sit justo tempor duo vel elitr sanctus vero dolore gubergren. Sit consetetur amet. Sea quod sed wisi consetetur euismod ipsum lorem praesent ipsum accusam adipiscing et.\nQuis labore cum laoreet dolore sadipscing no accusam sed stet et sit. Dolor lorem dolor stet ea. Sed hendrerit blandit facilisis. Enim lorem ea clita duo amet erat. At kasd praesent tempor sadipscing amet feugiat eos sed magna et volutpat delenit. Diam consetetur lorem facilisis sit vero elitr aliquyam aliquyam vel amet dolore kasd kasd et. Accusam aliquyam et ea est option wisi ipsum laoreet no lorem tempor. Erat dolor sit ea amet dolor lorem dolor dolore lorem sit vulputate eirmod amet ut diam dolor eros zzril. Sed duo sed ut magna labore nonumy amet autem velit illum ipsum vel sed. Rebum accusam ut magna diam sed clita. In et ut nonumy nulla iriure et. Sed eos gubergren et sadipscing sit aliquyam stet ea amet gubergren. Sed wisi ut augue sed nobis facilisis stet sea aliquyam stet dolor justo kasd nonummy ipsum sadipscing diam. Dolore ea dolor voluptua. Adipiscing sadipscing luptatum magna nostrud lorem ut accusam duo nulla consetetur.\nTempor autem delenit erat in amet gubergren invidunt nonumy lorem. Sea magna nulla veniam nobis iriure vero molestie magna et kasd nonumy invidunt consetetur stet diam. Et ea ut sadipscing sea gubergren rebum sed et gubergren. Eirmod duis justo dolor nihil nulla facilisi nobis sed mazim sadipscing sit. Eos aliquam sanctus justo aliquam duo qui labore clita dolore euismod sit ipsum. Nisl magna vero iriure dolore. Et sit amet ipsum enim elitr et. No quis illum nisl et elit accusam nonumy lorem amet. Veniam diam ipsum erat et lorem et rebum sit sit sit eu sea autem lorem nonumy. Possim volutpat elit consetetur lorem magna gubergren dolores dolore ut et ipsum. Erat sed labore clita eirmod. Duis est amet voluptua vel.\n",
    "publishDate": "2023-12-10T10:33:55.6509755+00:00"
  },
  {
    "id": 3,
    "title": "Book 3",
    "description": "Euismod aliquyam tempor dolor feugait sit lobortis eos et lorem vero vel molestie dolor nonumy lorem gubergren. Magna sit vero facilisis ad dolore labore dolores nostrud vero tempor dolor eirmod ut stet ipsum amet lorem odio. Dolor dolor voluptua tempor elitr. Et est voluptua justo dolores duo placerat sed nibh amet ipsum mazim nonumy.\n",
    "pageCount": 300,
    "excerpt": "Eos tempor dolor magna ea dolore amet dolor in sadipscing diam kasd. Duis nulla ea cum sed congue. Eirmod amet invidunt dolor ut dolore nulla rebum cum eirmod sit duis. Nonumy dolor et justo qui diam nonumy consetetur takimata facer dolore dolore diam volutpat nulla et feugiat duis eirmod. Nihil justo kasd delenit et dolor quod. Sanctus lorem amet euismod sea sed dolor. Kasd ut diam nonumy sanctus vero sit aliquyam hendrerit et minim. Accusam esse elitr ipsum lorem facilisi justo nostrud sit et elit amet nisl qui lorem lorem. Sed et et ea sit dignissim kasd justo sadipscing rebum sadipscing ea facilisis dolores sadipscing stet et. Quis dolore praesent feugait ea stet sea erat et dolor dolor voluptua no veniam sed dolore. Lorem consequat no dolore sadipscing voluptua dolor eu illum velit sit lorem et ullamcorper dolor sanctus dolore et sed. Vero sadipscing et eros iriure ad sit feugiat sit sea et sadipscing et amet amet et.\nNulla sit rebum diam justo est et invidunt sit euismod et. Diam lorem clita aliquyam kasd accusam feugiat lorem eros takimata erat iriure takimata elitr ipsum. Hendrerit clita autem tation elitr sanctus enim et elitr dolores invidunt amet diam dolore nonumy gubergren tempor. Adipiscing gubergren commodo lorem et amet et erat nulla magna kasd aliquam sed elit. Rebum tempor dolor suscipit labore vero nonummy sed magna ut takimata rebum ipsum. Exerci justo dolore diam blandit justo dolor vulputate dolore consetetur. Erat vel sed dolor ex sadipscing voluptua duo voluptua eros sea sed dolore ipsum eos sed et. Volutpat kasd vero ea justo et vero et in. Tation rebum amet sea commodo. Ea dolor exerci dolore sea invidunt et. Voluptua et dolore tincidunt nisl rebum esse duis exerci tempor ipsum. Vero no eirmod accusam. Eos velit elit congue augue invidunt velit takimata invidunt eros dolor ipsum et eros te et exerci ut accusam.\nNulla dolores dolores dolor kasd nulla ut lorem aliquam. Sed sanctus justo elitr nonummy elit lorem sea voluptua invidunt no zzril. Dolores diam dolor duo kasd et facilisi. Stet nibh labore rebum at est dolore iriure amet est consequat diam ipsum. Suscipit lorem sea amet sit. Dolor dolor soluta aliquyam erat. Stet tincidunt dolore consetetur diam sea ut option eirmod exerci dolores eum eos takimata in. Aliquam sadipscing dolore sanctus amet vel dolor nostrud labore et dolor amet et gubergren. Laoreet enim duo ipsum vel vulputate sanctus eirmod vel nonumy lorem diam autem elit dolores dolor sed dolores sanctus.\nSea eum accusam gubergren amet et consectetuer kasd nulla stet et eos kasd sanctus et ipsum ut. Justo ea at est amet tempor tempor assum aliquyam diam. Amet rebum et sed elitr ipsum dolor takimata nisl sed dolor diam. Eos invidunt nonumy molestie sea aliquyam et amet accusam sed doming sed et dolor. Ipsum et sit consequat consetetur in nonummy. Adipiscing molestie elitr. In diam eirmod sea eos sit ut augue option erat ipsum dolores eirmod elitr wisi iusto no stet dolor. Nonummy dolore diam takimata. Ea et ut. Soluta commodo dolore sanctus rebum takimata dolores ad sea soluta est erat stet. Augue in sed sed rebum ipsum ad consequat sea et stet velit dolor. Sadipscing et consequat eos odio gubergren invidunt feugiat takimata feugiat dolores ipsum. Kasd et dolor consectetuer sit gubergren facilisi elitr nonummy blandit erat est amet et stet. Nonummy eirmod minim ipsum vero accusam aliquyam lorem justo at stet est tempor. Augue nonumy clita sanctus invidunt tempor magna lorem justo eos consequat et et placerat dolor. Dolores est lorem.\nSanctus lorem est et. Amet et duis duo sea cum no est diam consetetur takimata iriure tempor at et ipsum velit id. At clita at gubergren sea justo diam diam duo clita gubergren duo. Elit clita magna liber consetetur consetetur clita. Sadipscing ipsum elit sadipscing dolore feugait aliquyam stet sea at dolores ut elitr tation duo dolore consetetur. Ipsum et ipsum et sit volutpat facilisis aliquip blandit. At sit gubergren ipsum elitr vero kasd diam sed. Sit dolores blandit amet kasd ea lorem et aliquam kasd dolor. Ut et sadipscing consetetur imperdiet dolore tempor ea sadipscing ipsum sed sed ut dolores duis labore elit. Rebum invidunt lorem. Ipsum sanctus sadipscing justo erat aliquyam dolores elitr accusam. Lorem lorem ad dolore blandit tempor aliquyam.\n",
    "publishDate": "2023-12-09T10:33:55.6511235+00:00"
  },
  ]
```
***
# 20. POST ​/api​/v1​/Books

- HTTP-метод: POST
- Полный URL запроса: https://fakerestapi.azurewebsites.net/api/v1/Books
- Заголовки запроса: `-H  "accept: */*" -H  "Content-Type: application/json; v=1.0"`
- Тело запроса (при наличии):
```
{
  "id": 0,
  "title": "string",
  "description": "string",
  "pageCount": 0,
  "excerpt": "string",
  "publishDate": "2023-12-12T10:36:17.947Z"
}
```
- Статус-код ответа: 200
- Тело ответа (при наличии). Если тело большое, то только его часть:
```

{
  "id": 0,
  "title": "string",
  "description": "string",
  "pageCount": 0,
  "excerpt": "string",
  "publishDate": "2023-12-12T10:36:17.947Z"
}

```
***

# 21. GET ​/api​/v1​/Books​/2

- HTTP-метод: GET
- Полный URL запроса: https://fakerestapi.azurewebsites.net/api/v1/Books/60
- Заголовки запроса: `-H  "accept: text/plain; v=1.0"`
- Тело запроса (при наличии):
- Статус-код ответа: 200
- Тело ответа (при наличии). Если тело большое, то только его часть:
```
{
  "id": 2,
  "title": "Book 2",
  "description": "Labore kasd dolores elitr congue et sit. Sed molestie erat et sed. Dolor accusam amet ea eirmod ut. Sed et et consequat nostrud esse ea amet rebum ut. Suscipit minim labore feugiat augue eu consetetur justo duo dolor magna diam. Aliquyam dolor rebum dolor aliquyam dolore elitr et at. Ex erat nonumy takimata dolor justo esse lorem. Aliquip tempor et dignissim consetetur sit sed sed facilisis justo et et sadipscing sanctus et et lorem. Et lorem eos at takimata consectetuer consectetuer sit hendrerit facilisi dolor gubergren rebum amet sed sed eirmod sed diam. Duis vero quis sed sit justo clita duis et dolor consequat sed sed et vero hendrerit. Elitr sea et sadipscing option at eos tincidunt.\n",
  "pageCount": 200,
  "excerpt": "Consetetur te aliquam sanctus sea elitr nobis no. Sed duo qui voluptua gubergren labore at et justo nonumy qui adipiscing invidunt labore amet. Gubergren ipsum invidunt kasd ipsum. Diam takimata consequat magna labore enim sit. Duo no volutpat eum dolore. Dolores sit odio. Sea tempor odio suscipit eum sit nulla stet et dolore sanctus sed. Et magna labore vel kasd. Eu delenit veniam ea invidunt et minim consectetuer sea.\nEos ipsum invidunt iusto eum ullamcorper rebum lorem vero nonumy aliquyam rebum gubergren ut in justo erat lorem ut. Nibh magna diam luptatum eos sit dolores sit. Voluptua dolores nostrud erat. Sit vel ipsum dolor ut ut dolores. Magna dignissim amet. Sed odio et facilisi rebum et vero vero lorem sed duo ut sanctus sea diam mazim. Dolor vero ut in lorem molestie consequat amet adipiscing. Dolore elit tempor eros gubergren hendrerit vulputate. Stet ea lorem at invidunt duis justo gubergren eleifend dolore tempor velit. At lorem aliquyam et dolor stet vero delenit dolore praesent nonumy diam. Dolore nostrud consetetur dolor ipsum molestie. Et dolore dolor ipsum. Autem sea kasd no hendrerit nisl autem. Et vero dolore invidunt eos duis.\nEa et voluptua iriure sed diam. At nulla sea. Takimata iriure minim rebum. Feugait accusam nobis invidunt nostrud nonumy lorem at erat. Eirmod ea ea stet et.\nEuismod eum no sadipscing consequat dolore consetetur accusam erat gubergren ipsum dolore consequat iusto et ipsum. Dolore amet et ea at invidunt minim takimata augue doming eos lobortis et option aliquyam dolore tincidunt. Ipsum diam eirmod sit at takimata. Sit dolores et. No ipsum sed kasd dolore sed dignissim at ea. In sadipscing diam dolor ipsum zzril option ut takimata vero. Sed sea zzril iriure sit sed iriure magna justo amet dolor est. Dolor qui ea sea vel commodo vulputate elitr. Dolore sed voluptua et dolores nonumy stet ipsum elitr vulputate eos justo nonumy est gubergren. Iriure sea lorem consequat diam nostrud. Et dolores dolore dolor quis lorem ipsum. Et voluptua sanctus elit tempor dolor. Hendrerit quis dolores sea in dolore tempor ex sadipscing. Nisl et nihil lorem et duis voluptua odio erat. Vulputate consectetuer sit lobortis rebum accusam sadipscing vero molestie tation augue vero erat aliquip sit et diam. Et tincidunt diam sadipscing aliquyam nonumy clita zzril diam et eu lorem et et eirmod. Voluptua eirmod no diam sit diam nonummy sit accusam diam consequat sed labore consetetur dolore.\nIpsum nibh iriure illum in veniam sanctus at tempor tempor dolore elit ipsum. Duo minim ut et lobortis erat labore magna sit lorem dolor clita et dolor consequat lorem odio. At sea dolore amet elitr adipiscing eum dolore eirmod voluptua luptatum diam. Soluta sit kasd sit dolores elitr. Ea erat magna eirmod no erat. Voluptua ea nostrud takimata ea iriure.\n",
  "publishDate": "2023-12-10T10:40:13.292195+00:00"
}

```
***
# 22. GET ​/api​/v1​/Books​/100000000000000
- HTTP-метод: GET
- Полный URL запроса: https://fakerestapi.azurewebsites.net/api/v1/Books/100000000000000
- Заголовки запроса: `-H  "accept: text/plain; v=1.0"`
- Тело запроса (при наличии):
- Статус-код ответа: 400
- Тело ответа (при наличии). Если тело большое, то только его часть:
```
{
  "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
  "title": "One or more validation errors occurred.",
  "status": 400,
  "traceId": "00-0fd20783646fac459c63594caa841a5c-777558dee4543b4c-00",
  "errors": {
    "id": [
      "The value '100000000000000' is not valid."
    ]
  }
}
```
***
# 23. PUT /api​/v1​/Books​/13

- HTTP-метод: PUT
- Полный URL запроса: https://fakerestapi.azurewebsites.net/api/v1/Books/70
- Заголовки запроса: `-H  "accept: */*" -H  "Content-Type: application/json; v=1.0"`
- Тело запроса (при наличии): 
```
{
  "id": 0,
  "title": "string",
  "description": "string",
  "pageCount": 0,
  "excerpt": "string",
  "publishDate": "2023-12-12T10:43:43.223Z"
}
```
- Статус-код ответа: 200
- Тело ответа (при наличии). Если тело большое, то только его часть:
```
{
  "id": 0,
  "title": "string",
  "description": "string",
  "pageCount": 0,
  "excerpt": "string",
  "publishDate": "2023-12-12T10:43:43.223Z"
}
```
***
# 24. PUT /api​/v1​/Books​/100000000000000000

- HTTP-метод: PUT
- Полный URL запроса: https://fakerestapi.azurewebsites.net/api/v1/Books/100000000000000000
- Заголовки запроса: `-H  "accept: */*" -H  "Content-Type: application/json; v=1.0"`
- Тело запроса (при наличии):
```
{
  "id": 0,
  "title": "string",
  "description": "string",
  "pageCount": 0,
  "excerpt": "string",
  "publishDate": "2023-12-12T10:45:11.585Z"
}
```
- Статус-код ответа: 400
- Тело ответа (при наличии). Если тело большое, то только его часть:
```
{
  "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
  "title": "One or more validation errors occurred.",
  "status": 400,
  "traceId": "00-66270e3f3f8a6044be88ea1aaa06de15-ec82ed73ef984d4e-00",
  "errors": {
    "id": [
      "The value '100000000000000000' is not valid."
    ]
  }
}
```
***


# 25. DELETE /api​/v1​/Books​/3

- HTTP-метод: DELETE
- Полный URL запроса: https://fakerestapi.azurewebsites.net/api/v1/Books/3
- Заголовки запроса: `-H  "accept: */*"`
- Тело запроса (при наличии):
- Статус-код ответа: 200
- Тело ответа (при наличии). Если тело большое, то только его часть:
***

# 26. DELETE /api​/v1​/Books​/121212121212121212

- HTTP-метод: DELETE
- Полный URL запроса: https://fakerestapi.azurewebsites.net/api/v1/Books/121212121212121212
- Заголовки запроса: `-H  "accept: */*"`
- Тело запроса (при наличии):
- Статус-код ответа: 400
- Тело ответа (при наличии). Если тело большое, то только его часть:
```
{
  "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
  "title": "One or more validation errors occurred.",
  "status": 400,
  "traceId": "00-d366dee66903ff4b822bfe8b37345bfa-fb10a0a1c371e84c-00",
  "errors": {
    "id": [
      "The value '121212121212121212' is not valid."
    ]
  }
}
```
***
# 27. GET /api​/v1​/CoverPhotos

- HTTP-метод: GET
- Полный URL запроса: https://fakerestapi.azurewebsites.net/api/v1/CoverPhotos
- Заголовки запроса:  `-H  "accept: text/plain; v=1.0"`
- Тело запроса (при наличии):
- Статус-код ответа: 200
- Тело ответа (при наличии). Если тело большое, то только его часть:
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
  },
  {
    "id": 3,
    "idBook": 3,
    "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 3&w=250&h=350"
  },
  {
    "id": 4,
    "idBook": 4,
    "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 4&w=250&h=350"
  },
  {
    "id": 5,
    "idBook": 5,
    "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 5&w=250&h=350"
  }
]
```
***
# 28. POST /api​/v1​/CoverPhotos

- HTTP-метод: POST
- Полный URL запроса: https://fakerestapi.azurewebsites.net/api/v1/CoverPhotos
- Заголовки запроса: `-H  "accept: text/plain; v=1.0" -H  "Content-Type: application/json; v=1.0"`
- Тело запроса (при наличии):
```
{
  "id": 0,
  "idBook": 0,
  "url": "MRX"
}
```
- Статус-код ответа: 200
- Тело ответа (при наличии). Если тело большое, то только его часть:
```
{
  "id": 0,
  "idBook": 0,
  "url": "MRX"
}
```
***
# 29. GET /api​/v1​/CoverPhotos​/books​/covers​/2

- HTTP-метод: GET
- Полный URL запроса: https://fakerestapi.azurewebsites.net/api/v1/CoverPhotos/books/covers/2
- Заголовки запроса:`-H  "accept: text/plain; v=1.0"`
- Тело запроса (при наличии):
- Статус-код ответа: 200
- Тело ответа (при наличии). Если тело большое, то только его часть:
```
[
  {
    "id": 2,
    "idBook": 2,
    "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 2&w=250&h=350"
  }
]
```
***

# 30. GET /api​/v1​/CoverPhotos​/books​/covers​/121212121212

- HTTP-метод: GET
- Полный URL запроса: https://fakerestapi.azurewebsites.net/api/v1/CoverPhotos/books/covers/121212121212
- Заголовки запроса: `-H  "accept: text/plain; v=1.0"`
- Тело запроса (при наличии):
- Статус-код ответа: 400
- Тело ответа (при наличии). Если тело большое, то только его часть:
```
{
  "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
  "title": "One or more validation errors occurred.",
  "status": 400,
  "traceId": "00-5a1f27445d8cd04a80da01227337e17d-78559cfbe139a84b-00",
  "errors": {
    "idBook": [
      "The value '121212121212' is not valid."
    ]
  }
}
```
***
# 31. GET ​/api​/v1​/CoverPhotos​/2

- HTTP-метод: GET 
- Полный URL запроса: https://fakerestapi.azurewebsites.net/api/v1/CoverPhotos/2
- Заголовки запроса: `-H  "accept: text/plain; v=1.0"`
- Тело запроса (при наличии):
- Статус-код ответа: 200
- Тело ответа (при наличии). Если тело большое, то только его часть:
```
{
  "id": 2,
  "idBook": 2,
  "url": "https://placeholdit.imgix.net/~text?txtsize=33&txt=Book 2&w=250&h=350"
}
```
***
# 32. GET ​/api​/v1​/CoverPhotos​/131313131313131

- HTTP-метод: GET
- Полный URL запроса: https://fakerestapi.azurewebsites.net/api/v1/CoverPhotos/131313131313131
- Заголовки запроса: `-H  "accept: text/plain; v=1.0"`
- Тело запроса (при наличии):
- Статус-код ответа: 400
- Тело ответа (при наличии). Если тело большое, то только его часть:
```
{
  "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
  "title": "One or more validation errors occurred.",
  "status": 400,
  "traceId": "00-eab6a57efc9f5f489402ce6ccae07109-60fbf21ab832e348-00",
  "errors": {
    "id": [
      "The value '131313131313131' is not valid."
    ]
  }
}
```
***
33. PUT /api​/v1​/CoverPhotos​/1

- HTTP-метод: PUT
- Полный URL запроса: https://fakerestapi.azurewebsites.net/api/v1/CoverPhotos/1
- Заголовки запроса: `-H  "accept: text/plain; v=1.0" -H  "Content-Type: application/json; v=1.0" -d "`
- Тело запроса (при наличии):
```
{
  "id": 0,
  "idBook": 0,
  "url": "string"
}
```
- Статус-код ответа: 200
- Тело ответа (при наличии). Если тело большое, то только его часть:
```
{
  "id": 0,
  "idBook": 0,
  "url": "string"
}
```
***
# 34. PUT /api​/v1​/CoverPhotos​/121212121212121212

- HTTP-метод: PUT
- Полный URL запроса: https://fakerestapi.azurewebsites.net/api/v1/CoverPhotos/121212121212121212
- Заголовки запроса: `-H  "accept: text/plain; v=1.0" -H  "Content-Type: application/json; v=1.0"`
- Тело запроса (при наличии):
```
{
  "id": 0,
  "idBook": 0,
  "url": "string"
}
```
- Статус-код ответа: 400
- Тело ответа (при наличии). Если тело большое, то только его часть:
```
{
  "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
  "title": "One or more validation errors occurred.",
  "status": 400,
  "traceId": "00-d44b6c6e130626458caba59f50470575-e05a6185ca1fb648-00",
  "errors": {
    "id": [
      "The value '121212121212121212' is not valid."
    ]
  }
}
```
***
# 35. DELETE /api​/v1​/CoverPhotos​/2

- HTTP-метод: DELETE 
- Полный URL запроса: https://fakerestapi.azurewebsites.net/api/v1/CoverPhotos/1
- Заголовки запроса:`-H  "accept: */*"`
- Тело запроса (при наличии):
- Статус-код ответа: 200
- Тело ответа (при наличии). Если тело большое, то только его часть:
***

# 36. DELETE /api​/v1​/CoverPhotos​/121212121212121212

- HTTP-метод: DELETE 
- Полный URL запроса: https://fakerestapi.azurewebsites.net/api/v1/CoverPhotos/121212121212121212
- Заголовки запроса:`-H  "accept: */*"`
- Тело запроса (при наличии):
- Статус-код ответа: 400
- Тело ответа (при наличии). Если тело большое, то только его часть:
```
{
  "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
  "title": "One or more validation errors occurred.",
  "status": 400,
  "traceId": "00-6f4c751e128918498e114f0f1d89cf77-890baaf2557d8040-00",
  "errors": {
    "id": [
      "The value '121212121212121212' is not valid."
    ]
  }
}
```
***

# 37. GET ​/api​/v1​/Users

- HTTP-метод: GET
- Полный URL запроса: https://fakerestapi.azurewebsites.net/api/v1/Users
- Заголовки запроса: `-H  "accept: text/plain; v=1.0"`
- Тело запроса (при наличии):
- Статус-код ответа: 200
- Тело ответа (при наличии). Если тело большое, то только его часть:
```
  [
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
  },
  {
    "id": 4,
    "userName": "User 4",
    "password": "Password4"
  },
  {
    "id": 5,
    "userName": "User 5",
    "password": "Password5"
  },
  {
    "id": 6,
    "userName": "User 6",
    "password": "Password6"
  },
  {
    "id": 7,
    "userName": "User 7",
    "password": "Password7"
  },
  {
    "id": 8,
    "userName": "User 8",
    "password": "Password8"
  }
  ]
```
***
# 38. POST /api​/v1​/Users

- HTTP-метод: POST
- Полный URL запроса: https://fakerestapi.azurewebsites.net/api/v1/Users
- Заголовки запроса: `-H  "accept: */*" -H  "Content-Type: application/json; v=1.0" -d`
- Тело запроса (при наличии):
```
{
  "id": 0,
  "userName": "string",
  "password": "string"
}
```
- Статус-код ответа: 200
- Тело ответа (при наличии). Если тело большое, то только его часть:
```
{
  "id": 0,
  "userName": "string",
  "password": "string"
}
```
***

# 39. GET /api​/v1​/Users​/2

- HTTP-метод:GET
- Полный URL запроса: https://fakerestapi.azurewebsites.net/api/v1/Users/2
- Заголовки запроса: `-H  "accept: */*"`
- Тело запроса (при наличии):
- Статус-код ответа: 200
- Тело ответа (при наличии). Если тело большое, то только его часть:
```
{
  "id": 2,
  "userName": "User 2",
  "password": "Password2"
}
```
# 40. GET /api​/v1​/Users​/12121221212212

- HTTP-метод:GET
- Полный URL запроса: https://fakerestapi.azurewebsites.net/api/v1/Users/12121221212212
- Заголовки запроса: `-H  "accept: */*"`
- Тело запроса (при наличии):
- Статус-код ответа: 400
- Тело ответа (при наличии). Если тело большое, то только его часть:
```
{
  "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
  "title": "One or more validation errors occurred.",
  "status": 400,
  "traceId": "00-48c06023c3f19d448adc0e5ac8b6ffcd-1d433168a3009c41-00",
  "errors": {
    "id": [
      "The value '12121221212212' is not valid."
    ]
  }
}
```
***
# 41. PUT /api​/v1​/Users​/2

- HTTP-метод: PUT
- Полный URL запроса: https://fakerestapi.azurewebsites.net/api/v1/Users/5
- Заголовки запроса: `-H  "accept: */*" -H  "Content-Type: application/json; v=1.0"`
- Тело запроса (при наличии):
```
{
  "id": 0,
  "userName": "string",
  "password": "string"
}
```
- Статус-код ответа: 200
- Тело ответа (при наличии). Если тело большое, то только его часть:
```
{
  "id": 0,
  "userName": "string",
  "password": "string"
}
```
***
# 42. PUT /api​/v1​/Users​/12121221212212

- HTTP-метод: PUT
- Полный URL запроса: https://fakerestapi.azurewebsites.net/api/v1/Users/12121221212212
- Заголовки запроса: `-H  "accept: */*" -H  "Content-Type: application/json; v=1.0"`
- Тело запроса (при наличии):
```
{
  "id": 0,
  "userName": "string",
  "password": "string"
}
```
- Статус-код ответа: 400
- Тело ответа (при наличии). Если тело большое, то только его часть:
```
{
  "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
  "title": "One or more validation errors occurred.",
  "status": 400,
  "traceId": "00-c03b037b22b72a4586cbed6c1bdda024-71cd2ebf82cbf348-00",
  "errors": {
    "id": [
      "The value '12121221212212' is not valid."
    ]
  }
}
```
***
# 43. DELETE /api​/v1​/Users​/1

- HTTP-метод: DELETE
- Полный URL запроса: https://fakerestapi.azurewebsites.net/api/v1/Users/1
- Заголовки запроса: `-H  "accept: */*"`
- Тело запроса (при наличии):
- Статус-код ответа: 200
- Тело ответа (при наличии). Если тело большое, то только его часть:
***

# 44. DELETE /api​/v1​/Users​/12121221212212

- HTTP-метод: DELETE
- Полный URL запроса: https://fakerestapi.azurewebsites.net/api/v1/Users/12121221212212
- Заголовки запроса: `-H  "accept: */*"`
- Тело запроса (при наличии):
- Статус-код ответа: 400
- Тело ответа (при наличии). Если тело большое, то только его часть:
```
{
  "type": "https://tools.ietf.org/html/rfc7231#section-6.5.1",
  "title": "One or more validation errors occurred.",
  "status": 400,
  "traceId": "00-e8aec53ad67d664a99c0ceedee49f247-d2edff0849ceb549-00",
  "errors": {
    "id": [
      "The value '12121221212212' is not valid."
    ]
  }
}
```