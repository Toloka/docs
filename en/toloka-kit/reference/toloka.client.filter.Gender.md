# Gender
`toloka.client.filter.Gender` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/filter.py#L249)

```python
Gender(
    self,
    operator: IdentityOperator,
    value: Union[Gender, str]
)
```

Filtering Tolokers by gender.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`operator`|**[IdentityOperator](toloka.client.primitives.operators.IdentityOperator.md)**|<p>An operator used in a condition. Allowed set of operators depends on the filter.</p>
`value`|**[Gender](toloka.client.filter.Gender.Gender.md)**|<p>Toloker&#x27;s gender specified in the profile.</p>
