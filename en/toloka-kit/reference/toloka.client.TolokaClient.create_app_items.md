# create_app_items
`toloka.client.TolokaClient.create_app_items` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/__init__.py#L4169)

Creates task items in an App project in Toloka and adds them to an existing batch.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`app_project_id`|**str**|<p>The ID of the App project.</p>
`batch_id`|**Optional\[str\]**|<p>The ID of the batch to place items to.</p>
`items`|**List\[Dict\[str, Any\]\]**|<p>A list with items. The items must follow the solution schema described in `App.input_spec`.</p>
`force_new_original`|**Optional\[bool\]**|<p>Whether to enable or disable the deduplication for all the items in the request. When set to true, all the items will be re-labeled regardless of whether pre-labeled duplicates exist. Default is `False`.</p>
`ignore_errors`|**Optional\[bool\]**|<p>Whether the data with incorrect items can be uploaded. Default is `False`.</p> <ul> <li>`True` — If incorrect task items are present, they will be skipped and the response will contain the information about errors.</li> <li>`False` — If incorrect task items are present, the data will not be uploaded and the response will contain the information about the errors. You can only use this parameter if batch_id is specified in the request.</li> </ul>

* **Returns:**

  The IDs of created app items.

* **Return type:**

  List\[str\]

**Examples:**

The following example is suitable for a project
that requires `query` and `website_url` keys to be present in input data.

```python
new_items = [
    {'id':'20', 'query':'toloka kit', 'website_url':'https://toloka.ai/docs/toloka-kit'},
    {'id':'21', 'query':'crowd kit', 'website_url':'https://toloka.ai/docs/crowd-kit'}
]
toloka_client.create_app_items(
    app_project_id='Q2d15QBjpwWuDz8Z321g', batch_id='4Va2BBWKL88S4QyAgVje',
    items=new_items
)
```
