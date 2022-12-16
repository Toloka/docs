# delete_user_restriction
`toloka.async_client.client.AsyncTolokaClient.delete_user_restriction` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.0.post1/src/async_client/client.py#L0)

```python
async delete_user_restriction(self, user_restriction_id: str)
```

Unlocks existing restriction

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`user_restriction_id`|**str**|<p>Restriction that should be removed.</p>

**Examples:**


```python
toloka_client.delete_user_restriction(user_restriction_id='1')
```
