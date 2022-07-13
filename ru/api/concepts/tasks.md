# Обзор

## Описание {#description}

Чтобы загрузить в пул задания, нужно сформировать JSON-объекты, которые содержат:

- входные данные задания (например, текст, URL картинок);
- правильные ответы (для контрольных заданий);
- подсказку (для тренировочных заданий).

Толока автоматически собирает задания на страницы. Вам нужно только указать количество заданий на каждой странице (ключ `mixer_config` в [пуле](pool.md)).

Если вы хотите сформировать страницы самостоятельно, используйте инструкции в разделе [Обзор](task-suite.md).

## Методы {#methods}

#|
||**Метод** | **Эндпоинт** | **Описание**||
||POST | [/tasks](create-task.md) |{% include [create-task-create](../_includes/concepts/create-task/id-create-task/create.md) %}||
||POST | [/tasks](create-task.md) |{% include [create-tasks-batch-create](../_includes/concepts/create-tasks-batch/id-create-tasks-batch/create.md) %}||
||GET | [/tasks/<task_id>](get-task.md) |{% include [get-task-get](../_includes/concepts/get-task/id-get-task/get.md) %}||
||GET | [/tasks](get-tasks-list.md) |{% include [get-tasks-list-get-list](../_includes/concepts/get-tasks-list/id-get-tasks-list/get-list.md) %}||
||PATCH | [/tasks/<task_id>](edit-task-overlap.md) |{% include [edit-task-overlap-edit-overlap](../_includes/concepts/edit-task-overlap/id-edit-task-overlap/edit-overlap.md) %}||
||PATCH | [/tasks/<task_id>/set-overlap-or-min](set-min-task-overlap.md) |{% include [set-min-task-overlap-set-min-overlap](../_includes/concepts/set-min-task-overlap/id-set-min-task-overlap/set-min-overlap.md) %}||
|#

## Слияние заданий {#task-merge}

Задания с полностью идентичными входными данными можно объединять. Это позволяет экономить средства, если одно и то же задание оказалось загруженным в разные пулы.

{% note alert %}

- Слияние заданий работает только в открытых пулах. Если в новый пул пришло задание, ранее размеченное в уже закрытом или архивном пуле, то задания не будут объединены.
- Слияние заданий можно применить только к основным заданиям.

{% endnote %}

Полученный ответ на задание будет автоматически назначен другому заданию, если:

- оба задания имеют одни и те же входные данные;
- они находятся в разных пулах одного проекта;
- идентичное задание доступно ответившему исполнителю;
- оно имеет количество ответов меньшее, чем перекрытие.

Ответ будет записан с нулевой ценой, а перекрытие уменьшено на единицу.

Опция доступна только для основных заданий без отложенной приемки, загруженных через [«умное смешивание»]({{ requester-task-upload }}).

Чтобы активировать слияние заданий в проекте, нужно в [проекте](project.md) указать флаг `"assignments_automerge_enabled": true`.

## Узнайте больше {#links}

 Подробнее о формировании страниц заданий см. в документе [Руководство заказчика]({{ requester-pool-main }}).