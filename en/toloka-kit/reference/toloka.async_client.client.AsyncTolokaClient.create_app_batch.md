# create_app_batch
`toloka.async_client.client.AsyncTolokaClient.create_app_batch` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.2/src/client/__init__.py#L0)

Creates a batch with task items in an App project in Toloka.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`app_project_id`|**str**|<p>The ID of the project.</p>
`name`|**Optional\[str\]**|<p>Batch name.</p>
`items`|**Optional\[List\[Dict\[str, Any\]\]\]**|<p>A list with task items. The items must follow the solution schema described in `App.input_spec`.</p>

* **Returns:**

  Created batch with updated parameters.

* **Return type:**

  [AppBatch](toloka.client.app.AppBatch.md)
