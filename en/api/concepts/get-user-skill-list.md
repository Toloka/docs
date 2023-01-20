# Get a list of Tolokers who have skills

{% include [announce](../_includes/announce.md) %}

Gets a list of Tolokers who have skills. With the [query parameters](#query-params), you can filter the data in the response the following way:

- Get the list of all the Tolokers who have the specific skill using the `skill_id` query parameter:

   ```bash
   GET https://toloka.dev/api/v1/user-skills?skill_id=<skill_id>
   ```

- Get the list of all the skills assigned to the specific Toloker using the `user_id` query parameter:

   ```bash
   GET https://toloka.dev/api/v1/user-skills?user_id=<user_id>
   ```

## Request {#request}

{% list tabs %}

- Production version

    ```bash
    GET https://toloka.dev/api/v1/user-skills
    Authorization: OAuth <OAuth token>
    ```

- Sandbox

    ```bash
    GET https://sandbox.toloka.dev/api/v1/user-skills
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
|| **user_id** | **string**

Toloker ID. It is used to get the list of the skills assigned to the specific Toloker.||
|| **skill_id** | **string**

Skill ID. It is used to get the list of the Tolokers who have the specific skill.||
|| **sort** | **string**

Parameters to sort by:

- `id` — Skill value ID.
- `created` — The date when the skill was created, in UTC in the YYYY-MM-DD format.
- `created` — The date when the skill was changed, in UTC in the YYYY-MM-DD format.


To learn how to configure sorting, see [Sorting the list of objects](sorting.md). ||
|| **Standard query parameters** |
[limit](./standard-query-parameters.md#limit), [id_gt](./standard-query-parameters.md#id_gt), [id_gte](./standard-query-parameters.md#id_gte), [id_lt](./standard-query-parameters.md#id_lt), [id_lte](./standard-query-parameters.md#id_lte), [created_gt](./standard-query-parameters.md#created_gt), [created_gte](./standard-query-parameters.md#created_gte), [created_lt](./standard-query-parameters.md#created_lt), [created_lte](./standard-query-parameters.md#created_lte), [modified_gt](./standard-query-parameters.md#modified_gt), [modified_gte](./standard-query-parameters.md#modified_gte), [modified_lt](./standard-query-parameters.md#modified_lt), [modified_lte](./standard-query-parameters.md#modified_lte). ||
|#

## Query example {#request-example}

You can set up the display of the list of skills in parts (for example, 10 skills at a time):

1. Show the first 10 skills, starting with the skill with the lowest ID.
1. Show the remaining skills (10 at a time) in ascending order.

**Show the first 10 skills**

{% list tabs %}

- Production version

    ```bash
    GET https://toloka.dev/api/v1/user-skills?sort=id&limit=10
    Authorization: OAuth <OAuth token>
    ```

- Sandbox

    ```bash
    GET https://sandbox.toloka.dev/api/v1/user-skills?sort=id&limit=10
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

[Skill properties](get-user-skill.md#response) in the `items` array:

```json
{"items" : [{<Toloker 1 skill 1 >}, {<Toloker 1 skill 2>}, ... {<Toloker 1 skill n>}, ... {<Toloker n skill 1>}, {<Toloker n skill 2>}, ... {<Toloker n skill n>}], "has_more": false}
```
