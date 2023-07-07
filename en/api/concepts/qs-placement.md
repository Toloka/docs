# Posting tasks

{% include [announce](../_includes/announce.md) %}

## Before you start {#start}

Choose a platform to get an OAuth token:

{% list tabs %}

- Sandbox

    1. [Register](https://toloka.ai/docs/api/api-reference/#overview--accessing-the-api) on the selected platform if you haven't done this before.

    1. Get an OAuth token in the [requester interface](https://sandbox.toloka.yandex.com/requester/profile/integration).

    1. All examples use the sandbox URL: `https://sandbox.toloka.dev/api/v1/{resource_path}`. If you decide to switch to the production version, replace the resource URL with `https://toloka.dev/api/v1/{resource_path}`.

- Production version

    1. [Register](https://toloka.ai/docs/api/api-reference/#overview--accessing-the-api) on the selected platform if you haven't done this before.

    1. Get an OAuth token in the [requester interface](https://platform.toloka.ai/requester/profile/integration).

    1. To send requests, replace the resource URL in the examples with `https://toloka.dev/api/v1/{resource_path}`, since all the examples are given for the sandbox.

    1. To post tasks in Toloka's production version, first top up your account balance.

{% endlist %}

## Create a project {#project}

### Request {#project-request}

Use the `POST /api/v1/projects` [method](https://toloka.ai/docs/api/api-reference/#post-/projects):

{% list tabs %}

- cURL

    Send a request from the command line using the cURL utility:

    ```bash
    curl -X POST 'https://sandbox.toloka.dev/api/v1/projects' \
         -H 'Authorization: OAuth PlaceYourRealOAuthToken_Here' \
         -H 'Content-Type: application/json' \
         -d '{
               "public_name": "Categories of shoes",
               "public_description": "Look at the picture and determine the category of shoes",
               "public_instructions": "In this task you will see images of different shoes. You need to determine their category.",
               "task_spec": {
                 "input_spec": {
                   "image": {
                     "type": "url",
                     "required": true,
                     "hidden": false
                   }
                 },
                 "output_spec": {
                   "result": {
                     "type": "string",
                     "required": true,
                     "hidden": false,
                     "allowed_values": ["boots","sneakers","other","failed to load"]
                   }
                 },
                 "view_spec": {
                   "lock": {
                     "core": "1.7.0",
                     "view.list": "1.0.5",
                     "view.image": "1.2.0",
                     "plugin.toloka": "1.1.8",
                     "field.radio-group": "1.1.10",
                     "condition.required": "1.1.5"
                   },
                   "type": "tb",
                   "config": "{\"view\": {\"items\": [{\"url\": {\"path\": \"image\", \"type\": \"data.input\"}, \"ratio\": [1, 1], \"type\": \"view.image\"}, {\"data\": {\"path\": \"result\", \"type\": \"data.output\"}, \"validation\": {\"type\": \"condition.required\"}, \"options\": [{\"label\": \"Boots\", \"value\": \"boots\"}, {\"label\": \"Sneakers\", \"value\": \"sneakers\"}, {\"label\": \"Other\", \"value\": \"other\"}, {\"label\": \"Failed to load\", \"value\": \"failed to load\"}], \"type\": \"field.radio-group\"}], \"type\": \"view.list\"}, \"plugins\": [{\"layout\": {\"kind\": \"scroll\", \"taskWidth\": 400}, \"type\": \"plugin.toloka\"}]}",
                   "settings": {
                     "showSkip": true,
                     "showTimer": true,
                     "showTitle": true,
                     "showFinish": true,
                     "showSubmit": true,
                     "showMessage": true,
                     "showFullscreen": true,
                     "showInstructions": true
                   }
                 }
               },
               "assignments_issuing_type": "AUTOMATED"
             }'
    ```

- Postman

    Fill in the fields:

    1. Request URL

        ```bash
        https://sandbox.toloka.dev/api/v1/projects
        ```

    1. Headers

        ```bash
        Authorization: OAuth PlaceYourRealOAuthToken_Here
        Content-Type: application/json
        ```

    1. Body

        ```json
        {
          "public_name": "Categories of shoes",
          "public_description": "Look at the picture and determine the category of shoes",
          "public_instructions": "In this task you will see images of different shoes. You need to determine their category.",
          "task_spec": {
            "input_spec": {
              "image": {
                "type": "url",
                "required": true,
                "hidden": false
              }
            },
            "output_spec": {
              "result": {
                "type": "string",
                "required": true,
                "hidden": false,
                "allowed_values": [
                  "boots",
                  "sneakers",
                  "other",
                  "failed to load"
                ]
              }
            },
            "view_spec": {
              "lock": {
                "core": "1.7.0",
                "view.list": "1.0.5",
                "view.image": "1.2.0",
                "plugin.toloka": "1.1.8",
                "field.radio-group": "1.1.10",
                "condition.required": "1.1.5"
              },
              "type": "tb",
              "config": "{\"view\": {\"items\": [{\"url\": {\"path\": \"image\", \"type\": \"data.input\"}, \"ratio\": [1, 1], \"type\": \"view.image\"}, {\"data\": {\"path\": \"result\", \"type\": \"data.output\"}, \"validation\": {\"type\": \"condition.required\"}, \"options\": [{\"label\": \"Boots\", \"value\": \"boots\"}, {\"label\": \"Sneakers\", \"value\": \"sneakers\"}, {\"label\": \"Other\", \"value\": \"other\"}, {\"label\": \"Failed to load\", \"value\": \"failed to load\"}], \"type\": \"field.radio-group\"}], \"type\": \"view.list\"}, \"plugins\": [{\"layout\": {\"kind\": \"scroll\", \"taskWidth\": 400}, \"type\": \"plugin.toloka\"}]}",
              "settings": {
                "showSkip": true,
                "showTimer": true,
                "showTitle": true,
                "showFinish": true,
                "showSubmit": true,
                "showMessage": true,
                "showFullscreen": true,
                "showInstructions": true
              }
            }
          },
          "assignments_issuing_type": "AUTOMATED"
        }
        ```

{% endlist %}

The example shows the basic parameters that are necessary to create a simple project. For a more detailed description of all request parameters, see [Create project](https://toloka.ai/docs/api/api-reference/#post-/projects).

### Response {#project-response}

In response to the  request, you will receive a JSON object for the created project. This object contains the project `id`.

```json
{
  "id": "12345",
  "public_name": "Categories of shoes",
  "public_description": "Look at the picture and determine the category of shoes",
  ...
}
```

{% note info %}

You'll need the `id` to create pools in the project: specify it in the [add pool](#pool) request.

{% endnote %}

## Add a pool {#pool}

### Request {#pool-post}

In the given code example, substitute the parameter values:

- In the `project_id` parameter, replace `{project_id}` with the ID of the project that the pool was created for (the ID received in response to the add project request).
- In `will_expire`, replace `{close_date}` with the UTC date and time in the ISO 8601 format: `YYYY-MM-DDThh:mm:ss[.sss]`, specifying when the pool needs to be closed even if some task suites are not completed.

Next, send a `POST` [request](https://toloka.ai/docs/api/api-reference/#post-/pools) to `/api/v1/pools`:

{% list tabs %}

- cURL

    Send a request from the command line using the cURL utility:

    ```bash
    curl -X POST 'https://sandbox.toloka.dev/api/v1/pools' \
         -H 'Authorization: OAuth PlaceYourRealOAuthToken_Here' \
         -H 'Content-Type: application/json' \
         -d '{
               "project_id": "{project_id}",
               "private_name": "Shoes pool 1",
               "may_contain_adult_content": true,
               "will_expire": "{close_date}",
               "reward_per_assignment": 0.02,
               "assignment_max_duration_seconds": 60,
               "filter": {
                 "and": [
                   {
                     "or": [
                       {
                         "category": "profile",
                         "key": "languages",
                         "operator": "IN",
                         "value": "RU"
                       }
                     ]
                   }
                 ]
               },
               "quality_control": {
                 "captcha_frequency": "LOW",
                 "configs": [
                   {
                     "collector_config": {
                       "type": "CAPTCHA",
                       "parameters": {
                         "history_size": 10
                       }
                     },
                     "rules": [
                       {
                         "conditions": [
                           {
                             "key": "stored_results_count",
                             "operator": "EQ",
                             "value": 10
                           },
                           {
                             "key": "success_rate",
                             "operator": "LTE",
                             "value": 70.0
                           }
                         ],
                         "action": {
                           "type": "RESTRICTION_V2",
                           "parameters": {
                             "scope": "PROJECT",
                             "duration_unit": "DAYS",
                             "duration": 3,
                             "private_comment": "Incorrect captcha input"
                           }
                         }
                       }
                     ]
                   }
                 ]
               },
               "mixer_config": {
                 "real_tasks_count": 3,
                 "golden_tasks_count": 0,
                 "training_tasks_count": 0
               },
               "defaults": {
                 "default_overlap_for_new_task_suites": 3
               }
             }'
    ```

- Postman

    Fill in the fields:

    1. Request URL

        ```bash
        https://sandbox.toloka.dev/api/v1/pools
        ```

    1. Headers

        ```bash
        Authorization: OAuth PlaceYourRealOAuthToken_Here
        Content-Type: application/json
        ```

    1. Body

        ```json
        {
          "project_id": "{project_id}",
          "private_name": "Shoes pool 1",
          "may_contain_adult_content": true,
          "will_expire": "{close_date}",
          "reward_per_assignment": 0.02,
          "assignment_max_duration_seconds": 60,
          "filter": {
            "and": [
              {
                "or": [
                  {
                    "category": "profile",
                    "key": "languages",
                    "operator": "IN",
                    "value": "RU"
                  }
                ]
              }
            ]
          },
          "quality_control": {
            "captcha_frequency": "LOW",
            "configs": [
              {
                "collector_config": {
                  "type": "CAPTCHA",
                  "parameters": {
                    "history_size": 10
                  }
                },
                "rules": [
                  {
                    "conditions": [
                      {
                        "key": "stored_results_count",
                        "operator": "EQ",
                        "value": 10
                      },
                      {
                        "key": "success_rate",
                        "operator": "LTE",
                        "value": 70
                      }
                    ],
                    "action": {
                      "type": "RESTRICTION_V2",
                      "parameters": {
                        "scope": "PROJECT",
                        "duration_unit": "DAYS",
                        "duration": 3,
                        "private_comment": "Incorrect captcha input"
                      }
                    }
                  }
                ]
              }
            ]
          },
          "mixer_config": {
            "real_tasks_count": 3,
            "golden_tasks_count": 0,
            "training_tasks_count": 0
          },
          "defaults": {
            "default_overlap_for_new_task_suites": 3
          }
        }
        ```

{% endlist %}

The example shows the basic parameters that are necessary to create a simple pool. For a more detailed description of all request parameters, see [Create pool](https://toloka.ai/docs/api/api-reference/#post-/pools).

### Response {#pool-response}

In response to the  request, you will receive a JSON object for the created pool. This object contains the pool `id`.

```json
{
  "id": "9876543",
  "project_id": "12345",
  "private_name": "Shoes pool 1",
  ...
}
```

{% note info %}

You'll need the `id` to add tasks to the pool: specify it in the [upload tasks](#task) request.

{% endnote %}

## Upload tasks {#task}

### Request {#tasks-post}

In the given code example, substitute the parameter values:

- In `input_values`, replace `https://example.com/image_1.jpg`–`https://example.com/image_3.jpg` with specific values for the input data set in the project's `input_spec` parameter (in this example, these are paths to the images for labeling; replace the example image links with the real ones).
- In the `pool_id` parameter, replace `{pool_id}` with the ID of the pool to upload the task to (the ID received in response to the add pool request).

Next, send a `POST` [request](https://toloka.ai/docs/api/api-reference/#post-/tasks) to `/api/v1/tasks`:

{% list tabs %}

- cURL

    Send a request from the command line using the cURL utility:

    ```bash
    curl -X POST 'https://sandbox.toloka.dev/api/v1/tasks' \
         -H 'Authorization: OAuth PlaceYourRealOAuthToken_Here' \
         -H 'Content-Type: application/json' \
         -d '[
               {
                 "input_values": {
                   "image": "https://example.com/image_1.jpg"
                 },
                 "pool_id": "{pool_id}",
                 "overlap": 2
               },
               {
                 "input_values": {
                   "image": "https://example.com/image_2.jpg"
                 },
                 "pool_id": "{pool_id}",
                 "overlap": 2
               },
               {
                 "input_values": {
                   "image": "https://example.com/image_3.jpg"
                 },
                 "pool_id": "{pool_id}",
                 "overlap": 2
               }
             ]'
    ```

- Postman

    Fill in the fields:

    1. Request URL

        ```bash
        https://sandbox.toloka.dev/api/v1/tasks
        ```

    1. Headers

        ```bash
        Authorization: OAuth PlaceYourRealOAuthToken_Here
        Content-Type: application/json
        ```

    1. Body

        ```json
        [
          {
            "input_values": {
              "image": "https://example.com/image_1.jpg"
            },
            "pool_id": "{pool_id}",
            "overlap": 2
          },
          {
            "input_values": {
              "image": "https://example.com/image_2.jpg"
            },
            "pool_id": "{pool_id}",
            "overlap": 2
          },
          {
            "input_values": {
              "image": "https://example.com/image_3.jpg"
            },
            "pool_id": "{pool_id}",
            "overlap": 2
          }
        ]
        ```

{% endlist %}

The example shows the basic parameters that are necessary to upload simple tasks. For a more detailed description of each task parameter, see [Create single/multiple tasks](https://toloka.ai/docs/api/api-reference/#post-/tasks).

## Start the pool {#pool-run}

### Before starting the pool {#pool-run-before}

Before you start the pool, go to the [Toloka interface](https://platform.toloka.ai/), select the pool, click **Preview**, and check that the tasks are displayed properly.

### Request {#pool-run-request}

In the `{pool_id}` path parameter, insert the ID of the pool to start (the ID received in response to the [add pool request](#pool)) and use the `POST` [method](https://toloka.ai/docs/api/api-reference/#post-/pools/-id-/open):

{% list tabs %}

- cURL

    Send a request from the command line using the cURL utility:

    ```bash
    curl -X POST 'https://sandbox.toloka.dev/api/v1/pools/{pool_id}/open' \
         -H 'Authorization: OAuth PlaceYourRealOAuthToken_Here' \
         -H 'Content-Type: application/json'
    ```

- Postman

    Fill in the fields:

    1. Request URL

        ```bash
        https://sandbox.toloka.dev/api/v1/pools/:pool_id/open
        ```

    1. Headers

        ```bash
        Authorization: OAuth PlaceYourRealOAuthToken_Here
        Content-Type: application/json
        ```

{% endlist %}

## Check the tasks {#check}

After starting the pool, make sure all the settings are correct and the tasks are displayed properly. To do this, log in to Toloka under the Toloker's username and open the card with the created tasks.

## What's next {#what-next}

Read the [instructions on how to get results](qs-results.md).

## Learn more {#links-qs-placement}

- [HTTP methods for working with projects](https://toloka.ai/docs/api/api-reference/#tag--project)
- [HTTP methods for working with pools](https://toloka.ai/docs/api/api-reference/#tag--pool)
- [HTTP methods for uploading tasks](https://toloka.ai/docs/api/api-reference/#tag--task)

{% include [contact-support](../../guide/_includes/contact-support.md) %}