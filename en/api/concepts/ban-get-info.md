# Get information about a ban

Gets information about a ban.

## Request {#request}

{% list tabs %}

- Production version

    ```bash
    GET https://toloka.yandex.com/api/v1/user-restrictions/<ban_id>
    Authorization: OAuth <OAuth token>
    ```

- Sandbox

    ```bash
    GET https://sandbox.toloka.yandex.com/api/v1/user-restrictions/<ban_id>
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

## Response {#response}

Contains ban parameters in JSON format. Example:

```json
{
  "scope": "PROJECT",
  "user_id": "f25a5f41-94e8-49bf-977f-3611087a16b3",
  "project_id": "10",
  "private_comment": "Many mistakes",
  "will_expire": "2016-04-10T18:08:07",
  "id": "54",
  "created": "2016-03-28T18:08:07"
}
```

#|
|| Parameter | Overview ||
|| **scope** | **string**

The scope of the ban:

- `ALL_PROJECTS` — All the requester's projects.
- `PROJECT` — A single project (specify the `project_id`).
- `POOL` — A pool (specify the `pool_id`). ||
|| **user_id** | **string**

Toloker ID. ||
|| **project_id** | **string**

Required if `scope=PROJECT`.

The ID of the project that is blocked. ||
|| **pool_id** | **string**

Specified if `scope=POOL`.

The ID of the pool that is blocked. ||
|| **private_comment** | **string**

Comments with the reason for blocking access.

Maximum length: 499 characters. ||
|| **will_expire** | **string**

The UTC date and time when access will be restored. It uses ISO 8601 format: `YYYY-MM-DDThh:mm:ss[.sss]`. ||
|| **created** | **string**

The UTC date and time of the ban, in ISO 8601 format: `YYYY-MM-DDThh:mm:ss[.sss]`. ||
|| **id** | **string**

ID of the ban. ||
|#