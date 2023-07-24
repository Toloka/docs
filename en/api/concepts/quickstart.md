# Overview

{% note info %}

To better understand how Toloka works, first try setting up tasks in the Toloka interface using the [documentation](../../guide/concepts/main-steps.md) and then proceed to setting them up in the API.

{% endnote %}

For example, create a project with tasks where Tolokers will determine the type of shoes.

{% cut "Sample result" %}

![Sample result](../_images/shoes-interface.png =390x)

{% endcut %}

The sample project described under "Quick start" is for the sandbox. To set up tasks in the Toloka production version, change the [resource URL](https://toloka.ai/docs/api/api-reference/#overview--accessing-the-api) and [API key](https://toloka.ai/docs/api/api-reference/#overview--accessing-the-api) in all requests.

## Steps to follow {#algorithm}

1. Post your tasks.

    - [Choose a platform and get an API key](qs-placement.md#start).
    - [Create a project](qs-placement.md#project) (`POST /api/v1/projects`).
    - [Add a pool](qs-placement.md#pool) (`POST /api/v1/pools`).
    - [Upload the tasks](qs-placement.md#task) (`POST /api/v1/tasks`).
    - [Start (open) the pool](qs-placement.md#pool-run) (`POST /api/v1/pools/{pool_id}/open`).
    - [Check the tasks from the Toloker's interface](qs-placement.md#check).

1. Get the required results after the tasks are completed by the Tolokers.

    - [Get responses](qs-results.md) (`GET /api/v1/assignments?pool_id={pool_id}`).
    - [Download attachments](https://toloka.ai/docs/api/api-reference/#get-/attachments) (`GET /api/v1/attachments`).

## What's next {#what-next}

Read the [instructions on how to post tasks](qs-placement.md).

{% include [image-styles](../../../_includes/image-styles-internal.md) %}