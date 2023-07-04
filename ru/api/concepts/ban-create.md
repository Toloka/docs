# Заблокировать доступ к заданиям

{% include [announce](../_includes/announce.md) %}

Создает блокировку для исполнителя.

## Запрос {#request}

{% list tabs %}

- Боевая версия

    ```bash
    PUT https://toloka.dev/api/v1/user-restrictions
    Authorization: OAuth PlaceYourRealOAuthToken_Here
    Content-Type: application/json
    ```

- Песочница

    ```bash
    PUT https://sandbox.toloka.dev/api/v1/user-restrictions
    Authorization: OAuth PlaceYourRealOAuthToken_Here
    Content-Type: application/json
    ```

{% endlist %}

## Заголовки {#headers}

{% include [reusables-auth-content](../_includes/reusables/id-reusables/auth-content.md) %}

## Тело запроса {#body}

```json
{
  "scope": "PROJECT",
  "user_id": "f25a5f41-94e8-49bf-977f-3611087a16b3",
  "project_id": "10",
  "private_comment": "Many mistakes",
  "will_expire": "2016-04-10T18:08:07"
}
```

#|
||**Параметр**| **Описание**||
||**scope** | **string \| обязательный**

Область блокировки:

- `ALL_PROJECTS` — все проекты заказчика;
- `PROJECT` — проект (указывается `project_id`);
- `POOL` — пул (указывается `pool_id`).||
||**user_id** | **string \| обязательный**

Идентификатор исполнителя.||
||**project_id** | **string \| обязательный при условии**

Обязателен, если `scope=PROJECT`.

Идентификатор проекта, к которому заблокирован доступ.||
||**pool_id** | **string \| обязательный при условии**

Обязателен, если `scope=POOL`.

Идентификатор пула, к которому заблокирован доступ.||
||**private_comment** | **string**

Комментарий с причиной ограничения доступа.

Максимальная длина: 499 символов.||
||**will_expire** | **string**

Дата и время по UTC, когда доступ будет восстановлен. Формат даты ISO 8601: `YYYY-MM-DDThh:mm:ss[.sss]`.||
|#

## Ответ {#response}

Содержит идентификатор и параметры блокировки, дату ограничения доступа.

```json
{
  "scope": "PROJECT",
  "user_id": "f25a5f41-94e8-49bf-977f-3611087a16b3",
  "project_id": "10",
  "private_comment": "Many mistakes",
  "will_expire": "2016-04-10T18:08:07",
  "id": "54",
  "created": "2016-03-28T18:08:07"
}
```

#|
||**Параметр**| **Описание**||
||**scope** | **string**

Область блокировки:

- `ALL_PROJECTS` — все проекты заказчика;
- `PROJECT` — проект (указывается `project_id`);
- `POOL` — пул (указывается `pool_id`).||
||**user_id** | **string**

Идентификатор исполнителя.||
||**project_id** | **string**

Указывается, если `scope=PROJECT`.

Идентификатор проекта, к которому заблокирован доступ.||
||**pool_id** | **string**

Указывается, если `scope=POOL`.

Идентификатор пула, к которому заблокирован доступ.||
||**private_comment** | **string**

Комментарий с причиной ограничения доступа.

Максимальная длина: 499 символов.||
||**will_expire** | **string**

Дата и время по UTC, когда доступ будет восстановлен. Формат даты ISO 8601: `YYYY-MM-DDThh:mm:ss[.sss]`.||
||**created** | **string**

Дата и время по UTC блокировки в формате ISO 8601: `YYYY-MM-DDThh:mm:ss[.sss]`.||
||**id** | **string**

Идентификатор блокировки.||
|#