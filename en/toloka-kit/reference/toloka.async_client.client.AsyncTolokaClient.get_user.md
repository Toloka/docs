# get_user
`toloka.async_client.client.AsyncTolokaClient.get_user` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.4/src/async_client/client.py#L0)

```python
async get_user(self, user_id: str)
```

Gets Toloker metadata by `user_id`.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`user_id`|**str**|<p>Toloker ID.</p>

* **Returns:**

  Contains Toloker metadata.

* **Return type:**

  [User](toloka.client.user.User.md)
