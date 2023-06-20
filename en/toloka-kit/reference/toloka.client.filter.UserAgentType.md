# UserAgentType
`toloka.client.filter.UserAgentType` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/client/filter.py#L644)

```python
UserAgentType(
    self,
    operator: IdentityOperator,
    value: Union[UserAgentType, str]
)
```

Filtering Tolokers by a user agent type.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`operator`|**[IdentityOperator](toloka.client.primitives.operators.IdentityOperator.md)**|<p>An operator used in a condition. Allowed set of operators depends on the filter.</p>
`value`|**[UserAgentType](toloka.client.filter.UserAgentType.UserAgentType.md)**|<p>The user agent type.</p>
