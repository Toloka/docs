# set_user_skill
`toloka.client.TolokaClient.set_user_skill` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/__init__.py#L3541)

Assigns a skill to a Toloker.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`user_id`|**Optional\[str\]**|<p>The Toloker&#x27;s ID.</p>
`skill_id`|**Optional\[str\]**|<p>The ID of the skill to set.</p>
`value`|**Optional\[Decimal\]**|<p>The value of the skill. Allowed values: from 0 to 100.</p>

* **Returns:**

  Updated skill information.

* **Return type:**

  [UserSkill](toloka.client.user_skill.UserSkill.md)

**Examples:**


```python
from decimal import Decimal
toloka_client.set_user_skill(
    skill_id='11294', user_id='fac97860c7929add8048ed2ef63b66fd', value=Decimal(100)
)
```
