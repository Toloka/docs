# Потоковая обработка элементов разметки

Для проектов с постоянным потоком новых заданий, которые не нужно группировать в пакеты, элементы разметки можно загружать в потоковом режиме. Они начнут обрабатываться сразу после добавления.

Такой режим подходит, например, для заданий на модерацию.

## Добавьте элемент разметки {#create-item}

### HTTP-запрос {#create-item-request}

```json
POST /app-projects/{app_project_id}/items/bulk
Host: https://toloka.yandex.ru
Authorization: OAuth <OAuth token>
```

### Path-параметры {#create-item-path-params}

#|
||**Параметр**|**Описание**||
||**app_project_id**|**string**

ID проекта.||
|#

### Тело запроса {#create-item-body}

```json
{
   "items":[
      {
         "id": "1",
         "image_url": "https://tlk.s3.yandex.net/dataset/cats_vs_dogs/dogs/048e5760fc5a46faa434922b2447a527.jpg"
      }
   ]
}
```

#|
||**Ключ**|**Описание**||
||**items**|**array of objects**

Массив элементов разметки в соответствии с `input_spec` Ready-to-go-решения.

Можно отправлять массив как из одного элемента разметки, так и из нескольких в одном запросе.||
|#

### Ответ {#create-item-response}

Содержит массив ID, присвоенных созданным элементам разметки.

## Проверьте статус элементов разметки {#get-result}

{% note info %}

При добавлении элементов без пакета данных обработка начинается сразу. По [статусу](https://toloka.ai/ru/docs/toloka-apps/api/concepts/quickstart-api.html#quickstart-api__check-items) каждого элемента можно узнать о завершении обработки.

{% endnote %}

Для получения результатов используйте запрос списка элементов разметки с сортировкой по времени окончания обработки.

После выполнения запроса найдите последний размеченный элемент с самым поздним `finished_at`. Используйте его ID в качестве `last_saved_item_id` в следующем запросе. 

### HTTP-запрос {#get-result-request}

```json
GET /app-projects/{app_project_id}/items?sort=finished&after_id={last_saved_item_id}
Host: https://toloka.yandex.ru
Authorization: OAuth <OAuth token>
```

### Path-параметры {#get-result-path-params}

#|
||**Параметр**|**Описание**||
||**app_project_id**|**string**

ID проекта.||
||**last_saved_item_id**|**string**

ID элемента, относительно которого будут запрошены более свежие результаты.||
|#

### Ответ {#get-result-response}

Содержит элементы разметки, обработка которых уже завершена.

```json
200 OK

{
    "content": [
        {
            "id": "QlvdZj5d53QHj5Nvx9Vd",
            "app_project_id": "6Vv8kdlrjLYu7ZgPdezj",
            "status": "COMPLETED",
            "input_data": {
                "id": "1",
                "text": "Kate likes dogs."
            },
            "output_data": {
                "text": "Kate likes dogs.",
                "result": [
                    "OK"
                ],
                "confidence": 0.9998542274
            },
            "errors": [],
            "created_at": "2021-10-03T09:49:14.028",
            "started_at": "2021-10-03T10:10:27.561182",
            "finished_at": "2021-10-03T11:24:46.818213"
        },
        {
            "id": "nbeya74y4PpU1NkbaxA4",
            "app_project_id": "6Vv8kdlrjLYu7ZgPdezj",
            "status": "COMPLETED",
            "input_data": {
                "id": "2",
                "text": "I don’t like hooney."
            },
            "output_data": {
                "text": "I don’t like hooney.",
                "result": [
                    "BAD"
                ],
                "confidence": 0.9998542274
            },
            "errors": [],
            "created_at": "2021-10-03T09:49:14.028",
            "started_at": "2021-10-03T10:10:27.561182",
            "finished_at": "2021-10-03T11:24:47.704265"
        }
    ],
    "has_more": false
}
```