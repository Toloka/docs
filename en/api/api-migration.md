# API migration

The Toloka API is migrating to the `toloka.dev` domain. Access to the Toloka API is about to change. The current API domain (`toloka.yandex.com`) works in deprecated mode and will be disabled **since March 1, 2023**. You need to update your applications to use the new domain.

{% note alert %}

If you do not change the domain, your requests to the Toloka API will end up with errors starting March 1, 2023.

{% endnote %}

{% cut "I'm currently using the Toloka API directly. How do I change the requests?" %}

You need to change the URL to which you send the requests. Replace the `toloka.yandex.com` domain part in the URL with `toloka.dev`. All the other request parameters remain unchanged.

For example, a cURL request to the Toloka API which gets the requester information should look like this:

```bash
curl -X GET 'https://toloka.dev/api/v1/requester' \
     -H 'Authorization: OAuth AQC2AGAJgyNSA8CtpdO9MWy_QEB6s6kDjHUoElE'
```

{% endcut %}

{% cut "I use Toloka-Kit. Do I have to do anything?" %}

If you are a user of Toloka-Kit version 1.0.0 and later, you are good to go, no need to do anything.

If your Toloka-Kit version is older than 1.0.0, please update it. You can do this with the help of the following command:

```bash
pip install toloka-kit --upgrade
```

Your Toloka-Kit library version will be updated to the latest version together with all the dependencies it requires.

Refer to our [GitHub repository](https://github.com/Toloka/toloka-kit/releases) for the list of available releases.

{% endcut %}

{% cut "I use Toloka Java SDK. Do I have to do anything?" %}

If you are a user of Toloka Java SDK version 0.0.6 and later, you are good to go, no need to do anything.

If your Toloka Java SDK version is older than 0.0.6, please rebuild your Java application using the latest available Toloka Java SDK version.

Go to the [Toloka Java SDK page](https://mvnrepository.com/artifact/ai.toloka/toloka-java-sdk) at the MVN repository and click the latest SDK version number.

![Toloka Java SDK version](./_images/mvnrepository.png =700x)

Then select your Java project type and copy the connection string.

![Toloka Java SDK connection string](./_images/copy-string.png =700x)

If you already use Toloka Java SDK, in most cases you will only need to change the version number.

Refer to our [GitHub repository](https://github.com/Toloka/toloka-java-sdk/releases) for the list of available releases.

{% endcut %}

{% cut "Do I have to reissue my API token to get access to the API when I change the URL or update my app to the latest version?" %}

You don't need to reissue API tokens — they will continue to work. Once you use the new domain to connect to the API (or upgrade your Toloka-Kit or Toloka Java SDK version), you can continue where you left off. You'll still have access to all your projects, pools, and settings.

{% endcut %}

{% cut "I have a question not answered here. Where can I ask it?" %}

If you can't find an answer to your question here, feel free to [contact Toloka Customer Care team](../guide/troubleshooting/support.md).

{% endcut %}