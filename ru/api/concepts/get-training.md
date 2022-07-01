# Получить свойства обучения

Получает свойства обучающего пула.

Идентификатор обучающего пула можно узнать из [списка обучающих пулов](get-training-list.md).

## Запрос {#request}

{% list tabs %}

- Боевая версия

  ```bash
  GET https://toloka.yandex.com/api/v1/trainings/<training_id>
  Authorization: OAuth <OAuth token>
  ```

- Песочница

  ```bash
  GET https://sandbox.toloka.yandex.com/api/v1/trainings/<training_id>
  Authorization: OAuth <OAuth token>
  ```
{% endlist %}

## Path-параметры {#path-params}

Параметр | Описание
----- | -----
**training_id** | Идентификатор пула.


## Заголовки {#headers}

{% include [reusables-auth](../_includes/reusables/id-reusables/auth.md) %}


## Ответ {#response}

Содержит сведения об обучающем пуле (см. описание в разделе [Создать обучение](create-training.md#response)).
