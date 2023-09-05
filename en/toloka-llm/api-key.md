# Adding OpenAI API key or bank card

We provide you with a free $5 credit, so you can try the service and play with it. This will be enough to run tests, but to deploy variants you need to provide your OpenAI API key.

## OpenAI API key {#openai-key}

If you already have an OpenAI account, you can enter the OpenAI API key and continue labeling with your OpenAI account.

To do that,

1. Enter the OpenAI API key into the field.

    {% cut "Where to get your OpenAI API key?" %}

    1. [Sign in](https://openai.com/) to the OpenAI website and visit the [API keys](https://platform.openai.com/account/api-keys) page.

        If you already have an API key, you must have it saved somewhere as you won't be able to copy it from that page.

    1. To generate a new key, click **+ Create new secret key**. Set the key name and copy it to the clipboard.

    1. Now you can enter it into the {{ llm-name }} **OpenAI API key** field.

    Refer to [this page](https://platform.openai.com/docs/api-reference/authentication) for more information about authentication in OpenAI.

    {% endcut %}

1. Click **Add my key**.

You will be redirected to the {{ llm-name }} **Endpoint** page where you can [upload the dataset](deploy.md#real-data) with real data and label it.