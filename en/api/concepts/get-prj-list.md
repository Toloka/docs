# Get the list of projects

{% include [announce](../_includes/announce.md) %}

Gets the list of projects.

## Request {#request}

{% list tabs %}

- Production version

    ```bash
    GET https://toloka.dev/api/v1/projects
    Authorization: OAuth <OAuth token>
    ```

- Sandbox

    ```bash
    GET https://sandbox.toloka.dev/api/v1/projects
    Authorization: OAuth <OAuth token>
    ```

{% endlist %}

## Headers {#headers}

#|
|| Title | Overview ||
|| **Authorization** | A token for account authorization. Add OAuth as a prefix. ||
|#

## Query parameters {#query-params}

Specified in the link after the question mark; separated by `&`.

#|
|| Parameter | Overview ||
|| **status** | **string**

Status of the project:

- `ACTIVE` — Active.
- `ARCHIVED` — Archived. ||
|| **sort** | **string**

Parameters to sort by:

- `id` — The project identifier.
- `created` — The date when the project was created, in UTC using ISO 8601 format: `YYYY-MM-DDThh:mm:ss[.sss]`.
- `public_name` — The project name.
- `private_comment` — A comment on the project.

To learn how to configure sorting, see [Sorting the list of objects](sorting.md). ||
|| **owner** | **string**

Requester ID. ||
|| **Standard query parameters** |
[limit](./standard-query-parameters.md#limit), [id_gt](./standard-query-parameters.md#id_gt), [id_gte](./standard-query-parameters.md#id_gte), [id_lt](./standard-query-parameters.md#id_lt), [id_lte](./standard-query-parameters.md#id_lte), [created_gt](./standard-query-parameters.md#created_gt), [created_gte](./standard-query-parameters.md#created_gte), [created_lt](./standard-query-parameters.md#created_lt), [created_lte](./standard-query-parameters.md#created_lte). ||
|#

## Query example {#request-example}

You can set up the display of the list of projects in parts (for example, 10 projects at a time):

1. Show the first 10 projects, starting with the project with the lowest ID.
1. Show the remaining projects (10 at a time) in ascending order.

**Show the first 10 projects**

{% list tabs %}

- Production version

    ```bash
    GET https://toloka.dev/api/v1/projects?sort=id&limit=10
    Authorization: OAuth <OAuth token>
    ```

- Sandbox

    ```bash
    GET https://sandbox.toloka.dev/api/v1/projects?sort=id&limit=10
    Authorization: OAuth <OAuth token>
    ```

{% endlist %}

**Show the remaining tasks sorted by ascending ID**

{% list tabs %}

- Production version

    ```bash
    GET https://toloka.dev/api/v1/projects?sort=id&limit=10&id_gt=<ID of the last project from the previous response>
    Authorization: OAuth <OAuth token>
    ```

- Sandbox

    ```bash
    GET https://sandbox.toloka.dev/api/v1/projects?sort=id&limit=10&id_gt=<id of the last project from the previous response>
    Authorization: OAuth <OAuth token>
    ```

{% endlist %}

## Response {#response}

Contains a list of projects and their properties in the `items` array:

```json
{"items": [{properties of project 1}, {properties of project 2}, ... {properties of project n}], "has_more": false}
```