# Get training properties

Gets the properties of a training pool.

You can get the training pool ID from the [list of training pools](get-training-list.md).

## Request {#request}

{% list tabs %}

- Production version

    ```bash
    GET https://toloka.yandex.com/api/v1/trainings/<training_id>
    Authorization: OAuth <OAuth token>
    ```

- Sandbox

    ```bash
    GET https://sandbox.toloka.yandex.com/api/v1/trainings/<training_id>
    Authorization: OAuth <OAuth token>
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

## Response {#response}

Contains information about a training pool (see the description in the [Create a training pool](create-training.md#response) section).