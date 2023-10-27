# get_user
`toloka.async_client.client.AsyncTolokaClient.get_user` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/async_client/client.py#L0)

```python
async get_user(self, user_id: str)
```

Gets information about a Toloker.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`user_id`|**str**|<p>The Toloker ID.</p>

* **Returns:**

  Information about the Toloker.

* **Return type:**

  [User](toloka.client.user.User.md)

**Examples:**


```python
toloker_info = toloka_client.get_user(user_id='fac97860c7929add8048ed2ef63b66fd')
print(toloker_info.country)
```
