# User
`toloka.client.user.User` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/user.py#L9)

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

Information about a Toloker.


Some information is got from the Toloker's profile, other is obtained from the Toloker's device.

Country and language are returned as [country codes](https://toloka.ai/docs/api/regions/).

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`id`|**Optional\[str\]**|<p>The Toloker's ID.</p>
`country`|**Optional\[str\]**|<p>The country set in the profile.</p>
`languages`|**Optional\[List\[str\]\]**|<p>A list of languages specified in the profile.</p>
`adult_allowed`|**Optional\[bool\]**|<p>Whether or not the Toloker agreed to complete tasks which contain adult content.</p>
`attributes`|**Optional\[[Attributes](toloka.client.user.User.Attributes.md)\]**|<p>Information obtained from the device.</p>
