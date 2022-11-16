# Обзор

{% include [deprecate](../../_includes/deprecate.md) %}

## Описание {#description}

В результате некоторых запросов к API (открытие и закрытие пула, отправка пула или проекта в архив, загрузка страниц заданий, выдача бонусов) создается асинхронная операция, выполняемая в фоновом режиме. Сведения об операции (например, статус, время создания) передаются в формате JSON.

Вы можете отслеживать выполнение операций с помощью API.

## Методы {#methods}

#|
||**Метод** | **Эндпоинт** | **Описание**||
||GET | [/operations](get-operations-list.md) |{% include [get-operations-list-operation-list](../_includes/concepts/get-operations-list/id-get-operations-list/operation-list.md) %}||
||GET | [/operations/<operation_id>](get-operation.md) |{% include [get-operation-operation](../_includes/concepts/get-operation/id-get-operation/operation.md) %}||
||GET | [/operations/<operation_id>/log](get-operation-log.md) |{% include [get-operation-log-operation-log](../_includes/concepts/get-operation-log/id-get-operation-log/operation-log.md) %}||
|#