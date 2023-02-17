# Get the list of skills

{% include [announce](../_includes/announce.md) %}

Gets the list of created skills.

## Request {#request}

{% list tabs %}

- Production version

    ```bash
    GET https://toloka.dev/api/v1/skills
    Authorization: OAuth <OAuth token>
    ```

- Sandbox

    ```bash
    GET https://sandbox.toloka.dev/api/v1/skills
    Authorization: OAuth <OAuth token>
    ```

{% endlist %}

## Headers {#headers}

Title | Overview
----- | -----
**Authorization** | A token for account authorization. Add OAuth as a prefix.

## Query parameters {#query-params}

Specified in the link after the question mark; separated by `&`.

#|
|| Parameter | Overview ||
|| **name** | **string**

Skill name. ||
|| **sort** | **string**

Parameters to sort by:

- `id` — Skill ID.
- `created` — The skill creation date in UTC using ISO 8601 format: `YYYY-MM-DDThh:mm:ss[.sss]`.

To learn how to configure sorting, see [Sorting the list of objects](sorting.md). ||
|| **Standard query parameters** | [limit](./standard-query-parameters.md#limit), [id_gt](./standard-query-parameters.md#id_gt), [id_gte](./standard-query-parameters.md#id_gte), [id_lt](./standard-query-parameters.md#id_lt), [id_lte](./standard-query-parameters.md#id_lte), [created_gt](./standard-query-parameters.md#created_gt), [created_gte](./standard-query-parameters.md#created_gte), [created_lt](./standard-query-parameters.md#created_lt), [created_lte](./standard-query-parameters.md#created_lte) ||
|#

## Query example {#request-example}

You can set up the display of the list of skills in parts (for example, 10 skills at a time):

1. Show the first 10 skills, starting with the skill with the lowest ID.
1. Show the remaining skills (10 at a time) in ascending order.

**Show the first 10 skills**

{% list tabs %}

- Production version

    ```bash
    GET https://toloka.dev/api/v1/skills?sort=id&limit=10
    Authorization: OAuth <OAuth token>
    ```

- Sandbox

    ```bash
    GET https://sandbox.toloka.dev/api/v1/skills?sort=id&limit=10
    Authorization: OAuth <OAuth token>
    ```

{% endlist %}

**Show the remaining tasks sorted by ascending ID**

{% list tabs %}

- Production version

    ```bash
    GET https://toloka.dev/api/v1/skills?sort=id&limit=10&id_gt=<ID of the last skill from the previous response>
    Authorization: OAuth <OAuth token>
    ```

- Sandbox

    ```bash
    GET https://sandbox.toloka.dev/api/v1/skills?sort=id&limit=10&id_gt=<ID of the last skill from the previous response>
    Authorization: OAuth <OAuth token>
    ```

{% endlist %}

## Response {#response}

[Information about skills](get-skill.md) in the `items` array:

```json
{"items": [{skill 1}, {skill 2}, ... {skill n}], "has_more": false}
```

{% include [contact-support](../../guide/_includes/contact-support.md) %}