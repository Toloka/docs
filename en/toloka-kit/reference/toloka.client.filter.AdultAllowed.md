# AdultAllowed
`toloka.client.filter.AdultAllowed` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0.post1/src/client/filter.py#L317)

```python
AdultAllowed(
    self,
    operator: IdentityOperator,
    value: bool
)
```

Filtering Tolokers who agreed to work with adult content.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`operator`|**[IdentityOperator](toloka.client.primitives.operators.IdentityOperator.md)**|<p>An operator used in a condition. Allowed set of operators depends on the filter.</p>
`value`|**bool**|<ul> <li>`True` — Toloker agrees to work with adult content.</li> <li>`False` — Toloker does not agree to work with adult content.</li> </ul>

**Examples:**


```python
adult_allowed_filter = toloka.client.filter.AdultAllowed == True
adult_not_allowed_filter = toloka.client.filter.AdultAllowed == False
```
