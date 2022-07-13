# Обзор

## Описание {#description}

Вы можете создать подписку и получать уведомления от Толоки при наступлении определенных событий, например:

- закрытие пула;
- переход задания в указанный статус;
- появление агрегированной оценки по динамическому перекрытию.

События, о наступлении которых вы хотите получать уведомления, определяются на этапе [создания подписки](put-webhook-subscriptions.md).

Уведомления по подписке приходят в формате JSON. Описание данных см. в разделе [Формат уведомлений](using-webhook-subscriptions.md).

Для создания подписки оставьте запрос в форму [Проблемы с настройкой проекта]({{ requester-support }}), чтобы согласовать с нами URL.

## Методы {#methods}

#|
||**Метод** | **Эндпоинт** | **Описание** ||
||PUT | [/webhook-subscriptions](put-webhook-subscriptions.md) | {% include [put-webhook-subscriptions-create](../_includes/concepts/put-webhook-subscriptions/id-put-webhook-subscriptions/create.md) %}||
||GET | [/webhook-subscriptions/<subscription_id>](get-webhook-subscriptions.md) | {% include [get-webhook-subscriptions-get-subscription](../_includes/concepts/get-webhook-subscriptions/id-get-webhook-subscriptions/get-subscription.md) %}||
||GET | [/webhook-subscriptions](get-webhook-subscriptions-list.md) | {% include [get-webhook-subscriptions-list-get-list](../_includes/concepts/get-webhook-subscriptions-list/id-get-webhook-subscriptions-list/get-list.md) %}||
||DELETE | [/webhook-subscriptions/<subscription_id>](delete-webhook-subscriptions.md) | {% include [delete-webhook-subscriptions-delete-subscription](../_includes/concepts/delete-webhook-subscriptions/id-delete-webhook-subscriptions/delete-subscription.md) %}||
||POST | [/webhook-subscriptions/<subscription_id>/test](post-webhook-subscriptions.md) | {% include [post-subscription](../_includes/concepts/post-webhook-subscriptions/post-subscription.md) %}||
|#