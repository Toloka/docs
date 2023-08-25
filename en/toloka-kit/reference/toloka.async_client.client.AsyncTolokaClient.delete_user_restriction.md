# delete_user_restriction
`toloka.async_client.client.AsyncTolokaClient.delete_user_restriction` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/async_client/client.py#L0)

```python
async delete_user_restriction(self, user_restriction_id: str)
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
