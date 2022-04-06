# Starting and stopping labeling

## Start labeling {#start-batch}

You can start labeling after uploading work items to a project's batch.

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

#### From a project

1. Open the project.
1. Click ![Pause](../_images/batch-pause.svg) on the right, next to the project name.

#### From a batch

1. Open the project.
1. Go to the desired batch.
1. Click **Pause labeling**.

{% note info %}

Work items in the **Processing** status will continue to be labeled and you'll be charged for them. These tasks are already reserved for performers and are being executed, so it isn't possible to stop their labeling.

{% endnote %}

{% include [contact-support](_includes/contact-support.md) %}