# Изменить задание

{% include [announce](../_includes/announce.md) %}

Меняет перекрытие задания.

Вы можете:

- задать [числовое значение](create-task.md#overlap) или установить [бесконечное перекрытие](create-task.md#infinite), чтобы выдавать задание всем исполнителям (например, для обучающих заданий);
- добавить предварительные ответы или изменить [их значения](create-task.md#baseline), если они уже были заданы.

  Предварительные ответы используются для расчета уверенности в ответе при динамическом перекрытии (incremental relabeling, IRL);

- сделать из обычных заданий контрольные и тренировочные или отредактировать [ответы](create-task.md) и [подсказки](create-task.md) для уже существующих заданий.

  Контрольные задания — задания с правильными ответами. Используются для контроля качества ответов.

  Тренировочные задания — задания для обучения исполнителей. Тренировочные задания содержат правильные ответы и подсказки. Если исполнитель отвечает неправильно, на экран выводится подсказка. Исполнитель не может перейти к следующему заданию, пока не введет правильный ответ.

## Запрос {#request}

{% list tabs %}

- Боевая версия

    ```bash
    PATCH https://toloka.dev/api/v1/tasks/<task_id>
    Authorization: ApiKey PlaceYourRealApiKey_Here
    Content-Type: application/json
    ```

- Песочница

    ```bash
    PATCH https://sandbox.toloka.dev/api/v1/tasks/<task ID>
    Authorization: ApiKey PlaceYourRealApiKey_Here
    Content-Type: application/json
    ```

{% endlist %}

## Заголовки {#headers}

{% include [reusables-auth-content](../_includes/reusables/id-reusables/auth-content.md) %}

## Path-параметры {#path-params}

Параметр | Описание
----- | -----
**task_id** | Идентификатор задания.

## Тело запроса {#body}

#### Числовое значение перекрытия

```json
{
  "overlap": <new overlap value>,
  "infinite_overlap": false
}
```

#### Бесконечное перекрытие

```json
{
  "overlap": null,
  "infinite_overlap": true
}
```

#### Предварительные ответы

```json
{
  "baseline_solutions":[
    {
      "output_values":{<output data values>},
      "confidence_weight":<from 0 to 1>
    }
]}
```

#### Ответы и подсказки для контрольных и тренировочных заданий

```json
{
  "known_solutions":[
    {
      "output_values":{<output data values>},
      "correctness_weight":<from 0 to 1>
    }
  ],
  "message_on_unknown_solution": <message string>
}
```

## Ответ {#response}

Содержит [данные задания в формате JSON](create-task.md#body).