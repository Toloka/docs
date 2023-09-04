# Creating endpoint

You can deploy the project right after you create it and generate variants.

{% note info %}

We provide you with a free $5 credit, so you can try the service and play with it. This will be enough to run tests, but to deploy variants you need to provide your [OpenAI API key](api-key.md).

{% endnote %}

When you have a variant with the accuracy to price ratio that fits your purpose, deploy the project and use it with real datasets.

For that, click **![Deploy](_images/deploy.svg) Deploy** on the [variant card](variants.md).

- If haven't added OpenAI API key, you will [have to do this](api-key.md). After that, you will be redirected to the **Endpoint** tab where you can test the model on [real data](#real-data).

The currently deployed variant will be available at the **Endpoint** tab.

## Using labeling API {#real-data}

Now you can upload real data and label it. To do that, use the API code samples (cURL, Python, or JSON) and include them into your application or send cURL requests.

Click ![Copy text](_images/copy-blue.svg) to copy **Link for this project** and **Toloka API key**. You will need the data to access your endpoint via API.

Use the link to the project as the request path and the API key as a part of the `Authorization: Bearer` request header. Include the input data into the request body payload.

**cURL API request sample**

```bash
curl -X POST 'https://link-to-your-endpoint/' \
     -d '{"inputs":"The text for the input. Replace it with your own data."}' \
     -H 'Authorization: Bearer PlaceYourRealApiKey_Here'
```

You can [view the labeling statistics](#statistics) and costs.

Alternatively, you can enter the text example into the **Try out variant** field and click **Run example text**. The input data will be displayed in the **Input text** area and the resulting output will appear in the **Output** area.

## Viewing labeling statistics {#statistics}

The labeling costs of the deployed variant are displayed in the **Approximate total spent** area and the number of labeled items in the **Labeled items** area. The costs calculations are approximate, you can view the exact data in the OpenAI usage dashboard.

## Switching among variants {#switch-variants}

To switch among the deployed variants:

1. Stop the current endpoint using the **![Pause](_images/pause.svg) Pause endpoint** button in the **Endpoint for variant** area.

1. Choose another variant from the drop-down list. If you have only one variant, the drop-down list will be disabled.

1. Click **![Activate](_images/reload.svg) Activate endpoint** to replace the current variant with the chosen one.

The link to the endpoint will be no longer active, you will need to replace it in your API requests. The endpoint history of labeling and statistics will also be lost.