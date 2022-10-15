{% include [image-styles](../../_includes/image-styles.md) %}

# Visual editor

For some Toloka presets, Template builder allows you to edit its template using a visual editor. It might be useful, if you do not know anything about JSON formatting or usage and you do not feel experienced enough for the code editor, and want to start working with Template Builder right away.

Currently, presets with the visual editor include:

- [Image classification](https://platform.toloka.ai/requester/new/project?templateId=image_classification)
- [Hand gesture classification](https://platform.toloka.ai/requester/new/project?templateId=videoModeration)
- [Clickbait or not?](https://platform.toloka.ai/requester/new/project?templateId=checkbox_dynamic)
- [Object recognition & detection](https://platform.toloka.ai/requester/new/project?templateId=polygon)
- [Product search relevance](https://platform.toloka.ai/requester/new/project?templateId=categorize)

When you choose to create a project that supports configuring the task interface through the visual editor, it will be opened by default.

The interface of the visual editor looks like this:

<a target="_blank" href="https://yastatic.net/s3/doc-binary/src/toloka/en/template-builder/visual-editor.png"><img src="https://yastatic.net/s3/doc-binary/src/toloka/en/template-builder/visual-editor.png" alt="Visual editor interface" style="box-shadow: 1px 1px 15px rgba(30,33,38,.12);border-radius:6px;cursor:zoom-in;width:700px;" /></a>

1. Switch between the visual editor and code editor using the buttons in the upper part of Template Builder.

1. To modify the template, use the **Config** section:

    - **Question performers will see in your task** displays the main question that you want Tolokers to answer. It is displayed right below the image.

    - The **Paste link to a sample image** field contains the link to some [web storage](https://toloka.ai/docs/guide/concepts/cloud-storage.html) where you uploaded your image. Make sure the link is publicly accessible, otherwise Tolokers will not see it.

    - The **Set answer options** section contains the possible responses to the question which you ask Tolokers. By default, it has a specific number of options (two to five), but you can add or remove as many as you need using the **Add answer option** button.

    - Enable **Add the Other option** so that Tolokers can choose **Other** if none of the answer options fits.

    - Use **Error answer** for Tolokers to choose **Failed to load** if they have technical issues (for example, the image or video didn't load).

    {% note info %}

    The fields in the **Config** section can differ depending on the template parameters. Follow the links in the list above to view the presets which support the visual editor and their available configuration settings.

    {% endnote %}

1. After you enter all the values, choose one of the options in **Preview** and click **Submit** to try and send the task data.

1. You will see the result in the **Submitted data** panel. Click **Reset** to clear the sent data and start anew.

## See also {#what-next}

- [Your first project](https://toloka.ai/docs/guide/concepts/first-project.html)
- [Image classification preset](templates/image-classification.md)
- [Hand gesture classification preset](templates/video-moderation.md)
- [Object recognition & detection preset](templates/object-recognition.md)
- [Product search relevance](templates/product-search-relevance.md)

{% include [contact-support](_includes/contact-support.md) %}
