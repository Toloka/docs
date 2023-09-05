# Labeling data with classes manually

After you [have classes](classes.md) (either in your dataset file or adding them manually), you can label several items with them.

To do that:

1. Click **+ Label dataset with classes** in the **Dataset** area.

1. The **Set classes for texts** popup will open. It will contain the texts with all the classes next to them. The automatically matched classes will be highlighted.

1. Check the highlighted class next to the text:

    - Click another class if that one better matches it than automatically matched.

    - Leave the highlighted class it the platform choice is good.

    The **Distribution of classes** area shows the ratio between the classes assigned to the texts. If you see that some of the classes have a very small percentage, it might be a sign that you need to add more text examples for this class for better model results.

1. When you check all the sample texts and classes this way, click **Save**.

You will see the results in the **Dataset** area.

If you want to re-label the dataset, click **![Edit labeling](_images/edit-blue.svg) Edit labeling** in the dataset table heading.

{{ llm-name }} will re-calculate all quality metrics by comparing the model's output to the labels you provide.

## Next steps {#next-steps}

- [Describe your task](task-description.md)