# Use quality control rules

_Use quality control rules to restrict access to the tasks for the Tolokers who try and breach them._

## Steps to follow

{% include [import](../_includes/recipes/import.md) %}

{% include [instantiate](../_includes/recipes/instantiate.md) %}

### 3. Create pool object {#step-three}

Create a pool and set the default overlap value for all the tasks which will be uploaded without additionally specifying it. Use the `default_overlap_for_new_task_suites` value of the [Defaults](../reference/toloka.client.pool.Pool.Defaults.md) class for that.

Refer to the [{#T}](./create-pool.md) recipe for more information on how to create a pool and what parameters you can use.

```python
new_pool = toloka.pool.[Pool](*Pool)(
    project_id='133047',
    private_name='Pool with quality control rules',
    will_expire=datetime(2030, 1, 1),
    reward_per_assignment=0.05,
    assignment_max_duration_seconds=60*5
)
```

Now, add some quality control rules to the pool.

{% note tip %}

Each of the quality control rules has three main components:

- `collector` which specifies what information to collect before the system applies some conditions and restrictions,
- `conditions` which sets conditions that the system considers before applying some actions,
- and `action` which define the actions that the system applies based on the `collector` and `conditions` data.

{% endnote %}

### 4. Add 'Fast responses' quality control rule {#step-four}

Set up the **Fast responses** quality control rule using the [add_action()](../reference/toloka.client.quality_control.QualityControl.add_action.md) method to create the [AssignmentSubmitTime](../reference/toloka.client.collectors.AssignmentSubmitTime.md) collector class object with the appropriate conditions and actions.

```python
new_pool.quality_control.[add_action](*add_action)(
    collector=toloka.collectors.[AssignmentSubmitTime](*AssignmentSubmitTime)(history_size=5, fast_submit_threshold_seconds=20),
    conditions=[toloka.conditions.[FastSubmittedCount](*FastSubmittedCount) > 1],
    action=toloka.actions.[RestrictionV2](*RestrictionV2)(
        scope='POOL',
        duration=10,
        duration_unit='DAYS',
        private_comment='Fast responses',
    )
)
```

{% cut "'Fast responses' quality control rule in the Toloka interface" %}

#### Parameters with corresponding interface elements

**Toloka-Kit parameter** | **Interface element**
------------------------- | ---------------------
`toloka.collectors.AssignmentSubmitTime(history_size=5)` | **Recent task suites to use 5**
`toloka.collectors.AssignmentSubmitTime(fast_submit_threshold_seconds=20)` | **Minimum time per task suite 20**
`toloka.conditions.FastSubmittedCount > 1` | **If number of fast responses > 1**
`toloka.actions.RestrictionV2()` | **then suspend**
`toloka.actions.RestrictionV2(scope='POOL')` | **in pool**
`toloka.actions.RestrictionV2(duration=10, duration_unit='DAYS')` | **10 days**
`toloka.actions.RestrictionV2(private_comment='Fast responses')` | **Fast responses**

The image below shows how the created **Fast responses** quality control rule looks in the pool interface.

!['Fast responses' quality control rule](../_images/recipes/quality-control-rule-fast-responses.png =700x)

{% endcut %}

Refer to the [{#T}](../../guide/concepts/quick-answers.md) section for more information on how to set up the **Fast responses** quality control rule and what parameters it should have for the correct settings.

### 5. Add 'Majority vote' quality control rule {#step-five}

Set up the **Majority votes** quality control rule using the [add_action()](../reference/toloka.client.quality_control.QualityControl.add_action.md) method to create the [MajorityVote](../reference/toloka.client.collectors.MajorityVote.md) collector class object with the appropriate conditions and actions.

```python
new_pool.quality_control.[add_action](*add_action)(
    collector=toloka.collectors.[MajorityVote](*MajorityVote)(answer_threshold=2),
    conditions=[
        toloka.conditions.[TotalAnswersCount](*TotalAnswersCount) > 9,
        toloka.conditions.[CorrectAnswersRate](*CorrectAnswersRate) < 60,
    ],
    action=toloka.actions.[RejectAllAssignments](*RejectAllAssignments)(public_comment='Too low quality')
)
```

{% cut "'Majority vote' quality control rule in the Toloka interface" %}

#### Parameters with corresponding interface elements

**Toloka-Kit parameter** | **Interface element**
------------------------- | ---------------------
`toloka.collectors.MajorityVote(answer_threshold=2)` | **Accept as majority 5**
`toloka.conditions.TotalAnswersCount > 9` | **If number responses > 9**
`toloka.conditions.CorrectAnswersRate < 60` | **and correct responses (%) < 60**
`toloka.actions.RejectAllAssignments()` | **reject all assignments from this Toloker in the pool**
`toloka.actions.RejectAllAssignments(public_comment='Too low quality')` | **Too low quality**

The image below shows how the created **Majority vote** quality control rule looks in the pool interface.

!['Majority vote' quality control rule](../_images/recipes/quality-control-rule-majority-vote.png =700x)

{% endcut %}

Refer to the [{#T}](../../guide/concepts/mvote.md) section for more information on how to set up the **Majority vote** quality control rule and what parameters it should have for the correct settings.

### 6. Add 'Skipped assignments' quality control rule {#step-six}

Set up the **Skipped assignments** quality control rule using the [add_action()](../reference/toloka.client.quality_control.QualityControl.add_action.md) method to create the [SkippedInRowAssignments](../reference/toloka.client.collectors.SkippedInRowAssignments.md) collector class object with the appropriate conditions and actions.

```python
new_pool.quality_control.[add_action](*add_action)(
    collector=toloka.collectors.[SkippedInRowAssignments](*SkippedInRowAssignments)(),
    conditions=[toloka.conditions.[SkippedInRowCount](*SkippedInRowCount) > 3],
    action=toloka.actions.[RestrictionV2](*RestrictionV2)(
        scope='POOL',
        duration=15,
        duration_unit='DAYS',
        private_comment='Skips too many task suites in a row',
    )
)
```

{% cut "'Skipped assignments' quality control rule in the Toloka interface" %}

#### Parameters with corresponding interface elements

**Toloka-Kit parameter** | **Interface element**
------------------------- | ---------------------
`toloka.conditions.SkippedInRowCount > 3` | **If task suites skipped in a row > 3**
`toloka.actions.RestrictionV2()` | **then suspend**
`toloka.actions.RestrictionV2(scope='POOL')` | **in pool**
`toloka.actions.RestrictionV2(duration=15,duration_unit='DAYS')` | **15 days**
`toloka.actions.RestrictionV2(private_comment='Skips too many task suites in a row')` | **Skips too many task suites in a row**

The image below shows how the created **Skipped assignments** quality control rule looks in the pool interface.

!['Skipped assignments' quality control rule](../_images/recipes/quality-control-rule-skipped-assignments.png =700x)

{% endcut %}

Refer to the [{#T}](../../guide/concepts/skipped-assignments.md) section for more information on how to set up the **Skipped assignments** quality control rule and what parameters it should have for the correct settings.

### 7. Add 'Control tasks' quality control rule {#step-seven}

Set up the **Control tasks** quality control rule using the [add_action()](../reference/toloka.client.quality_control.QualityControl.add_action.md) method to create the [GoldenSet](../reference/toloka.client.collectors.GoldenSet.md) collector class object with the appropriate conditions and actions.

```python
new_pool.quality_control.[add_action](*add_action)(
    collector=toloka.collectors.[GoldenSet](*GoldenSet)(history_size=5),
    conditions=[
        toloka.conditions.[GoldenSetCorrectAnswersRate](*GoldenSetCorrectAnswersRate) > 80,
        toloka.conditions.[GoldenSetAnswersCount](*GoldenSetAnswersCount) >= 5,
    ],
    action=toloka.actions.[ApproveAllAssignments](*ApproveAllAssignments)()
)
```

{% cut "'Control tasks' quality control rule in the Toloka interface" %}

#### Parameters with corresponding interface elements

**Toloka-Kit parameter** | **Interface element**
------------------------- | ---------------------
`toloka.collectors.GoldenSet(history_size=5)` | **Recent control and training task responses to use 5**
`conditions.GoldenSetCorrectAnswersRate > 80` | **If correct control responses (%) > 80**
`toloka.conditions.GoldenSetAnswersCount >=5` | **and number of control responses ≥ 5**
`toloka.actions.ApproveAllAssignments()` | **then accept all assignments from this Toloker in the pool**

The image below shows how the created **Control tasks** quality control rule looks in the pool interface.

!['Control tasks' quality control rule](../_images/recipes/quality-control-rule-control-tasks.png =700x)

{% endcut %}

Refer to the [{#T}](../../guide/concepts/goldenset.md) section for more information on how to set up the **Control tasks** quality control rule and what parameters it should have for the correct settings.

{% note tip %}

See the [Collectors](../reference/toloka.client.collectors.AcceptanceRate.md) section of the Toloka-Kit reference for the complete list of the available collectors used to create quality control rules and their possible values.

{% endnote %}

### 8. Create pool on platform {#step-eight}

This actually creates a pool in Toloka.

```python
new_pool = toloka_client.[create_pool](*create_pool)(new_pool)
```

### 9. Print created pool ID {#step-nine}

The `create_pool()` request will return the [Pool](../reference/toloka.client.pool.Pool.md) class object. You can use its attributes to print the information you need.

```python
print(new_pool.id)
```

You should get an output with the created pool ID which looks like this.

```bash
1444049
```

## Complete code: Use quality control rules {#complete-code}

```python
import toloka.client as toloka

toloka_client = toloka.TolokaClient('PlaceYourRealOAuthToken_Here', 'PRODUCTION')

new_pool = toloka.pool.Pool(
    project_id='133047',
    private_name='Pool with quality control rules',
    will_expire=datetime(2030, 1, 1),
    reward_per_assignment=0.05,
    assignment_max_duration_seconds=60*5
)
new_pool.quality_control.add_action(
    collector=toloka.collectors.AssignmentSubmitTime(history_size=5, fast_submit_threshold_seconds=20),
    conditions=[toloka.conditions.FastSubmittedCount > 1],
    action=toloka.actions.RestrictionV2(
        scope='POOL',
        duration=10,
        duration_unit='DAYS',
        private_comment='Fast responses',
    )
)
new_pool.quality_control.add_action(
    collector=toloka.collectors.MajorityVote(answer_threshold=2),
    conditions=[
        toloka.conditions.TotalAnswersCount > 9,
        toloka.conditions.CorrectAnswersRate < 60,
    ],
    action=toloka.actions.RejectAllAssignments(public_comment='Too low quality')
)
new_pool.quality_control.add_action(
    collector=toloka.collectors.SkippedInRowAssignments(),
    conditions=[toloka.conditions.SkippedInRowCount > 3],
    action=toloka.actions.RestrictionV2(
        scope='POOL',
        duration=15,
        duration_unit='DAYS',
        private_comment='Skips too many task suites in a row',
    )
)
new_pool.quality_control.add_action(
    collector=toloka.collectors.GoldenSet(history_size=5),
    conditions=[
        toloka.conditions.GoldenSetCorrectAnswersRate > 80,
        toloka.conditions.GoldenSetAnswersCount >= 5,
    ],
    action=toloka.actions.ApproveAllAssignments()
)
new_pool = toloka_client.create_pool(new_pool)
print(new_pool.id)
```

{% note tip "List of classes and methods used in this recipe" %}

- _[TolokaClient](../reference/toloka.client.TolokaClient.md) class_
- _[Pool](../reference/toloka.client.pool.Pool.md) class_
- _[add_action()](../reference/toloka.client.quality_control.QualityControl.add_action.md) method_
- _[AssignmentSubmitTime](../reference/toloka.client.collectors.AssignmentSubmitTime.md) collector class_
- _[FastSubmittedCount](../reference/toloka.client.conditions.FastSubmittedCount.md) condition class_
- _[RestrictionV2](../reference/toloka.client.actions.RestrictionV2.md) action class_
- _[MajorityVote](../reference/toloka.client.collectors.MajorityVote.md) collector class_
- _[TotalAnswersCount](../reference/toloka.client.conditions.TotalAnswersCount.md) condition class_
- _[CorrectAnswersRate](../reference/toloka.client.conditions.CorrectAnswersRate.md) condition class_
- _[RejectAllAssignments](../reference/toloka.client.actions.RejectAllAssignments.md) action class_
- _[SkippedInRowAssignments](../reference/toloka.client.collectors.SkippedInRowAssignments.md) collector class_
- _[SkippedInRowCount](../reference/toloka.client.conditions.SkippedInRowCount.md) condition class_
- _[GoldenSet](../reference/toloka.client.collectors.GoldenSet.md) collector class_
- _[GoldenSetCorrectAnswersRate](../reference/toloka.client.conditions.GoldenSetCorrectAnswersRate.md) condition class_
- _[GoldenSetAnswersCount](../reference/toloka.client.conditions.GoldenSetAnswersCount.md) condition class_
- _[ApproveAllAssignments](../reference/toloka.client.actions.ApproveAllAssignments.md) action class_

{% endnote %}

## See also {#see-also}

- [{#T}](../../guide/concepts/overview.md)
- [{#T}](./learn-basics.md)
- [{#T}](./use-cases.md)
- [{#T}](../../guide/concepts/control.md)
- [{#T}](../../guide/concepts/quick-answers.md)
- [{#T}](../../guide/concepts/mvote.md)
- [{#T}](../../guide/concepts/skipped-assignments.md)
- [{#T}](../../guide/concepts/goldenset.md)
- [Toloka API: Create pool](https://toloka.ai/docs/api/api-reference/#post-/pools)

[*TolokaClient]: [TolokaClient](../reference/toloka.client.TolokaClient.md) class
[*Pool]: [Pool](../reference/toloka.client.pool.Pool.md) class
[*add_action]: [add_action()](../reference/toloka.client.quality_control.QualityControl.add_action.md) method
[*AssignmentSubmitTime]: [AssignmentSubmitTime](../reference/toloka.client.collectors.AssignmentSubmitTime.md) collector class
[*FastSubmittedCount]: [FastSubmittedCount](../reference/toloka.client.conditions.FastSubmittedCount.md) condition class
[*RestrictionV2]: [RestrictionV2](../reference/toloka.client.actions.RestrictionV2.md) action class
[*MajorityVote]: [MajorityVote](../reference/toloka.client.collectors.MajorityVote.md) collector class
[*TotalAnswersCount]: [TotalAnswersCount](../reference/toloka.client.conditions.TotalAnswersCount.md) condition class
[*CorrectAnswersRate]: [CorrectAnswersRate](../reference/toloka.client.conditions.CorrectAnswersRate.md) condition class
[*RejectAllAssignments]: [RejectAllAssignments](../reference/toloka.client.actions.RejectAllAssignments.md) action class
[*SkippedInRowAssignments]: [SkippedInRowAssignments](../reference/toloka.client.collectors.SkippedInRowAssignments.md) collector class
[*SkippedInRowCount]: [SkippedInRowCount](../reference/toloka.client.conditions.SkippedInRowCount.md) condition class
[*GoldenSet]: [GoldenSet](../reference/toloka.client.collectors.GoldenSet.md) collector class
[*GoldenSetCorrectAnswersRate]: [GoldenSetCorrectAnswersRate](../reference/toloka.client.conditions.GoldenSetCorrectAnswersRate.md) condition class
[*GoldenSetAnswersCount]: [GoldenSetAnswersCount](../reference/toloka.client.conditions.GoldenSetAnswersCount.md) condition class
[*ApproveAllAssignments]: [ApproveAllAssignments](../reference/toloka.client.actions.ApproveAllAssignments.md) action class

{% include [image-styles](../../../_includes/image-styles-internal.md) %}