# Receiving responses

{% include [announce](../_includes/announce.md) %}

This example was created in the sandbox. Therefore, you need to perform tasks as a trusted user to process the results:

1. Register as a Toloker in the [Toloka sandbox](https://sandbox.toloka.yandex.com/).

1. Log in to the sandbox with the requester's username and follow the **Add trusted users** link on the [Users](https://sandbox.toloka.yandex.com/requester/workers) page.

1. Click **Add user** and enter the username of the account you created.

1. Perform the tasks in the sandbox under the username of a trusted user.

If at least one task from the pool is completed, you can get responses.

In the example given, Tolokers were not required to upload any files as a response to tasks. Therefore, you can get the responses themselves.

## Get responses {#get-responses}

### Request {#get-responses-request}

In the `pool_id` query parameter, replace `<pool id>` with the ID of the pool you want to get responses for (the ID received in response to the [add pool request](qs-placement.md#pool)).

Next, use the `GET` method:

{% list tabs %}

- cURL

    Send a request from the command line using the cURL utility:

    ```bash
    curl -X GET \
         -H 'Authorization: OAuth <OAuth token>' \
    https://sandbox.toloka.dev/api/v1/assignments?pool_id=<pool id>
    ```

- Postman

    Fill in the fields:

    1. Request URL

        ```bash
        https://sandbox.toloka.dev/api/v1/assignments?pool_id=<pool id>
        ```

    1. Headers

        ```bash
        Authorization: OAuth <OAuth token>
        ```

{% endlist %}

### Response {#get-responses}

Toloker responses are returned in the `items` array in the following format:

```json
{
  "items": [
    {
      "id": "00000f80eb-–617d0d2f515c446d68cc2785",
      "task_suite_id": "00000f80eb-–617d0d2f515c446d68cc2783",
      "pool_id": "9876543",
      "user_id": "f2a33d6eb1d3c8f9c917adbf259c0539",
      "status": "ACCEPTED",
      "reward": 0.02,
      "tasks": [
        {
          "id": "00000f80eb--617d0cbba52cc70d7118c5bc",
          "input_values": {
            "image": "https://sandbox.toloka.dev/api/proxy/thgn1/photos/3.jpg"
          },
          "pool_id": "9876543",
          "overlap": 2,
          "infinite_overlap": false,
          "reserved_for": [],
          "unavailable_for": [],
          "created": "2021-10-30T09:13:31.153",
          "remaining_overlap": 0
        },
        {
          "id": "00000f80eb--617d0cbaa52cc70d7118c5b8",
          "input_values": {
            "image": "https://sandbox.toloka.dev/api/proxy/thgn1/photos/1.jpg"
          },
          "pool_id": "9876543",
          "overlap": 2,
          "infinite_overlap": false,
          "reserved_for": [],
          "unavailable_for": [],
          "created": "2021-10-30T09:13:30.951",
          "remaining_overlap": 0
        },
        {
          "id": "00000f80eb--617d0cbba52cc70d7118c5ba",
          "input_values": {
            "image": "https://sandbox.toloka.dev/api/proxy/thgn1/photos/2.jpg"
          },
          "pool_id": "9876543",
          "overlap": 2,
          "infinite_overlap": false,
          "reserved_for": [],
          "unavailable_for": [],
          "created": "2021-10-30T09:13:31.069",
          "remaining_overlap": 0
        }
      ],
      "solutions": [
        {
          "output_values": {
            "result": "boots"
          }
        },
        {
          "output_values": {
            "result": "sneakers"
          }
        },
        {
          "output_values": {
            "result": "boots"
          }
        }
      ],
      "mixed": true,
      "automerged": false,
      "created": "2021-10-30T09:15:27.217",
      "submitted": "2021-10-30T09:15:36.570",
      "accepted": "2021-10-30T09:15:36.570",
      "owner": {
        "id": "9ea475935832de1dde0ece716c9df178",
        "myself": true
      }
    },
    {
      "id": "00000f80eb--617d0d82a52cc70d7118c614",
      "task_suite_id": "00000f80eb--617d0d82a52cc70d7118c612",
      "pool_id": "1016043",
      "user_id": "d01e518a746b149b07b81a10f4cfb1c2",
      "status": "ACCEPTED",
      "reward": 0.02,
      "tasks": [
        {
          "id": "00000f80eb--617d0cbba52cc70d7118c5ba",
          "input_values": {
            "image": "https://sandbox.toloka.dev/api/proxy/thgn1/photos/2.jpg"
          },
          "pool_id": "9876543",
          "overlap": 2,
          "infinite_overlap": false,
          "reserved_for": [],
          "unavailable_for": [],
          "created": "2021-10-30T09:13:31.069",
          "remaining_overlap": 0
        },
        {
          "id": "00000f80eb--617d0cbba52cc70d7118c5bc",
          "input_values": {
            "image": "https://sandbox.toloka.dev/api/proxy/thgn1/photos/3.jpg"
          },
          "pool_id": "9876543",
          "overlap": 2,
          "infinite_overlap": false,
          "reserved_for": [],
          "unavailable_for": [],
          "created": "2021-10-30T09:13:31.153",
          "remaining_overlap": 0
        },
        {
          "id": "00000f80eb--617d0cbaa52cc70d7118c5b8",
          "input_values": {
            "image": "https://sandbox.toloka.dev/api/proxy/thgn1/photos/1.jpg"
          },
          "pool_id": "9876543",
          "overlap": 2,
          "infinite_overlap": false,
          "reserved_for": [],
          "unavailable_for": [],
          "created": "2021-10-30T09:13:30.951",
          "remaining_overlap": 0
        }
      ],
      "solutions": [
        {
          "output_values": {
            "result": "sneakers"
          }
        },
        {
          "output_values": {
            "result": "boots"
          }
        },
        {
          "output_values": {
            "result": "sneakers"
          }
        }
      ],
      "mixed": true,
      "automerged": false,
      "created": "2021-10-30T09:16:50.542",
      "submitted": "2021-10-30T09:16:59.739",
      "accepted": "2021-10-30T09:16:59.739",
      "owner": {
        "id": "9ea475935832de1dde0ece716c9df178",
        "myself": true
      }
    }
  ],
  "has_more": false
}
```

## Learn more {#links-qs-results}

- [HTTP methods used for processing Toloker responses](get-response.md)
- [HTTP methods used for processing files in Toloker responses](attachments.md)
- [Response aggregation](aggregated-solutions.md)
- [Using libraries](libraries.md)

{% include [contact-support](../../guide/_includes/contact-support.md) %}