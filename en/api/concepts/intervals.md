# Task distribution intervals

Toloka allows you to either set intervals for tasks during which they will be [selected for majority vote check](#selective-mv), or to [distribute the control or training](#smart-mixing-distribution) tasks among the general tasks in the pool if you use smart mixing.

![Task distibution intervals](../_images/intervals.png =700x)

In Toloka API, use the following JSON format to set the intervals:

```json
"intervals": [
  {
    "from": 1,
    "to": 5,
    "frequency": 3
  },
  {
    "from": 6,
    "to": 1000,
    "frequency": 5
  }
]
```

You can change these settings with a `POST` request when you [create a pool](https://toloka.ai/docs/api/api-reference/#post-/pools) or with a `PUT` request when you [edit a pool](https://toloka.ai/docs/api/api-reference/#put-/pools/-id-).

We provide samples for the `POST` request. `PUT` requests look similar, but you must send all the existing pool attributes in the request together with the ones you want to change.

## Selective majority vote check {#selective-mv}

The sample requests below contain the intervals for the general, control, and training tasks which will be [selected for majority vote check](../../guide/concepts/selective-mvote.md). The intervals are set according to the scheme above.

{% list tabs %}

- General task check intervals

  With the sample request below, the first, fourth, and sixth general tasks in the first task suite and the twelfth general task from the second task suite will be selected for majority vote check.

  We use the `quality_control.checkpoints_config.real_settings.intervals` parameter to set this scheme.

  ### Sample request

  ```bash
  curl -X POST 'https://toloka.dev/api/v1/pools' \
       -H 'Content-Type: application/json' \
       -H 'Authorization: OAuth AQC2AGAJgyNSA8CtpdO9MWy_QEB6s6kDjHUoElE' \
       -d '{
            "project_id": "120798",
            "private_name": "Cat or Dog?",
            "will_expire": "2024-06-23T07:11:19.963",
            "reward_per_assignment": 0.02,
            "assignment_max_duration_seconds": 600,
            "auto_accept_solutions": false,
            "quality_control": {
              "checkpoints_config": {
                "real_settings": {
                  "target_overlap": 3,
                  "task_distribution_function": {
                    "scope": "PROJECT",
                    "distribution": "UNIFORM",
                    "window_days": 10,
                    "intervals": [
                      {
                        "from": 1,
                        "to": 5,
                        "frequency": 3
                      },
                      {
                        "from": 6,
                        "to": 1000,
                        "frequency": 5
                      },
                      {
                        "from": 1001,
                        "frequency": 8
                      }
                    ]
                  }
                }
              }
            },
            "defaults": {
              "default_overlap_for_new_task_suites": 1
            }
          }'
  ```

- Control task check intervals

  With the sample request below, the first, fourth, and sixth control tasks in the first task suite and the twelfth control task from the second task suite will be selected for majority vote check.

  We use the `quality_control.checkpoints_config.golden_settings.intervals` parameter to set this scheme.

  ### Sample request

  ```bash
  curl -X POST 'https://toloka.dev/api/v1/pools' \
       -H 'Content-Type: application/json' \
       -H 'Authorization: OAuth AQC2AGAJgyNSA8CtpdO9MWy_QEB6s6kDjHUoElE' \
       -d '{
            "project_id": "120798",
            "private_name": "Cat or Dog?",
            "will_expire": "2024-06-23T07:11:19.963",
            "reward_per_assignment": 0.02,
            "assignment_max_duration_seconds": 600,
            "auto_accept_solutions": false,
            "quality_control": {
              "checkpoints_config": {
                "golden_settings": {
                  "target_overlap": 3,
                  "task_distribution_function": {
                    "scope": "PROJECT",
                    "distribution": "UNIFORM",
                    "window_days": 10,
                    "intervals": [
                      {
                        "from": 1,
                        "to": 5,
                        "frequency": 3
                      },
                      {
                        "from": 6,
                        "to": 1000,
                        "frequency": 5
                      },
                      {
                        "from": 1001,
                        "frequency": 8
                      }
                    ]
                  }
                }
              }
            },
            "defaults": {
              "default_overlap_for_new_task_suites": 1
            }
          }'
  ```

- Training task check intervals

  With the sample request below, the first, fourth, and sixth training tasks in the first task suite and the twelfth training task from the second task suite will be selected for majority vote check.

  We use the `quality_control.checkpoints_config.training_settings.intervals` parameter to set this scheme.

  ### Sample request

  ```bash
  curl -X POST 'https://toloka.dev/api/v1/pools' \
       -H 'Content-Type: application/json' \
       -H 'Authorization: OAuth AQC2AGAJgyNSA8CtpdO9MWy_QEB6s6kDjHUoElE' \
       -d '{
            "project_id": "120798",
            "private_name": "Cat or Dog?",
            "will_expire": "2024-06-23T07:11:19.963",
            "reward_per_assignment": 0.02,
            "assignment_max_duration_seconds": 600,
            "auto_accept_solutions": false,
            "quality_control": {
              "checkpoints_config": {
                "training_settings": {
                  "target_overlap": 3,
                  "task_distribution_function": {
                    "scope": "PROJECT",
                    "distribution": "UNIFORM",
                    "window_days": 10,
                    "intervals": [
                      {
                        "from": 1,
                        "to": 5,
                        "frequency": 3
                      },
                      {
                        "from": 6,
                        "to": 1000,
                        "frequency": 5
                      },
                      {
                        "from": 1001,
                        "frequency": 8
                      }
                    ]
                  }
                }
              }
            },
            "defaults": {
              "default_overlap_for_new_task_suites": 1
            }
          }'
  ```

{% endlist %}

## Smart mixing distribution {#smart-mixing-distribution}

When you use [smart mixing](../../guide/concepts/distribute-tasks-by-pages.md#smart-mixing), you can set intervals for the control and training tasks in the pool and distribute these tasks unevenly throughout the pool.

{% list tabs %}

- Control task distibution intervals

  With the sample request below, the first, fourth, and sixth tasks in the first task suite and the twelfth task from the second task suite will be a **control task**, like in the image above.

  We use the `mixer_config.golden_task_distribution_function.intervals` parameter to set this scheme.

  ### Sample request

  ```bash
  curl -X POST 'https://toloka.dev/api/v1/pools' \
       -H 'Content-Type: application/json' \
       -H 'Authorization: OAuth AQC2AGAJgyNSA8CtpdO9MWy_QEB6s6kDjHUoElE' \
       -d '{
            "project_id": "120798",
            "private_name": "Cat or Dog?",
            "will_expire": "2024-06-23T07:11:19.963",
            "reward_per_assignment": 0.02,
            "assignment_max_duration_seconds": 600,
            "auto_accept_solutions": false,
            "mixer_config": {
              "golden_task_distribution_function": {
                "distribution": "UNIFORM",
                "intervals": [
                  {
                    "from": 1,
                    "to": 5,
                    "frequency": 3
                  },
                  {
                    "from": 6,
                    "to": 1000,
                    "frequency": 5
                  },
                  {
                    "from": 1001,
                    "frequency": 8
                  }
                ]
              }
            },
            "defaults": {
              "default_overlap_for_new_task_suites": 1
            }
          }'
  ```

- Training task distibution intervals

  With the sample request below, the first, fourth, and sixth tasks in the first task suite and the twelfth task from the second task suite will be a **training task**, like in the image above.

  We use the `mixer_config.training_task_distribution_function.intervals` parameter to set this scheme.

  ### Sample request

  ```bash
  curl -X POST 'https://toloka.dev/api/v1/pools' \
       -H 'Content-Type: application/json' \
       -H 'Authorization: OAuth AQC2AGAJgyNSA8CtpdO9MWy_QEB6s6kDjHUoElE' \
       -d '{
            "project_id": "120798",
            "private_name": "Cat or Dog?",
            "will_expire": "2024-06-23T07:11:19.963",
            "reward_per_assignment": 0.02,
            "assignment_max_duration_seconds": 600,
            "auto_accept_solutions": false,
            "mixer_config": {
              "training_task_distribution_function": {
                "distribution": "UNIFORM",
                "intervals": [
                  {
                    "from": 1,
                    "to": 5,
                    "frequency": 3
                  },
                  {
                    "from": 6,
                    "to": 1000,
                    "frequency": 5
                  },
                  {
                    "from": 1001,
                    "frequency": 8
                  }
                ]
              }
            },
            "defaults": {
              "default_overlap_for_new_task_suites": 1
            }
          }'
  ```

{% endlist %}

## See also {#see-also}

- [{#T}](../../guide/concepts/selective-mvote.md)
- [{#T}](../../guide/concepts/distribute-tasks-by-pages.md#smart-mixing)
- [Toloka API: Create pool](https://toloka.ai/docs/api/api-reference/#post-/pools)
- [Toloka API: Edit pool](https://toloka.ai/docs/api/api-reference/#put-/pools/-id-)

{% include [contact-support](../../guide/_includes/contact-support.md) %}

{% include [image-styles-internal](../../../_includes/image-styles-internal.md) %}