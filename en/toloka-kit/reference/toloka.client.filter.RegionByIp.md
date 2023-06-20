# RegionByIp
`toloka.client.filter.RegionByIp` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/client/filter.py#L497)

```python
RegionByIp(
    self,
    operator: InclusionOperator,
    value: int
)
```

Filtering Tolokers by a region which is determined by their IP address.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`operator`|**[InclusionOperator](toloka.client.primitives.operators.InclusionOperator.md)**|<p>An operator used in a condition. Allowed set of operators depends on the filter.</p>
`value`|**int**|<p>The ID from the [list of regions](https://toloka.ai/en/docs/api/concepts/regions).</p>
