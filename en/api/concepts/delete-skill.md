# Remove a skill for a Toloker

{% include [announce](../_includes/announce.md) %}

Removes a skill for a Toloker.

## Request {#request}

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