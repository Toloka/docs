# get_requester
`toloka.async_client.client.AsyncTolokaClient.get_requester` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.0/src/async_client/client.py#L0)

```python
async get_requester(self)
```

Reads information about the customer and the account balance


* **Returns:**

  Object that contains all information about customer.

* **Return type:**

  [Requester](toloka.client.requester.Requester.md)

**Examples:**

Make sure that you've entered a valid OAuth token.

```python
toloka_client.get_requester()
```

You can also estimate approximate pipeline costs and check if there is enough money on your account.

```python
requester = toloka_client.get_requester()
if requester.balance >= approx_pipeline_price:
    print('You have enough money on your account!')
else:
    print("You haven't got enough money on your account!")
```
