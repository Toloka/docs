# AppProjectSearchRequest
`toloka.client.search_requests.AppProjectSearchRequest` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.0.2/src/client/search_requests.py#L953)

```python
AppProjectSearchRequest(
    self,
    app_id: Optional[str] = None,
    parent_app_project_id: Optional[str] = None,
    status: Optional[AppProject.Status] = None,
    after_id: Optional[str] = None,
    scope: Optional[Scope] = None,
    requester_ids: Union[str, List[str], None] = None,
    id_lt: Optional[str] = None,
    id_lte: Optional[str] = None,
    id_gt: Optional[str] = None,
    id_gte: Optional[str] = None,
    name_lt: Optional[str] = None,
    name_lte: Optional[str] = None,
    name_gt: Optional[str] = None,
    name_gte: Optional[str] = None,
    created_lt: Optional[datetime] = None,
    created_lte: Optional[datetime] = None,
    created_gt: Optional[datetime] = None,
    created_gte: Optional[datetime] = None
)
```

Parameters for searching App projects.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`app_id`|**Optional\[str\]**|<p>Projects created using the solution with the specified ID.</p>
`parent_app_project_id`|**Optional\[str\]**|<p>Projects cloned from the project with the specified ID. Projects can be cloned in the web version of Toloka.</p>
`status`|**Optional\[[AppProject.Status](toloka.client.app.AppProject.Status.md)\]**|<p>App project status. Refer to the [AppProject.Status](toloka.client.app.AppProject.Status.md) page for more information on the available `status` values.</p>
`after_id`|**Optional\[str\]**|<p>The ID of a project used for cursor pagination.</p>
`scope`|**Optional\[[Scope](toloka.client.search_requests.AppProjectSearchRequest.Scope.md)\]**|<p>Values:</p> <ul> <li>`&#x27;MY&#x27;` — Projects created by you.</li> <li>`&#x27;COMPANY&#x27;` — Projects created by requesters from your company.</li> <li>`&#x27;REQUESTER_LIST&#x27;` — Projects created by requesters in the `requester_ids` list.</li> </ul>
`requester_ids`|**Optional\[List\[str\]\]**|<p>A list with requester IDs separated by a comma. Use the list with parameter `scope = REQUESTER_LIST`.</p>
`id_gt`|**Optional\[str\]**|<p>Projects with IDs greater than the specified value.</p>
`id_gte`|**Optional\[str\]**|<p>Projects with IDs greater than or equal to the specified value.</p>
`id_lt`|**Optional\[str\]**|<p>Projects with IDs less than the specified value.</p>
`id_lte`|**Optional\[str\]**|<p>Projects with IDs less than or equal to the specified value.</p>
`name_gt`|**Optional\[str\]**|<p>Projects with a name lexicographically greater than the specified value.</p>
`name_gte`|**Optional\[str\]**|<p>Projects with a name lexicographically greater than or equal to the specified value.</p>
`name_lt`|**Optional\[str\]**|<p>Projects with a name lexicographically less than the specified value.</p>
`name_lte`|**Optional\[str\]**|<p>Projects with a name lexicographically less than or equal to the specified value.</p>
`created_gt`|**Optional\[datetime\]**|<p>Projects created after the specified date.</p>
`created_gte`|**Optional\[datetime\]**|<p>Projects created after or on the specified date.</p>
`created_lt`|**Optional\[datetime\]**|<p>Projects created before the specified date.</p>
`created_lte`|**Optional\[datetime\]**|<p>Projects created before or on the specified date.</p>
