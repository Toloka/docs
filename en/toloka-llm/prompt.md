# Generating and editing prompt

A good prompt provides the context to the model to enable the best judgement from it. It puts all the context parts into a single place. Task description, class names and descriptions, dataset items, and other data can be used to build a good prompt.

{{ llm-name }} splits the provided dataset into two parts:

- Measure quality — Items labeled by a model for quality measurement.
- Prompt examples — Items that will be used as few shots to show a model what you want it to do.

Providing few-shot examples significantly improves the result quality. At the same time, to get a representative measurement {{ llm-name }} doesn't include examples into a dataset used to measure quality on.

## Customizing the prompt

You can use variables to customize your prompt. Variables allow you to include data from your dataset file into the prompt. They will update together with the dataset file and will not have to change the prompt manually.

The variables include:

- `{task}` — The [description](task-description.md) of the task you provided.
- `{class.name}`, `{class.description}` — The details of the classes you [created](classes.md) or uploaded in the dataset file.
- `{text}` — The text item from the uploaded [dataset file](dataset.md).

Additionally, you can include some tags into your prompt (like, `<text></text>` or `<example1></example1>`) to further structure the prompt for the model.

## Available models

You can use the following models to generate prompts:

- GPT 3.5
- GPT 4

To change the model used, click the **Prompt powered by** drop-down list and choose the model for your prompt.

## Next steps {#next-steps}

- [Run tests and get variants](variants.md)