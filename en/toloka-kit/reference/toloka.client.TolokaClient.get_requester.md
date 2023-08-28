# get_requester
`toloka.client.TolokaClient.get_requester` | [Source code](https://github.com/Toloka/toloka-kit/blob/v1.2.1/src/client/__init__.py#L3418)

```python
get_requester(self)
```

Gets information about the requester and the account balance.


* **Returns:**

  Information about the requester's account.

* **Return type:**

  [Requester](toloka.client.requester.Requester.md)

**Examples:**


```python
requester = toloka_client.get_requester()
print(requester.public_name, requester.balance)
```
