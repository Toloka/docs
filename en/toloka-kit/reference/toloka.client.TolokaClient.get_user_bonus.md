# get_user_bonus
`toloka.client.TolokaClient.get_user_bonus` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.3/src/client/__init__.py#L3064)

```python
get_user_bonus(self, user_bonus_id: str)
```

Gets information about a Toloker's reward.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`user_bonus_id`|**str**|<p>The ID of the reward.</p>

* **Returns:**

  The information about the reward.

* **Return type:**

  [UserBonus](toloka.client.user_bonus.UserBonus.md)

**Examples:**


```python
toloka_client.get_user_bonus(user_bonus_id='1')
```
