# Introduction

The Toloka API lets you create or delete projects, configure them as accurately as possible, and receive a list of these projects.

You can:

- Set up a [project](https://toloka.ai/docs/api/api-reference/#tag--project) with a description of task settings (visual appearance, input fields, and so on).

- Create a [pool of tasks](https://toloka.ai/docs/api/api-reference/#tag--pool).

- Define the logic for [selecting Tolokers](concepts/my_users.md) who will complete the tasks.

- Import [data for tasks](https://toloka.ai/docs/api/api-reference/#tag--task) (image URLs, text, and so on).

- [Receive](https://toloka.ai/docs/api/api-reference/#get-/assignments) and [review](https://toloka.ai/docs/api/api-reference/#patch-/assignments/-id-) responses.

Requests are sent to the Toloka API over the HTTPS protocol. The service returns data in JSON format.

For debugging tasks, Toloka provides a testing environment — the [sandbox](https://sandbox.toloka.yandex.ru). Once you have tested the settings, you can use the project and pool in the production version of Toloka (the only thing you need to change is the [request URL and the API key](https://toloka.ai/docs/api/api-reference/#overview--accessing-the-api)).

{% note info %}

If you use [bespoke solutions](https://toloka.ai/pricing) and want to integrate your application with them or automate your requests, visit the [apps API documentation](https://toloka.ai/docs/api/apps-reference/) to learn how you can do that.

{% endnote %}

{% include [global-community](../_includes/global-community.md) %}

{% include [social-media](../_includes/social-media.md) %}