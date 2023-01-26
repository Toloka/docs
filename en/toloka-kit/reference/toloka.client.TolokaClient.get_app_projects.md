# get_app_projects
`toloka.client.TolokaClient.get_app_projects` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.2/src/client/__init__.py#L3562)

Finds all App projects that match certain criteria.


`get_app_projects` returns a generator. You can iterate over all found projects using the generator. Several requests to the Toloka server are possible while iterating.

If you need to sort App projects use the [find_app_projects](toloka.client.TolokaClient.find_app_projects.md) method.

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`app_id`|**Optional\[str\]**|<p>Projects created using the solution with the specified ID.</p>
`parent_app_project_id`|**Optional\[str\]**|<p>Projects cloned from the project with the specified ID. Projects can be cloned in the web version of Toloka.</p>
`status`|**Optional\[[AppProject.Status](toloka.client.app.AppProject.Status.md)\]**|<p>App project status. Refer to the [AppProject.Status](toloka.client.app.AppProject.Status.md) page for more information on the available `status` values.</p>
`after_id`|**Optional\[str\]**|<p>The ID of a project used for cursor pagination.</p>
`scope`|**Optional\[[AppProjectSearchRequest.Scope](toloka.client.search_requests.AppProjectSearchRequest.Scope.md)\]**|<p>Values:</p> <ul> <li>`&#x27;MY&#x27;` — Projects created by you.</li> <li>`&#x27;COMPANY&#x27;` — Projects created by requesters from your company.</li> <li>`&#x27;REQUESTER_LIST&#x27;` — Projects created by requesters in the `requester_ids` list.</li> </ul>
`requester_ids`|**Union\[str, List\[str\], None\]**|<p>A list with requester IDs separated by a comma. Use the list with parameter `scope = REQUESTER_LIST`.</p>
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
`batch_size`|**Optional\[int\]**|<p>Returned projects limit for each request. The maximum batch_size is 5000.</p>

* **Yields:**

  The next matching App project.

* **Yield type:**

  Generator\[[AppProject](toloka.client.app.AppProject.md), None, None\]
