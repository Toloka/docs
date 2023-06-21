# Owner
`toloka.client.owner.Owner` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0.post1/src/client/owner.py#L4)

```python
Owner(
    self,
    *,
    id: Optional[str] = None,
    myself: Optional[bool] = None,
    company_id: Optional[str] = None
)
```

Parameters of the customer who created an object.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`id`|**Optional\[str\]**|<p>Customer ID.</p>
`myself`|**Optional\[bool\]**|<p>An object accessory marker. Possible values:</p> <ul> <li>`True` — An object is created by the customer whose OAuth token is used in the request.</li> <li>`False` — An object does not belong to the customer whose OAuth token is used in the request.</li> </ul>
`company_id`|**Optional\[str\]**|<p>ID of the customer&#x27;s company.</p>
