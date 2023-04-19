# Overview

You can block a Toloker's access to one or more projects. This lets you control which Tolokers will complete tasks. For example, you can select Tolokers with a skill value lower than N and block their access to tasks. You can also unblock access.

## Methods {#methods}

{% note tip %}

**Try our [new API reference](https://toloka.ai/docs/api/api-reference/#tag--user-restriction):** more parameter details, request/response examples, and code samples in various programming languages, including the [Toloka-Kit](../../toloka-kit/index.md) usage samples.

{% endnote %}

Method | Endpoint | Overview
----- | ----- | -----
PUT | [/user-restrictions](ban-create.md) | Blocks a Toloker from accessing tasks.
GET | [/user-restrictions](ban-get-list.md) | Gets the list of Toloker bans.
GET | [/user-restrictions/<ban_id>](ban-get-info.md) | Gets information about a ban.
DELETE | [/user-restrictions/<ban_id>](ban-delete.md) | Removes a ban.

## See also {#see-also}

- [{#T}](../../guide/concepts/ban.md)

{% include [contact-support](../../guide/_includes/contact-support.md) %}