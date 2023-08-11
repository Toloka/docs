# Using classes

The model uses the classes you provide for labeling the texts present in your [dataset file](dataset.md).

## Adding classes and their descriptions

You must specify **at least two classes**.

If you don't have the classes in your dataset file, add them:

1. Click the **+ Add classes** button in the **Dataset** area.

1. The **Describe classes for your task** popup will open. Enter the following data:

    - **Name** is the class name that will be used for [prompt generation](prompt.md) and for [labeling](deploy.md). Names should be unique and it also helps if they are short.

    - **Description** is the class description that will be used for prompt generation. The description is an optional field, but it greatly helps the model better understand the context and the task and leads to better labeling results. We recommend that you to provide it for each class.

1. Click **+ Add** to add more classes or ![Delete class](_images/delete.svg) to remove the class from the list and discard it.

1. Click **Save classes** to add the classes to your project.

You will see the classes in the **Settings** area.

## Labeling data with classes {#label-classes}

After you have classes (either in your dataset file or adding them manually), you can label several items with them.

To do that:

1. Click **Label** in the **Dataset** area.

1. The **Label sample data with your classes** popup will open. It will contain the texts with all the classes next to them. The automatically matched classes will be highlighted.

1. Check the highlighted class next to the text:

    - Click another class if that one better matches it than automatically matched.

    - Leave the highlighted class it the platform choice is good.

1. When you check all the sample texts and classes this way, click **Label**.

You will see the results in the **Dataset** area.

## Next steps {#next-steps}

- [Generate and tailor the prompt](prompt.md)