# Изменить приоритет пула

Изменяет приоритет пула.

Если у вас несколько пулов и вы хотите, чтобы исполнителям один пул предлагался раньше другого — измените приоритет пула. Останавливать пул при этом не надо, пул должен быть в статусе «открыт» или «закрыт».

Приоритет — это число по шкале от 0 до 100. Чем больше число, тем быстрее пул будет размечен относительно других ваших пулов.

## Запрос {#request}

{% list tabs %}

- Боевая версия

  ```bash
  PATCH https://toloka.yandex.com/api/v1/pools/<pool_id>
  Authorization: OAuth <OAuth token>
  Content-Type: application/JSON
  ```

- Песочница

  ```bash
  PATCH https://sandbox.toloka.yandex.com/api/v1/pools/<pool_id>
  Authorization: OAuth <OAuth token>
  Content-Type: application/JSON
  ```
{% endlist %}

## Path-параметры {#path-params}

Параметр | Описание
----- | -----
**pool_id** | Идентификатор пула.


## Заголовки {#headers}

{% include [reusables-auth-content](../_includes/reusables/id-reusables/auth-content.md) %}


## Тело запроса {#body}

```json
{
   "priority": <from 0 to 100>
}
```
#|
||**Параметр** | **Описание**||
||**priority** | **integer**

Приоритет пула среди других пулов проекта с такой же стоимостью заданий и набором фильтров. Сначала исполнителям выдаются задания с большим приоритетом.
Возможные значения: от `0` до `100`.
По умолчанию значение `0`.||
|#


## Ответ {#response}

{% note info %}

Если пул архивирован, будет возвращен пустой ответ со статусом 409.

{% endnote %}


Содержит обновленную информацию о пуле (см. описание в разделе [Создать пул](create-pool.md#response)).
