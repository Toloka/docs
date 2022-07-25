# Introduction

The Toloka API lets you create or delete projects, configure them as accurately as possible, and receive a list of these projects.

You can:

- Set up a [project](./concepts/project.md) with a description of task settings (visual appearance, input fields, and so on).

- Create a [pool of tasks](./concepts/pool.md).

- Define the logic for [selecting Tolokers](./concepts/my_users.md) who will complete the tasks.

- Import [data for tasks](./concepts/tasks.md) (image URLs, text, and so on).

- [Receive](./concepts/result.md) and [review](./concepts/accept.md) responses.

Requests are sent to the Toloka API over the HTTPS protocol. The service returns data in JSON format.

For debugging tasks, Toloka provides a testing environment – the [sandbox](https://sandbox.toloka.yandex.ru). Once you have tested the settings, you can use the project and pool in the production version of Toloka (the only thing you need to change is the [request URL and the OAuth token](./concepts/access.md)).

{% include [global-community](../_includes/global-community.md) %}

{% include [social-media](../_includes/social-media.md) %}