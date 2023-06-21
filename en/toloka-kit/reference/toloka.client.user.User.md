# User
`toloka.client.user.User` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0.post1/src/client/user.py#L9)

```python
User(
    self,
    *,
    id: Optional[str] = None,
    country: Optional[str] = None,
    languages: Optional[List[str]] = None,
    adult_allowed: Optional[bool] = None,
    attributes: Optional[Attributes] = None
)
```

Toloker metadata.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`id`|**Optional\[str\]**|<p>Toloker ID.</p>
`country`|**Optional\[str\]**|<p>Toloker country code.</p>
`languages`|**Optional\[List\[str\]\]**|<p>list of languages that Toloker know represented with language codes.</p>
`adult_allowed`|**Optional\[bool\]**|<p>shows whether Toloker agreed to complete tasks with adult content.</p>
`attributes`|**Optional\[[Attributes](toloka.client.user.User.Attributes.md)\]**|<p>Toloker attributes.</p>
