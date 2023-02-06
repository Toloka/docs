# get_user_restriction
`toloka.async_client.client.AsyncTolokaClient.get_user_restriction` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.3/src/async_client/client.py#L0)

```python
async get_user_restriction(self, user_restriction_id: str)
```

Gets information about a Toloker restriction.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`user_restriction_id`|**str**|<p>ID of the Toloker restriction.</p>

* **Returns:**

  The Toloker restriction.

* **Return type:**

  [UserRestriction](toloka.client.user_restriction.UserRestriction.md)

**Examples:**


```python
toloka_client.get_user_restriction(user_restriction_id='1')
```
