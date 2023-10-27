# Requester
`toloka.client.requester.Requester` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.2/src/client/requester.py#L9)

```python
Requester(
    self,
    *,
    id: Optional[str] = None,
    balance: Optional[Decimal] = None,
    public_name: Optional[Dict[str, str]] = None,
    company: Optional[Company] = None
)
```

Information about a requester.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`id`|**Optional\[str\]**|<p>The requester&#x27;s ID.</p>
`balance`|**Optional\[Decimal\]**|<p>Account balance in dollars.</p>
`public_name`|**Optional\[Dict\[str, str\]\]**|<p>The requester&#x27;s name in Toloka.</p>
`company`|**Optional\[[Company](toloka.client.requester.Requester.Company.md)\]**|<p>Information about a requester&#x27;s company.</p>
