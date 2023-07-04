# Profile
`toloka.client.filter.Profile` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/client/filter.py#L177)

```python
Profile(
    self,
    *,
    operator: Any,
    value: Any
)
```

A base class for a category of filters that use Toloker's profile.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`operator`|**Any**|<p>An operator used in a condition. Allowed set of operators depends on the filter.</p>
`value`|**Any**|<p>A value to compare with. For example, the minimum value of some skill, or a language specified in a Toloker&#x27;s profile.</p>
