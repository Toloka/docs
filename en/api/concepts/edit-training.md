# Edit a training pool

Makes changes to a training pool.

{% note info %}

Learn about editing a main pool in the section [Edit pool](edit-pool.md).

{% endnote %}

## Request {#request}

{% list tabs %}

- Production version

    ```bash
    PUT https://toloka.yandex.com/api/v1/trainings/<training_id>
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON

    {<training parameters, including updated ones>}
    ```

- Sandbox

    ```bash
    PUT https://sandbox.toloka.yandex.com/api/v1/trainings/<training_id>
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON

    {<training parameters, including updated ones>}
    ```

{% endlist %}

## Path parameters {#path-params}

Parameter | Overview
----- | -----
**training_id** | Pool ID.

## Headers {#headers}

Title | Overview
----- | -----
**Authorization** | A token for account authorization. Add OAuth as a prefix.
**Content-Type** | Specifies the data format in the request body.

## Request body {#body}

In the request body, specify **all** the pool [parameters](create-training.md#training-param), including those that are updated.

## Response {#response}

Contains information about a modified training pool (see the description in the [Create a training pool](create-training.md#response) section).