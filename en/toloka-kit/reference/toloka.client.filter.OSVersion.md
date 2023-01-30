# OSVersion
`toloka.client.filter.OSVersion` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.2/src/client/filter.py#L586)

```python
OSVersion(
    self,
    operator: CompareOperator,
    value: float
)
```

Filtering Tolokers by an OS version.


The version consists of major and minor version numbers, for example, `14.4`.
The version is represented as a single floating point number in conditions.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`operator`|**[CompareOperator](toloka.client.primitives.operators.CompareOperator.md)**|<p>An operator used in a condition. Allowed set of operators depends on the filter.</p>
`value`|**float**|<p>The version of the OS.</p>
