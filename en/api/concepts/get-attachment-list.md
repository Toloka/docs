# Get the list of files

{% include [announce](../_includes/announce.md) %}

Gets the list of files saved in Toloka.

{% note warning %}

Files are downloaded not in the order in which they were uploaded to the server.

{% endnote %}

## Request {#request}

{% list tabs %}

- Production version

  ```bash
  GET https://toloka.dev/api/v1/attachments
  Authorization: OAuth <OAuth token>
  ```

- Sandbox

  ```bash
  GET https://sandbox.toloka.dev/api/v1/attachments
  Authorization: OAuth <OAuth token>
  ```

{% endlist %}

## Headers {#headers}

Title | Overview
----- | -----
**Authorization** | A token for account authorization. Add OAuth as a prefix.

## Query parameters {#query-params}

{% include [query-params](../_includes/query-params.md) %}

#|
|| Parameter | Overview ||
|| **pool_id** | **string**

Pool ID. ||
|| **assignment_id** | **string**

ID of the task suite assignment. ||
|| **name** | **string**

File name. ||
|| **type** | **string**

Attachment type. Currently the key can have only one value — `ASSIGNMENT_ATTACHMENT`. ||
|| **user_id** | **string**

ID of the Toloker who uploaded the file(s). ||
|| **sort** | **string**

Parameters to sort by:

- `id` — The file identifier.
- `created` — The date when the file was uploaded, in UTC using ISO 8601 format: `YYYY-MM-DDThh:mm:ss[.sss]`.

To learn how to configure sorting, see [Sorting the list of objects](sorting.md). ||
|| **Standard query parameters** | [limit](standard-query-parameters.md#limit), [id_gt](standard-query-parameters.md#id_gt), [id_gte](standard-query-parameters.md#id_gte), [id_lt](standard-query-parameters.md#id_lt), [id_lte](standard-query-parameters.md#id_lte), [created_gt](standard-query-parameters.md#created_gt), [created_gte](standard-query-parameters.md#created_gte), [created_lt](standard-query-parameters.md#created_lt), [created_lte](standard-query-parameters.md#created_lte). ||
|#

## Query example {#request-example}

You can set up the display of the list of files in parts (for example, 10 files at a time):

1. Show the first 10 files, starting with the one with the lowest ID.
1. Show the remaining files (10 at a time) in ascending order.

**Show the first 10 files**

{% list tabs %}

- Production version

  ```bash
  GET https://toloka.dev/api/v1/attachments?sort=id&limit=10
  Authorization: OAuth <OAuth token>
  ```

- Sandbox

  ```bash
  GET https://sandbox.toloka.dev/api/v1/attachments?sort=id&limit=10
  Authorization: OAuth <OAuth token>
  ```

{% endlist %}

**Show the remaining tasks sorted by ascending ID**

{% list tabs %}

- Production version

  ```bash
  GET https://toloka.dev/api/v1/attachments?sort=id&limit=10&id_gt=<ID of the last file from the previous response>
  Authorization: OAuth <OAuth token>
  ```

- Sandbox

  ```bash
  GET https://sandbox.toloka.dev/api/v1/attachments?sort=id&limit=10&id_gt=<ID of the last file from the previous response>
  Authorization: OAuth <OAuth token>
  ```

{% endlist %}

## Response {#response}

```json
{"items" : [{file #1}, {file #2}, ... {file #n}], "has_more": false}
```

#|
|| Property | Description ||
|| **items[]** | **array of objects**

Contains [information about files](get-attachment.md). ||
|| **has_more** | {% include [has-more](../_includes/has-more.md) %} ||
|#

{% include [contact-support](../../guide/_includes/contact-support.md) %}