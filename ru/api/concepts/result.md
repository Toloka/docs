# Получить ответы

Получает ответы во всех страницах заданий пула.

## Запрос {#request}

{% list tabs %}

- Боевая версия

  ```json
  GET https://toloka.yandex.com/api/v1/assignments
  Authorization: OAuth <OAuth token>
  ```

- Песочница

  ```json
  GET https://sandbox.toloka.yandex.com/api/v1/assignments
  Authorization: OAuth <OAuth token>
  ```
{% endlist %}

## Заголовки {#headers}

{% include [reusables-auth](../_includes/reusables/id-reusables/auth.md) %}


## Query-параметры {#query-params}

{% include [reusables-query](../_includes/reusables/id-reusables/query.md) %}


#|
||**Параметр**|**Описание**||
||**status** | **string**

Статус выданной страницы заданий. Можно перечислить несколько статусов через запятую:
- `ACTIVE` — выполняется исполнителем;
- `SUBMITTED` — выполнена, но не проверена;
- `ACCEPTED` — принята заказчиком;
- `REJECTED` — отклонена заказчиком;
- `SKIPPED` — пропущена исполнителем;
- `EXPIRED` — истек срок выполнения заданий.||
||**task_id** | **string**

Обязательно указать `task_id`, `pool_id`, либо `task_suite_id`.
Идентификатор задания на страницах, сформированных автоматически (с помощью «умного смешивания»). Вы получите ответы для страниц заданий, на которых есть указанное задание.||
||**task_suite_id** | **string**

{% include [result-necessarily-specify](../_includes/concepts/result/id-result/necessarily-specify.md) %}

Идентификатор страницы заданий.||
||**pool_id** | **string**

{% include [result-necessarily-specify](../_includes/concepts/result/id-result/necessarily-specify.md) %}

Идентификатор пула.||
||**user_id** | **string**

Идентификатор исполнителя.||
||**sort** | **string**

Параметры для сортировки:
- `id` — идентификатор выдачи страницы заданий;
- `created` — дата выдачи страницы заданий;
- `submitted` — дата выполнения страницы заданий;
- `skipped` — дата пропуска страницы заданий;
- `expired` — дата истечения срока выполнения страницы заданий;
- `accepted` — дата принятия заказчиком страницы заданий;
- `rejected` — дата отклонения заказчиком страницы заданий.

{% note info %}

Все даты имеют формат ISO 8601 YYYY-MM-DDThh:mm:ss[.sss].

{% endnote %}

{% include [get-tasks-list-about-sorting](../_includes/concepts/get-tasks-list/id-get-tasks-list/about-sorting.md) %}
||
||**Стандартные query-параметры** |
- **limit** (**integer** — ограничение на количество возвращаемых результатов. По умолчанию — 50, максимум — 300)
- **id_gt** (**string** — объекты с идентификатором больше указанного значения)
- **id_gte** (**string** — объекты с идентификатором больше или равным указанному значению)
- **id_lt** (**string** — объекты с идентификатором меньше указанного значения)
- **id_lte** (**string** — объекты с идентификатором меньше или равным указанному значению)
- **created_gt** (**string** — объекты, выданные или созданные после указанной даты)
- **created_gte** (**string** — объекты, выданные или созданные после указанной даты включительно)
- **created_lt** (**string** — объекты, выданные или созданные до указанной даты)
- **created_lte** (**string** — объекты, выданные или созданные до указанной даты включительно)
- **submitted_gt** (**string** — объекты, выданные или созданные после указанной даты)
- **submitted_gte** (**string** — объекты, выданные или созданные после указанной даты включительно)
- **submitted_lt** (**string** — объекты, выданные или созданные до указанной даты)
- **submitted_lte** (**string** — объекты, выданные или созданные до указанной даты включительно)
- **accepted_gt** (**string** — объекты, принятые заказчиком после указанной даты)
- **accepted_gte** (**string** — объекты, принятые заказчиком после указанной даты включительно)
- **accepted_lt** (**string** — объекты, принятые заказчиком до указанной даты)
- **accepted_lte** (**string** — объекты, принятые заказчиком до указанной даты включительно)
- **rejected_gt** (**string** — объекты, отклоненные заказчиком после указанной даты)
- **rejected_gte** (**string** — объекты, отклоненные заказчиком после указанной даты включительно)
- **rejected_lt** (**string** — объекты, отклоненные заказчиком до указанной даты)
- **rejected_lte** (**string** — объекты, отклоненные заказчиком до указанной даты включительно)
- **skipped_gt** (**string** — объекты, пропущенные после указанной даты)
- **skipped_gte** (**string** — объекты, пропущенные после указанной даты включительно)
- **skipped_lt** (**string** — объекты, пропущенные до указанной даты)
- **skipped_lte** (**string** — объекты, пропущенные до указанной даты включительно)
- **expired_gt** (**string** — объекты, у которых срок выполнения истекает после указанной даты)
- **expired_gte** (**string** — объекты, у которых срок выполнения истекает после указанной даты включительно)
- **expired_lt** (**string** — объекты, у которых срок выполнения истекает до указанной даты)
- **expired_lte** (**string** — объекты, у которых срок выполнения истекает до указанной даты включительно)||
|#

## Пример запроса {#request-example}

Можно настроить показ списка ответов частями (например, по 10 ответов):

1. Показать первые 10 бонусов, начиная с ответа с наименьшим идентификатором.
1. Показывать оставшиеся ответы по 10 штук в порядке возрастания.

**Показать первые 10 бонусов**

{% list tabs %}

- Боевая версия

  ```json
  GET https://toloka.yandex.com/api/v1/assignments?sort=id&limit=10
  Authorization: OAuth <OAuth token>
  ```

- Песочница

  ```json
  GET https://sandbox.toloka.yandex.com/api/v1/assignments?sort=id&limit=10
  Authorization: OAuth <OAuth token>
  ```
{% endlist %}

**Показывать остальные части с сортировкой по возрастанию идентификатора**

{% list tabs %}

- Боевая версия

  ```json
  GET >https://toloka.yandex.com/api/v1/assignments?sort=id&limit=10&id_gt=<ID of the last task suite from the previous response>
  Authorization: OAuth <OAuth token>
  ```

- Песочница

  ```json
  GET https://sandbox.toloka.yandex.com/api/v1/assignments?sort=id&limit=10&id_gt=<ID of the last task suite from the previous response>
  Authorization: OAuth <OAuth token>
  ```
{% endlist %}

## Ответ {#response}

[Сведения об ответах](get-assignment-id.md) в массиве `items`:

```json
{"items" : [{task suite #1}, {task suite #2}, ... {task suite #n}], "has_more": true}
```

