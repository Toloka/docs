# create_app_items
`toloka.async_client.client.AsyncTolokaClient.create_app_items` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0.post1/src/client/__init__.py#L0)

Creates task items in an App project in Toloka and adds them to an existing batch.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`app_project_id`|**str**|<p>The ID of the App project.</p>
`batch_id`|**Optional\[str\]**|<p>The ID of the batch to place items to.</p>
`items`|**Optional\[List\[Dict\[str, Any\]\]\]**|<p>A list with items. The items must follow the solution schema described in `App.input_spec`.</p>

**Examples:**

The following example is suitable for a project
that requires `query` and `website_url` keys to be present in input data.

```python
new_items = [
    {'id':'20', 'query':'toloka kit', 'website_url':'https://toloka.ai/docs/toloka-kit'},
    {'id':'21', 'query':'crowd kit', 'website_url':'https://toloka.ai/docs/crowd-kit'}
]
toloka_client.create_app_items(app_project_id = 'Q2d15QBjpwWuDz8Z321g', batch_id = '4Va2BBWKL88S4QyAgVje', items = new_items)
```
