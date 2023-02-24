# Pool
`toloka.client.pool.Pool` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.1.4/src/client/pool/__init__.py#L35)

```python
Pool(
    self,
    *,
    project_id: Optional[str] = None,
    private_name: Optional[str] = None,
    may_contain_adult_content: Optional[bool] = None,
    reward_per_assignment: Optional[float] = None,
    assignment_max_duration_seconds: Optional[int] = None,
    defaults: Optional[Defaults] = ...,
    will_expire: Optional[datetime] = None,
    private_comment: Optional[str] = None,
    public_description: Optional[str] = None,
    public_instructions: Optional[str] = None,
    auto_close_after_complete_delay_seconds: Optional[int] = None,
    dynamic_pricing_config: Optional[DynamicPricingConfig] = None,
    auto_accept_solutions: Optional[bool] = None,
    auto_accept_period_day: Optional[int] = None,
    assignments_issuing_config: Optional[AssignmentsIssuingConfig] = None,
    priority: Optional[int] = None,
    filter: Optional[FilterCondition] = None,
    quality_control: Optional[QualityControl] = ...,
    speed_quality_balance: Optional[SpeedQualityBalanceConfig] = None,
    dynamic_overlap_config: Optional[DynamicOverlapConfig] = None,
    mixer_config: Optional[MixerConfig] = None,
    training_config: Optional[TrainingConfig] = None,
    metadata: Optional[Dict[str, List[str]]] = None,
    owner: Optional[Owner] = None,
    id: Optional[str] = None,
    status: Optional[Status] = None,
    last_close_reason: Optional[CloseReason] = None,
    created: Optional[datetime] = None,
    last_started: Optional[datetime] = None,
    last_stopped: Optional[datetime] = None,
    type: Optional[Type] = None
)
```

A set of [tasks](toloka.client.task.Task.md) that share the same properties.


In the pool properties, you set the task price, overlap, Toloker selection filters, quality control rules, and so on.

Pool tasks are grouped into [task suites](toloka.client.task_suite.TaskSuite.md). Whole task suites are assigned to Tolokers.

Learn more about:
* [Pools](https://toloka.ai/en/docs/guide/concepts/pool-main)
* [Pricing](https://toloka.ai/en/docs/guide/concepts/dynamic-pricing)

## Parameters Description

| Parameters | Type | Description |
| :----------| :----| :-----------|
`project_id`|**Optional\[str\]**|<p>The ID of the project containing the pool.</p>
`private_name`|**Optional\[str\]**|<p>The pool name. It is visible to the requester and is not visible to Tolokers.</p>
`may_contain_adult_content`|**Optional\[bool\]**|<p>The presence of adult content.</p>
`reward_per_assignment`|**Optional\[float\]**|<p>Payment in US dollars for a Toloker for completing a task suite. For cents, use the dot as a separator. If the pool `type` is `REGULAR`, the minimum payment per task suite is $0.005. For other pool types, you can set the `reward_per_assignment` to zero.</p>
`assignment_max_duration_seconds`|**Optional\[int\]**|<p>Time limit to complete one task suite. Take into account loading a page with a task suite and sending responses to the server. It is recommended that you set at least 60 seconds. Tasks not completed within the limit are reassigned to other Tolokers.</p>
`defaults`|**Optional\[[Defaults](toloka.client.pool.Pool.Defaults.md)\]**|<p>Default settings that are applied to new tasks in the pool.</p>
`will_expire`|**Optional\[datetime\]**|<p>The UTC date and time when the pool is closed automatically, even if not all tasks are completed.</p>
`private_comment`|**Optional\[str\]**|<p>A comment about the pool. It is visible to the requester and is not visible to Tolokers.</p>
`public_description`|**Optional\[str\]**|<p>The pool description. If pool&#x27;s `public_description` is not set, then project&#x27;s `public_description` is used.</p>
`public_instructions`|**Optional\[str\]**|<p>The pool instructions for Tolokers. If pool&#x27;s `public_instructions` is not set, then project&#x27;s `public_instructions` is used.</p>
`auto_close_after_complete_delay_seconds`|**Optional\[int\]**|<p>The pool remains open after all tasks are completed during the specified time in seconds. Use non zero value if:</p> <ul> <li>You process data in real time.</li> <li>The pool must stay open so that you can upload new tasks.</li> <li>Dynamic overlap is enabled in the pool.</li> </ul> <p>Allowed range: from 0 to 259200 seconds (3 days). The default value is 0.</p>
`dynamic_pricing_config`|**Optional\[[DynamicPricingConfig](toloka.client.pool.dynamic_pricing_config.DynamicPricingConfig.md)\]**|<p>The dynamic pricing settings.</p>
`auto_accept_solutions`|**Optional\[bool\]**|<ul> <li>`True` — Responses from Tolokers are accepted or rejected automatically based on some rules.</li> <li>`False` — Responses are checked manually. Time reserved for checking is limited by the `auto_accept_period_day` parameter.   Learn more about [non-automatic acceptance](https://toloka.ai/en/docs/guide/concepts/offline-accept).</li> </ul>
`auto_accept_period_day`|**Optional\[int\]**|<p>The number of days reserved for checking responses if the `auto_accept_solutions` parameter is set to `False`.</p>
`assignments_issuing_config`|**Optional\[[AssignmentsIssuingConfig](toloka.client.pool.Pool.AssignmentsIssuingConfig.md)\]**|<p>Settings for assigning tasks in the pool.</p>
`priority`|**Optional\[int\]**|<p>The priority of the pool in relation to other pools in the project with the same task price and set of filters. Tolokers are assigned tasks with a higher priority first.</p> <p>Allowed range: from 0 to 100. The default value is 0.</p>
`filter`|**Optional\[[FilterCondition](toloka.client.filter.FilterCondition.md)\]**|<p>Settings for Toloker selection filters.</p>
`quality_control`|**Optional\[[QualityControl](toloka.client.quality_control.QualityControl.md)\]**|<p>Settings for quality control rules and the ID of the pool with training tasks.</p>
`speed_quality_balance`|**Optional\[[SpeedQualityBalanceConfig](toloka.client.pool.speed_quality_balance_config.SpeedQualityBalanceConfig.md)\]**|<p>Settings for choosing Tolokers for your tasks.</p>
`dynamic_overlap_config`|**Optional\[[DynamicOverlapConfig](toloka.client.pool.dynamic_overlap_config.DynamicOverlapConfig.md)\]**|<p>Dynamic overlap settings.</p>
`mixer_config`|**Optional\[[MixerConfig](toloka.client.pool.mixer_config.MixerConfig.md)\]**|<p>Parameters for automatically creating task suites.</p>
`training_config`|**Optional\[[TrainingConfig](toloka.client.pool.Pool.TrainingConfig.md)\]**|<p>Additional settings for linked training.</p>
`metadata`|**Optional\[Dict\[str, List\[str\]\]\]**|<p>A dictionary with metadata.</p>
`owner`|**Optional\[[Owner](toloka.client.owner.Owner.md)\]**|<p>The pool owner.</p>
`id`|**Optional\[str\]**|<p>The ID of the pool. Read-only field.</p>
`status`|**Optional\[[Status](toloka.client.pool.Pool.Status.md)\]**|<p>The status of the pool. Read-only field.</p>
`last_close_reason`|**Optional\[[CloseReason](toloka.client.pool.Pool.CloseReason.md)\]**|<p>A reason why the pool was closed last time. Read-only field.</p>
`created`|**Optional\[datetime\]**|<p>The UTC date and time when the pool was created. Read-only field.</p>
`last_started`|**Optional\[datetime\]**|<p>The UTC date and time when the pool was started last time. Read-only field.</p>
`last_stopped`|**Optional\[datetime\]**|<p>The UTC date and time when the pool was stopped last time. Read-only field.</p>
`type`|**Optional\[[Type](toloka.client.pool.Pool.Type.md)\]**|<p>The type of the pool. Deprecated.</p>

**Examples:**

Creating a new pool.

```python
new_pool = toloka.client.Pool(
    project_id='1',
    private_name='Experimental pool',
    may_contain_adult_content=False,
    will_expire=datetime.datetime.now(datetime.timezone.utc) + datetime.timedelta(days=365),
    reward_per_assignment=0.01,
    assignment_max_duration_seconds=60*20,
    defaults=toloka.client.Pool.Defaults(default_overlap_for_new_task_suites=3),
    filter=toloka.client.filter.Languages.in_('EN'),
)
new_pool.set_mixer_config(real_tasks_count=10)
new_pool = toloka_client.create_pool(new_pool)
print(new_pool.id)
```
## Methods Summary

| Method | Description |
| :------| :-----------|
[is_archived](toloka.client.pool.Pool.is_archived.md)| None
[is_closed](toloka.client.pool.Pool.is_closed.md)| None
[is_locked](toloka.client.pool.Pool.is_locked.md)| None
[is_open](toloka.client.pool.Pool.is_open.md)| None
[set_assignments_issuing_config](toloka.client.pool.codegen_setter_for_assignments_issuing_config.md)| A shortcut setter for assignments_issuing_config
[set_captcha_frequency](toloka.client.pool.codegen_setter_for_quality_control_captcha_frequency.md)| A shortcut setter for quality_control.captcha_frequency
[set_checkpoints_config](toloka.client.pool.codegen_setter_for_quality_control_checkpoints_config.md)| A shortcut setter for quality_control.checkpoints_config
[set_defaults](toloka.client.pool.codegen_setter_for_defaults.md)| A shortcut setter for defaults
[set_dynamic_overlap_config](toloka.client.pool.codegen_setter_for_dynamic_overlap_config.md)| A shortcut setter for dynamic_overlap_config
[set_dynamic_pricing_config](toloka.client.pool.codegen_setter_for_dynamic_pricing_config.md)| A shortcut setter for dynamic_pricing_config
[set_filter](toloka.client.pool.codegen_setter_for_filter.md)| A shortcut setter for filter
[set_mixer_config](toloka.client.pool.codegen_setter_for_mixer_config.md)| A shortcut setter for mixer_config
[set_owner](toloka.client.pool.codegen_setter_for_owner.md)| A shortcut setter for owner
[set_quality_control](toloka.client.pool.codegen_setter_for_quality_control.md)| A shortcut setter for quality_control
[set_quality_control_configs](toloka.client.pool.codegen_setter_for_quality_control_configs.md)| A shortcut method for setting 
[set_speed_quality_balance](toloka.client.pool.codegen_setter_for_speed_quality_balance.md)| A shortcut setter for speed_quality_balance
[set_training_config](toloka.client.pool.codegen_setter_for_training_config.md)| A shortcut setter for training_config
[set_training_requirement](toloka.client.pool.codegen_setter_for_quality_control_training_requirement.md)| A shortcut setter for quality_control.training_requirement
