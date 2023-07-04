# Проверка заданий

{% include [announce](../_includes/announce.md) %}

Проверить задания вручную и отклонить их, если задание выполнено неудовлетворительно. Чтобы принять или отклонить полученные ответы, измените статус страницы заданий с помощью PATCH-запроса к ресурсу `/assignments/<id выдачи страницы заданий>`:

- Принять ответы: измените статус `SUBMITTED` на `ACCEPTED`.

- Отклонить ответы: измените статус `SUBMITTED` на `REJECTED`.

- Изменить решение об отклонении: измените статус `REJECTED` на `ACCEPTED`.

Чтобы отклоненные задания отправлялись на повторное выполнение другим исполнителям, добавьте в пул блок контроля качества (см. [Повторное выполнение заданий](restore-task-overlap.md)).

## Запрос {#request}

{% list tabs %}

- Боевая версия

    ```bash
    PATCH https://toloka.dev/api/v1/assignments/<task_suite_assignment_id>
    Authorization: OAuth PlaceYourRealOAuthToken_Here
    Content-Type: application/json
    ```

- Песочница

    ```bash
    PATCH https://sandbox.toloka.dev/api/v1/assignments/<task_suite_assignment_id>
    Authorization: OAuth PlaceYourRealOAuthToken_Here
    Content-Type: application/json
    ```

{% endlist %}

## Path-параметры {#path-params}

Параметр | Описание
----- | -----
**task_suite_assignment_id** | Идентификатор выдачи страницы заданий.

## Заголовки {#headers}

{% include [reusables-auth-content](../_includes/reusables/id-reusables/auth-content.md) %}

## Тело запроса {#body}

```json
{
  "status": "ACCEPTED",
  "public_comment": "Well done!"
}
```

#|
||**Параметр**| **Описание**||
||**status** | **string**

Статус выданной страницы заданий. Можно перечислить несколько статусов через запятую:

- `ACTIVE` — выполняется исполнителем;
- `SUBMITTED` — выполнена, но не проверена;
- `ACCEPTED` — принята заказчиком;
- `REJECTED` — отклонена заказчиком;
- `SKIPPED` — пропущена исполнителем;
- `EXPIRED` — истек срок выполнения заданий.||
||**public_comment** | **string**

Комментарий исполнителю.
Максимальная длина: 2048 символов.||
|#

## Ответ {#response}

Ответ содержит измененные значения полей:

```json
{
  "status": "ACCEPTED",
  "public_comment": "Well done!",
  "bonus_ids": [10]
}
```

#|
||**Параметр**| **Описание**||
||**status** | **string**

Статус выданной страницы заданий. Можно перечислить несколько статусов через запятую:

- `ACTIVE` — выполняется исполнителем;
- `SUBMITTED` — выполнена, но не проверена;
- `ACCEPTED` — принята заказчиком;
- `REJECTED` — отклонена заказчиком;
- `SKIPPED` — пропущена исполнителем;
- `EXPIRED` — истек срок выполнения заданий.||
||**public_comment** | **string**

Комментарий исполнителю.
Максимальная длина: 2048 символов.||
||**bonus_ids[]** | **array of strings**

Идентификаторы выплаченных бонусов.||
|#