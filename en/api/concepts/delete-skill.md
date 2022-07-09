# Remove a skill for a Toloker

Removes a skill for a Toloker.

## Request {#request}

{% list tabs %}

- Production version

    ```bash
    DELETE https://toloka.yandex.com/api/v1/user-skills/<id>
    Authorization: OAuth <OAuth token>
    ```

- Sandbox

    ```bash
    DELETE https://sandbox.toloka.yandex.com/api/v1/user-skills/<id>
    Authorization: OAuth <OAuth token>
    ```

{% endlist %}

## Path parameters {#path-params}

Parameter | Overview
----- | -----
**id** | The ID of a Toloker's skill that is assigned to the "skill-Toloker" pair.

## Headers {#headers}

Title | Overview
----- | -----
**Authorization** | A token for account authorization. Add OAuth as a prefix.