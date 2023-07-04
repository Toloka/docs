# Остаток на счете

{% include [announce](../_includes/announce.md) %}

Получает информацию об остатке на счете.

## Запрос {#request}

{% list tabs %}

- Боевая версия

    ```bash
    GET https://toloka.dev/api/v1/requester
    Authorization: OAuth PlaceYourRealOAuthToken_Here
    ```

- Песочница

    ```bash
    GET https://sandbox.toloka.dev/api/v1/requester
    Authorization: OAuth PlaceYourRealOAuthToken_Here
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