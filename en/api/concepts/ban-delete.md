# Unblock access

Removes a ban.

## Request {#query-params}

{% list tabs %}

- Production version

    ```bash
    DELETE https://toloka.yandex.com/api/v1/user-restrictions/<ban_id>
    Authorization: OAuth <OAuth token>
    ```

- Sandbox

    ```bash
    DELETE https://sandbox.toloka.yandex.com/api/v1/user-restrictions/<ban_id>
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