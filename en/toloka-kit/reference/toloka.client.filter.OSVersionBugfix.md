# OSVersionBugfix
`toloka.client.filter.OSVersionBugfix` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/client/filter.py#L633)

```python
OSVersionBugfix(
    self,
    operator: CompareOperator,
    value: int
)
```

Filtering Tolokers by a build number or a bugfix version of their OS.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`operator`|**[CompareOperator](toloka.client.primitives.operators.CompareOperator.md)**|<p>An operator used in a condition. Allowed set of operators depends on the filter.</p>
`value`|**int**|<p>The build number or the bugfix version of the OS.</p>
