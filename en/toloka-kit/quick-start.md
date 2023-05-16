# Quick start

To start with Toloka-Kit:

1. Install the Toloka-Kit package:

    ```shell
    $ pip install toloka-kit
    $ pip install pandas
    ```

1. Check access to the API with the following Python script.

    ```python
    import toloka.client as toloka

    target = 'SANDBOX'      # Send requests to the Sandbox
    # target = 'PRODUCTION' # Uncomment to send requests to the production version

    toloka_client = toloka.TolokaClient(input("Enter your token:"), target)
    print(toloka_client.get_requester())
    ```

    The script:

    - Imports the package.
    - Asks to enter the [OAuth token](./registration.md#oauth-token).
    - Requests general information about your account.

    The response to the above request should look like this:

    ```bash
    Requester(_unexpected={}, id='6c6c50dce62ca4aef87dfcbc6e9de162', balance=Decimal('1.0000'), public_name={'EN': 'John Smith'}, company=None)
    ```

## What's next {#what-next}

- Complete one of the [tutorials](../guide/tutorials/usecases.md) to get acquainted with Toloka web interface.

- Create your [first project](./recipes/learn-basics.md) using Toloka-Kit.

- Try [Toloka-Kit usage examples](./recipes/use-cases.md).

- Read the package reference starting with [TolokaClient](reference/toloka.client.TolokaClient.md).

- Study [Toloka API documentation](../api/index.md).

- See other features in [Toloka documentation](../guide/concepts/overview.md).

- Contribute to [Toloka-Kit on GitHub](https://github.com/Toloka/toloka-kit): open pull requests, report bugs or share your [usage examples](https://github.com/Toloka/toloka-kit/tree/main/examples#need-more-examples).
