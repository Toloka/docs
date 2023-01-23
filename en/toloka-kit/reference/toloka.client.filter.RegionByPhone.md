# RegionByPhone
`toloka.client.filter.RegionByPhone` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.1/src/client/filter.py#L485)

```python
RegionByPhone(
    self,
    operator: InclusionOperator,
    value: int
)
```

Filtering Tolokers by a region which is determined by their mobile phone number.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`operator`|**[InclusionOperator](toloka.client.primitives.operators.InclusionOperator.md)**|<p>An operator used in a condition. Allowed set of operators depends on the filter.</p>
`value`|**int**|<p>The ID from the [list of regions](https://toloka.ai/en/docs/api/concepts/regions).</p>
