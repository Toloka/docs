# get_app
`toloka.client.TolokaClient.get_app` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/client/__init__.py#L3916)

```python
get_app(
    self,
    app_id: str,
    lang: Optional[str] = None
)
```

Gets information from Toloka about an App solution.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`app_id`|**str**|<p>The ID of the solution.</p>
`lang`|**Optional\[str\]**|<p>ISO 639 language code.</p>

* **Returns:**

  The App solution.

* **Return type:**

  [App](toloka.client.app.App.md)

**Examples:**


```python
app = toloka_client.get_app('2eN4l59qL2xHB5b8Jqp6')
print(app.id, app.name)
print(app.description)
```
