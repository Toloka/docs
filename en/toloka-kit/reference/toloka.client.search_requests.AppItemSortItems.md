# AppItemSortItems
`toloka.client.search_requests.AppItemSortItems`

```python
AppItemSortItems(self, items=None)
```

Keys for sorting App items in search results.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`items`|**Optional\[List\[[SortItem](toloka.client.search_requests.AppItemSortItems.SortItem.md)\]\]**|<p>A list of sorting keys. Supported values:</p> <ul> <li>`&#x27;id&#x27;` — A task item ID.</li> <li>`&#x27;created&#x27;` — The date and time when the item was created.</li> <li>`&#x27;finished&#x27;` — The date and time when the item processing was completed.</li> <li>`&#x27;status&#x27;` — The item status.</li> </ul>
