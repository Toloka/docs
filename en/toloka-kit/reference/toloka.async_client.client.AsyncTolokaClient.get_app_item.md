# get_app_item
`toloka.async_client.client.AsyncTolokaClient.get_app_item` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.2/src/async_client/client.py#L0)

```python
async get_app_item(
    self,
    app_project_id: str,
    app_item_id: str
)
```

Gets information from Toloka about an App task item.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`app_project_id`|**str**|<p>The ID of the App project.</p>
`app_item_id`|**str**|<p>The ID of the item.</p>

* **Returns:**

  The App task item.

* **Return type:**

  [AppItem](toloka.client.app.AppItem.md)
