# Edit a project

{% include [announce](../_includes/announce.md) %}

Edits a project.

In the request body, specify **all** the parameters for the project being updated. You can get the project ID from the [list of projects](get-prj-list.md).

## Request {#request}

{% note tip %}

**Try our [new API reference](https://toloka.ai/docs/api/api-reference/#put-/projects/-id-):** more parameter details, request/response examples, and code samples in various programming languages, including the [Toloka-Kit](../../toloka-kit/index.md) usage samples.

{% endnote %}

{% list tabs %}

- Production version

    ```bash
    PUT https://toloka.dev/api/v1/projects/<project_id>
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON

    {<project parameters, including updated ones>}
    ```

- Sandbox

    ```bash
    PUT https://sandbox.toloka.dev/api/v1/projects/<project_id>
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON

    {<project parameters, including updated ones>}
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
**Content-Type** | Specifies the data format in the request body.

## Response {#response}

Contains updated information about the project in JSON format (see the [sample project](create-prj.md#body)).

## See also {#see-also}

- [{#T}](../../guide/concepts/edit-project.md)

{% include [contact-support](../../guide/_includes/contact-support.md) %}