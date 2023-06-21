# Citizenship
`toloka.client.filter.Citizenship` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0.post1/src/client/filter.py#L282)

```python
Citizenship(
    self,
    operator: IdentityOperator,
    value: str
)
```

Filtering Tolokers by a country of citizenship specified in their profiles.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`operator`|**[IdentityOperator](toloka.client.primitives.operators.IdentityOperator.md)**|<p>An operator used in a condition. Allowed set of operators depends on the filter.</p>
`value`|**str**|<p>A two-letter code of the country taken from the [ISO 3166-1](https://en.wikipedia.org/wiki/ISO_3166-1_alpha-2) standard.</p>
