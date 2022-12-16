# create_app_items
`toloka.client.TolokaClient.create_app_items` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.0.post1/src/client/__init__.py#L3696)

Creates task items in an App project in Toloka and adds them to an existing batch.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`app_project_id`|**str**|<p>The ID of the App project.</p>
`batch_id`|**Optional\[str\]**|<p>The ID of the batch to place items to.</p>
`items`|**Optional\[List\[Dict\[str, Any\]\]\]**|<p>A list with items. The items must follow the solution schema described in `App.input_spec`.</p>
