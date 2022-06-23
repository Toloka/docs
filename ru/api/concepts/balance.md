# Остаток на счете

Получает информацию об остатке на счете.

## Запрос {#request}

{% list tabs %}

- Боевая версия

  ```json
  GET https://toloka.yandex.com/api/v1/requester
  Authorization: OAuth <OAuth token>
  ```

- Песочница

  ```json
  GET https://sandbox.toloka.yandex.com/api/v1/requester
  Authorization: OAuth <OAuth token>
  ```
{% endlist %}

## Заголовки {#headers}

{% include [reusables-auth](../_includes/reusables/id-reusables/auth.md) %}


## Ответ {#response}

Содержит информацию о заказчике и остатке на счете:

```json
{
  "balance": 121.30,
  "id": "566ec2b0ff0deeaae5f9d500",
  "public_name": {
    "EN": "Ya.Shield"   
  }
}
```

#|
||**Параметр**| **Описание**||

||**balance** | **float**

Остаток на счете в долларах.||
||**id** | **string**

Идентификатор заказчика.||
||**public_name** | **object**

Имя заказчика в Толоке.||
|#

