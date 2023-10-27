# BaseData
`toloka.client.project.template_builder.data.BaseData` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/project/template_builder/data.py#L29)

```python
BaseData(
    self,
    path: Optional[Any] = None,
    default: Optional[Any] = None
)
```

A base class for data components.


For more information, see [Working with data](https://toloka.ai/docs/template-builder/operations/work-with-data).

 Attributes:
    path: A path to a data property in a component hierarchy.
        Dots are used as separators: `path.to.some.element`.
        For an array element, specify its sequence number after a dot: `items.0`.
    default: A default data value.
        Note, that it is shown in the interface, so it might hide placeholders, for example, in text fields.

