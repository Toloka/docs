# Describing task

After you upload a dataset and match the fields, describe the task you want to complete.

Describing your task is an optional step that helps the model understand the context of the task you have. When you provide this information, it improves the quality of the labels.

We recommend that you think of the task description as if you want to continue the phrase "Here is the business context for classification problem we need to solve:".

{% note tip "Example of a task description" %}

_We need to classify support requests in our ridesharing service into informational ones and all the rest. We will respond to informational ones automatically and redirect the rest to our support specialists._

Here you inform the language model, that:

- You have a ridesharing service.
- The text excerpts are support requests.
- The model must divide all the requests in two types: informational and others.
- You are going to have automatic responses to the informational requests.
- Our support specialists will handle the rest of the requests.

The model now has the context which helps understand what exactly you expect it to do.

{% endnote %}

Enter your task description into the **Settings → Task** field. The better you describe the task, the more context the model will get and the better the result will be.

## Next steps {#next-steps}

- [Add classes and their descriptions](classes.md)