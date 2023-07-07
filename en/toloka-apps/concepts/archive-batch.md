# Archiving batches

You can [archive](#archive-batch) the batch with the data to hide it. The data will not be deleted or lost in this case. To restore it later, [unarchive](#unarchive-batch) the previously archived batch.

## Archiving batches {#archive-batch}

{% note info %}

You can archive only batches which are currently in statuses other than **Processing**.

{% endnote %}

{% list tabs %}

- From a project

  1. Open the project.
  1. Click the ![Archive batch](../_images/archive-batch-list.svg) icon at the bespoke project page next to the batch name.

- From a batch

  1. Open the project.
  1. Go to the desired batch.
  1. Click the **![Archive batch](../_images/archive-batch.svg) Archive results** button in the upper-right part of the batch page.

- Using the apps API

  Send the following `POST` request:

  ```bash
  curl -X POST 'https://toloka.dev/api/app/v0/app-projects/{project_id}/batches/{batch_id}/archive' \
       -H 'Authorization: OAuth PlaceYourRealOAuthToken_Here'
  ```

  Where `{project_id}` is the ID of the project with which the batch is associated, and `{batch_id}` is the ID of the batch you want to archive.

  {% note tip "Visit apps API reference" %}

  Refer to the [Archive batch](https://toloka.ai/docs/api/apps-reference/#post-/app-projects/-app_project_id-/batches/-batch_id-/archive) section of the apps API documentation for more details about the request, its parameters, and possible responses. You will find examples of the requests for [Toloka-Kit](../../toloka-kit/index.md) and other code samples there.

  {% endnote %}

{% endlist %}

After this, both the uploaded items and the batch itself get the **Archived** status.

The only action available for the archived batches in the interface is to [download the results](download-results.md).

## Unarchiving batches {#unarchive-batch}

You can't restore archived data using the platform interface. Use the apps API instead.

Send the following `POST` request:

```bash
curl -X POST 'https://toloka.dev/api/app/v0/app-projects/{project_id}/batches/{batch_id}/unarchive' \
     -H 'Authorization: OAuth PlaceYourRealOAuthToken_Here'
```

Where `{project_id}` is the ID of the project with which the batch is associated, and `{batch_id}` is the ID of the batch you want to unarchive.

{% note tip "Visit apps API reference" %}

Refer to the [Unarchive batch](https://toloka.ai/docs/api/apps-reference/#post-/app-projects/-app_project_id-/batches/-batch_id-/unarchive) section of the apps API documentation for more details about the request, its parameters, and possible responses. You will find examples of the requests for [Toloka-Kit](../../toloka-kit/index.md) and other code samples there.

{% endnote %}

After the operation, the batch gets the status it had before archiving. You can continue interacting with it.

{% include [contact-support](../_includes/contact-support.md) %}