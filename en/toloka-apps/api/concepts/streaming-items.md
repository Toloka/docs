# Stream processing of task items

For projects with a constant stream of new tasks that don't need to be grouped into batches, task items can be uploaded in streaming mode. They will be processed immediately after uploading.

This mode is suitable, for example, for moderation tasks.

## Add a task item {#create-item}

### HTTP request {#create-item-request}

```http
POST /app-projects/{app_project_id}/items/bulk
Host: https://toloka.dev
Authorization: OAuth <OAuth token>
```

### Path parameters {#create-item-path-params}

#|
||**Parameter**|**Overview**||
||**app_project_id**|**string**

Project ID.||
|#

### Request body {#create-item-body}

```json
{
   "items":[
      {
         "id": "1",
         "image_url": "https://tlk.s3.yandex.net/dataset/cats_vs_dogs/dogs/048e5760fc5a46faa434922b2447a527.jpg"
      }
   ]
}
```

#|
||**Key**|**Overview**||
||**items**|**array of objects**

Array of task items according to the `input_spec` value of the solution.

You can upload an array from a single task item or from several task items within a single request.||
|#

### Response {#create-item-response}

Contains an array of IDs assigned to created task items.

## Check the status of task items {#get-result}

{% note info %}

When you upload items without a batch, processing starts immediately. You can learn about the completion of processing from each item's [status](quickstart-api.md#quickstart-api__check-items).

{% endnote %}

To get the results, request the list of task items sorted by processing completion time.

After the request is completed, find the last labeled item with the latest `finished_at` value. Use its ID as `last_saved_item_id` in the next request.

### HTTP request {#get-result-request}

```http
GET /app-projects/{app_project_id}/items?sort=finished&after_id={last_saved_item_id}
Host: https://toloka.dev
Authorization: OAuth <OAuth token>
```

### Path parameters {#get-result-path-params}

#|
||**Parameter**|**Overview**||
||**app_project_id**|**string**

Project ID.||
||**last_saved_item_id**|**string**

ID of the item used to request more recent results.||
|#

### Response {#get-result-response}

Contains already processed task items.

```json
200 OK

{
    "content": [
        {
            "id": "QlvdZj5d53QHj5Nvx9Vd",
            "app_project_id": "6Vv8kdlrjLYu7ZgPdezj",
            "status": "COMPLETED",
            "input_data": {
                "id": "1",
                "text": "Kate likes dogs."
            },
            "output_data": {
                "text": "Kate likes dogs.",
                "result": [
                    "OK"
                ],
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
            "status": "COMPLETED",
            "input_data": {
                "id": "2",
                "text": "I don’t like hooney."
            },
            "output_data": {
                "text": "I don’t like hooney.",
                "result": [
                    "BAD"
                ],
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