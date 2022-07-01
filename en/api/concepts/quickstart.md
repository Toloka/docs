# Overview

{% note info %}

To better understand how Toloka works, first try setting up tasks in the Toloka interface using the [Requester's guide](https://toloka.ai/docs/guide/concepts/main-steps.html?lang=en) and then proceed to setting them up in the API.

{% endnote %}


For example, create a project with tasks where Tolokers will determine the type of animal.


{% cut "Sample result" %}

![](../_images/cat-interface.png)

{% endcut %}

The sample project described under "Quick start" is for the sandbox. To set up tasks in the Toloka production version, change the [resource URL](access.md#urls) and [OAuth token](access.md#token) in all requests.

## Steps to follow {#algorithm}

1. Post your tasks.

    - [Choose a platform and get a token](./qs-placement.md#start).
    - [Create a customizable project](./qs-placement.md#project) (`POST /api/v1/projects`).
    - [Add a pool](./qs-placement.md#pool) (`POST /api/v1/pools`).
    - [Upload the tasks](./qs-placement.md#task) (`POST /api/v1/tasks`).
    - [Start (open) the pool](./qs-placement.md#pool-run) (`POST /api/v1/pools/<pool_id>/open`).
    - [Check the tasks from the Toloker's interface](./qs-placement.md#check).

1. Get the required results after the tasks are completed by the Tolokers.

    - [Get responses](qs-results.md) (`GET /api/v1/assignments?pool_id=<pool ID>`).
    - [Download attachments](get-attachment-list.md) (`GET /api/v1/attachments`).



## What's next {#what-next}

Read the [instructions on how to post tasks](./qs-placement.md).
