# Unblock access

{% include [announce](../_includes/announce.md) %}

Removes a ban.

## Request {#query-params}

{% note tip %}

**Try our [new API reference](https://toloka.ai/docs/api/api-reference/#delete-/user-restrictions/-id-):** more parameter details, request/response examples, and code samples in various programming languages, including the [Toloka-Kit](../../toloka-kit/index.md) usage samples.

{% endnote %}

{% list tabs %}

- Production version

    ```bash
    DELETE https://toloka.dev/api/v1/user-restrictions/<ban_id>
    Authorization: OAuth <OAuth token>
    ```

- Sandbox

    ```bash
    DELETE https://sandbox.toloka.dev/api/v1/user-restrictions/<ban_id>
    Authorization: OAuth <OAuth token>
    ```

{% endlist %}

## Path parameters {#path-params}

Parameter | Overview
----- | -----
**ban_id** | ID of the ban.

## Headers {#headers}

Title | Overview
----- | -----
**Authorization** | A token for account authorization. Add OAuth as a prefix.

{% include [contact-support](../../guide/_includes/contact-support.md) %}