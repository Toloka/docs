# create_app_item
`toloka.async_client.client.AsyncTolokaClient.create_app_item` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/client/__init__.py#L0)

Creates an App task item in Toloka.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`app_project_id`|**str**|<p>The ID of the App project to create the item in.</p>
`id`|**-**|<p>The ID of the item.</p>
`app_project_id`|**str**|<p>The ID of the project that contains the item.</p>
`batch_id`|**Optional\[str\]**|<p>The ID of the batch that contains the item.</p>
`input_data`|**Optional\[Dict\[str, Any\]\]**|<p>Input data. It must follow the solution schema described in `App.input_spec`.</p>
`status`|**-**|<p>The item status:</p> <ul> <li>`NEW` — The item is uploaded to Toloka and ready for processing.</li> <li>`PROCESSING` — The item is being processed by Tolokers.</li> <li>`COMPLETED` — Item annotation is completed.</li> <li>`ERROR` — An error occurred during processing.</li> <li>`CANCELLED` — Item processing cancelled.</li> <li>`ARCHIVE` — The item is archived.</li> <li>`NO_MONEY` — There are not enough money for processing.</li> </ul>
`output_data`|**-**|<p>Annotated data.</p>
`errors`|**-**|<p>Errors occurred during annotation.</p>
`created_at`|**-**|<p>The date and time when the item was created.</p>
`started_at`|**-**|<p>The date and time when the item processing started.</p>
`finished_at`|**-**|<p>The date and time when the item processing was completed.</p>

* **Returns:**

  Created App task item with updated parameters.

* **Return type:**

  [AppItem](toloka.client.app.AppItem.md)

**Examples:**

The following example is suitable for a project
that requires `query` and `website_url` keys to be present in input data.

```python
new_item = {
    'batch_id' : '4Va2BBWKL88S4QyAgVje',
    'input_data' : {
        'id':'40', 'query':'toloka kit', 'website_url':'https://toloka.ai/en/docs/toloka-kit'
    }
}
new_item = toloka_client.create_app_item(app_project_id = 'Q2d15QBjpwWuDz8Z321g', app_item = new_item)
print(new_item.created_at)
```
