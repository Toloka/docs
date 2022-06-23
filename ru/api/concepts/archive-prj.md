# Отправить проект в архив

Отправляет проект в архив.

Если проект не используется, его можно отправить в архив. Для выполнения операции все пулы в проекте должны быть [архивированы](archive-pool.md). Идентификатор проекта можно узнать из [списка проектов](get-prj-list.md).

## Запрос {#request}

{% list tabs %}

- Боевая версия

  ```json
  POST https://toloka.yandex.com/api/v1/projects/<project_id>/archive
  Authorization: OAuth <OAuth token>
  ```

- Песочница

  ```json
  POST https://sandbox.toloka.yandex.com/api/v1/projects/<project_id>/archive
  Authorization: OAuth <OAuth token>
  ```
{% endlist %}

## Path-параметры {#path-params}

Параметр | Описание
----- | -----
**project_id** | Идентификатор проекта.


## Заголовки {#headers}

{% include [reusables-auth](../_includes/reusables/id-reusables/auth.md) %}


## Ответ {#response}

Ответ содержит сведения о выполнении операции.

```json
{
  "id" : "57068577e4b0bf7b07a0256f",
  "type" : "PROJECT.ARCHIVE",
  "status" : "SUCCESS",
  "submitted" : "2016-04-07T16:06:15.902",
  "started" : "2016-04-07T16:06:15.902",
  "finished" : "2016-04-07T16:06:15.902",
  "progress" : 100,
  "parameters" : {
    "project_id" : "1"
  }
}
```
#|
||Параметр | Описание||
||**id** | **string**

Идентификатор операции.||
||**type** | **string**

Тип операции:
- `PROJECT.ARCHIVE` — отправка проекта в архив;||
||**status** | **string**

Статус операции:
- `PENDING` — выполнение не началось;
- `RUNNING` — выполняется;
- `SUCCESS` — успешно выполнена;
- `FAIL` — не выполнена.||
||**submitted** | **string**

Дата и время отправки запроса по UTC в формате ISO 8601: YYYY-MM-DDThh:mm:ss[.sss].||
||**started** | **string**

Дата и время начала операции по UTC в формате ISO 8601: YYYY-MM-DDThh:mm:ss[.sss].||
||**finished** | **string**

Дата и время окончания операции по UTC в формате ISO 8601: YYYY-MM-DDThh:mm:ss[.sss].||
||**progress** | **float**

Ход выполнения операции в процентах.||
||**parameters.project_id** | **string**

Идентификатор проекта.||
|#

В дальнейшем статус операции можно отслеживать с помощью запросов к ресурсу `/operations`. Подробнее см. в разделе [Обзор](operations.md).

