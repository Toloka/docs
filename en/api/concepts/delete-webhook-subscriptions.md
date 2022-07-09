# Delete a subscription

Deletes a subscription.

## Request {#request}

{% list tabs %}

- Production version

    ```bash
    DELETE https://toloka.yandex.com/api/v1/webhook-subscriptions/<subscription_id>
    Authorization: OAuth <OAuth token>
    ```

- Sandbox

    ```bash
    DELETE https://sandbox.toloka.yandex.com/api/v1/webhook-subscriptions/<subscription_id>
    Authorization: OAuth <OAuth token>
    ```

{% endlist %}

## Path parameters {#path-params}

Parameter | Overview
----- | -----
**subscription_id** | ID of the subscription.

## Headers {#headers}

Title | Overview
----- | -----
**Authorization** | A token for account authorization. Add OAuth as a prefix.

## Response {#response}

If the request is successful, the server returns the "204 No Content" or "404 Not Found" HTTP operation status.