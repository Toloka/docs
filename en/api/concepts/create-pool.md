# Create a pool

{% include [announce](../_includes/announce.md) %}

Creates a pool.

The pool is automatically assigned an ID.

{% note alert "Restriction" %}

You can send a maximum of 20 requests of this kind per minute and 100 requests per day.

{% endnote %}

{% note info %}

Learn about creating a training pool in [Create a training pool](create-training.md).

{% endnote %}

## Request {#request}

{% list tabs %}

- Production version

    ```bash
    POST https://toloka.dev/api/v1/pools
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON
    ```

- Sandbox

    ```bash
    POST https://sandbox.toloka.dev/api/v1/pools
    Authorization: OAuth <OAuth token>
    Content-Type: application/JSON
    ```

{% endlist %}

## Headers {#headers}

Title | Overview
----- | -----
**Authorization** | A token for account authorization. Add OAuth as a prefix.
**Content-Type** | Specifies the data format in the request body.

## Request body {#body}

```json
{
  "project_id": "1",
  "private_name": "My first pool",
  "private_comment": "This is my first pool",
  "public_description": "Pool's description ",
  "may_contain_adult_content": false,
  "will_expire": "2020-09-01T13:00",
  "reward_per_assignment": 0.02,
  "dynamic_pricing_config": {
    "type": "SKILL",
    "skill_id": "1289",
    "intervals": [
      {
        "from": 0,
        "to": 60,
        "reward_per_assignment": 0.03
      },
      {
        "from": 61,
        "to": 100,
        "reward_per_assignment": 0.04
      }
    ]
  },
  "assignment_max_duration_seconds": 300,
  "auto_accept_solutions": true,
  "auto_accept_period_day": 7,
  "auto_close_after_complete_delay_seconds": 60,
  "assignments_issuing_config": {
    "issue_task_suites_in_creation_order": false
  },
  "filter": {<settings for filtering Tolokers>},
  "quality_control": {
    "training_requirement": {
      "training_pool_id": "21",
      "training_passing_skill_value": 70
    },
    "captcha_frequency": "LOW",
    "configs": {<quality control rule settings>},
    "checkpoints_config": {
      "real_settings": {
        "target_overlap": 5,
        "task_distribution_function": {
          "scope": "PROJECT",
          "distribution": "UNIFORM",
          "window_days": 7,
          "intervals": [
            {
              "from": 1,
              "to": 100,
              "frequency": 5
            },
            {
              "from": 101,
              "to": 1000,
              "frequency": 25
            }
          ]
        }
      },
      "golden_settings": {
        "target_overlap": 5,
        "task_distribution_function": {
          "scope": "PROJECT",
          "distribution": "UNIFORM",
          "window_days": 7,
          "intervals": [
            {
              "from": 1,
              "to": 100,
              "frequency": 5
            },
            {
              "from": 101,
              "to": 1000,
              "frequency": 25
            }
          ]
        }
      },
      "training_settings": {
        "target_overlap": 5,
        "task_distribution_function": {
          "scope": "PROJECT",
          "distribution": "UNIFORM",
          "window_days": 7,
          "intervals": [
            {
              "from": 1,
              "to": 100,
              "frequency": 5
            },
            {
              "from": 101,
              "to": 1000,
              "frequency": 25
            }
          ]
        }
      }
    }
  },
  "speed_quality_balance": {
    "type": "TOP_PERCENTAGE_BY_QUALITY",
    "percent": 80
  },
  "dynamic_overlap_config": {
    "type": "BASIC",
    "max_overlap": 5,
    "min_confidence": 0.9,
    "answer_weight_skill_id": "1289",
    "fields": [
      {
        "name": "result"
      }
    ]
  },
  "defaults" : {
    "default_overlap_for_new_task_suites" : 3,
    "default_overlap_for_new_tasks": 3
  },
  "mixer_config": {
    "real_tasks_count": 6,
    "golden_tasks_count": 1,
    "training_tasks_count": 1,
    "min_real_tasks_count": 2,
    "min_golden_tasks_count": 0,
    "min_training_tasks_count": 0,
    "force_last_assignment": true,
    "force_last_assignment_delay_seconds": 10,
    "mix_tasks_in_creation_order": true,
    "shuffle_tasks_in_task_suite": false,
    "golden_task_distribution_function": {
      "scope": "PROJECT",
      "distribution": "UNIFORM",
      "window_days": 7 ,
      "intervals": [
        {
          "from": 1,
          "to": 25,
          "frequency": 5
        },
        {
          "from": 26,
          "to": 1000,
          "frequency": 25
        }
      ]
    },
    "training_task_distribution_function": {
      "scope": "PROJECT",
      "distribution": "UNIFORM",
      "window_days": 7,
      "intervals": [
        {
          "from": 1,
          "to": 25,
          "frequency": 5
        },
        {
          "from": 26,
          "to": 1000,
          "frequency": 25
        }
      ]
    }
  },
  "priority": 10
}
```

#|
|| Parameter {#pool-param} | Overview ||
|| **project_id** | **string \| mandatory**

ID of the project that the pool was created for. ||
|| **private_name** | **string \| mandatory**

Name of the pool (only visible to the requester). ||
|| **may_contain_adult_content** | **boolean \| required**

Whether the tasks contain adult content. ||
|| **will_expire** | **string \| mandatory**

The date and time in UTC when the pool needs to be closed (even if not all task suites have been completed). It uses ISO 8601 format: `YYYY-MM-DDThh:mm:ss[.sss]`. ||
|| **reward_per_assignment** | **float \| mandatory**

Payment per task suite in U.S. dollars. For cents, use the dot (".") as the separator. The minimum payment is $0.005.

Only training and control tasks can be uploaded to zero-price pools. ||
|| **defaults** | **object \| mandatory**

Settings that are applied by default when uploading new task suites to a pool. ||
|| **defaults.default_overlap_ for_new_task_suites** {#default_overlap_for_new_task_suites} | **integer \| mandatory**

The overlap for task suites that are uploaded to the pool (used if the `allow_defaults=true` parameter is set at upload). ||
|| **assignment_max_duration_ seconds** | **integer \| mandatory**

The time allowed for completing a task suite, in seconds. Tasks not completed within this time are reassigned to other Tolokers.

We recommend giving at least 60 seconds per task suite (including the time for loading the page and submitting responses). ||
|| **dynamic_pricing_config.type** | **string \| required if**

Required if dynamic pricing is used.

Parameter type for calculating dynamic pricing. The `SKILL` value. ||
|| **dynamic_pricing_config. skill_id** | **string \| required if**

Required if dynamic pricing is used.

ID of the skill that the task price is based on. ||
|| **dynamic_pricing_config. intervals[]** | **array of objects \| required if**

Required if dynamic pricing is used.

Skill level intervals. Must not overlap.

A Toloker with a skill level that is not included in any interval will receive the basic price for a task suite. ||
|| **dynamic_pricing_config. intervals[].from** | **integer \| required if**

Required if dynamic pricing is used.

Lower bound of the interval. May take a value from 0 to 100. By default `0`. ||
|| **dynamic_pricing_config. intervals[].to** | **integer \| required if**

Required if dynamic pricing is used.

Upper bound of the interval. May take a value from 0 to 100. By default `100`. ||
|| **dynamic_pricing_config. intervals[].reward_per_ assignment** | **float \| required if**

Required if dynamic pricing is used. The price per task suite for a Toloker with the specified skill level. ||
|| **quality_control. checkpoints_config. real_settings. target_overlap** | **integer \| required if**

Required if selective review is used. Overlap in tasks with selective review. ||
|| **quality_control. checkpoints_config. real_settings. task_distribution_function** | **object \| required if**

Required if selective review is used. Distribution of tasks with selective review. For more information about how verification tasks are assigned, see the [Requester's guide](../../guide/concepts/pool-main.md). ||
|| **quality_control. checkpoints_config. real_settings. task_distribution_function. scope** | **string \| required if**

Required if selective review is used.

How to count tasks completed by the Toloker:

- `POOL` — Count completed pool tasks.
- `PROJECT` — Count completed project tasks. ||
|| **quality_control. checkpoints_config. real_settings. task_distribution_function. distribution** | **string \| required if**

Required if selective review is used.

Distribution of tasks with selective review within an interval. This parameter has only one possible value — `UNIFORM`. ||
|| **quality_control. checkpoints_config. real_settings. task_distribution_function. window_days** | **integer \| required if**

Required if selective review is used.

Period in which completed tasks are counted (number of days). ||
|| **quality_control. checkpoints_config. real_settings. task_distribution_function. intervals[]** | **array of objects \| required if**

Required if selective review is used.

Interval limits and frequency of tasks with selective review. ||
|| **quality_control. checkpoints_config. real_settings. task_distribution_function. intervals[].from** | **integer \| required if**

Required if selective review is used.

Start of the interval (number of tasks completed by the Toloker in the project or in the pool). ||
|| **quality_control. checkpoints_config. real_settings. task_distribution_function. intervals[].to** | **integer \| required if**

Required if selective review is used.

End of the interval (number of tasks completed by the Toloker in the project or in the pool). ||
|| **quality_control. checkpoints_config. real_settings. task_distribution_function. intervals[].frequency** | **integer \| required if**

Required if selective review is used.

Frequency of tasks with selective review within an interval. The first task in an interval is a majority vote task. For example, if you set `frequency: 3`, then tasks number 1, 4, 7, and so on, will be majority vote tasks. ||
|| **quality_control. checkpoints_config. golden_settings. target_overlap** | **integer \| required if**

Required if selective review is used.

Overlap in control tasks with selective review. ||
|| **quality_control. checkpoints_config. golden_settings. task_distribution_function** | **object \| required if**

Required if selective review is used.

Distribution of control tasks with selective review. ||
|| **quality_control. checkpoints_config. golden_settings. task_distribution_function. scope** | **string \| required if**

Required if selective review is used.

How to count tasks completed by the Toloker:

- `POOL` — Count completed pool tasks.
- `PROJECT` — Count completed project tasks. ||
|| **quality_control. checkpoints_config. golden_settings. task_distribution_function** | **string \| required if**

Required if selective review is used. Distribution of control tasks with selective review within an interval. This parameter has only one possible value — `UNIFORM`. ||
|| **quality_control. checkpoints_config. golden_settings. task_distribution_function. window_days** | **integer \| required if**

Required if selective review is used.

Period in which completed tasks are counted (number of days). ||
|| **quality_control. checkpoints_config. golden_settings. task_distribution_function. intervals[]** | **array of objects \| required if**

Required if selective review is used.

Interval limits and frequency of control tasks with selective review. ||
|| **quality_control. checkpoints_config. golden_settings. task_distribution_function. intervals[].from** | **integer \| required if**

Required if selective review is used. Start of the interval (number of tasks completed by the Toloker in the project or in the pool). ||
|| **quality_control. checkpoints_config. golden_settings. task_distribution_function. intervals[].to** | **integer \| required if**

Required if selective review is used.

End of the interval (number of tasks completed by the Toloker in the project or in the pool). ||
|| **quality_control. checkpoints_config. golden_settings. task_distribution_function. intervals[].frequency** | **integer \| required if**

Required if selective review is used.

Frequency of control tasks with selective review within an interval. The first task in an interval is a majority vote task. For example, if you set `frequency: 3`, then tasks number 1, 4, 7, and so on, will be majority vote tasks. ||
|| **quality_control. checkpoints_config. training_settings. target_overlap** | **integer \| required if**

Required if selective review is used. Overlap in training tasks with selective review. ||
|| **quality_control. checkpoints_config. training_settings. task_distribution_function** | **object \| required if**

Required if selective review is used. Distribution of training tasks with selective review. ||
|| **quality_control. checkpoints_config. training_settings. task_distribution_function. scope** | **string \| required if**

Required if selective review is used.

How to count tasks completed by the Toloker:

- `POOL` — Count completed pool tasks.
- `PROJECT` — Count completed project tasks. ||
|| **quality_control. checkpoints_config. training_settings. task_distribution_function. distribution** | **string \| required if**

Required if selective review is used.

Distribution of training tasks with selective review within an interval. This parameter has only one possible value — `UNIFORM`. ||
|| **quality_control. checkpoints_config. training_settings. task_distribution_function. window_days** | **integer \| required if**

Required if selective review is used.

Period in which completed tasks are counted (number of days). ||
|| **quality_control. checkpoints_config. training_settings. task_distribution_function. intervals[]** | **array of objects \| required if**

Required if selective review is used. Interval limits and frequency of training tasks with selective review. ||
|| **quality_control. checkpoints_config. training_settings. task_distribution_function. intervals[].from** | **integer \| required if**

Required if selective review is used.

Start of the interval (number of tasks completed by the Toloker in the project or in the pool). ||
|| **quality_control. checkpoints_config. training_settings. task_distribution_function. intervals[].to** | **integer \| required if**

Required if selective review is used.

End of the interval (number of tasks completed by the Toloker in the project or in the pool). ||
|| **quality_control. checkpoints_config. training_settings. task_distribution_function. intervals[].frequency** | **integer \| required if**

Required if selective review is used. Frequency of training tasks with selective review within an interval. The first task in an interval is a majority vote task. For example, if you set `frequency: 3`, then tasks number 1, 4, 7, and so on, will be majority vote tasks. ||
|| **dynamic_overlap_config.type** | **string \| required if**

Required if dynamic overlap is used.

The algorithm for dynamic overlap.

`BASIC` — Each response is assigned a weight depending on the Toloker's skill value. The aggregated response confidence is calculated based on the probability algorithm. The task overlap increases until it reaches `max_overlap` or until the confidence of the aggregated response exceeds `min_confidence`.

You have to specify `max_overlap`, `min_confidence`, `answer_weight_skill_id` and `fields`. ||
|| **dynamic_overlap_config. max_overlap** | **integer \| required if**

Required if dynamic overlap is used.

Maximum overlap. Must be higher than the values in `defaults`. Minimum — 1. Maximum — 30000. ||
|| **dynamic_overlap_config. min_confidence** | **float \| required if**

Required if dynamic overlap is used.

Minimum confidence of the aggregated response. Values from 0 to 1. ||
|| **dynamic_overlap_config. answer_weight_skill_id** | **string \| required if**

Required if dynamic overlap is used.

A skill that determines the weight of the Toloker's response. For best results, use a skill calculated as the [percentage of correct responses in control tasks](goldenset.md). ||
|| **dynamic_overlap_config. fields[]** | **array of objects \| required if**

Required if dynamic overlap is used.

[Output data fields](../../guide/concepts/result-aggregation.md) to use for aggregating responses. For best results, each of these fields must have a limited number of response options.

Don't specify several fields if their values depend on each other. ||
|| **dynamic_overlap_config. fields.name** | **string \| required if**

Required if dynamic overlap is used.

The output data field name. ||
|| **mixer_config** {#mixer_config} | **object \| required if**

Required if "smart mixing" is used.

Parameters for automatically creating a task suite ("smart mixing"). For more information about creating task suites, see the [Requester's guide](../../guide/concepts/pool-main.md). ||
|| **mixer_config. real_tasks_count** | **integer \| required if**

Required if "smart mixing" is used.

Number of general tasks per suite.

The maximum number of tasks per task suite if `golden_task_distribution_function` or `training_task_distribution_function` is used. ||
|| **mixer_config. golden_tasks_count** | **integer \| required if**

Required if "smart mixing" is used.

Number of control tasks per suite. ||
|| **mixer_config. training_tasks_count** | **integer \| required if**

Required if "smart mixing" is used.

Number of training tasks per suite. ||
|| **mixer_config.golden_task_ distribution_function.scope** | **string \| required if**

Required if control tasks are assigned at a variable rate.

How to count tasks completed by the Toloker:

- `POOL` — Count completed pool tasks.
- `PROJECT` — Count completed project tasks. ||
|| **mixer_config.golden_task_ distribution_function. distribution** | **string \| required if**

Required if control tasks are assigned at a variable rate.

Distribution of control tasks within an interval. This parameter has only one possible value — `UNIFORM`. ||
|| **mixer_config.golden_task_ distribution_function. window_days** | **integer \| required if**

Required if control tasks are assigned at a variable rate.

Period in which completed tasks are counted (number of days). ||
|| **mixer_config.golden_task_ distribution_function. intervals[]** | **array of objects \| required if**

Required if control tasks are assigned at a variable rate. Interval borders and number of control tasks in an interval. ||
|| **mixer_config.golden_task_ distribution_function. intervals[].from** | **integer \| required if**

Required if control tasks are assigned at a variable rate.

Start of the interval (number of tasks completed by the Toloker in the project or in the pool). ||
|| **mixer_config.golden_task_ distribution_function. intervals[].to** | **integer \| required if**

Required if control tasks are assigned at a variable rate.

End of the interval (number of tasks completed by the Toloker in the project or in the pool). ||
|| **mixer_config.golden_task_ distribution_function. intervals[].frequency** | **integer \| required if**

Required if control tasks are assigned at a variable rate.

Frequency of control tasks in an interval. The first task in an interval is a control task. For example, if you set `frequency: 3` tasks number 1, 4, 7 and so on will be control tasks. ||
|| **mixer_config.training_task_ distribution_function.scope** | **string \| required if**

Required if training tasks are assigned at a variable rate.

How to count tasks completed by the Toloker:

- `POOL` — Count completed pool tasks.
- `PROJECT` — Count completed project tasks. ||
|| **mixer_config.training_task_ distribution_function. distribution** | **string \| required if**

Required if training tasks are assigned at a variable rate.

Distribution of training tasks within an interval. This parameter has only one possible value — `UNIFORM`. ||
|| **mixer_config.training_task_ distribution_function. window_days** | **integer \| required if**

Required if training tasks are assigned at a variable rate.

Period in which completed tasks are counted (number of days). ||
|| **mixer_config.training_task_ distribution_function. intervals[]** | **array of objects \| required if**

Required if training tasks are assigned at a variable rate.

Interval borders and number of control tasks in an interval. ||
|| **mixer_config.training_task_ distribution_function. intervals[].from** | **integer \| required if**

Required if training tasks are assigned at a variable rate.

Start of the interval (number of tasks completed by the Toloker in the project or in the pool).

Yes, if you use uneven distribution of training tasks ||
|| **mixer_config.training_task_ distribution_function. intervals[].to** | **integer \| required if**

Required if training tasks are assigned at a variable rate. End of the interval (number of tasks completed by the Toloker in the project or in the pool). ||
|| **mixer_config.training_task_ distribution_function. intervals[].frequency** | **integer \| required if**

Required if training tasks are assigned at a variable rate.

Frequency of training tasks in an interval. The first task in an interval is a training task. For example, if you set `frequency: 3` tasks number 1, 4, 7 and so on will be training tasks. ||
|| **private_comment** | **string**

Comments on the pool (only visible to the requester). ||
|| **public_description** | **string**

Description for Tolokers. If it is filled in, the text will be displayed instead of the project's `public_description` in the list of tasks for Tolokers. ||
|| **dynamic_pricing_config** | **object**

[Dynamic pricing](../../guide/concepts/dynamic-pricing.md#dynamic-pricing__section_ucl_3hl_vlb) settings. ||
|| **auto_accept_solutions** | **boolean**

Whether tasks must be checked manually:

- `true` — Automatic task acceptance (manual checking isn't necessary).
- `false` — The requester will check the tasks.

The default value is `true`. ||
|| **auto_accept_period_day** | **integer**

Time (number of days) for the requester to review the task. If the requester doesn't accept or reject the task within this period, the decision will be made automatically. May take a value from 1 to 21. ||
|| **auto_close_after_complete_ delay_seconds** | **integer**

Waiting time (in seconds) before automatic closure of the pool after all tasks are completed. Minimum — 0, maximum — 259 200 seconds (three days). The default value is 0.

Use it if:

- Your data processing is close to real time.
- You need an open pool where you upload tasks.
- Dynamic overlap is enabled in the pool (`dynamic_overlap_config`). ||
|| **assignments_issuing_config** | **object**

Settings for assigning tasks in the pool. ||
|| **assignments_issuing_config. issue_task_suites_in_ creation_order** {#issue_task_suites_in_creation_order} | **boolean**

For pools that don't use "smart mixing".

Assign task suites in the order in which they were uploaded. For example, for a pool with an overlap of 5, the first task suite is assigned to five Tolokers, then the second task suite, and so on.

This parameter is available when the project has `"assignments_issuing_type": "AUTOMATED".` ||
|| **Priority** {#priority} | **integer**

The priority of the pool in relation to other pools in the project with the same task price and set of filters. Users are assigned tasks with a higher priority first.

Possible values: from `-100` to `100`.

By default the value is `0`. ||
|| **filter** | **object**

Settings for [Toloker selection filters](filters.md). ||
|| **quality_control** | **object**

Settings for quality control rules and the ID of the pool with training tasks. ||
|| **quality_control. training_requirement** | **object**

Parameters of the training pool that is linked to the general task pool. ||
|| **quality_control. training_requirement. training_pool_id** | **string**

ID of the training pool that is linked to the general task pool. ||
|| **quality_control. training_requirement. training_passing_skill_value** | **integer**

Percentage of correct answers in training tasks (from 0 to 100) required in order to access the general tasks. Only the first answer of the Toloker in each task is taken into account. ||
|| **quality_control. captcha_frequency** | **string**

The frequency of showing captchas:

- `LOW` — Show one for every 20 tasks.
- `MEDIUM`, `HIGH` — Show one for every 10 tasks.

By default, captchas aren't displayed. ||
|| **quality_control.configs** | **object**

[Quality control rules](quality_control.md). ||
|| **quality_control. checkpoints_config** | **object**

Selective task review. If you want to use the [majority vote](mv.md) quality control method, specify `MAJORITY_VOTE` in the [quality_control](#quality-control-popup) parameter. Some tasks are assigned with higher overlap (for example, "5") and checked. The rest of the tasks are assigned with the overlap set for the pool (for example, "1") and they are not checked. Selective review lets you improve pool completion quality.

You can reduce the frequency of checking tasks over time.

Example of settings: in the first 100 tasks completed by the Toloker in the pool, assign every 5th task with an overlap of "5" to check matching responses. In the following tasks, every 25th task is issued with an overlap of "5". ||
|| **quality_control. checkpoints_config. real_settings** | **object**

Selective review of general tasks. To make sure selective review is enabled, don't forget to set up task display in [mixer_config](#mixer_config). ||
|| **quality_control. checkpoints_config. golden_settings** | **object**

Selective review of control tasks. To make sure selective review is enabled, don't forget to set up display of this type of task in [mixer_config](#mixer_config). ||
|| **quality_control. checkpoints_config. training_settings** | **object**

Selective review of training tasks. To make sure selective review is enabled, don't forget to set up display of this type of task in [mixer_config](#mixer_config). ||
|| **speed_quality_balance** | **object**

[Speed/quality balance](../../guide/concepts/adjust.md). ||
|| **speed_quality_balance. type** | **string**

Balance type. Possible values:

- `TOP_PERCENTAGE_BY_QUALITY` — Users with the best task completion quality.
- `BEST_CONCURRENT_USERS_BY_QUALITY` — Active Tolokers with access to the task. ||
|| **speed_quality_balance. percent** | **integer**

Percentage of Tolokers with the best task completion quality. The field is shown if the balance type is set to `TOP_PERCENTAGE_BY_QUALITY`. Possible values are 10, 20, 30, 40...100. ||
|| **speed_quality_balance. count** | **integer**

The number of active Tolokers the task is available to. The field is shown if the balance type is set to `BEST_CONCURRENT_USERS_BY_QUALITY`. May take a value from 1 to 100. ||
|| **dynamic_overlap_config** | **object**

Setting up dynamic overlap (also known as incremental relabeling or IRL). Allows you to change the overlap depending on how well the Tolokers handle the task.

Set the closing interval (`auto_close_after_complete_delay_seconds`). It should be enough to complete tasks with an overlap higher than the minimum.

When all pool tasks are completed, [aggregate the responses](aggregated-solutions.md). ||
|| **defaults.default_overlap_ for_new_tasks** {#default-overlap-tasks} | **integer**

The overlap for tasks that are uploaded to the pool (used if the `allow_defaults=true` parameter is set at upload). ||
|| **mixer_config. min_real_tasks_count** | **float**

Minimum number of general tasks in a task suite (if the number of assignments left is less than the number specified in `mixer_config.real_tasks_count`). Minimum — 0. By default, the value is the same as in `mixer_config.real_tasks_count`. ||
|| **mixer_config. min_golden_tasks_count** | **integer**

Minimum number of control tasks per task suite (if the number of assignments left is less than the number specified in `mixer_config.golden_tasks_count`). Minimum — 0. By default, the value is the same as in `mixer_config.golden_tasks_count`. ||
|| **mixer_config. min_training_tasks_count** | **integer**

Minimum number of training tasks per task suite (if the number of assignments left is less than the number specified in `mixer_config.golden_tasks_count`). Minimum — 0. By default, the value is the same as in `mixer_config.training_tasks_count`. ||
|| **mixer_config. force_last_assignment** | **boolean**

Setting for the last task suite in the pool, if less than the minimum remaining number of tasks are not completed (`mixer_config.min_real_tasks_count`). Values:

- `true` — Assign an incomplete task suite.
- `false` — Don't assign tasks. This option can be used if you are adding tasks after the pool is started.

The default value is `true`.

This parameter only applies to general tasks. The number of control and training tasks in the last suite must be complete (`mixer_config.golden_tasks_count`, `mixer_config.training_tasks_count`). ||
|| **mixer_config.force_last_ assignment_ delay_seconds** | **integer**

Waiting time (in seconds) after adding a task or increasing the overlap before assigning the last task suite in the pool. Minimum — 0, maximum — 86,400 seconds (one day).

This parameter can be used if the pool has `force_last_assignment: true`. ||
|| **mixer_config.mix_tasks_ in_creation_ order** | **boolean**

The order used to add tasks to suites:

- `true` — Add tasks to suites in the order in which they were uploaded. For example, in a pool with an overlap of 5, the first uploaded task will be included in the first 5 task suites. They will be assigned to 5 Tolokers.
- `false` — Add tasks to suites in random order.

The default value is `false`. ||
|| **mixer_config. shuffle_tasks_in_task_suite** | **boolean**

The order of tasks within a suite:

- `true` — Random.
- `false` — The order in which tasks were uploaded.

The default value is `true`. ||
|| **mixer_config.golden_task_ distribution_function** | **object**

Vary the frequency of control tasks. The option allows you to change the frequency of checking as the Toloker completes more tasks.

If it is filled in, use `real_task_count` to specify the maximum number of tasks per task suite. To use the option, set the `golden_task_count:0` and `min_golden_tasks_count:null` parameter values.

The interval bound is the number of a task in the pool. If the task suite has several intervals, the settings for the first interval are applied.

#### Example:

In the first task suite (the range from 1 to 25), every fifth task is a control task, and in the following suites, every 25th task is a control task. ||

|| **mixer_config.training_task_ distribution_function** | **object**

Issue of training tasks with uneven frequency. This option allows you to change the frequency of training tasks as the Toloker completes more tasks.

If it is filled in, then in `real_task_count` specify the maximum number of tasks to put in a task suite. To use the option, set parameter values `training_task_count:0` and `min_training_tasks_count:null`.

#### Example:
In the first task suite (the range from 1 to 25), every fifth task is a training task, and in the following suites, every 25th task is a training task. ||
|#

## Response {#response}

Contains information about the created training pool. Besides [parameters that are set when creating a training pool,](#pool-param) it includes parameters that are assigned to the pool automatically:

#|
|| Parameter | Overview ||
|| **id** | **string**

Pool ID. ||
|| **status** | **string**

Status of the pool:

- `OPEN` — Open.
- `CLOSED` — Closed.
- `ARCHIVED` — Archived. ||
|| **last_close_reason** | **string**

The reason for closing the pool the last time:

- `MANUAL` — Closed by the requester.
- `EXPIRED` — Reached the date and time set in `will_expire`.
- `COMPLETED` — Closed automatically because all the pool tasks were completed.
- `NOT_ENOUGH_BALANCE` — Closed automatically because the Toloka account ran out of funds.
- `ASSIGNMENTS_LIMIT_EXCEEDED` — Closed automatically because it exceeded the limit on assigned task suites (2 million maximum).
- `BLOCKED` — Closed automatically because the requester's account was blocked by a Toloka administrator.
- `FOR_UPDATE` — The pool is closed for editing. ||
|| **created** | **string**

The UTC date and time when the pool was created, in ISO 8601 format: `YYYY-MM-DDThh:mm:ss[.sss]`. ||
|| **last_started** | **string**

The date and time when the pool was last started, in UTC in ISO 8601 format: `YYYY-MM-DDThh:mm:ss[.sss]`. ||
|| **last_stopped** | **string**

The date and time when the pool was last stopped, in UTC in ISO 8601 format: `YYYY-MM-DDThh:mm:ss[.sss]`. ||
|| **type** | **string**

Deprecated parameter.

Pool type. The value is always `REGULAR` indicating a normal pool. ||
|#