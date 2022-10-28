# AssignmentSortItems
`toloka.client.search_requests.AssignmentSortItems`

```python
AssignmentSortItems(self, items=None)
```

Keys for sorting assignments in search results.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`items`|**Optional\[List\[[SortItem](toloka.client.search_requests.AssignmentSortItems.SortItem.md)\]\]**|<p>A list of sorting keys. Supported values:</p> <ul> <li>`&#x27;id&#x27;` — An assignment ID.</li> <li>`&#x27;created&#x27;` — The assigning date of a task suite.</li> <li>`&#x27;submitted&#x27;` — The completion date of a task suite.</li> <li>`&#x27;accepted&#x27;` — The acceptance date of a task suite.</li> <li>`&#x27;rejected&#x27;` — The rejection date a task suite.</li> <li>`&#x27;skipped&#x27;` — The date when a task suite was skipped.</li> <li>`&#x27;expired&#x27;` — The expiration date of a task suite.</li> </ul>

**Examples:**

The example shows how to find assignments sorted by the completion date in descending order. Assignments with equal completion dates are sorted by IDs in ascending order.

```python
sort = toloka.client.search_requests.AssignmentSortItems(['-submitted', 'id'])
result = toloka_client.find_assignments(status='SUBMITTED', sort=sort, limit=10)
```
