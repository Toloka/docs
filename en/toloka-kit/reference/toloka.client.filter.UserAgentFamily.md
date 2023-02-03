# UserAgentFamily
`toloka.client.filter.UserAgentFamily` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.3/src/client/filter.py#L657)

```python
UserAgentFamily(
    self,
    operator: IdentityOperator,
    value: Union[UserAgentFamily, str]
)
```

Filtering Tolokers by a user agent family.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`operator`|**[IdentityOperator](toloka.client.primitives.operators.IdentityOperator.md)**|<p>An operator used in a condition. Allowed set of operators depends on the filter.</p>
`value`|**[UserAgentFamily](toloka.client.filter.UserAgentFamily.UserAgentFamily.md)**|<p>The user agent family.</p>
