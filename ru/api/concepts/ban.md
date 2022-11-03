# Обзор

## Описание {#description}

Вы можете закрыть доступ исполнителя к одному или нескольким проектам. Это позволяет регулировать, какие исполнители будут выполнять задания. Например, можно выбрать исполнителей со значением навыка ниже N и заблокировать им доступ к заданиям. Вы также можете разблокировать доступ.

## Методы {#methods}

#|
||**Метод** | **Эндпоинт** | **Описание**||
||PUT | [/user-restrictions](ban-create.md) | {% include [ban-create-create](../_includes/concepts/ban-create/id-ban-create/create.md) %}||
||GET | [/user-restrictions](ban-get-list.md) | {% include [ban-get-list-get-list](../_includes/concepts/ban-get-list/id-ban-get-list/get-list.md) %}||
||GET | [/user-restrictions/<ban_id>](ban-get-info.md) | {% include [ban-get-info-get-info](../_includes/concepts/ban-get-info/id-ban-get-info/get-info.md) %}||
||DELETE | [/user-restrictions/<ban_id>](ban-delete.md) | {% include [ban-delete-delete](../_includes/concepts/ban-delete/id-ban-delete/delete.md) %}||
|#

## Узнайте больше {#links}

- [Описание блокировок в Руководстве заказчика]({{ requester-ban }})