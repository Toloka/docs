# Adding OpenAI API key or bank card

We provide you with a free $5 credit, so you can try the service and play with it. Once you use it, you either need to provide us with an [OpenAI API key](#openai-key) or [top up your balance](#bank-card).

## OpenAI API key {#openai-key}

If you already have an OpenAI account, you can enter the OpenAI API key and continue labeling with your OpenAI account.

To do that,

1. Choose **OpenAI API key**.

1. Enter the OpenAI API key into the field.

    {% cut "Where to get your OpenAI API key?" %}

    1. [Sign in](https://openai.com/) to the OpenAI website and visit the [API keys](https://platform.openai.com/account/api-keys) page.

        If you already have an API key, you must have it saved somewhere as you won't be able to copy it from that page.

    1. To generate a new key, click **+ Create new secret key**. Set the key name and copy it to the clipboard.

    1. Now you can enter it into the {{ llm-name }} **OpenAI API key** field.

    Refer to [this page](https://platform.openai.com/docs/api-reference/authentication) for more information about authentication in OpenAI.

    {% endcut %}

1. Click **Add my key**.

You will be redirected to the {{ llm-name }} **Deployment** page where you can [upload the dataset](deploy.md#real-data) with real data and label it.

## Bank card {#bank-card}

If you don't have an OpenAI account and you don't want to or don't have a possibility to register it, you can top up your account in {{ llm-name }} and it will do all the rest for you.

To top up your account, add a bank card.

1. Choose **Credit/Debit card**.

1. Enter the amount of money in U.S. dollars you want to top up your account and click **Continue**.

1. Provide the billing information at the next step (first and last names, email address, postal code, and other details), click **Register**.

1. Enter the bank card details (card number, expiry date, CVC, and country) and click **Submit**.

If everything is okay, your account will be topped up for the amount you entered and you will be redirected to the {{ llm-name }} **Deployment** page where you can [upload the dataset](deploy.md#real-data) with real data and label it.

## Next steps {#next-steps}

- [Upload real data to label](deploy.md#real-data)