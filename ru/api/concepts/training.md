# Обзор

{% include [deprecate](../../_includes/deprecate.md) %}

## Описание {#description}

Обучающий пул — это неоплачиваемые страницы заданий. Обучающий пул должен быть привязан к основному пулу.

После выполнения обучающего пула исполнителю присваивается навык, значение которого — процент правильных ответов. Если процент выше или равен значению **Уровень прохождения** в привязанном пуле, то исполнителю станет доступен основной пул.

- Обучающий пул — задания для обучения исполнителей. Тренировочные задания содержат правильные ответы и подсказки. Если исполнитель отвечает неправильно, на экран выводится подсказка. Исполнитель не может перейти к следующему заданию, пока не введет правильный ответ.

## Методы {#methods}

#|
||**Метод** | **Эндпоинт** | **Описание**||
||POST | [/trainings](create-training.md) |{% include [create-training-create](../_includes/concepts/create-training/id-create-training/create.md) %}||
||PUT | [/trainings/<training_pool_id>](edit-training.md) |{% include [edit-training-edit](../_includes/concepts/edit-training/id-edit-training/edit.md) %}||
||POST | [/trainings/<training_pool_id>/open](open-training.md) |{% include [open-training-open](../_includes/concepts/open-training/id-open-training/open.md) %}||
||POST | [/trainings/<training_pool_id>/close](close-training.md) |{% include [close-training-close](../_includes/concepts/close-training/id-close-training/close.md) %}||
||POST | [/training/<training_pool_id>/archive](archive-training.md) |{% include [archive-training-archive](../_includes/concepts/archive-training/id-archive-training/archive.md) %}||
||POST | [/training/<training_pool_id>/clone](clone-training.md) |{% include [clone-training-clone](../_includes/concepts/clone-training/id-clone-training/clone.md) %}||
||GET | [/trainings](get-training-list.md) |{% include [get-training-list-get-list](../_includes/concepts/get-training-list/id-get-training-list/get-list.md) %}||
||GET | [/trainings/<training_pool_id>](get-training.md) |{% include [get-training-get-settings](../_includes/concepts/get-training/id-get-training/get-settings.md) %}||
|#

## Узнайте больше {#links}

- [Подробнее о обучающих пулах](../../guide/concepts/train.md)