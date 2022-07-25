# Uploading task items

You can add data to a bespoke project with the **Active** or **Pending** status.

## Creating a new batch {#new-batch}

1. Open the project.
1. Click **Create batch**.
1. Enter a unique name for the batch.
1. Add task items in one of the following ways:

    - Upload a ready-made TSV file.
    - Enter the data in text format.

1. Click **Create batch**.

## Adding items to an existing batch {#edit}

1. Open the project and go to the appropriate batch.
1. Click **Add items** on the right.
1. Add task items in one of the following ways:

    - Upload a ready-made TSV file.
    - Enter the data in text format.

## What's next {#whats-next}

Wait until the labeling is done and [download the results](download-results.md).

## Troubleshooting {#troubleshooting}

{% cut "What should I add to a batch?" %}

Batches are datasets that need to be labeled. Add to batches TSV files with IDs and links to media files.

Example of filling in a TSV file:

```
id  image_url
1   https://yastat.net/s3/tb/static/file-examples/special/street.jpg
```

{% endcut %}

{% cut "My project is being moderated. Can I add task items to it?" %}

Yes. You can add task items to projects in the **Active** or **Pending** status.

{% endcut %}

{% include [contact-support](../_includes/contact-support.md) %}