# AttachmentSortItems
`toloka.client.search_requests.AttachmentSortItems`

```python
AttachmentSortItems(self, items=None)
```

Keys for sorting attachments in search results.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`items`|**Optional\[List\[[SortItem](toloka.client.search_requests.AttachmentSortItems.SortItem.md)\]\]**|<p>A list of sorting keys. Supported values:</p> <ul> <li>`&#x27;id&#x27;` — The ID of an attachment.</li> <li>`&#x27;created&#x27;` — The date of uploading an attachment.</li> </ul>

**Examples:**

The example shows how to find attachments sorted by uploading date in descending order. Attachments with equal uploading dates are sorted by IDs in descending order.

```python
sort = toloka.client.search_requests.AttachmentSortItems(['-created', '-id'])
result = toloka_client.find_attachments(pool_id='1086170', sort=sort, limit=10)
```
