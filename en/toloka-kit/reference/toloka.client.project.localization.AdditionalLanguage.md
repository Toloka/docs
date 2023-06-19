# AdditionalLanguage
`toloka.client.project.localization.AdditionalLanguage` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/client/project/localization.py#L11)

```python
AdditionalLanguage(
    self,
    *,
    language: Optional[str] = None,
    public_name: Optional[FieldTranslation] = None,
    public_description: Optional[FieldTranslation] = None,
    public_instructions: Optional[FieldTranslation] = None
)
```

A translation of a project interface.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`language`|**Optional\[str\]**|<p>The language into which the translation is made. Two-letter [ISO 639-1](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes) language code in upper case.</p>
`public_name`|**Optional\[[FieldTranslation](toloka.client.project.localization.AdditionalLanguage.FieldTranslation.md)\]**|<p>A translated project name.</p>
`public_description`|**Optional\[[FieldTranslation](toloka.client.project.localization.AdditionalLanguage.FieldTranslation.md)\]**|<p>A translated project description.</p>
`public_instructions`|**Optional\[[FieldTranslation](toloka.client.project.localization.AdditionalLanguage.FieldTranslation.md)\]**|<p>Translated instructions for Tolokers.</p>
