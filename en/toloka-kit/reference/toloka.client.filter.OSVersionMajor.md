# OSVersionMajor
`toloka.client.filter.OSVersionMajor` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/client/filter.py#L611)

```python
OSVersionMajor(
    self,
    operator: CompareOperator,
    value: int
)
```

Filtering Tolokers by an OS major version.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`operator`|**[CompareOperator](toloka.client.primitives.operators.CompareOperator.md)**|<p>An operator used in a condition. Allowed set of operators depends on the filter.</p>
`value`|**int**|<p>The major version of the OS.</p>
