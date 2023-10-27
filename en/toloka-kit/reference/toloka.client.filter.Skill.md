# Skill
`toloka.client.filter.Skill` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/filter.py#L227)

```python
Skill(
    self,
    key: str,
    operator: CompareOperator = CompareOperator.EQ,
    value: Optional[float] = None
)
```

Filtering Tolokers by skills.


Pass the ID of a skill to the filter constructor.
To select Tolokers without a skill, compare created filter with `None`.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`key`|**str**|<p>The ID of a skill.</p>
`operator`|**[CompareOperator](toloka.client.primitives.operators.CompareOperator.md)**|<p>An operator in the condition.</p>
`value`|**Optional\[float\]**|<p>A value to compare the skill with.</p>

**Examples:**

Selecting Tolokers with a skill with ID '224' greater than 70.
```python
filter = toloka.client.filter.Skill('224') > 70
```
