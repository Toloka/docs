# Ways to upload tasks

{% include [announce](../_includes/announce.md) %}

## Uploading tasks using the API {#download-tasks-api}

Toloka provides two ways of uploading tasks using the API:

### Uploading each task individually

Choose this method if:

- You [created a pool](https://toloka.ai/docs/api/api-reference/#post-/pools) using ["smart mixing"](../../guide/concepts/distribute-tasks-by-pages.md#distribute-tasks-by-pages__smart-mixing) (the `mixer_config` parameter).

- Apart from the general tasks, the pool will contain control or training tasks.

With this method, Toloka will split tasks into suites according to the "smart mixing" settings. When uploading tasks this way, use the [POST /tasks](https://toloka.ai/docs/api/api-reference/#post-/tasks) request.

{% cut "Sample request" %}

{% list tabs %}

- Single task

  ```bash
  curl -X POST 'https://toloka.dev/api/v1/tasks' \
      -H 'Authorization: OAuth PlaceYourRealOAuthToken_Here' \
      -H 'Content-Type: application/json' \
      -d '{
            "pool_id": "1",
            "input_values": {
              "image_url": "www.images/image1.ru"
            },
            "known_solutions": [
              {
                "output_values": {
                  "result": "OK",
                  "like": false
                },
                "correctness_weight": 0.8
              },
              {
                "output_values": {
                  "result": "OK",
                  "like": true
                },
                "correctness_weight": 1
              }
            ],
            "baseline_solutions": [
              {
                "output_values": {
                  "result": "OK",
                  "like": false
                },
                "confidence_weight": 0.8
              },
              {
                "output_values": {
                  "result": "OK",
                  "like": true
                },
                "confidence_weight": 1
              }
            ],
            "message_on_unknown_solution": "The cat is in a good mood.",
            "overlap": 3,
            "infinite_overlap": false,
            "reserved_for": [],
            "unavailable_for": []
          }'
  ```

- Multiple tasks

  ```bash
  curl -X POST 'https://toloka.dev/api/v1/tasks' \
      -H 'Authorization: OAuth PlaceYourRealOAuthToken_Here' \
      -H 'Content-Type: application/json' \
      -d '[
            {
              "pool_id": "1",
              "input_values": {
                "image_url": "www.images/image1.ru"
              },
              "known_solutions": [
                {
                  "output_values": {
                    "result": "OK",
                    "like": false
                  },
                  "correctness_weight": 0.8
                },
                {
                  "output_values": {
                    "result": "OK",
                    "like": true
                  },
                  "correctness_weight": 1
                }
              ],
              "baseline_solutions": [
                {
                  "output_values": {
                    "result": "OK",
                    "like": false
                  },
                  "confidence_weight": 0.8
                },
                {
                  "output_values": {
                    "result": "OK",
                    "like": true
                  },
                  "confidence_weight": 1
                }
              ],
              "message_on_unknown_solution": "The cat is in a good mood.",
              "overlap": 3,
              "infinite_overlap": false,
              "reserved_for": [],
              "unavailable_for": []
            },
            {
              <task #2>
            },
            ,
            {
              <task #3>
            }
          ]'
  ```

{% endlist %}

{% endcut %}

### Uploading tasks grouped by suite

Choose this method if you:

- Create task suites yourself.
- Determine yourself which tasks to include in each suite.

This method won't work if you created a pool using [smart mixing](../../guide/concepts/distribute-tasks-by-pages.md#smart-mixing). When uploading tasks this way, use the [POST /task-suites](https://toloka.ai/docs/api/api-reference/#post-/task-suites) request.

{% cut "Sample request" %}

{% list tabs %}

- Single task suite

  ```bash
  curl -X POST 'https://toloka.dev/api/v1/task-suites' \
      -H 'Authorization: OAuth PlaceYourRealOAuthToken_Here' \
      -H 'Content-Type: application/json' \
      -d '{
            "id": "63614047-38c3-4ad4-8a86-99c5c651a9b8",
            "pool_id": "1",
            "tasks": [
              {
                "id": "49a333ea-2728-4c1c-ab1f-8ab1bfe4ee7e",
                "origin_task_id": "e3da7fe1-828d-4d9c-b49d-42c0eb5fcfde",
                "input_values": {
                  "image_url": "www.image1.ru"
                },
                "known_solutions": [
                  {
                    "correctness_weight": 0.95,
                    "output_values": {
                      "colour": "black"
                    }
                  },
                  {
                    "correctness_weight": 0.7,
                    "output_values": {
                      "colour": "gray"
                    }
                  }
                ],
                "message_on_unknown_solution": "The elephant is black"
              },
              {
                "input_values": {
                  "image_url": "www.image2.ru"
                },
                "known_solutions": [
                  {
                    "correctness_weight": 1,
                    "output_values": {
                      "colour": "white"
                    }
                  }
                ],
                "message_on_unknown_solution": "The elephant is white"
              }
            ],
            "overlap": 5,
            "infinite_overlap": false,
            "remaining_overlap": 3,
            "reserved_for": [],
            "unavailable_for": [],
            "issuing_order_override": 3,
            "mixed": true,
            "automerged": false,
            "created": "2016-04-18T12:43:04.988"
          }'
  ```

- Multiple task suites

  ```bash
  curl -X POST 'https://toloka.dev/api/v1/task-suites' \
      -H 'Authorization: OAuth PlaceYourRealOAuthToken_Here' \
      -H 'Content-Type: application/json' \
      -d '[
            {
              "id": "63614047-38c3-4ad4-8a86-99c5c651a9b8",
              "pool_id": "1",
              "tasks": [
                {
                  "id": "49a333ea-2728-4c1c-ab1f-8ab1bfe4ee7e",
                  "origin_task_id": "e3da7fe1-828d-4d9c-b49d-42c0eb5fcfde",
                  "input_values": {
                    "image_url": "www.image1.ru"
                  },
                  "known_solutions": [
                    {
                      "correctness_weight": 0.95,
                      "output_values": {
                        "colour": "black"
                      }
                    },
                    {
                      "correctness_weight": 0.7,
                      "output_values": {
                        "colour": "gray"
                      }
                    }
                  ],
                  "message_on_unknown_solution": "The elephant is black"
                },
                {
                  "input_values": {
                    "image_url": "www.image2.ru"
                  },
                  "known_solutions": [
                    {
                      "correctness_weight": 1,
                      "output_values": {
                        "colour": "white"
                      }
                    }
                  ],
                  "message_on_unknown_solution": "The elephant is white"
                }
              ],
              "overlap": 5,
              "infinite_overlap": false,
              "remaining_overlap": 3,
              "reserved_for": [],
              "unavailable_for": [],
              "issuing_order_override": 3,
              "mixed": true,
              "automerged": false,
              "created": "2016-04-18T12:43:04.988"
            },
            {
              <task suite #2>
            },
            ,
            {
              <task suite #3>
            }
          ]'
  ```

{% endlist %}

{% endcut %}

## Uploading tasks using the Python SDK {#download-tasks-python}

If you're developing Python apps, you can create API requests using [Toloka-Kit](../../toloka-kit/index.md) methods to achieve a result with less effort and avoid possible errors.

Ways to upload tasks using Toloka-Kit:

Way | Method
----- | -----
Creates a new task | [create_task](../../toloka-kit/reference/toloka.client.TolokaClient.create_task.md)
Creates multiple tasks within a single request | [create_tasks](../../toloka-kit/reference/toloka.client.TolokaClient.create_tasks.md)
Creates multiple tasks asynchronously | [create_tasks_async](../../toloka-kit/reference/toloka.client.TolokaClient.create_tasks_async.md)
Creates a task suite | [create_tasks_suite](../../toloka-kit/reference/toloka.client.TolokaClient.create_task_suite.md)
Creates multiple task suites within a single request | [create_tasks_suites](../../toloka-kit/reference/toloka.client.TolokaClient.create_task_suites.md)
Creates multiple task suites asynchronously | [create_tasks_suites_async](../../toloka-kit/reference/toloka.client.TolokaClient.create_task_suites_async.md)

{% include [contact-support](../../guide/_includes/contact-support.md) %}