# Iterating results

It might happen, that you have rather a big number of items in a single batch or in all the batches. If the number of items exceeds 1000, you will not be able to get all the items due to the limits.

In this case, you will need to iterate through the items and get the results splitting them in smaller sets.

{% note tip %}

Getting the items from all the batches is similar to getting them from a single batch. In the scope of this tutorial, we will try and get the items from a single batch (specifying it by ID). You can either iterate through the batches, or remove the batch ID from the request query parameters to get the items from all the batches at once.

{% endnote %}

## Step 1: Get first item

First, you need to get an item to start with. To do this, you must know the IDs of the project and batch containing the items. We also `sort` the returned items by their IDs and `limit` the request to exactly one item.

{% list tabs %}

- cURL

  ```bash
  curl -X GET 'https://toloka.dev/api/app/v0/app-projects/8lvN9kBN4wwsj47ZqNal/items?batch_id=7d0YYJ2Av5OhnLVwAygZ&sort=id&limit=1' \
      -H 'Authorization: OAuth PlaceYourRealOAuthToken_Here'
  ```

  The response prints the details of the first item which include the item ID, input and output data.

  ```json
  {
    "content": [
      {
        "app_project_id": "8lvN9kBN4wwsj47ZqNal",
        "batch_id": "7d0YYJ2Av5OhnLVwAygZ",
        "created_at": "2022-01-22T07:44:57.035",
        "errors": [],
        "id": "QPVvLYdlRPBH9pl7KzBV",
        "input_data": {
          "id": "1",
          "text": "Kate likes dogs."
        },
        "output_data": {
          "confidence": 0.9998542274,
          "result": [
            "OK"
          ],
          "text": "Kate likes dogs."
        },
        "status": "NEW"
      }
    ],
    "has_more": true
  }
  ```

- Toloka-Kit

  ```python
  # Connect Toloka-Kit library to your Python script
  import toloka.client as toloka

  # Instantiate the TolokaClient class object
  toloka_client = toloka.TolokaClient('PlaceYourRealOAuthToken_Here', 'PRODUCTION')

  # Get the first item in the batch
  items = toloka_client.find_app_items(
      app_project_id='8lvN9kBN4wwsj47ZqNal',
      batch_id='7d0YYJ2Av5OhnLVwAygZ',
      sort=['id'],
      limit=1
  )

  print(items.content[0].id)
  print(items.content[0].input_data)
  print(items.content[0].output_data)
  ```

  The response prints the details of the first item which include the item ID, input and output data.

  ```bash
  QPVvLYdlRPBH9pl7KzBV
  {'id': '1', 'text': 'Kate likes dogs.'}
  {'text': 'Kate likes dogs.', 'result': ['OK'], 'confidence': '0.9998542274'}
  ```

{% endlist %}

In the requests above:

Parameter | Description
--------- | -----------
`app_project_id` | The ID of the project we want to get the items from.
`batch_id` | The ID of the batch we limit our requests to.
`sort` | The sorting direction (`id`) which allows us to get the ID of the first item.
`limit` | The number of items in the response. For the first request we limit it to `1`.

Note the `has_more` attribute in the response to the cURL request. It means that there are more items in this project batch, we will learn how to get them at the next step.

## Step 2: Get next items

Now that we have the ID of the first item in the selected batch, we can use it to iterate through the next items using the `after_id` query parameter in the request. We set this parameter equal to the ID of the first item and then the IDs of the consequent items to get the next ones.

In cURL requests, we must manually iterate through the items, while in Toloka-Kit we can cycle through them until we get the last result.

{% list tabs %}

- cURL

  ```bash
  curl -X GET 'https://toloka.dev/api/app/v0/app-projects/8lvN9kBN4wwsj47ZqNal/items?batch_id=7d0YYJ2Av5OhnLVwAygZ&sort=id&limit=1&after_id=QPVvLYdlRPBH9pl7KzBV' \
       -H 'Authorization: OAuth PlaceYourRealOAuthToken_Here'
  ```

  The response prints the details of the second item which include the item ID, input and output data.

  ```json
  {
    "content": [
      {
        "app_project_id": "8lvN9kBN4wwsj47ZqNal",
        "batch_id": "7d0YYJ2Av5OhnLVwAygZ",
        "created_at": "2022-01-22T07:44:57.035",
        "errors": [],
        "id": "Vnj0LMw4Rn5Hkev3Y4aD",
        "input_data": {
          "id": "4",
          "text": "Pete likes cats."
        },
        "output_data": {
          "confidence": 0.9993645425,
          "result": [
            "OK"
          ],
          "text": "Pete likes cats."
        },
        "status": "NEW"
      }
    ],
    "has_more": true
  }
  ```

- Toloka-Kit

  ```python
  # The ID of the first item is used to start the iteration
  last_id = items.content[0].id

  # While the 'has_more' parameter in the response is equal to `True`,
  # we iterate through the items in the batch
  while items.has_more:
      items = toloka_client.find_app_items(
          app_project_id='8lvN9kBN4wwsj47ZqNal',
          batch_id='7d0YYJ2Av5OhnLVwAygZ',
          sort=['id'],
          limit=10,
          after_id=last_id
      )

      # As we set the limit to '10', we need to additionally iterate
      # through the items in the returned set of items
      for i in range(0,len(items.content)):
          print(items.content[i].id)
          print(items.content[i].input_data)
          print(items.content[i].output_data)

      # Now we use the ID of the last item in the set for the next iteration
      last_id = items.content[-1].id

  # When 'has_more' is finally equal to 'False', no more items are left
  print('No more items in batch')
  ```

  The response prints the details of the second and subsequent items which include the item IDs, input and output data.

  ```bash
  Vnj0LMw4Rn5Hkev3Y4aD
  {'id': '4', 'text': 'Pete likes cats.'}
  {'text': 'Pete likes cats.', 'result': ['OK'], 'confidence': '0.9993645425'}
  ...
  zNkQE9y1ANzTdVQp3JwY
  {'id': '12024', 'text': 'Mary likes dogs.'}
  {'text': 'Mary likes dogs.', 'result': ['OK'], 'confidence': '0.9874202523'}
  No more items in batch
  ```

{% endlist %}

In the requests above:

Parameter | Description
--------- | -----------
`app_project_id` | The ID of the project we want to get the items from.
`batch_id` | The ID of the batch we limit our requests to.
`sort` | The sorting direction (`id`) which allows us to get the item IDs in the descending alphanumerical order.
`limit` | The number of items in the response. For the second and subsequent requests we limit it to `100`–`1000`.
`after_id` | The ID of the item after which we start the next set of items.

{% cut "Toloka-Kit complete code" %}

```python
# Connect Toloka-Kit library to your Python script
import toloka.client as toloka

# Instantiate the TolokaClient class object
toloka_client = toloka.TolokaClient('PlaceYourRealOAuthToken_Here', 'PRODUCTION')

# Get the first item in the batch
items = toloka_client.find_app_items(
    app_project_id='8lvN9kBN4wwsj47ZqNal',
    batch_id='7d0YYJ2Av5OhnLVwAygZ',
    sort=['id'],
    limit=1
)

print(items.content[0].id)
print(items.content[0].input_data)
print(items.content[0].output_data)

# The ID of the first item is used to start the iteration
last_id = items.content[0].id

# While the 'has_more' parameter in the response is equal to `True`,
# we iterate through the items in the batch
while items.has_more:
    items = toloka_client.find_app_items(
        app_project_id='8lvN9kBN4wwsj47ZqNal',
        batch_id='7d0YYJ2Av5OhnLVwAygZ',
        sort=['id'],
        limit=10,
        after_id=last_id
    )

    # As we set the limit to '10', we need to additionally iterate
    # through the items in the returned set of items
    for i in range(0,len(items.content)):
        print(items.content[i].id)
        print(items.content[i].input_data)
        print(items.content[i].output_data)

    # Now we use the ID of the last item in the set for the next iteration
    last_id = items.content[-1].id

# When 'has_more' is finally equal to 'False', no more items are left
print('No more items in batch')
```

{% endcut %}

## See also

- [Apps API reference: Get project items](https://toloka.ai/docs/api/apps-reference/#get-/app-projects/-app_project_id-/items)
- [Toloka-Kit reference: find_app_items() method](../../../toloka-kit/reference/toloka.client.TolokaClient.find_app_items.md)

{% include [contact-support](../../_includes/contact-support.md) %}
