# Assets
`toloka.client.project.view_spec.ClassicViewSpec.Assets` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/client/project/view_spec.py#L84)

```python
Assets(
    self,
    *,
    style_urls: Optional[List[str]] = None,
    script_urls: Optional[List[str]] = None
)
```

Links to external files.


You can link:
    * CSS libraries
    * JavaScript libraries
    * Toloka assets — libraries that can be linked using the `$TOLOKA_ASSETS` path:
        * `$TOLOKA_ASSETS/js/toloka-handlebars-templates.js` — [Handlebars template engine](http://handlebarsjs.com/).
        * `$TOLOKA_ASSETS/js/image-annotation.js` — Image labeling interface. Note, that this library requires Handlebars and must be linked after it.
            For more information, see [Image with area selection](https://toloka.ai/docs/guide/t-components/image-annotation).

    Add items in the order they should be linked.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`style_urls`|**Optional\[List\[str\]\]**|<p>Links to CSS libraries.</p>
`script_urls`|**Optional\[List\[str\]\]**|<p>Links to JavaScript libraries and Toloka assets.</p>

**Examples:**


```python
from toloka.client.project.view_spec import ClassicViewSpec
view_spec = ClassicViewSpec(
    ...,
    assets = ClassicViewSpec.Assets(
        script_urls = [
            "$TOLOKA_ASSETS/js/toloka-handlebars-templates.js",
            "$TOLOKA_ASSETS/js/image-annotation.js",
        ]
    )
)
```
