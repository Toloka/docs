# Troubleshooting

[Ready-to-go](#app-projects)

[Labeling results](#results)

[Uploading data for labeling](#add-items)

## Ready-to-go {#app-projects}

I didn't find a suitable ready-to-go solution
: If you can't find a solution that fits your goals, [contact us](https://toloka.ai/docs/guide/troubleshooting/support.html#troubleshooting__new_1).

## Labeling results {#results}

Why can't I download the results?
: The **Download results** button is only available for batches with the **Completed** status. Wait until the labeling is completed and return to the batch after a while.

How do I find out how long it took to label my data?
: Select the desired batch. The section on the right will show all available statistics.

## Uploading data for labeling {#add-items}

What should I add to a batch?
: Batches are datasets that need to be labeled. Add to batches TSV files with IDs and links to media files.

  Example of filling in a TSV file:

  ```
  id  image_url
  1   https://yastat.net/s3/tb/static/file-examples/special/street.jpg
  ```

My project is being moderated. Can I add work items to it?
: Yes. You can add work items to projects in the **Active** or **Pending** status.

{% include [contact-support](_includes/contact-support.md) %}