# Processing rejected and accepted assignments

## Overview {#about}

You can use this rule to:

- Resend rejected task suites for recompletion to other Tolokers.

    If you rejected a task suite, you may want it to be completed by a different Toloker instead of the one whose response you rejected. To do this, you can increase the [overlap](../../glossary.md#overlap) for this task suite only. This is especially helpful if you have the overlap value set to 1.

- Save money on re-completing task suites that you have already accepted.

    If you reviewed and accepted a task suite, it may not make sense for other Tolokers to complete it. To avoid this, you can reduce the overlap only for accepted task suites.

## Request body {#body}

Re-assign task suites that didn't pass manual review.

```json
{
  "configs": [{
    "collector_config": {
      "type": "ASSIGNMENTS_ASSESSMENT"
    },
    "rules": [{
      "conditions": [{
          "key": "rejected_assignments_count",
          "operator": "GTE",
          "value": "1"
        },
        {
          "key": "assessment_event",
          "operator": "EQ",
          "value": "REJECT"
        }
      ],
      "action": {
        "type": "CHANGE_OVERLAP",
        "parameters": {
          "delta": 1,
          "open_pool": true,
        }
      }
    }]
  }]
}
```

#|
|| Parameter | Overview ||
|| **configs[]** | **array of objects \| required**

Array of quality control settings. ||
|| **configs.collector_config** | **object \| required**

Parameters for collecting statistics (for example, the number of tasks skipped in the pool). ||
|| **configs.collector_config.type** | **string \| required**

Criteria for the quality control rule:

- `GOLDEN_SET` — The number of correct and incorrect responses in the control tasks.
- `MAJORITY_VOTE` — The percentage of responses that matched the majority vote.
- `CAPTCHA` — The number of captchas entered successfully and unsuccessfully.
- `INCOME` — Payment for tasks completed by the Toloker over the past 24 hours.
- `SKIPPED_IN_ROW_ASSIGNMENTS` — The number of task suites skipped in a row.
- `ANSWER_COUNT` — The number of task suites completed by the Toloker in the pool.
- `ASSIGNMENT_SUBMIT_TIME` — The number of "fast" responses (the minimum response speed is set in the parameters).
- `ACCEPTANCE_RATE` — The percentage of Toloker responses that were rejected during manual review.
- `ASSIGNMENTS_ASSESSMENT` — The number of assignments accepted or rejected with manual review enabled.
- `USERS_ASSESSMENT` — The Toloker's skill value and their bans. ||
|| **configs.collector_config. parameters.history_size** | **integer \| required**

The maximum number of the Toloker's recent responses in the project to use for calculating the percentage of correct responses.

If this field is omitted, the calculation is based on all the Toloker's responses in the pool. ||
|| **configs.rules.conditions** | **object \| required**

Conditions (for example, 10 task suites skipped in a row). Multiple conditions are combined with the "OR" operator. ||
|| **configs.rules.conditions.key** | **string \| required**

Values that are checked in the condition:

- `pending_assignments_count` — The number of task suites that are completed and awaiting review.
- `accepted_assignments_count` — The number of task suites accepted after the review.
- `rejected_assignments_count` — The number of task suites rejected after the review. ||
|| **configs.rules.conditions. operator** | **string \| required**

Comparison operator (the `key` data is compared with the threshold value from `value`):

- `EQ` ("Equal") — Equal to.
- `NE` ("Not equal to") — Not equal to.
- `GT` ("Greater than") — Greater than.
- `LT` ("Less than") — Less than.
- `GTE` ("Greater than equal to") — Greater than or equal to.
- `LTE` ("Less than equal to") — Less than or equal to. ||
|| **configs.rules.conditions. value** | **string \| required**

The number of task suites with a specific status. ||
|| **configs.rules.action** | **object \| required**

The action to perform if conditions are met (for example, block access to the project). ||
|| **configs.rules.action.type** | **string \| required**

`CHANGE_OVERLAP` — Change the overlap. For example, to re-assign a task suite to other Tolokers or cancel the recompletion of accepted task suites. ||
|| **configs.rules.action. parameters** | **object \| required**

Action parameters. ||
|| **configs.rules.action. parameters.scope** | **string \| required**

Scope:

- `POOL` — pool. Affects the Toloker's rating.
- `PROJECT` — The project. Affects the Toloker's rating.
- `ALL_PROJECTS` — All the requester's projects. ||
|| **configs.collector_config. parameters** | **object \| required if**

Required if `configs.collector_config.type=``GOLDEN_SET`, `MAJORITY_VOTE`, `CAPTCHA`, `ASSIGNMENT_SUBMIT_TIME`.

Parameters for collecting data (depends on the quality control rule specified in the `type` key). ||
|| **configs.rules.action. parameters.skill_id** | **string \| required if**

Required if `type=SET_SKILL_FROM_OUTPUT_FIELD`.

ID of the skill to update as tasks are completed. ||
|| **configs.rules.action. parameters.from_field** | **string \| required if**

Required if `type=SET_SKILL_FROM_OUTPUT_FIELD`.

The value to assign to the skill:

- `correct_answers_rate` — The percentage of correct responses.
- `wrong_answers_rate` — The percentage of incorrect responses. ||
|| **configs.rules.action. parameters.skill_value** | **integer \| required if**

Required if `type=SET_SKILL_FROM_OUTPUT_FIELD`.

A fixed value to assign to the skill (a number from 0 to 100). ||
|| **configs.rules.action. parameters.delta** | **integer \| required if**

Required if `type=CHANGE_OVERLAP`.
The value determines the amount to change the overlap by. ||
|| **configs.rules.action. parameters.public_comment** | **string \| required if**

Required if `type=REJECT_ALL_ASSIGNMENTS`.

Comments (the reason for rejecting responses). Available to the requester and the Toloker. ||
|| **configs.rules.conditions.key** | **string**

Changing the task suite acceptance status. ||
|| **configs.rules.conditions. value** | **string**

The value can be `ACCEPT`, `ACCEPT_AFTER_REJECT`, or `REJECT` (task suites get accepted, accepted after rejection, or rejected, respectively). ||
|| **configs.rules.action. parameters.duration_unit** | **string**

Ban duration unit:

- `MINUTES` — Minutes
- `HOURS` — Hours
- `DAYS` — Days
- `PERMANENT` — Permanent ban ||
|| **configs.rules.action. parameters.duration** | **integer**

Ban duration. ||
|| **configs.rules. action.parameters. private_comment** | **string**

Comments (the reason for blocking access). Visible only to the requester. ||
|| **configs.rules.action. parameters.open_pool** | **boolean**

Determines whether to re-open a closed pool:

- `true` — Open the pool after making changes if it is closed.
- `false` — Don't open the pool after making changes, if it is closed.||
|#