# DateOfBirth
`toloka.client.filter.DateOfBirth` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.0.2/src/client/filter.py#L344)

```python
DateOfBirth(
    self,
    operator: CompareOperator,
    value: int
)
```

Filtering Tolokers by a date of birth.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`operator`|**[CompareOperator](toloka.client.primitives.operators.CompareOperator.md)**|<p>An operator used in a condition. Allowed set of operators depends on the filter.</p>
`value`|**int**|<p>The date of birth in seconds since January 1, 1970 (UNIX time).</p>
