# Обзор

{% include [deprecate](../../_includes/deprecate.md) %}

## Описание {#description}

Разошлите сообщения исполнителям. Адресатов укажите [списком](message-send.md#spis) или отберите с помощью [фильтра](message-send.md#didi).

Отправленное сообщение добавляется в новую цепочку сообщений. До получения первого ответа цепочка сообщений находится в папке `UNREAD`. Если в цепочке несколько адресов и один из них отвечает, то будет создана новая цепочка сообщений.

## Методы

#|
||**Метод** | **Эндпоинт** | **Описание**||
||POST | [/message-threads/compose](message-send.md) | {% include [messages-send](../_includes/concepts/message-send/id-messages/send.md) %}||
||POST | [/message-threads/<thread_id>/reply](reply-message.md) |
{% include [reply-message-threads](../_includes/concepts/reply-message/id-reply/message-threads.md) %}||
||GET | [/message-threads](get-chain-list.md) |
{% include [get-chain-list-chain-list](../_includes/concepts/get-chain-list/id-get-chain-list/chain-list.md) %}||
||POST | [/message-threads/<thread_id>/add-to-folders](move-message.md) |
{% include [move-message-add-message-thread](../_includes/concepts/move-message/id-move-message/add-message-thread.md) %}||
||POST | [/message-threads/<thread_id>/remove-from-folders](move-message.md) |
{% include [move-message-remove-message-thread](../_includes/concepts/move-message/id-move-message/remove-message-thread.md) %}||
|#

## Узнайте больше

- [Получение и отправка сообщений](../../guide/concepts/messaging.md)