# Отправить тестовое уведомление

{% include [announce](../_includes/announce.md) %}

Отправляет тестовое уведомление на URL, который указан в подписке.

## Запрос {#request}

{% list tabs %}

- Боевая версия

    ```bash
    POST https://toloka.dev/api/v1/webhook-subscriptions/<subscription_id>/test
    Authorization: OAuth PlaceYourRealOAuthToken_Here
    ```

- Песочница

    ```bash
    POST https://sandbox.toloka.dev/api/v1/webhook-subscriptions/<subscription_id>/test
    Authorization: OAuth PlaceYourRealOAuthToken_Here
    ```

{% endlist %}

## Path-параметры {#path-params}

Параметр | Описание
----- | -----
**subscription_id** | Идентификатор подписки.

## Заголовки {#headers}

{% include [reusables-auth](../_includes/reusables/id-reusables/auth.md) %}

## Пример тела уведомления {#body}

```json
{
  "uuid": "uuid",
  "event_time": "2020-02-14T12:22:58",
  "project_id": "projectId",
  "pool_id": "poolId",
  "type": "TEST_EVENT"
}
```

#|
||**Параметр**| **Описание**||
||**uuid** | **string \| обязательный**

Уникальный номер события, который генерируется при каждом новом запросе.||
||**event_time** | **string \| обязательный**

Время наступления события.||
||**project_id** | **string \| обязательный**

Идентификатор проекта, для которого создан пул.||
||**pool_id** | **string \| обязательный**

Идентификатор пула, для которого создана подписка.||
||**type** | **string \| обязательный**

Тип уведомления.
Принимает значение `TEST_EVENT` — тестовое уведомление.||
|#

## Ответ {#response}

Если запрос выполнен успешно, сервер возвращает HTTP-статус выполнения операции: «200 Ok» или «404 Not Found».

```json
{
  "success": true,
  "responseReceivedAt": "2020-02-14T12:22:58",
  "errorType": "WRONG_STATUS_CODE",
  "originalStatusCode": 1,
  "uuids": ["uuid1", ..."uuid5"]
}
```

#|
||**Параметр**| **Описание**||
||**success** | **boolean**

Статус выполнения запроса.
Принимает значение `true` или `false`.||
||**responseReceivedAt** | **string**

Дата и время создания подписки (UTC) в формате ISO 8601 `YYYY-MM-DDThh:mm:ss[.sss]`.||
||**errorType** | **string**

Тип ошибки.

Возможные значения:

- `WRONG_STATUS_CODE` — неверный код состояния.
- `TOO_MANY_CONNECTIONS` — превышен лимит соединений.
- `REQUEST_TIMEOUT` — таймаут запроса.
- `CONNECTION_ERROR` — ошибка соединения.
- `INTERNAL_ERROR` — внутренняя ошибка.
- `UNKNOWN` — неизвестная ошибка.||
||**originalStatusCode** | **int**

Код статуса ответа с URL-адреса подписки.||
||**uuids** | **array of strings**

Массив уникальных номеров события.||
|#