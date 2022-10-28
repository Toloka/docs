# MessageThreadSearchResult
`toloka.client.search_results.MessageThreadSearchResult`

```python
MessageThreadSearchResult(
    self,
    *,
    items: Optional[List[MessageThread]] = None,
    has_more: Optional[bool] = None
)
```

The result of searching message threads.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`items`|**Optional\[List\[[MessageThread](toloka.client.message_thread.MessageThread.md)\]\]**|<p>A list with found message threads.</p>
`has_more`|**Optional\[bool\]**|<p>A flag showing whether there are more matching message threads.</p> <ul> <li>`True` — There are more matching message threads, not included in `items` due to the limit set in the search request.</li> <li>`False` — `items` contains all matching message threads.</li> </ul>
