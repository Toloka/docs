# AppSearchRequest
`toloka.client.search_requests.AppSearchRequest` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.1/src/client/search_requests.py#L1029)

```python
AppSearchRequest(
    self,
    after_id: Optional[str] = None,
    lang: Optional[str] = None,
    id_lt: Optional[str] = None,
    id_lte: Optional[str] = None,
    id_gt: Optional[str] = None,
    id_gte: Optional[str] = None
)
```

Parameters for searching App solutions.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`after_id`|**Optional\[str\]**|<p>The ID of a solution used for cursor pagination.</p>
`lang`|**Optional\[str\]**|<p>ISO 639 language code.</p>
`id_gt`|**Optional\[str\]**|<p>Solutions with IDs greater than the specified value.</p>
`id_gte`|**Optional\[str\]**|<p>Solutions with IDs greater than or equal to the specified value.</p>
`id_lt`|**Optional\[str\]**|<p>Solutions with IDs less than the specified value.</p>
`id_lte`|**Optional\[str\]**|<p>Solutions with IDs less than or equal to the specified value.</p>
`name_gt`|**-**|<p>Solutions with names lexicographically greater than the specified value.</p>
`name_gte`|**-**|<p>Solutions with names lexicographically greater than or equal to the specified value.</p>
`name_lt`|**-**|<p>Solutions with names lexicographically less than the specified value.</p>
`name_lte`|**-**|<p>Solutions with names lexicographically less than or equal to the specified value.</p>
