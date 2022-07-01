# Account balance

Gets information about the account balance.

## Request {#request}

{% list tabs %}

- Production version

  ```bash
  GET https://toloka.yandex.com/api/v1/requester
  Authorization: OAuth <OAuth token>
  ```

- Sandbox

  ```bash
  GET https://sandbox.toloka.yandex.com/api/v1/requester
  Authorization: OAuth <OAuth token>
  ```

{% endlist %}

## Headers {#headers}

Title | Overview
----- | -----
**Authorization** | A token for account authorization. Add OAuth as a prefix.


## Response {#response}

Contains information about the requester and the account balance:

```json
{
  "balance": 121.30,
  "id": "566ec2b0ff0deeaae5f9d500",
  "public_name": {
    "EN": "Ya.Shield"
  }
}
```

#|
|| Parameter | Overview ||
|| **balance** | **float**

Account balance in US dollars. ||
|| **id** | **string**

Requester ID. ||
|| **public_name** | **object**

The requester's name in Toloka. ||
|#
