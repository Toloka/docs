# Uploading task items

You can add data to a bespoke project with the **Active** or **Pending** status.

## Creating a new batch {#new-batch}

1. Open the project.
1. Click **Create batch**.
1. Enter a unique name for the batch.
1. On the batch page, download the template in a supported format: XLSX, TSV, CSV, JSON.
1. In the template, replace the data with your own.
1. Upload using one of the methods:

    - Select the finished file.
    - Copy and paste data from the file.
    - API.

1. Click **Create batch**.

Your batches are completed in order of labeling queue. If you batches with same queue, first will be labeled the smallest one (Queue 5). To complete the batch faster, select a higher queue from the drop-down menu.

## Adding items to an existing batch {#edit}

1. Open the project and go to the appropriate batch.
1. Click **Add items** on the right.
1. On the batch page, download the template in a supported format: XLSX, TSV, CSV, JSON.
1. In the template, replace the data with your own.
1. Upload using one of the methods:

    - Select the finished file.
    - Copy and paste data from the file.
    - API.
    
Your batches are completed in order of labeling queue. If you batches with same queue, first will be labeled the smallest one (Queue 5). To complete the batch faster, select a higher queue from the drop-down menu.

## Renaming an existing batch {#rename}

1. Open the project and go to the appropriate batch.

1. Next to the batch name, click ![Rename](../_images/edit.svg).

1. Enter a new batch name and click **Save**.

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