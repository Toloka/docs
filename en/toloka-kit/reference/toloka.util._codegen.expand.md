# expand
`toloka.util._codegen.expand` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/util/_codegen.py#L279)

```python
expand(
    arg_name: str,
    arg_type: Optional[Type] = None,
    check_type: bool = True
)
```

Allows you to call function also via passing values for creating "arg_name", not only via passing an instance of "arg_name"


If used on class, expands some argument in __init__

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`arg_name`|**str**|<p>Parameter that will be expanded.</p>
`arg_type`|**Optional\[Type\]**|<p>Specify the type of this parameter. Defaults to None and calc it themselves.</p>
`check_type`|**bool**|<p>If True, check that one argument has a compatible type for none expanded version. If not, calls an expanded version. Defaults to True.</p>
