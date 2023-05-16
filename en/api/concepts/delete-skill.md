# Remove a skill for a Toloker

{% include [announce](../_includes/announce.md) %}

Removes a skill for a Toloker.

## Request {#request}

{% note tip %}

**Try our [new API reference](https://toloka.ai/docs/api/api-reference/#delete-/user-skills/-id-):** more parameter details, request/response examples, and code samples in various programming languages, including the [Toloka-Kit](../../toloka-kit/index.md) usage samples.

{% endnote %}

{% list tabs %}

- Production version

    ```bash
    DELETE https://toloka.dev/api/v1/user-skills/<id>
    Authorization: OAuth <OAuth token>
    ```

- Sandbox

    ```bash
    DELETE https://sandbox.toloka.dev/api/v1/user-skills/<id>
    Authorization: OAuth <OAuth token>
    ```

{% endlist %}

## Path parameters {#path-params}

Parameter | Overview
----- | -----
**id** | The ID of a Toloker's skill that is assigned to the "skill-Toloker" pair. You can find this ID using the [Get a list of Tolokers who have skills](get-user-skill-list.md) request.

## Headers {#headers}

Title | Overview
----- | -----
**Authorization** | A token for account authorization. Add OAuth as a prefix.

## See also {#see-also}

- [{#T}](../../guide/concepts/nav-delete.md)

{% include [contact-support](../../guide/_includes/contact-support.md) %}