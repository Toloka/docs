# Uploading dataset

An effective model produces good resulting quality. You need a dataset with the texts you want to label. It's great if you can provide a labeled dataset, but it's also okay if you label your dataset in {{ llm-name }}.

This dataset will serve as a reference to measure the quality of the labels a combination of a model and a prompt provides. You will use it to iterate through the variants to produce a variant of higher quality than you already have at hand. The platform provides you with a good default, but you can find the variant that will be even better.

{% cut "Dataset file sample" %}

{% list tabs %}

- CSV

  ```plaintext
  Text,Label
  "Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",opinion
  "Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.",fact
  ```

- JSON

  ```json
  [
    {
      "Text":"Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.",
      "Label":"opinion"
    },
    {
      "Text": "Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat.",
      "Label": "fact"
    }
  ]
  ```

{% endlist %}

{% endcut %}

To upload and label your dataset file:

1. Click **![Upload dataset](_images/upload-dataset.svg) Upload dataset**.

1. Choose and open the file in either CSV or JSON format that contains your dataset.

    The dataset rows will be displayed in the **Match data columns to input texts and labels** area.

1. Visually verify that it contains the data you want to use, then specify two columns:

    - Input (the required column), contains texts to label and is displayed under **Text to label**.

    - Label (the optional column), contains a class for each text and is displayed under **Label (ground truth)**.

    {% note info %}

    If your dataset file doesn't contain labels, they will not be displayed (the **Label (ground truth)** drop-down menu will only contain the **None** option). In this case, you can [add the classes](classes.md) together with their descriptions later and label your dataset using them.

    {% endnote %}

    If your dataset file contains labels, check that the **Text to label** values match the **Label (ground truth)**, or correct them if not, using the drop-down menu.

When done, click **Save dataset**.

{{ llm-name }} will calculate all quality metrics by comparing the model's output to the labels you provide.

## Trying unlabeled data {#unlabeled-data}

You can run a model and see its output without labels. You can also [deploy a variant](deploy.md) without quality measurements if you wish so.

It's possible to use {{ llm-name }} without labeled data providing only texts for labeling. Note, that the tool provides the best value when there is a labeled dataset which serves as a ground truth in quality measurement.

To run a resulting model without labels, [add a prompt](prompt.md) and click **![Deploy](_images/deploy.svg) Deploy**.

## Next steps {#next-steps}

- [Describe your task](task-description.md)