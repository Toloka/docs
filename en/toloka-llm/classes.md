# Using classes

The model uses the classes you provide for labeling the texts present in your [dataset file](dataset.md).

If you don't have the classes in your dataset file, [add them](#add-classes). You must specify **at least two classes**.

## Adding classes and their descriptions {#add-classes}

1. Click the **+ Add classes** button in the **Settings** area.

1. The **Describe at least 2 classes for your task** popup will open. Enter the following data:

    - **Name** is the class name that will be used for [prompt generation](prompt.md) and for [labeling](deploy.md). Names should be unique and it also helps if they are short (ideally — one token).

    - **Description** is the class description that will be used for prompt generation. The description is an optional field, but it greatly helps the model better understand the context and the task and leads to better labeling results. We recommend that you to provide it for each class.

1. Click **+ Add** to add more classes or ![Delete class](_images/delete.svg) to remove the class from the list and discard it.

1. Click **Save classes** to add the classes to your project.

You will see the classes in the **Settings** area.

## Editing existing classes {#edit-classes}

To edit the classes present in the [dataset file](dataset.md) or [added manually](#add-classes), click the ![Edit classes](_images/edit-blue.svg) icon next to the **Classes** field in the **Settings** area. Then follow the steps in the [Adding classes and their descriptions](#add-classes) section to edit or delete classes and their descriptions.

## Next steps {#next-steps}

- [Label data with classes](label.md)
- [Describe your task](task-description.md)