# UserAgentVersionMinor
`toloka.client.filter.UserAgentVersionMinor` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.3/src/client/filter.py#L722)

```python
UserAgentVersionMinor(
    self,
    operator: CompareOperator,
    value: Optional[int] = None
)
```

Filtering Tolokers by a minor browser version.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`operator`|**[CompareOperator](toloka.client.primitives.operators.CompareOperator.md)**|<p>An operator used in a condition. Allowed set of operators depends on the filter.</p>
`value`|**Optional\[int\]**|<p>The minor browser version.</p>
