# get_app_item
`toloka.client.TolokaClient.get_app_item` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0.post1/src/client/__init__.py#L4078)

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

**Examples:**


```python
item = toloka_client.get_app_item(app_project_id = 'Q2d15QBjpwWuDz8Z321g', app_item_id = 'V40aPPA2j64TORQyY54Z')
print(item.input_data)
print(item.output_data)
```
