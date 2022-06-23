# Создать обучение

Создает обучающий пул (обучение).

Созданному обучению автоматически присваивается идентификатор.

{% note alert %}

Вы можете отправить не более 20 таких запросов в минуту и не более 100 в день.

{% endnote %}


{% note info %}

О создании обычного пула читайте в разделе [Создать пул](create-pool.md).

{% endnote %}


## Запрос {#request}

{% list tabs %}

- Боевая версия

  ```json
  POST https://toloka.yandex.com/api/v1/trainings
  Authorization: OAuth <OAuth token>
  Content-Type: application/JSON
  ```

- Песочница

  ```json
  POST https://sandbox.toloka.yandex.com/api/v1/trainings
  Authorization: OAuth <OAuth token>
  Content-Type: application/JSON
  ```
{% endlist %}

## Заголовки {#headers}

{% include [reusables-auth-content](../_includes/reusables/id-reusables/auth-content.md) %}


## Тело запроса {#body}

```json
{
  "project_id": "654321",
  "private_name": "Selection for a labeling task",
  "inherited_instructions": false,
  "public_instructions": "Unpaid selection for a project: 10 tasks, 90% threshold.",
  "may_contain_adult_content": false,
  "assignment_max_duration_seconds": 600,
  "mix_tasks_in_creation_order": true,
  "shuffle_tasks_in_task_suite": true,
  "training_tasks_in_task_suite_count": 10,
  "task_suites_required_to_pass": 1,
  "retry_training_after_days": 7
}
```

#|
||**Параметр**| **Описание**||
||**project_id** | **string \| обязательный**

Идентификатор проекта, для которого создан обучающий пул.||
||**private_name** | **string \| обязательный**

Название обучающего пула (доступно только заказчику).||
||**inherited_instructions** | **boolean \| обязательный**

Указывает, использовать ли инструкцию проекта. Если для обучения нужна своя инструкция, то укажите ее в `public_instructions`.
По умолчанию значение `false`.||
||**may_contain_adult_content** | **boolean \| обязательный**

Присутствие контента для взрослых в заданиях.||
||**training_tasks_in_task_ suite_count** | **integer \| обязательный**
Количество обучающих заданий на одной странице.||
||**task_suites_required_to_ pass** | **integer**

Количество страниц, которые нужно успешно выполнить для назначения навыка и допуска к боевым заданиям.||
||**public_instructions** | **string**

Инструкция по выполнению обучающих заданий. Можно использовать любую HTML-разметку.||
||**assignment_max_duration_ seconds** | **integer**
Время на выполнение страницы заданий в секундах. Рекомендуется выделять на страницу заданий не менее 60 секунд (с учетом времени на загрузку страницы и отправку ответов).||
||**mix_tasks_in_creation_ order** | **boolean**
Выдаются ли обучающие задания в порядке загрузки:
- `true` — для формирования страниц задания берутся по порядку строк (сверху вниз) из загруженного файла;
- `false` — задания будут браться в случайном порядке.<br/> По умолчанию значение `true`.||
||**shuffle_tasks_in_task_suite** | **boolean**
Перемешиваются ли обучающие задания внутри каждой страницы:
- `true` — да;
- `false` — нет, они будут располагаться в том порядке, в каком были загружены.
По умолчанию значение `true`.||
||**retry_training_after_days** | **integer**

Через сколько дней станет доступно повторное прохождение.||
|#

## Ответ {#response}

Содержит сведения о созданном обучении.

```json
{
  "id": "123456",
  "project_id": "654321",
  "private_name": "Selection for a labeling task",
  "inherited_instructions": false,
  "public_instructions": "Unpaid selection for a project: 10 tasks, 90% threshold.",
  "may_contain_adult_content": false,
  "assignment_max_duration_seconds": 600,
  "mix_tasks_in_creation_order": true,
  "shuffle_tasks_in_task_suite": true,
  "training_tasks_in_task_suite_count": 10,
  "task_suites_required_to_pass": 1,
  "retry_training_after_days": 7,
  "owner": {
    "id": "ec00d2407f7241258d0faba610110d95",
    "myself": true
  },
  "status": "CLOSED",
  "created": "2021-02-24T18:12:57.962"
}
```

Помимо [параметров, которые задаются при создании обучающего пула,](#training-param) включает параметры, которые присваиваются пулу автоматически:

#|
||**Параметр**| **Описание**||
||**id** | **string**

Идентификатор обучающего пула.||
||**owner.id** | **string**

Идентификатор заказчика.||
||**owner.myself** | **boolean**
Проверяет, кому принадлежит объект:
- `true` — пользователю, который совершил запрос;
- `false` — другому аккаунту (сотруднику или владельцу).||
||**status** | **string**
Статус обучающего пула:
- `OPEN` — открыт;
- `CLOSED` — закрыт;
- `ARCHIVED` — архивный.||
||**created** | **string**<br/><br/>Дата и время создания обучающего пула по UTC в формате ISO 8601: YYYY-MM-DDThh:mm:ss[.sss].||
|#

