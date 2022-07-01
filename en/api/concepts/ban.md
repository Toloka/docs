# Overview

## Overview {#description}

You can block a Toloker's access to one or more projects. This lets you control which Tolokers will complete tasks. For example, you can select Tolokers with a skill value lower than N and block their access to tasks. You can also unblock access.

## Methods {#methods}

Method | Endpoint | Overview
----- | ----- | -----
PUT | [/user-restrictions](ban-create.md) | Blocks a Toloker from accessing tasks.
GET | [/user-restrictions](ban-get-list.md) | Gets the list of Toloker bans.
GET | [/user-restrictions/<ban_id>](ban-get-info.md) | Gets information about a ban.
DELETE | [/user-restrictions/<ban_id>](ban-delete.md) | Removes a ban.


## Learn more {#links}

- [Description of bans in the Requester's guide](https://toloka.ai/docs/guide/concepts/ban.html?lang=en)
