## Задание 1
Ссылка на страницу, которую необходимо протестировать:

>https://widgets.inssmart.ru/contract/mortgage/?appId=ebb867fc-3483-5a8f-ad54-639ff255e57e&secret=c63d2d79-4c17-5e6c-b30f-7ac95577d2ab

*Внимание! Ссылка была изменена!*

Задача:
1. Составьте перечень проверок  в google sheets.
2. Сгруппируйте проверки по категориям на ваше усмотрение, расставьте приоритеты.
3. Произведите тестирование по составленному чек-листу, найдите и опишите ошибки.
4. Составьте отчет проверки в формате, который Вы считаете правильным и использовали бы в реальной ситуации.
5. Опишите принципы, по которым Вы расставляли приоритеты.

Условия:
Проверку необходимо сделать только для первого экрана, экран с предложениями и последующие тестировать не нужно.

Критерии оценки по приоритетам:
1. Категоризация и приоритезация ошибок.
2. Найденные ошибки, качество и проработка чек-листа.
3. Качество составления документов. 
4. Оценка времени проверки


## Задание 2
Коллекция в swagger, с которой предстоит работать: https://petstore.swagger.io/

>Base URL: https://petstore.swagger.io/v2/<br>
Headers: 'content-type': `application/json`


Вам необходимо на основе этой коллекции, создать коллекцию в Postman
Нужно будет работать с запросами:

1. Создать нового питомца (метод `POST /pet`)
Прописать скрипт, который берет из тела ответа id созданного питомца и записывает в 
окружение (Environment).

Подсказка, скрипт прописывается во вкладке «tests», для записи переменной в 
окружение можно использовать pm.environment

2. Запросить питомца по id (метод `GET /pet/{petId}`) используя в запросе ранее 
записанную переменную из окружения
Прописать скрипт, который будет брать тело ответа, менять параметр «status» на 
«sold» (продан) и перенаправлять его в запрос на изменение питомца (метод `PUT 
/pet`)

Подсказка, скрипт прописывается во вкладке «tests», для перенаправления запроса 
можно использовать pm.sendRequest

3. Коллекцию необходимо экспортировать (Export/ Export Collection) и отправить нам.

## Задание 3 
Вам потребуется linux консоль

Необходимо создать текстовый файл следующего содержания:

au<br>
hh<br>
ha<br>
fa<br>
jj<br>
kl<br>
lp<br>
at<br>
fa

И вывести из него количество повторяющихся строк, где есть буква “а”.
