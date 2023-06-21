# UserAgentVersionMajor
`toloka.client.filter.UserAgentVersionMajor` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0.post1/src/client/filter.py#L722)

```python
UserAgentVersionMajor(
    self,
    operator: CompareOperator,
    value: Optional[int] = None
)
```

Filtering Tolokers by a major browser version.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`operator`|**[CompareOperator](toloka.client.primitives.operators.CompareOperator.md)**|<p>An operator used in a condition. Allowed set of operators depends on the filter.</p>
`value`|**Optional\[int\]**|<p>The major browser version.</p>
