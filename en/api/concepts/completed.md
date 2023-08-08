# Number of tasks completed

You can limit the number of tasks in the pool per Toloker, in order to:

- Get responses from as many Tolokers as possible (for this purpose, set a low threshold, such as one task suite).

- Protect yourself from robots (for this purpose, the threshold should be higher, such as 10% of the pool's tasks).

Set key values in the `quality_control.configs` array in the [pool settings](https://toloka.ai/docs/api/api-reference/#tag--pool).

## Request body {#body}

If a Toloker completes **12** task suites, you can ban them from your project for a given number of days, hours, minutes (at a time or in total), or permanently.

#### Ban for 10 days

```json
{
  "configs": [
    {
      "collector_config": {
        "type": "ANSWER_COUNT"
      },
      "rules": [
        {
          "conditions": [
            {
              "key": "assignments_accepted_count",
              "operator": "GTE",
              "value": 12
            }
          ],
          "action": {
            "type": "RESTRICTION_V2",
            "parameters": {
              "scope": "POOL",
              "duration_unit": "DAYS",
              "duration": 10,
              "private_comment": "Completed 12 pages of tasks in the pool"
            }
          }
        }
      ]
    }
  ]
}
```

To set a different ban period, change the [duration_unit](*duration-unit) and [duration](*duration) parameters for the `action` key:

{% list tabs %}

- for 12 hours

    ```json
    {
      ...
        "action": {
          "type": "RESTRICTION_V2",
          "parameters": {
            "scope": "POOL",
            "duration_unit": "HOURS",
            "duration": 12,
            "private_comment": "Completed 12 pages of tasks in the pool"
          }
        }
      ...
    }
    ```

- for 30 minutes

    ```json
    {
      ...
        "action": {
          "type": "RESTRICTION_V2",
          "parameters": {
            "scope": "POOL",
            "duration_unit": "MINUTES",
            "duration": 30,
            "private_comment": "Completed 12 pages of tasks in the pool"
          }
        }
      ...
    }
    ```

- permanently

    ```json
    {
      ...
        "action": {
          "type": "RESTRICTION_V2",
          "parameters": {
            "scope": "POOL",
            "duration_unit": "PERMANENT",
            "private_comment": "Completed 12 pages of tasks in the pool"
          }
        }
      ...
    }
    ```

{% endlist %}

#|
|| Parameter | Overview ||
|| `configs[]` | _array of objects_ \| **required**

Array of quality control settings. ||
|| `configs[].collector_config` | _object_ \| **required**

Parameters for collecting statistics (for example, the number of tasks skipped in the pool). ||
|| `configs[].collector_config.type` | _string_ \| **required**

{% include [quality-control-criteria](../_includes/quality-control-list.md) %}
||
|| `configs[].collector_config.parameters` | _object_ \| **required if**

Required if `configs[].collector_config.type` is equal to one of the values:

- `GOLDEN_SET`
- `MAJORITY_VOTE`
- `ASSIGNMENT_SUBMIT_TIME`

Parameters for collecting data (depends on the quality control rule specified in the `type` key). ||
|| `configs[].rules` | _object_ \| **required**

{% include [configs-rules](../_includes/configs-rules.md) %} ||
|| `configs[].rules.conditions` | _object_ \| **required**

Conditions (for example, 10 task suites skipped in a row). Multiple conditions are combined with the `AND` operator. ||
|| `configs[].rules.conditions.key` | _string_ \| **required**

Values that are checked in the condition:

- `assignments_accepted_count` — The number of task suites completed by the Toloker. ||
|| `configs[].rules.conditions.operator` | _string_ \| **required**

Comparison operator (the `key` data is compared with the threshold value from `value`):

- `EQ` — Equal to.
- `NE` — Not equal to.
- `GT` — Greater than.
- `LT` — Less than.
- `GTE` — Greater than or equal to.
- `LTE` — Less than or equal to. ||
|| `configs[].rules.conditions.value` | _integer_ \| **required**

The threshold value of the variable specified in `key`. ||
|| `configs[].rules.action` | _object_ \| **required**

The action to perform if conditions are met (for example, block access to the project). ||
|| `configs[].rules.action.type` | _string_ \| **required**

Type of action:

- `RESTRICTION` — Ban access to projects or pools.
- `SET_SKILL_FROM_OUTPUT_FIELD` — Set the "percentage of correct responses" as the skill value (used in [control tasks](goldenset.md) and [majority vote](mv.md) rules).

    You can use the skill value for filtering Tolokers.

- `CHANGE_OVERLAP` — Change the overlap. For example, to re-assign a task suite to other Tolokers or cancel the recompletion of already accepted assignments.
- `REJECT_ALL_ASSIGNMENTS` — Reject all Toloker responses. For example, after a certain number of Toloker responses, it became clear that the Toloker completed tasks poorly.
- `APPROVE_ALL_ASSIGNMENTS` — Accept all Toloker responses. For example, if the Toloker completes most tasks well and you are satisfied with this result.
- `SET_SKILL` — Assign the specified constant value to the skill. ||
|| `configs[].rules.action.parameters` | _object_ \| **required**

Action parameters. ||
|| `configs[].rules.action.parameters.scope` | _string_ \| **required**

Scope:

- `POOL` — pool. Affects the Toloker's rating.
- `PROJECT` — The project. Affects the Toloker's rating.
- `ALL_PROJECTS` — All the requester's projects. ||
|| `configs[].rules.action.parameters.skill_id` | _string_ \| **required if**

Required if `type=SET_SKILL_FROM_OUTPUT_FIELD`.

ID of the skill to update as tasks are completed. ||
|| `configs[].rules.action.parameters.from_field` | _string_ \| **required if**

Required if `type=SET_SKILL_FROM_OUTPUT_FIELD`.

The value to assign to the skill:

- `correct_answers_rate` — The percentage of correct responses.
- `wrong_answers_rate` — The percentage of incorrect responses. ||
|| `configs[].rules.action.parameters.skill_value` | _integer_ \| **required if**

Required if `type=SET_SKILL_FROM_OUTPUT_FIELD`.

A fixed value to assign to the skill (a number from 0 to 100). ||
|| `configs[].rules.action.parameters.delta` | _integer_ \| **required if**

Required if `type=CHANGE_OVERLAP`.

The value determines the amount to change the overlap by. ||
|| `configs[].rules.action.parameters.public_comment` | _string_ \| **required if**

Required if `type=REJECT_ALL_ASSIGNMENTS`.

Comments (the reason for rejecting responses). Available to the requester and the Toloker. ||
|| `configs[].rules.action.parameters.duration_unit` | _string_

{% include [duration-unit](../_includes/duration-unit.md) %} ||
|| `configs[].rules.action.parameters.duration` | _integer_

{% include [duration](../_includes/duration.md) %} ||
|| `configs[].rules.action.parameters.private_comment` | _string_

Comments (the reason for blocking access). Visible only to the requester. ||
|| `configs[].rules.action.parameters.open_pool` | _boolean_

Determines whether to re-open a closed pool:

- `true` — Open the pool after making changes if it is closed.
- `false` — Don't open the pool after making changes, if it is closed.||
|#

## See also {#see-also}

- [{#T}](../../guide/concepts/submitted-answers.md)
- [Toloka-Kit recipe: Use quality control rules](../../toloka-kit/recipes/use-quality-control-rules.md)

{% include [contact-support](../../guide/_includes/contact-support.md) %}

[*duration-unit]: {% include [duration-unit](../_includes/duration-unit.md) %}
[*duration]: {% include [duration](../_includes/duration.md) %}