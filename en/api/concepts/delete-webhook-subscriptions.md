# Delete a subscription

{% include [announce](../_includes/announce.md) %}

Deletes a subscription.

## Request {#request}

{% note tip %}

**Try our [new API reference](https://toloka.ai/docs/api/api-reference/#delete-/webhook-subscriptions/-id-):** more parameter details, request/response examples, and code samples in various programming languages, including the [Toloka-Kit](../../toloka-kit/index.md) usage samples.

{% endnote %}

{% list tabs %}

- Production version

    ```bash
    DELETE https://toloka.dev/api/v1/webhook-subscriptions/<subscription_id>
    Authorization: OAuth <OAuth token>
    ```

- Sandbox

    ```bash
    DELETE https://sandbox.toloka.dev/api/v1/webhook-subscriptions/<subscription_id>
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

If the request is successful, the server returns the `204 No Content` or `404 Not Found` HTTP operation status.

{% include [contact-support](../../guide/_includes/contact-support.md) %}