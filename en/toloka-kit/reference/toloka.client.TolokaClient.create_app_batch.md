# create_app_batch
`toloka.client.TolokaClient.create_app_batch` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/__init__.py#L4308)

Creates a batch with task items in an App project in Toloka.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`app_project_id`|**str**|<p>The ID of the project.</p>
`name`|**Optional\[str\]**|<p>The batch name.</p>
`items`|**Optional\[List\[Dict\[str, Any\]\]\]**|<p>A list with task items. The items must follow the solution schema described in the `App.input_spec`.</p>

* **Returns:**

  Created batch with updated parameters.

* **Return type:**

  [AppBatch](toloka.client.app.AppBatch.md)

**Examples:**

The following example is suitable for a project
that requires `query` and `website_url` keys to be present in input data.

```python
new_items = [
    {'id':'30', 'query':'toloka kit', 'website_url':'https://toloka.ai/docs/toloka-kit'},
    {'id':'31', 'query':'crowd kit', 'website_url':'https://toloka.ai/docs/crowd-kit'}
]
toloka_client.create_app_batch(
    app_project_id='Q2d15QBjpwWuDz8Z321g',
    items=new_items
)
```
