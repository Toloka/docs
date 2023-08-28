# Owner
`toloka.client.owner.Owner` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/owner.py#L4)

```python
Owner(
    self,
    *,
    id: Optional[str] = None,
    myself: Optional[bool] = None,
    company_id: Optional[str] = None
)
```

Information about a requester who owns some object.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`id`|**Optional\[str\]**|<p>The ID of the requester.</p>
`myself`|**Optional\[bool\]**|<p>A match of the owner OAuth token with the token that is used in the request:</p> <ul> <li>`True` — The tokens are the same.</li> <li>`False` — The tokens are different.</li> </ul>
`company_id`|**Optional\[str\]**|<p>The ID of the requester's company.</p>
