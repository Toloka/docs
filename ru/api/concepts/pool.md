# Обзор

## Описание {#description}

Пул — это страницы заданий, которые отправляются на выполнение единовременно. В свойствах пула
 нужно определить цену задания, перекрытие, [фильтры для отбора исполнителей](filters.md), [логику контроля качества](quality_control.md)
 и т. д.

Если в проекте несколько пулов, очередность их выполнения зависит от параметров:

- Пулы с одинаковыми настройками фильтров и платой за задание выдаются исполнителям в порядке, в котором эти пулы были запущены. Пул, запущенный раньше, будет выполняться быстрее. Вы можете [изменить порядок выполнения таких пулов](create-pool.md#priority).

- Пулы с разными настройками фильтров и/или разной платой за задание отправляются на выполнение при [открытии пула](open-pool.md).

{% note info %}

Перед выполнением любой новой операции, кроме создания пула, дождитесь завершения предыдущей (перехода в [статус](get-operation.md) `SUCCESS` или `FAIL`).

{% endnote %}

## Методы {#methods}

#|
||Метод | Эндпоинт | Описание||
||POST | [/pools](create-pool.md) | {% include [create-pool-create](../_includes/concepts/create-pool/id-create-pool/create.md) %}||
||POST | [/pools/<pool_id>/close-for-update](close-pool-for-update.md) | {% include [close-pool-for-update-close](../_includes/concepts/close-pool-for-update/id-close-pool-for-update/close.md) %}||
||PUT | [/pools/<pool_id>](edit-pool.md) | {% include [edit-pool-edit](../_includes/concepts/edit-pool/id-edit-pool/edit.md) %}||
||POST | [/pools/<pool_id>/open](open-pool.md) | {% include [open-pool-open](../_includes/concepts/open-pool/id-open-pool/open.md) %}||
||POST | [/pools/<pool_id>/close](close-pool.md) | {% include [close-pool-close](../_includes/concepts/close-pool/id-close-pool/close.md) %}||
||POST | [/pools/<pool_id>/archive](archive-pool.md) | {% include [archive-pool-archive](../_includes/concepts/archive-pool/id-archive-pool/archive.md) %}||
||POST | [/pools/<pool_id>/clone](clone-pool.md) | {% include [clone-pool-clone](../_includes/concepts/clone-pool/id-clone-pool/clone.md) %}||
||GET | [/pools](get-pool-list.md) | {% include [get-pool-list-get-list](../_includes/concepts/get-pool-list/id-get-pool-list/get-list.md) %}||
||GET | [/pools/<pool_id>](get-pool.md) | {% include [get-pool-get-settings](../_includes/concepts/get-pool/id-get-pool/get-settings.md) %}||
||PATCH | [/pools/pool_id>](set-priority-pool.md) | {% include [set-priority-pool-set-priority](../_includes/concepts/set-priority-pool/id-set-priority-pool/set-priority.md) %}||
|#

## Узнайте больше {#links}

- [Описание пула в Руководстве заказчика](../../guide/concepts/pool-main.md)