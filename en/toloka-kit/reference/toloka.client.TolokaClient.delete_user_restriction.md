# delete_user_restriction
`toloka.client.TolokaClient.delete_user_restriction` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/__init__.py#L3403)

```python
delete_user_restriction(self, user_restriction_id: str)
```

Removes existing restriction.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`user_restriction_id`|**str**|<p>The ID of the restriction you want to remove.</p>

**Examples:**


```python
toloka_client.delete_user_restriction(user_restriction_id='20974')
```
