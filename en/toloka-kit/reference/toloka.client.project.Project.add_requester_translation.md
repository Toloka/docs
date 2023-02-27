# add_requester_translation
`toloka.client.project.Project.add_requester_translation` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.4/src/client/project/__init__.py#L207)

```python
add_requester_translation(
    self,
    language: str,
    public_name: Optional[str] = None,
    public_description: Optional[str] = None,
    public_instructions: Optional[str] = None
)
```

Adds a project interface translation to other language.


To translate to several languages call this method for each translation.
A subsequent call with the same `language` updates the translation of passed parameters and doesn't touch omitted parameters.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`language`|**str**|<p>Two-letter [ISO 639-1](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes) language code in upper case.</p>
`public_name`|**Optional\[str\]**|<p>A translated project name.</p>
`public_description`|**Optional\[str\]**|<p>A translated project description.</p>
`public_instructions`|**Optional\[str\]**|<p>Translated instructions for Tolokers.</p>

**Examples:**

How to add russian translation to the project.

```python
project = toloka.client.Project(
    public_name='Cats vs dogs',
    public_description='A simple image classification',
    public_instructions='Determine which animal is in an image',
    ...
)
project.set_default_language('EN')
project.add_requester_translation(
    language='RU',
    public_name='Кошки или собаки'
    public_description='Простая классификация изображений'
)
project.add_requester_translation(language='RU', public_instructions='Определите, какое животное изображено')
```
