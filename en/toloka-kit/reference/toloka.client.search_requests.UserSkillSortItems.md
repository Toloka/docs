# UserSkillSortItems
`toloka.client.search_requests.UserSkillSortItems`

```python
UserSkillSortItems(self, items=None)
```

Keys for sorting skills in search results.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`items`|**Optional\[List\[[SortItem](toloka.client.search_requests.UserSkillSortItems.SortItem.md)\]\]**|<p>A list of sorting keys. Supported values:</p> <ul> <li>`&#x27;id&#x27;` — The ID of a skill.</li> <li>`&#x27;created&#x27;` — The date when a skill was created.</li> <li>`&#x27;modified&#x27;` — The date when a skill was modified.</li> </ul>

**Examples:**

The example shows how to find Tolokers' skills sorted by creation date in descending order. Skills with equal creation dates are sorted by IDs in ascending order.

```python
sort = toloka.client.search_requests.UserSkillSortItems(['-created', 'id'])
result = toloka_client.find_user_skills(skill_id=my_useful_skill_id, sort=sort, limit=10)
```
