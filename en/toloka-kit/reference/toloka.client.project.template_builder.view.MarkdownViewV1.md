# MarkdownViewV1
`toloka.client.project.template_builder.view.MarkdownViewV1` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/project/template_builder/view.py#L384)

```python
MarkdownViewV1(
    self,
    content: Optional[Any] = None,
    *,
    hint: Optional[Any] = None,
    label: Optional[Any] = None,
    validation: Optional[BaseComponent] = None,
    version: Optional[str] = '1.0.0'
)
```

A component for formatting Markdown.


The Markdown content must not contain line breaks. To insert them, place `\n` in the text.
    Straight quotation marks must be escaped: `"`.

    For more information, see [view.markdown](https://toloka.ai/docs/template-builder/reference/view.markdown).

    Attributes:
        content: A text with Markdown.

    Example:
        Adding a title and description using Markdown.

```python
import toloka.client.project.template_builder as tb
header = tb.view.MarkdownViewV1('# Some Header:\n---\nSome detailed description')
```

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`hint`|**Optional\[Any\]**|<p>A hint text.</p>
`label`|**Optional\[Any\]**|<p>A label above the component.</p>
`validation`|**Optional\[[BaseComponent](toloka.client.project.template_builder.base.BaseComponent.md)\]**|<p>Validation rules.</p>
