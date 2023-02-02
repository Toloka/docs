# AsyncTolokaClient
`toloka.async_client.client.AsyncTolokaClient` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.3/src/async_client/client.py#L27)

```python
AsyncTolokaClient(
    self,
    token: str,
    environment: Union[TolokaClient.Environment, str, None] = None,
    retries: Union[int, Retry] = 3,
    timeout: Union[float, Tuple[float, float]] = 10.0,
    url: Optional[str] = None,
    retry_quotas: Union[List[str], str, None] = 'MIN',
    retryer_factory: Optional[Callable[[], Retry]] = None,
    act_under_account_id: Optional[str] = None
)
```

Class that implements interaction with [Toloka API](https://toloka.ai/en/docs/api/), in an asynchronous way.


All methods are wrapped as async. So all methods calls must be awaited.
All arguments, same as in TolokaClient.

## Methods Summary

| Method | Description |
| :------| :-----------|
[accept_assignment](toloka.async_client.client.AsyncTolokaClient.accept_assignment.md)| Accepts an assignment.
[add_message_thread_to_folders](toloka.async_client.client.AsyncTolokaClient.add_message_thread_to_folders.md)| Adds a message chain to one or more folders ("unread", "important" etc.)
[aggregate_solutions_by_pool](toloka.async_client.client.AsyncTolokaClient.aggregate_solutions_by_pool.md)| Starts aggregation of responses in all completed tasks in a pool.
[aggregate_solutions_by_task](toloka.async_client.client.AsyncTolokaClient.aggregate_solutions_by_task.md)| Aggregates responses to a single task on the Toloka server.
[archive_app_project](toloka.async_client.client.AsyncTolokaClient.archive_app_project.md)| Archives an App project.
[archive_pool](toloka.async_client.client.AsyncTolokaClient.archive_pool.md)| Archives a pool.
[archive_pool_async](toloka.async_client.client.AsyncTolokaClient.archive_pool_async.md)| Archives a pool. Sends an asynchronous request to Toloka.
[archive_project](toloka.async_client.client.AsyncTolokaClient.archive_project.md)| Sends project to archive
[archive_project_async](toloka.async_client.client.AsyncTolokaClient.archive_project_async.md)| Sends project to archive, asynchronous version
[archive_training](toloka.async_client.client.AsyncTolokaClient.archive_training.md)| Archives a training.
[archive_training_async](toloka.async_client.client.AsyncTolokaClient.archive_training_async.md)| Archives a training. Sends an asynchronous request to Toloka.
[clone_pool](toloka.async_client.client.AsyncTolokaClient.clone_pool.md)| Clones an existing pool.
[clone_pool_async](toloka.async_client.client.AsyncTolokaClient.clone_pool_async.md)| Clones an existing pool. Sends an asynchronous request to Toloka.
[clone_project](toloka.async_client.client.AsyncTolokaClient.clone_project.md)| Synchronously clones the project, all pools and trainings
[clone_training](toloka.async_client.client.AsyncTolokaClient.clone_training.md)| Clones an existing training.
[clone_training_async](toloka.async_client.client.AsyncTolokaClient.clone_training_async.md)| Clones an existing training. Sends an asynchronous request to Toloka.
[close_pool](toloka.async_client.client.AsyncTolokaClient.close_pool.md)| Closes a pool.
[close_pool_async](toloka.async_client.client.AsyncTolokaClient.close_pool_async.md)| Closes a pool. Sends an asynchronous request to Toloka.
[close_pool_for_update](toloka.async_client.client.AsyncTolokaClient.close_pool_for_update.md)| Closes a pool that is to be updated.
[close_pool_for_update_async](toloka.async_client.client.AsyncTolokaClient.close_pool_for_update_async.md)| Closes a pool that is to be updated. Sends an asynchronous request to Toloka.
[close_training](toloka.async_client.client.AsyncTolokaClient.close_training.md)| Closes a training.
[close_training_async](toloka.async_client.client.AsyncTolokaClient.close_training_async.md)| Closes a training. Sends an asynchronous request to Toloka.
[compose_message_thread](toloka.async_client.client.AsyncTolokaClient.compose_message_thread.md)| Sends a message to a Toloker.
[create_app_batch](toloka.async_client.client.AsyncTolokaClient.create_app_batch.md)| Creates a batch with task items in an App project in Toloka.
[create_app_item](toloka.async_client.client.AsyncTolokaClient.create_app_item.md)| Creates an App task item in Toloka.
[create_app_items](toloka.async_client.client.AsyncTolokaClient.create_app_items.md)| Creates task items in an App project in Toloka and adds them to an existing batch.
[create_app_project](toloka.async_client.client.AsyncTolokaClient.create_app_project.md)| Creates an App project in Toloka.
[create_pool](toloka.async_client.client.AsyncTolokaClient.create_pool.md)| Creates a new pool in Toloka.
[create_project](toloka.async_client.client.AsyncTolokaClient.create_project.md)| Creates a new project
[create_skill](toloka.async_client.client.AsyncTolokaClient.create_skill.md)| Creates a new Skill
[create_task](toloka.async_client.client.AsyncTolokaClient.create_task.md)| Creates a new task in Toloka.
[create_task_suite](toloka.async_client.client.AsyncTolokaClient.create_task_suite.md)| Creates a task suite in Toloka.
[create_task_suites](toloka.async_client.client.AsyncTolokaClient.create_task_suites.md)| Creates several task suites in Toloka.
[create_task_suites_async](toloka.async_client.client.AsyncTolokaClient.create_task_suites_async.md)| Creates several task suites in Toloka asynchronously.
[create_tasks](toloka.async_client.client.AsyncTolokaClient.create_tasks.md)| Creates several tasks in Toloka.
[create_tasks_async](toloka.async_client.client.AsyncTolokaClient.create_tasks_async.md)| Creates tasks in Toloka asynchronously.
[create_training](toloka.async_client.client.AsyncTolokaClient.create_training.md)| Creates a new training in Toloka.
[create_user_bonus](toloka.async_client.client.AsyncTolokaClient.create_user_bonus.md)| Issues payments directly to a Toloker.
[create_user_bonuses](toloka.async_client.client.AsyncTolokaClient.create_user_bonuses.md)| Creates rewards for Tolokers.
[create_user_bonuses_async](toloka.async_client.client.AsyncTolokaClient.create_user_bonuses_async.md)| Issues payments directly to Tolokers, asynchronously creates many `UserBonus` instances.
[delete_user_restriction](toloka.async_client.client.AsyncTolokaClient.delete_user_restriction.md)| Unlocks existing restriction
[delete_user_skill](toloka.async_client.client.AsyncTolokaClient.delete_user_skill.md)| Drop specific UserSkill
[delete_webhook_subscription](toloka.async_client.client.AsyncTolokaClient.delete_webhook_subscription.md)| Drop specific webhook-subscription
[download_attachment](toloka.async_client.client.AsyncTolokaClient.download_attachment.md)| Downloads specific attachment
[find_aggregated_solutions](toloka.async_client.client.AsyncTolokaClient.find_aggregated_solutions.md)| Finds aggregated responses that match certain criteria.
[find_app_batches](toloka.async_client.client.AsyncTolokaClient.find_app_batches.md)| Finds batches that match certain criteria in an App project.
[find_app_items](toloka.async_client.client.AsyncTolokaClient.find_app_items.md)| Finds task items that match certain criteria in an App project.
[find_app_projects](toloka.async_client.client.AsyncTolokaClient.find_app_projects.md)| Finds App projects that match certain criteria.
[find_apps](toloka.async_client.client.AsyncTolokaClient.find_apps.md)| Finds App solutions that match certain criteria.
[find_assignments](toloka.async_client.client.AsyncTolokaClient.find_assignments.md)| Finds assignments that match certain criteria.
[find_attachments](toloka.async_client.client.AsyncTolokaClient.find_attachments.md)| Finds attachments that match certain criteria and returns their metadata.
[find_message_threads](toloka.async_client.client.AsyncTolokaClient.find_message_threads.md)| Finds message threads that match certain criteria.
[find_operations](toloka.async_client.client.AsyncTolokaClient.find_operations.md)| Finds operations that match certain criteria.
[find_pools](toloka.async_client.client.AsyncTolokaClient.find_pools.md)| Finds pools that match certain criteria.
[find_projects](toloka.async_client.client.AsyncTolokaClient.find_projects.md)| Finds projects that match certain criteria.
[find_skills](toloka.async_client.client.AsyncTolokaClient.find_skills.md)| Finds skills that match certain criteria.
[find_task_suites](toloka.async_client.client.AsyncTolokaClient.find_task_suites.md)| Finds task suites that match certain criteria.
[find_tasks](toloka.async_client.client.AsyncTolokaClient.find_tasks.md)| Finds tasks that match certain criteria.
[find_trainings](toloka.async_client.client.AsyncTolokaClient.find_trainings.md)| Finds trainings that match certain criteria.
[find_user_bonuses](toloka.async_client.client.AsyncTolokaClient.find_user_bonuses.md)| Finds Tolokers' rewards that match certain criteria.
[find_user_restrictions](toloka.async_client.client.AsyncTolokaClient.find_user_restrictions.md)| Finds Toloker restrictions that match certain criteria.
[find_user_skills](toloka.async_client.client.AsyncTolokaClient.find_user_skills.md)| Finds Toloker's skills that match certain criteria.
[find_webhook_subscriptions](toloka.async_client.client.AsyncTolokaClient.find_webhook_subscriptions.md)| Finds webhook subscriptions that match certain criteria.
[from_sync_client](toloka.async_client.client.AsyncTolokaClient.from_sync_client.md)| None
[get_aggregated_solutions](toloka.async_client.client.AsyncTolokaClient.get_aggregated_solutions.md)| Finds all aggregated responses that match certain criteria.
[get_analytics](toloka.async_client.client.AsyncTolokaClient.get_analytics.md)| Sends analytics queries, for example, to estimate the percentage of completed tasks in the pool
[get_app](toloka.async_client.client.AsyncTolokaClient.get_app.md)| Gets information from Toloka about an App solution.
[get_app_batch](toloka.async_client.client.AsyncTolokaClient.get_app_batch.md)| Gets information from Toloka about a batch in an App project.
[get_app_batches](toloka.async_client.client.AsyncTolokaClient.get_app_batches.md)| Finds all batches that match certain criteria in an App project.
[get_app_item](toloka.async_client.client.AsyncTolokaClient.get_app_item.md)| Gets information from Toloka about an App task item.
[get_app_items](toloka.async_client.client.AsyncTolokaClient.get_app_items.md)| Finds all App task items that match certain criteria in an App project.
[get_app_project](toloka.async_client.client.AsyncTolokaClient.get_app_project.md)| Gets information from Toloka about an App project.
[get_app_projects](toloka.async_client.client.AsyncTolokaClient.get_app_projects.md)| Finds all App projects that match certain criteria.
[get_apps](toloka.async_client.client.AsyncTolokaClient.get_apps.md)| Finds all App solutions that match certain criteria.
[get_assignment](toloka.async_client.client.AsyncTolokaClient.get_assignment.md)| Gets an assignment from Toloka.
[get_assignments](toloka.async_client.client.AsyncTolokaClient.get_assignments.md)| Finds all assignments that match certain criteria.
[get_assignments_df](toloka.async_client.client.AsyncTolokaClient.get_assignments_df.md)| Downloads assignments as pandas.DataFrame.
[get_attachment](toloka.async_client.client.AsyncTolokaClient.get_attachment.md)| Gets attachment metadata without downloading it
[get_attachments](toloka.async_client.client.AsyncTolokaClient.get_attachments.md)| Finds all attachments that match certain criteria and returns their metadata.
[get_message_threads](toloka.async_client.client.AsyncTolokaClient.get_message_threads.md)| Finds all message threads that match certain criteria.
[get_operation](toloka.async_client.client.AsyncTolokaClient.get_operation.md)| Reads information about operation
[get_operation_log](toloka.async_client.client.AsyncTolokaClient.get_operation_log.md)| Reads information about validation errors and which task (or task suites) were created
[get_operations](toloka.async_client.client.AsyncTolokaClient.get_operations.md)| Finds all operations that match certain rules and returns them in an iterable object
[get_pool](toloka.async_client.client.AsyncTolokaClient.get_pool.md)| Gets pool data from Toloka.
[get_pools](toloka.async_client.client.AsyncTolokaClient.get_pools.md)| Finds all pools that match certain criteria.
[get_project](toloka.async_client.client.AsyncTolokaClient.get_project.md)| Reads one specific project
[get_projects](toloka.async_client.client.AsyncTolokaClient.get_projects.md)| Finds all projects that match certain criteria.
[get_requester](toloka.async_client.client.AsyncTolokaClient.get_requester.md)| Reads information about the customer and the account balance
[get_skill](toloka.async_client.client.AsyncTolokaClient.get_skill.md)| Reads one specific skill
[get_skills](toloka.async_client.client.AsyncTolokaClient.get_skills.md)| Finds all skills that match certain criteria.
[get_task](toloka.async_client.client.AsyncTolokaClient.get_task.md)| Gets a task with specified ID from Toloka.
[get_task_suite](toloka.async_client.client.AsyncTolokaClient.get_task_suite.md)| Reads one task suite.
[get_task_suites](toloka.async_client.client.AsyncTolokaClient.get_task_suites.md)| Finds all task suites that match certain criteria.
[get_tasks](toloka.async_client.client.AsyncTolokaClient.get_tasks.md)| Finds all tasks that match certain criteria.
[get_training](toloka.async_client.client.AsyncTolokaClient.get_training.md)| Gets information about a training from Toloka.
[get_trainings](toloka.async_client.client.AsyncTolokaClient.get_trainings.md)| Finds all trainings that match certain criteria.
[get_user](toloka.async_client.client.AsyncTolokaClient.get_user.md)| Gets Toloker metadata by `user_id`.
[get_user_bonus](toloka.async_client.client.AsyncTolokaClient.get_user_bonus.md)| Gets information about a Toloker's reward.
[get_user_bonuses](toloka.async_client.client.AsyncTolokaClient.get_user_bonuses.md)| Finds all Tolokers' rewards that match certain rules and returns them in an iterable object
[get_user_restriction](toloka.async_client.client.AsyncTolokaClient.get_user_restriction.md)| Gets information about a Toloker restriction.
[get_user_restrictions](toloka.async_client.client.AsyncTolokaClient.get_user_restrictions.md)| Finds all Toloker restrictions that match certain criteria.
[get_user_skill](toloka.async_client.client.AsyncTolokaClient.get_user_skill.md)| Gets the value of a Toloker's skill
[get_user_skills](toloka.async_client.client.AsyncTolokaClient.get_user_skills.md)| Finds all Toloker's skills that match certain criteria.
[get_webhook_subscription](toloka.async_client.client.AsyncTolokaClient.get_webhook_subscription.md)| Get one specific webhook-subscription
[get_webhook_subscriptions](toloka.async_client.client.AsyncTolokaClient.get_webhook_subscriptions.md)| Finds all webhook subscriptions that match certain criteria.
[open_pool](toloka.async_client.client.AsyncTolokaClient.open_pool.md)| Opens a pool.
[open_pool_async](toloka.async_client.client.AsyncTolokaClient.open_pool_async.md)| Opens a pool. Sends an asynchronous request to Toloka.
[open_training](toloka.async_client.client.AsyncTolokaClient.open_training.md)| Opens a training.
[open_training_async](toloka.async_client.client.AsyncTolokaClient.open_training_async.md)| Opens a training. Sends an asynchronous request to Toloka.
[patch_app_batch](toloka.async_client.client.AsyncTolokaClient.patch_app_batch.md)| Updates an App batch name.
[patch_assignment](toloka.async_client.client.AsyncTolokaClient.patch_assignment.md)| Changes an assignment status and associated public comment.
[patch_pool](toloka.async_client.client.AsyncTolokaClient.patch_pool.md)| Changes pool parameters in Toloka.
[patch_task](toloka.async_client.client.AsyncTolokaClient.patch_task.md)| Changes a task overlap value.
[patch_task_overlap_or_min](toloka.async_client.client.AsyncTolokaClient.patch_task_overlap_or_min.md)| Stops assigning a task to Tolokers.
[patch_task_suite](toloka.async_client.client.AsyncTolokaClient.patch_task_suite.md)| Changes task suite parameter values in Toloka.
[patch_task_suite_overlap_or_min](toloka.async_client.client.AsyncTolokaClient.patch_task_suite_overlap_or_min.md)| Stops issuing the task suites
[reject_assignment](toloka.async_client.client.AsyncTolokaClient.reject_assignment.md)| Rejects an assignment.
[remove_message_thread_from_folders](toloka.async_client.client.AsyncTolokaClient.remove_message_thread_from_folders.md)| Deletes a message chain from one or more folders ("unread", "important" etc.)
[reply_message_thread](toloka.async_client.client.AsyncTolokaClient.reply_message_thread.md)| Replies to a message in thread
[resume_app_batch](toloka.async_client.client.AsyncTolokaClient.resume_app_batch.md)| Resumes annotation of a batch of task items in an App project.
[set_user_restriction](toloka.async_client.client.AsyncTolokaClient.set_user_restriction.md)| Restricts access to projects or pools for a Toloker.
[set_user_skill](toloka.async_client.client.AsyncTolokaClient.set_user_skill.md)| Assigns a skill to a Toloker.
[start_app_batch](toloka.async_client.client.AsyncTolokaClient.start_app_batch.md)| Launches annotation of a batch of task items in an App project.
[stop_app_batch](toloka.async_client.client.AsyncTolokaClient.stop_app_batch.md)| Stops annotation of a batch of task items in an App project.
[unarchive_app_project](toloka.async_client.client.AsyncTolokaClient.unarchive_app_project.md)| Unarchives an App project.
[update_pool](toloka.async_client.client.AsyncTolokaClient.update_pool.md)| Updates all pool parameters in Toloka.
[update_project](toloka.async_client.client.AsyncTolokaClient.update_project.md)| Makes changes to the project
[update_skill](toloka.async_client.client.AsyncTolokaClient.update_skill.md)| Makes changes to the skill
[update_training](toloka.async_client.client.AsyncTolokaClient.update_training.md)| Updates parameters of a training in Toloka.
[upsert_webhook_subscriptions](toloka.async_client.client.AsyncTolokaClient.upsert_webhook_subscriptions.md)| Creates (upsert) many webhook-subscriptions.
[wait_operation](toloka.async_client.client.AsyncTolokaClient.wait_operation.md)| Asynchronous version of wait_operation
