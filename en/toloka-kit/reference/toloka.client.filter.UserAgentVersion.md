# UserAgentVersion
`toloka.client.filter.UserAgentVersion` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.0.2/src/client/filter.py#L695)

```python
UserAgentVersion(
    self,
    operator: CompareOperator,
    value: Optional[float] = None
)
```

Filtering Tolokers by a browser version.


The version consists of major and minor version numbers.
The version is represented as a single floating point number in conditions.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`operator`|**[CompareOperator](toloka.client.primitives.operators.CompareOperator.md)**|<p>An operator used in a condition. Allowed set of operators depends on the filter.</p>
`value`|**Optional\[float\]**|<p>The version of the browser.</p>
