# Account balance

{% include [announce](../_includes/announce.md) %}

Gets information about the account balance.

## Request {#request}

{% note tip %}

**Try our [new API reference](https://toloka.ai/docs/api/api-reference/#tag--requester):** more parameter details, request/response examples, and code samples in various programming languages, including the [Toloka-Kit](../../toloka-kit/index.md) usage samples.

{% endnote %}

{% list tabs %}

- Production version

    ```bash
    GET https://toloka.dev/api/v1/requester
    Authorization: OAuth <OAuth token>
    ```

- Sandbox

    ```bash
    GET https://sandbox.toloka.dev/api/v1/requester
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

{% include [contact-support](../../guide/_includes/contact-support.md) %}