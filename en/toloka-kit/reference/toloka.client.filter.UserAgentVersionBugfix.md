# UserAgentVersionBugfix
`toloka.client.filter.UserAgentVersionBugfix` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.0.post1/src/client/filter.py#L733)

```python
UserAgentVersionBugfix(
    self,
    operator: CompareOperator,
    value: Optional[int] = None
)
```

Filtering Tolokers by a build number or a bugfix version of their browser.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`operator`|**[CompareOperator](toloka.client.primitives.operators.CompareOperator.md)**|<p>An operator used in a condition. Allowed set of operators depends on the filter.</p>
`value`|**Optional\[int\]**|<p>The build number or the bugfix version of the browser.</p>
