# get_user_bonus
`toloka.client.TolokaClient.get_user_bonus` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/__init__.py#L3253)

```python
get_user_bonus(self, user_bonus_id: str)
```

Gets information about a Toloker's bonus.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`user_bonus_id`|**str**|<p>The ID of the bonus.</p>

* **Returns:**

  The information about the bonus.

* **Return type:**

  [UserBonus](toloka.client.user_bonus.UserBonus.md)

**Examples:**


```python
bonus = toloka_client.get_user_bonus(user_bonus_id='3295')
print(bonus.amount)
```
