# ClientType
`toloka.client.filter.ClientType` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.0.2/src/client/filter.py#L531)

```python
ClientType(
    self,
    operator: IdentityOperator,
    value: Union[ClientType, str]
)
```

Filtering Tolokers by a client application type.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`operator`|**[IdentityOperator](toloka.client.primitives.operators.IdentityOperator.md)**|<p>An operator used in a condition. Allowed set of operators depends on the filter.</p>
`value`|**[ClientType](toloka.client.filter.ClientType.ClientType.md)**|<p>The client application type.</p>
