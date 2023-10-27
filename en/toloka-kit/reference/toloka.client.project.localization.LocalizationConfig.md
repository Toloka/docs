# LocalizationConfig
`toloka.client.project.localization.LocalizationConfig` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/project/localization.py#L47)

```python
LocalizationConfig(
    self,
    *,
    default_language: Optional[str] = None,
    additional_languages: Optional[List[AdditionalLanguage]] = ...
)
```

All translations of a project interface.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`default_language`|**Optional\[str\]**|<p>The main language used for text parameters when the project was created. It is a required parameter.</p>
`additional_languages`|**Optional\[List\[[AdditionalLanguage](toloka.client.project.localization.AdditionalLanguage.md)\]\]**|<p>A list of translations to other languages.</p>
