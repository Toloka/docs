# get_app_item
`toloka.client.TolokaClient.get_app_item` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.2/src/client/__init__.py#L3829)

```python
get_app_item(
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
