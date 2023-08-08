# API quick start

## Choose a solution

Request a list of solutions and choose the one that fits your goals.

In this example, we'll run the **Text Classification** solution.

First, get the list of the available solutions to find the ID of the **Text Classification** solution.

```bash
curl -X GET 'https://toloka.dev/api/app/v0/apps' \
     -H 'Authorization: ApiKey PlaceYourRealApiKey_Here'
```

{% cut "Response" %}

```json
200 OK

{
  "content": [
    {
      "id": "qQAbNn1RPP5CyJRj5995",
      "name": "Image Classification",
      "image": "https://labs-images-testing.s3.yandex.net/large/4-NEW-img-classification.png",
      "description": "This solution helps you classify images. For example, you can divide them into categories or evaluate their quality.",
      "examples": [
        {
          "name": "Was the driver wearing a seatbelt?"
        },
        {
          "name": "Is there any illegal content/porn/profanity in the picture?"
        }
      ],
      "default_item_price": 0.07
    },
    {
      "id": "2eN4l59qL2xHB5b8Jqp6",
      "name": "Text Classification",
      "image": "https://labs-images-testing.s3.yandex.net/large/1-NEW-text-classification.png",
      "description": "This solution helps you classify texts. For example, you can divide reviews into categories or evaluate their grammatical correctness.",
      "examples": [
        {
          "name": "Evaluate the sentiment of a review"
        },
        {
          "name": "Select a category for an ad"
        }
      ],
      "default_item_price": 0.07
    }
  ],
  "has_more": false
}
```

{% endcut %}

## Get information about the solution

Request information about the solution to check the spec parameters and input data.

For example, to view the **Text Classification** solution specs, specify its `id` in the request: `2eN4l59qL2xHB5b8Jqp6`.

```bash
curl -X GET 'https://toloka.dev/api/app/v0/apps/2eN4l59qL2xHB5b8Jqp6' \
     -H 'Authorization: ApiKey PlaceYourRealApiKey_Here'
```

{% cut "Response" %}

```json
200 OK

{
  "id": "2eN4l59qL2xHB5b8Jqp6",
  "name": "Text Classification",
  "image": "https://labs-images-testing.s3.yandex.net/large/1-NEW-text-classification.png",
  "description": "This solution helps you classify texts. For example, you can divide reviews into categories or evaluate their grammatical correctness.",
  "param_spec": {
    "fields": {
      "type": "object",
      "required": [
        "default_language",
        "name",
        "option_multiple_choice",
        "option_other",
        "instruction_classes",
        "instruction_examples",
        "instruction_intro"
      ],
      "properties": {
        "name": {
          "type": "string"
        },
        "option_other": {
          "type": "boolean"
        },
        "default_language": {
          "type": "string"
        },
        "instruction_intro": {
          "type": "string"
        },
        "instruction_classes": {
          "type": "array",
          "items": {
            "type": "object",
            "required": ["label", "value", "description"],
            "properties": {
              "label": {
                "type": "string"
              },
              "value": {
                "type": "string"
              },
              "description": {
                "type": "string"
              }
            }
          }
        },
        "instruction_examples": {
          "type": "array",
          "items": {
            "type": "object",
            "required": ["text", "label", "description"],
            "properties": {
              "text": {
                "type": "string"
              },
              "label": {
                "type": "string"
              },
              "description": {
                "type": "string"
              }
            }
          }
        },
        "option_multiple_choice": {
          "type": "boolean"
        }
      }
    }
  },
  "input_spec": {
    "id": {
      "type": "string",
      "required": false
    },
    "text": {
      "type": "string",
      "required": true
    }
  },
  "output_spec": {
    "result": {
      "type": "array_string",
      "required": true
    },
    "confidence": {
      "type": "float",
      "required": false
    }
  },
  "examples": [
    {
      "name": "Evaluate the sentiment of a review"
    },
    {
      "name": "Select a category for an ad"
    }
  ],
  "constraints_description": "For tasks with a single response, you can specify up to 12 classes, and for tasks with multiple responses, up to 8. The data file size must be 7 MB max.",
  "input_format_info": {
    "input_fields": [
      {
        "name": "text",
        "description": "Text"
      },
      {
        "name": "id",
        "description": "Optional identificator"
      }
    ],
    "format_description": "Prepare data in TSV-file: Single file for all your data"
  },
  "default_item_price": 0.07
}
```

{% endcut %}

## Create a project

Create an object named `parameters`. It should match the JSON schema in the solution's `param_spec`.

```bash
curl -X POST 'https://toloka.dev/api/app/v0/app-projects' \
     -H 'Authorization: ApiKey PlaceYourRealApiKey_Here' \
     -H 'Content-Type: application/json' \
     -d '{
           "app_id": "2eN4l59qL2xHB5b8Jqp6",
           "name": "Text Classification",
           "parameters": {
             "name": "Text Classification",
             "instruction_classes": [
               {
                 "label": "Correct",
                 "value": "OK",
                 "description": "There are no errors in the text"
               },
               {
                 "label": "Mistake",
                 "value": "BAD",
                 "description": "There are errors in the text"
               }
             ],
             "instruction_examples": [
               {
                 "text": "It’s raining.",
                 "label": "Correct",
                 "description": "There are no errors in the text"
               },
               {
                 "text": "There is my hause.",
                 "label": "Mistake",
                 "description": "There are errors in the text"
               }
             ],
             "default_language": "en",
             "option_other": false,
             "option_multiple_choice": false,
             "instruction_intro": "Are there any errors in the text"
           }
         }'
```

{% cut "Response" %}

```json
200 OK

{
  "id": "6Vv8kdlrjLYu7ZgPdezj",
  "app_id": "2eN4l59qL2xHB5b8Jqp6",
  "parent_app_project_id": "",
  "status": "CREATING",
  "created": "2021-10-03T09:19:44.378888",
  "name": "Text Classification",
  "parameters": {
    "name": "Text Classification",
    "option_other": false,
    "default_language": "en",
    "instruction_intro": "Are there any errors in the text",
    "instruction_classes": [
      {
        "label": "Correct",
        "value": "OK",
        "description": "There are no errors in the text"
      },
      {
        "label": "Mistake",
        "value": "BAD",
        "description": "There are errors in the text"
      }
    ],
    "instruction_examples": [
      {
        "text": "It’s raining.",
        "label": "Correct",
        "description": "There are no errors in the text"
      },
      {
        "text": "There is my hause.",
        "label": "Mistake",
        "description": "There are errors in the text"
      }
    ],
    "option_multiple_choice": false
  },
  "errors": [],
  "item_price": 0.0700,
  "read_only": false
}
```

{% endcut %}

Now you have the `app_project_id` of your project. In this case, it's `6Vv8kdlrjLYu7ZgPdezj`.

The project gets the `CREATING` status. You don't have to wait until it's moderated and can immediately start uploading task items.

## Create a batch for labeling

Let's create a batch and upload task items to it. We'll use the schema from the project template. It's specified in the `input_spec` parameter. In this case, it's `id` and `text`.

```bash
curl -X POST 'https://toloka.dev/api/app/v0/app-projects/6Vv8kdlrjLYu7ZgPdezj/batches' \
     -H 'Authorization: ApiKey PlaceYourRealApiKey_Here' \
     -H 'Content-Type: application/json' \
     -d '{
           "items": [
             {
               "id": "1",
               "text": "Kate likes dogs."
             },
             {
               "id": "2",
               "text": "I don’t like honey."
             }
           ]
         }'
```

{% cut "Response" %}

```json
200 OK

{
  "id": "z1Qy7aryrj9har9yKdY0",
  "app_project_id": "6Vv8kdlrjLYu7ZgPdezj",
  "status": "NEW",
  "name": "",
  "items_count": 2,
  "item_price": 0.0700,
  "cost": 0.1400,
  "created_at": "2021-10-03T09:49:14.028",
  "read_only": false
}
```

{% endcut %}

## Wait for the READY status

At this stage, you need to wait until the project's status changes to `READY`.

To find out the status of the project, use the request:

```bash
curl -X GET 'https://toloka.dev/api/app/v0/app-projects/6Vv8kdlrjLYu7ZgPdezj' \
     -H 'Authorization: ApiKey PlaceYourRealApiKey_Here'
```

## Start processing the batch

```bash
curl -X POST 'https://toloka.dev/api/app/v0/app-projects/6Vv8kdlrjLYu7ZgPdezj/batches/z1Qy7aryrj9har9yKdY0/start' \
     -H 'Authorization: ApiKey PlaceYourRealApiKey_Here'
```

## Check the status of the project's task items

Check the status of the task items from time to time:

- `NEW`: A new object.
- `PROCESSING`: The object is being processed.
- `COMPLETED`: Object processing is complete.

The expected status is `COMPLETED`.

```bash
curl -X GET 'https://toloka.dev/api/app/v0/app-projects/6Vv8kdlrjLYu7ZgPdezj/items?batch_id=z1Qy7aryrj9har9yKdY0' \
     -H 'Authorization: ApiKey PlaceYourRealApiKey_Here'
```

{% cut "Response" %}

```json
200 OK

{
  "content": [
    {
      "id": "QlvdZj5d53QHj5Nvx9Vd",
      "app_project_id": "6Vv8kdlrjLYu7ZgPdezj",
      "batch_id": "z1Qy7aryrj9har9yKdY0",
      "status": "COMPLETED",
      "input_data": {
        "id": "1",
        "text": "Kate likes dogs."
      },
      "output_data": {
        "text": "Kate likes dogs.",
        "result": ["OK"],
        "confidence": 0.9998542274
      },
      "errors": [],
      "created_at": "2021-10-03T09:49:14.028",
      "started_at": "2021-10-03T10:10:27.561182",
      "finished_at": "2021-10-03T11:24:46.818213"
    },
    {
      "id": "nbeya74y4PpU1NkbaxA4",
      "app_project_id": "6Vv8kdlrjLYu7ZgPdezj",
      "batch_id": "z1Qy7aryrj9har9yKdY0",
      "status": "COMPLETED",
      "input_data": {
        "id": "2",
        "text": "I don’t like honey."
      },
      "output_data": {
        "text": "I don’t like honey.",
        "result": ["BAD"],
        "confidence": 0.9998542274
      },
      "errors": [],
      "created_at": "2021-10-03T09:49:14.028",
      "started_at": "2021-10-03T10:10:27.561182",
      "finished_at": "2021-10-03T11:24:47.704265"
    }
  ],
  "has_more": false
}
```

{% endcut %}

### Parameters

#|
||**Parameter**|**Overview**||
||**app_project_id**|**string**

Project ID.||
||**batch_id**|**string**

Batch ID.||
|#

{% include [contact-support](../../_includes/contact-support.md) %}