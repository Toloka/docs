# Getting started

{% include [index-abstract-quickstart](_includes/index/id-index/abstract-quickstart.md) %}

## Choose a ready-to-go solution {#choose-app-project}

1. Open the [page](https://toloka.yandex.com/requester/templates) with examples of tasks that are available in Toloka.
1. Choose a solution that fits your task.

## Fill out a form {#set-application}

Once you choose a ready-to-go solution, you need to fill out a form. In the form, you'll be requested any information that is necessary to create a project: its name, instructions, sample tasks, and so on.

It will take about 30 minutes to fill out the form. To make sure you get good results, fill out the application form carefully.

Once you fill out the form, you'll see your project on the **Ready-to-go** tab in the **Pending** status. You don't have to wait until it's moderated and can immediately start uploading task items.

{% cut "Task items" %}

A task item is a labeling unit – in other words, data uploaded to a batch. The batch consists of task items, and the project consists of batches.

{% endcut %}

## Upload task items {#new-batch}

{% note info %}

Before uploading work items to a batch, you need to upload them to photo hosting or cloud storage. Learn more in the [Where to store data](cloud-storage.md) section.

{% endnote %}

Your items are uploaded to a batch. A batch is a set of data for labeling that you'll assign to performers at a time. You'll get labeling results separately for each batch, too.

1. Select your project on the **Ready-to-go** tab.

1. Click **Create batch**.

1. Enter a name for the batch.

1. Upload work items in one of the following ways:

    - Upload a ready-made TSV file.

    - Enter the data in text format.

      Each line with data is a work item. You can later view each item's status.

1. Click **Create batch** again. Done! You created a batch.

## Send the data for labeling {#section_fr2_gfv_wqb}

1. Wait until the project passes moderation: its status will change to **Active**.
1. Send the batch for labeling by clicking **Launch**.

## Are there any errors? {#errors}

If there are errors in the project, its status changes to **Rejected**. No worries:

1. Go to the rejected project.
1. Click **Show errors**. Read the error description.
1. Click **Clone project** to create a duplicate for editing and fix the errors in it.

{% note tip %}

If you need help with setting up your project, [contact us](https://toloka.ai/docs/guide/troubleshooting/support.html#troubleshooting__new_1).

{% endnote %}

## What's next {#whats-next}

[Download the labeling results](download-results.md).

[Upload more items to the batch or create a new one](add-task.md#edit).

## Troubleshooting {#troubleshooting}

{% cut "I didn't find a suitable ready-to-go solution" %}

If you can't find a solution that fits your goals, [contact us](https://toloka.ai/docs/guide/troubleshooting/support.html#troubleshooting__new_1).

{% endcut %}

{% include [contact-support](_includes/contact-support.md) %}