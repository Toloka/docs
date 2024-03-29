# get_user_restriction
`toloka.client.TolokaClient.get_user_restriction` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/__init__.py#L3332)

```python
get_user_restriction(self, user_restriction_id: str)
```

Gets information about a Toloker restriction.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`user_restriction_id`|**str**|<p>The ID of the Toloker restriction.</p>

* **Returns:**

  The Toloker restriction.

* **Return type:**

  [UserRestriction](toloka.client.user_restriction.UserRestriction.md)

**Examples:**


```python
restriction = toloka_client.get_user_restriction(user_restriction_id='19124')
print(restriction.will_expire)
```
