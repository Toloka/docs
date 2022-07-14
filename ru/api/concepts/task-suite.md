# Обзор

## Описание {#description}

Страница заданий — это задания, размещенные на одной веб-странице. Если задания простые, можно добавлять 10—20 заданий на страницу. Не рекомендуем создавать длинные страницы, это снизит скорость загрузки данных у исполнителя.

Чтобы создать страницу заданий, загрузите в Толоку JSON, который содержит:

- входные данные заданий (например, текст, URL картинок);

- правильные ответы (для контрольных заданий);

- подсказки (для тренировочных заданий);

- параметры распределения заданий.


## Методы {#methods}

#|
||**Метод** | **Эндпоинт** | **Описание**||
||POST | [/task-suites](create-task-suite.md) |{% include [create-task-suite-create-one](../_includes/concepts/create-task-suite/id-create-task-suite/create-one.md) %}||
||POST | [/task-suites](create-task-suite.md) |{% include [create-task-suite-batch-create-batch](../_includes/concepts/create-task-suite-batch/id-create-task-suite-batch/create-batch.md) %}||
||GET | [/task-suites](get-task-suite-list.md) |{% include [get-task-suite-list-get-list](../_includes/concepts/get-task-suite-list/id-get-task-suite-list/get-list.md) %}||
||GET | [/task-suites/<task_suite_id>](get-task-suite.md) |{% include [get-task-suite-get-one](../_includes/concepts/get-task-suite/id-get-task-suite/get-one.md) %}||
||PATCH | [/task-suites/<task_suite_id>](edit-overlap.md) |{% include [edit-overlap-edit](../_includes/concepts/edit-overlap/id-edit-overlap/edit.md) %}||
||PATCH | [/task-suites/<task_suite_id>](edit-order.md) |{% include [edit-order-edit](../_includes/concepts/edit-order/id-edit-order/edit.md) %}||
||PATCH | [/task-suites/<task_suite_id>/set-overlap-or-min](set-min-suite-overlap.md) |{% include [set-min-suite-overlap-set-min-suite](../_includes/concepts/set-min-suite-overlap/id-set-min-suite-overlap/set-min-suite.md) %}||
|#

## Узнайте больше {#links}

- [Создание пула]({{ requester-pool-main }}) в Руководстве заказчика
- [Загрузка заданий в пул]({{ requester-task-upload }}) в Руковосдстве заказчика