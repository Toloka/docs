# Get user metadata

Gets user data by `user_id`.

## Request {#request}

{% list tabs %}

- Production version

  ```bash
  GET https://toloka.yandex.com/api/v1/user-metadata/<user_id>
  Authorization: OAuth <OAuth token>
  ```

- Sandbox

  ```bash
  GET https://sandbox.toloka.yandex.com/api/v1/user-metadata/<user_id>
  Authorization: OAuth <OAuth token>
  ```

{% endlist %}

## Path parameters {#path-params}

Parameter | Overview
----- | -----
**user_id** | User ID.


## Headers {#headers}

Title | Overview
----- | -----
**Authorization** | A token for account authorization. Add OAuth as a prefix.


## Response {#response}

Contains user metadata in JSON format.

```
{
  "id": "123cdfggh",
  "country": "EN",
  "languages": [
    "en",
    "fr"
    ],
  "adultAllowed": true,
  "attributes": {
    "country_by_phone": "EN",
    "country_by_ip": "EN",
    "client_type": "TOLOKA_APP",
    "user_agent_type": "OTHER",
    "device_category": "SMARTPHONE",
    "os_family": "IOS",
    "os_version": 15,
    "os_version_major": 15,
    "os_version_minor": 0,
    "os_version_bugfix": 0
  }
}
```
