# AttachmentSearchResult
`toloka.client.search_results.AttachmentSearchResult`

```python
AttachmentSearchResult(
    self,
    *,
    items: Optional[List[Attachment]] = None,
    has_more: Optional[bool] = None
)
```

The result of searching attachments.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`items`|**Optional\[List\[[Attachment](toloka.client.attachment.Attachment.md)\]\]**|<p>A list with found attachments.</p>
`has_more`|**Optional\[bool\]**|<p>A flag showing whether there are more matching attachments.</p> <ul> <li>`True` — There are more matching attachments, not included in `items` due to the limit set in the search request.</li> <li>`False` — `items` contains all matching attachments.</li> </ul>
