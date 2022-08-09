# Get project properties

{% include [announce](../_includes/announce.md) %}

Gets project properties.

You can get the project ID from the [list of projects](get-prj-list.md).

## Request {#request}

{% list tabs %}

- Production version

    ```bash
    GET https://toloka.dev/api/v1/projects/<project_id>
    Authorization: OAuth <OAuth token>
    ```

- Sandbox

    ```bash
    GET https://sandbox.toloka.dev/api/v1/projects/<project_id>
    Authorization: OAuth <OAuth token>
    ```

{% endlist %}

## Path parameters {#path-params}

Parameter | Overview
----- | -----
**project_id** | Project ID.

## Headers {#headers}

Title | Overview
----- | -----
**Authorization** | A token for account authorization. Add OAuth as a prefix.

## Response {#response}

Contains project properties in JSON format (see the [sample project](create-prj.md#body)).