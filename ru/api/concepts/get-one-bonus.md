# Получить свойства бонуса

Получает свойства выданного бонуса.

## Запрос {#request}

{% list tabs %}

- Боевая версия

  ```bash
  GET https://toloka.yandex.com/api/v1/user-bonuses/<bonus_id>
  Authorization: OAuth <OAuth token>
  ```

- Песочница

  ```bash
  GET https://sandbox.toloka.yandex.com/api/v1/user-bonuses/<bonus_id>
  Authorization: OAuth <OAuth token>
  ```
{% endlist %}

## Path-параметры {#path-params}

Параметр | Описание
----- | -----
**bonus_id** | Идентификатор выданного бонуса.


## Заголовки {#headers}

{% include [reusables-auth](../_includes/reusables/id-reusables/auth.md) %}


## Ответ {#response}

Сведения о бонусе.

```json
{
  "user_id": "21c4f092ebad180cf56b9babe0ef9f19",
  "amount": 1.5,
  "assignment_id": "6946cefa-32af-4f62-b530-8d2c71fa2966",
  "private_comment": "Good job!",
  "public_title": {
    "EN": "Completed tasks"
  },
  "public_message": {
    "EN": "10 tasks successfully completed"
  },
  "without_message": false,
  "id": "2092",
  "created": "2021-02-12T10:37:36.631"
}
```

#|
||**Параметр**| **Описание**||
||**user_id** | **string**

Идентификатор исполнителя.||
||**amount** | **float**

Сумма бонуса в долларах.||
||**assignment_id** | **string**

Идентификатор ответа исполнителя на задание, за которое выплачивается бонус.||
||**private_comment** | **string**

Комментарий, доступный только заказчику.||
||**public_title** | **object**

Заголовок сообщения для исполнителя. Может быть на нескольких языках (сообщение придет на языке исполнителя). Формат: "`<язык RU/EN/TR/ID/FR>": "<текст заголовка>`".||
||**public_message** | **object**

Текст сообщения для исполнителя. Может быть текст на нескольких языках (сообщение придет на языке исполнителя). Формат: `"<язык RU/EN/TR/ID/FR>": "<текст сообщения>"`.||
||**without_message** | **boolean**

Позволяет не отправлять исполнителю сообщение о бонусе. По умолчанию `false`.

Для того чтобы выдать бонус без сообщения, нужно указать `null` для `public_title` и `public_message` и `true` для `without_message`.||
||**id** | **string**

Идентификатор бонуса.||
||**created** | **string**

Дата выдачи бонуса по UTC в формате ISO 8601 `YYYY-MM-DDThh:mm:ss[.sss]`||
|#
