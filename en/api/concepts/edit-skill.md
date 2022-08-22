# Edit a skill

{% include [announce](../_includes/announce.md) %}

Changes the name, comment, and access to the skill.

## Request {#request}

{% list tabs %}

- Production version

    ```bash
    PUT https://toloka.dev/api/v1/skills/<skill id>
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON

    {<skill parameters, including updated ones>}
    ```

- Sandbox

    ```bash
    PUT https://sandbox.toloka.dev/api/v1/skills/<skill id>
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON

    {<skill parameters, including updated ones>}
    ```

{% endlist %}

## Path parameters {#path-params}

Parameter | Overview
----- | -----
**skill_id** | Skill ID.

## Headers {#headers}

Title | Overview
----- | -----
**Authorization** | A token for account authorization. Add OAuth as a prefix.
**Content-Type** | Specifies the data format in the request body.

## Request body {#body}

In the request body, specify **all** [the skill parameters](create-skill.md#body), including those that are updated.

## Response {#response}

Contains updated information about the skill (see the description in the [Create a skill](create-skill.md#response) section).