# Overview

Send messages to Tolokers. You can specify recipients in a [list](message-send.md#spis) or select Tolokers using a [filter](message-send.md#didi).

The sent message is added to a new message thread. Until the first response is received, the message chain is located in the `UNREAD` folder. If the thread contains several addresses and one of them responds, a new message thread will be created.

## Methods {#methods}

{% note tip %}

**Try our [new API reference](https://toloka.ai/docs/api/api-reference/#tag--message-thread):** more parameter details, request/response examples, and code samples in various programming languages, including the [Toloka-Kit](../../toloka-kit/index.md) usage samples.

{% endnote %}

Method | Endpoint | Overview
----- | ----- | -----
POST | [/message-threads/compose](message-send.md) | Sends a message to Tolokers.
POST | [/message-threads/<thread_id>/reply](reply-message.md) | Replies to a message thread.
GET | [/message-threads](get-chain-list.md) | Gets the list of message threads.
POST | [/message-threads/<thread_id>/add-to-folders](move-message.md) | Adds a message thread to a folder.
POST | [/message-threads/<thread_id>/remove-from-folders](move-message.md) | Deletes a message thread from a folder.

## See also {#see-also}

- [{#T}](../../guide/concepts/messaging.md)

{% include [contact-support](../../guide/_includes/contact-support.md) %}