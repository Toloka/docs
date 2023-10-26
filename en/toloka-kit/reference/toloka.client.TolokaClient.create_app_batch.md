# create_app_batch
`toloka.client.TolokaClient.create_app_batch` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/__init__.py#L4290)

Creates a batch with task items in an App project in Toloka.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`app_project_id`|**str**|<p>The ID of the project.</p>
`name`|**Optional\[str\]**|<p>The batch name.</p>
`items`|**Optional\[List\[Dict\[str, Any\]\]\]**|<p>A list with task items. The items must follow the solution schema described in the `App.input_spec`.</p>
`priority_order`|**Optional\[[AppBatch.PriorityOrder](toloka.client.app.AppBatch.PriorityOrder.md)\]**|<p>The batch priority. See [PriorityOrder](toloka.client.app.AppBatch.PriorityOrder.md) for details. Default is `FIVE`.</p>
`force_new_original`|**Optional\[bool\]**|<p>Whether to enable or disable the deduplication for all the items in the request. When set to true, all the items will be re-labeled regardless of whether pre-labeled duplicates exist. Default is `False`.</p>
`ignore_errors`|**Optional\[bool\]**|<p>Whether the data with incorrect items can be uploaded. Default is `False`.</p>

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
