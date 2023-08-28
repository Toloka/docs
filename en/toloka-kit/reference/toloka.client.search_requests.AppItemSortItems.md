# AppItemSortItems
`toloka.client.search_requests.AppItemSortItems`

```python
AppItemSortItems(self, items=None)
```

Keys for sorting App items in search results.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`items`|**Optional\[List\[[SortItem](toloka.client.search_requests.AppItemSortItems.SortItem.md)\]\]**|<p>A list of sorting keys. Supported values:</p> <ul> <li>`'id'` — A task item ID.</li> <li>`'created'` — The date and time when the item was created.</li> <li>`'finished'` — The date and time when the item processing was completed.</li> <li>`'status'` — The item status.</li> </ul>
