# Languages
`toloka.client.filter.Languages` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.3/src/client/filter.py#L366)

```python
Languages(
    self,
    operator: InclusionOperator,
    value: Union[str, List[str]],
    verified: bool = False
)
```

Filtering Tolokers by languages specified in their profiles.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`operator`|**[InclusionOperator](toloka.client.primitives.operators.InclusionOperator.md)**|<p>An operator used in a condition. Allowed set of operators depends on the filter.</p>
`value`|**Union\[str, List\[str\]\]**|<p>Languages specified in the profile. A two-letter [ISO 639-1](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes) code in upper case is used.</p>
`verified`|**-**|<p>If set to `True`, only Tolokers who have passed a language test are selected. Tests are available for languages: `AR`, `DE`, `EN`, `ES`, `FR`, `HE`, `ID`, `JA`, `PT`, `RU`, `SV`, `ZH-HANS`.</p>
