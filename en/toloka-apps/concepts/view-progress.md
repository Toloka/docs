# Starting and stopping labeling

## Start labeling {#start-batch}

You can start labeling after uploading task items to a project's batch.

The following project statuses are supported:

- **Pending** — Created, under moderation.
- **Active** — Verified, can be used.
- **Rejected** — [Errors found](quickstart.md#errors).
- **Archived** — Archived.

{% note info %}

Once created, a project needs to pass moderation. It may take up to two hours.

{% endnote %}

To send a batch of data for labeling:

1. Wait until the project status changes to **Active**.
1. Click **Launch**.

## Stop labeling {#stop-batch}

You can stop labeling if it isn't completed.

{% list tabs %}

- From a project

  1. Open the project.
  1. Click ![Pause](../_images/batch-pause.svg) on the right, next to the batch name.

- From a batch

  1. Open the project.
  1. Go to the desired batch.
  1. Click **Pause labeling**.

- Using the apps API

  Send the following `POST` request:

  ```bash
  curl -X POST 'https://toloka.dev/api/app/v0/app-projects/{project_id}/batches/{batch_id}/stop' \
       -H 'Authorization: OAuth PlaceYourRealOAuthToken_Here'
  ```

  Where `{project_id}` is the ID of the project with which the batch is associated, and `{batch_id}` is the ID of the batch you want to pause.

  {% note tip "Visit apps API reference" %}

  Refer to the [Stop batch processing](https://toloka.ai/docs/api/apps-reference/#post-/app-projects/-app_project_id-/batches/-batch_id-/stop) section of the apps API documentation for more details about the request, its parameters, and possible responses. You will find examples of the requests for [Toloka-Kit](../../toloka-kit/index.md) and other code samples there.

  {% endnote %}

{% endlist %}

{% note info %}

Task items in the **Processing** status will continue to be labeled and you'll be charged for them. These tasks are already reserved for performers and are being executed, so it isn't possible to stop their labeling.

{% endnote %}

{% include [contact-support](../_includes/contact-support.md) %}