{% include [image-styles](../../../_includes/image-styles.md) %}

# Monitoring field objects

In this tutorial, you will learn how to run a project to monitor field objects. We will use a project preset designed specifically for this type of data labeling.

Monitoring field objects is intended for field tasks in the Toloka mobile app. The preset is suitable for finding objects in open spaces. A Toloker chooses a point on the map where they should go to check something and take photos.

Use this preset when you need to:

- Monitor equipment quality and condition.

- Check if equipment is installed at a particular address.

{% note info %}

You may need additional projects for your task, such as dataset pre-check or checking Tolokers' responses. Learn more about this in [Decomposition of the task](../concepts/solution-architecture.md).

{% endnote %}

## Prerequisites {#prerequisites}

Before you begin:

- {% include [tutorials-register](../_includes/tutorials/register.md) %}

- {% include [tutorials-top-up-tutorial](../_includes/tutorials/top-up-tutorial.md) %}

## Choose a preset {#preset}

{% include [toloka-requester-source-use-preset](../_includes/toloka-requester-source/id-toloka-requester-source/use-preset.md) %}

1. Follow [this link]({{ monitoring-preset }}), or create a project manually:

    1. {% include [tutorials-create-project-button](../_includes/tutorials/create-project-button.md) %}

        {% include [tutorials-choose-preset-image](../_includes/tutorials/choose-preset-image.md) %}

    1. Select the {% if locale == "en-com" %}**Monitoring field objects**{% endif %} preset.

1. Click {% if locale == "en-com" %}**Choose this preset**{% endif %} in the pop-up tab.

## Create a project {#project}

{% include [tutorials-who-are-tolokers](../_includes/tutorials/who-are-tolokers.md) %}

1. {% include [tutorials-add-name-description](../_includes/tutorials/add-name-description.md) %}

    - {% if locale == "en-com" %}**Name to show performers**{% endif %}: In 2–5 words, state the general idea of the project.

    - {% if locale == "en-com" %}**Description for performers**{% endif %}: In a couple of sentences, explain what you expect Tolokers to do. This is just an overview. You will write instructions later.

    [![Create a project. Step 1](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/monitoring-field-objects/monitoring-field-objects-create-project-step-1.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/monitoring-field-objects/monitoring-field-objects-create-project-step-1.png)

1. In the {% if locale == "en-com" %}**Task interface**{% endif %} section, set up what your tasks will look like.

    {% include [toloka-requester-source-tb-or-html](../_includes/toloka-requester-source/id-toloka-requester-source/tb-or-html.md) %}

    1. Copy the code of the [example](https://tb.yandex.net/editor?config=N4Igxg9gdgZglgcxALhMAOlABF9IBucApgO57JYbY64gAuAngA5Hm2GkB0ANnAM508AGkw1acOkQC2fNgG1RYyoqW1GLNng4lOAQ25EAToJAjqqvJCiTrbKqrF51rFO2I7JADxNmHNS9A2JhR4ALLQEhCGcFAIWPBE3AAmWBAARgBWRGB0siAqSgC+vg5OABbSLiEgMTAQeAU4xY3K5kpOzFVuXF4+LTh43LppiZogACoSBsjC-bRWQXZzA-SdY0m6dLqcMUwArn1tFiBMm2VjULpSLnOFLc1HrX4dGq5a7pxJcIRJRg2PD1U9lKq1e1W0nF6s0eKyGI24YwAgkkkoYiHw+DNTHMAtYiLZXMDnqCungNlsdlB9oc-CtTnRzm8QLoUWiMf8-HcASUxET2iSxhCvj8-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-R1HFhMhSek91gy-wslROiEuFcEBQBHVr9bhOqN67IjUg353pWm9ae0u7TAI2W5AtbtkdvEDYFfXk0PtuP5-JAjkzjtZEBlAfdEWI+cSrJDBdAM2fArggXpUQOswHCswpdzrthSLPyfZAOisYWLCzIBLHiglC6iV7BJVWMlFL3lUtrPWOl1bGXu2ZapXQ-LEgcq5fHvgvLMiT8FbOFyjYXKThFTETg4qq7e4XbK+V1sjVl56xXjnu2BUoOuF8fVhrzq9aCmR0K4vKuS5JjRk+tqJty+m00xELq+GcaB4W6J7R6six7cqSBraVbC5BpgBnShoVaUYnARpVo1pC6M4IbP4v5UZs4ZplINYkJMi5r5ox6rxEbnZlouKPZdDD4xrwowGu4Hzu4RItp1Jn7G5Sym5JJ1TcZmh8BO6baCbsG65VIe6sG14+7VBJIqhgQdSHpAEDJRJQAjxcbWC6AxB3QJRmy1grz56GAfQMKDohRvIoiah1jqHcAlw5xECl7O7wqMGapQYwxbATy15M6E6v4jQ1bprf6YYBBSA8Ya4bb0E2Ksxpx2KcgdxuK4g9pP7M6VRDbv6ja2rKIOpOCRp4CLwtxpE6KwaIH7yaq4FzoEGujsCWIUI2IRFoxEJ4BOIuIDaToygfC8ACA5F+KGan47ZMGiEsGzqG6VSSG0AtJtIgQKEerB5x4oQJ6HqArAp-z0RxAwajIaj6DcCzKRjogLKbqmw-SrJdLZhbIZIkDbFPojIKZlwYiVy2GCHa7CGQYX46rX4GpwBH7nZ9bmr5H4EHzS6f70bo7y43x-5bAAFjGep55zFhwLF8BQFIYwErDBoIFYFdFjGoHxzoFCbuFTaFHeFoZTZ+E1BSB5pLwgocrZHH7l5dGUEVpH4UC0F2FlIOFV49Ge5sFdGDHJJ+4h5uo-ggFW5gEYjrEO6pAzF8k24CkQEJ6PJYDJ4ICp5RBgpYQvELGPx54F6zLVrF68ZQrkkqq3FdEiFcDIq17165j5hN4t74qErEqkpNi97QyeDUqD5LbD6oSj5wysrsqcrSASlz58qenL6r7r6ipb4Sr9HEjskgByoKpH70mBKV4VLapX56rPGvH37bz9afGMbfHDa0a-Gy5hmVTXzOrAllCAFB68kh78klwSkwn0HnYImuJ4koGuB0nonsGYkS5VZmQUgEJ4FZn4nEFLxVlBHMLsFUnUGol0FlIMHxnWjMEskSF75cE8EBF8ECF1l6lIEGk6D66slIERnjD6FHrxAxApCPokBlAfR5KDznHlxgrvKzIsBgAPJXl-gTx8C54aF5L4Zmi1nuadFbn3FT6QjOEwZuGYHxFZnYk9m1Z9k1z4k-mEZC61qhFMxZR1rRHUaxENHIbWjWopGWE5GYwNxNzBqrwlJlZ5FImWpsJFEFlSj4nBweRWLdZVGRFLS1Hojlo4WeFJg8DeJtHqg-YAUs7blhJiF9G74dpjBJJAmuoB5B5LKmzbIkA7qF4QmgoZ5LEPl5Lvm54XkfS3SQDOJJDKGmwTwAFDJ7K+ramxlgyMmIrNE170X8gmnVCN44qt5Wmd42nkqUoOkD60rOkMqulLZj77SL7T7emz7z4ZCRUuQHgb5iqhlSUm7VBRmH5KobkiVfGOEPFJk34vF37sHvFi6QU0UVI-HjZ-FTZFlMhyUAEKXAFerqWGAkn3kQojm2L1lwEhqNmdlZrNm0loHQEYHlbUWiW0U4ns4v7EKlF4CDlkTzEuSLxkWLRtmUkPaVotkjXTlCH6lMnToSVe5CYRnDH+7clPQVl3RVmCmR4imVlinVnx7Px3Yylynp5xCKnZ4Z656ApqlF4l62U3E5VQWHVeJpjGnZgN5mmeWWnt7Wnd62n+WOlBX0oj5hXukT6ekz48p+kX4uQBlr5JUhk76nVLnpUH7bV2XeyzljCJm6qFWpklUP4ZkTW5VyI5kf7VX5n-E-6An-6llNU8ktU3VPWTGQFdVwm0ANk8Uggok7VomjUYkQUeFdm4zTVwVmJc4LWEkkHDk6mgZjlbU0lRpK17WbmTWOVHW9EnXsFnVJKhDvKbBRCrK8HWD8HA3ZX2F01NE20LkuXtppVDFyrcoaEGUURURcYmVmXjzrKWXerWValBEzl3EJkPHQauGB0hgdmzU4Ga2+E62HyrlIXK0s3pkfHs1g2VVc2jYy6TYDX81jBsaQScaIW8ZS0oXKphExbhRsU0A91FAFCD2BhZpxwIB0odHbYapsI2x7AT1xRY0VSDDvSWQWp4CpinljDagegJQTROAWwsaRiEEUDLjziMwAgFB2JhGFCmA1BUgHAoBoDoDRhtCZEF5jDjDOHLG4DoDv10J-0gAnlT6zCv1SgARATWgeXN6ljdKVjViBVNjhVqQ9jFRDhGCjgTgzgLgrhrgbjbi7j7hHgnhngXhXg3h3gPigMFB4CkEex4Bf3eA-1-20PDmAPAPJDUNv0nAehegUJybf3AxjK-1Zq8PQIsNAPspcMNJkwMTCLVAHgHicBbizgHgXjLgMyNhjg7iKNCB7icBjjzjLi47LgXi7jLjLhjjLgNCv232FBAA&locale=en) and paste it to the {% if locale == "en-com" %}**Config**{% endif %} section of your project. This code has validation and task layout pre-configured.

        [![Create a project. Config section](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/monitoring-field-objects/monitoring-field-objects-config-section.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/monitoring-field-objects/monitoring-field-objects-config-section.png)

    1. You can edit the code. For example, to change the description, replace the sample text with your value in the `content` property.

        [![Create a project. Config text](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/monitoring-field-objects/monitoring-field-objects-config-text.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/monitoring-field-objects/monitoring-field-objects-config-text.png)

    1. A Toloker will be able to submit a response when they are within 50 meters of the specified location. To change this condition, replace the value of the `max` property with the desired distance:

        [![Create a project. Config distance](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/monitoring-field-objects/monitoring-field-objects-config-distance.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/monitoring-field-objects/monitoring-field-objects-config-distance.png)

        {% note info %}

        To learn about other properties of the {% if locale == "en-com" %}**Config**{% endif %} section, their possible values and the impact on the task interface, see the [Template Builder Help](../../template-builder/reference/index.md).

        {% endnote %}

    1. {% include [toloka-requester-source-specification-definition](../_includes/toloka-requester-source/id-toloka-requester-source/specification-definition.md) %}

        {% include [toloka-requester-source-click-show-specifications](../_includes/toloka-requester-source/id-toloka-requester-source/click-show-specifications.md) %}

        - {% if locale == "en-com" %}**Input data**{% endif %}: Parameters in the file with raw task data.

        - {% if locale == "en-com" %}**Output data**{% endif %}: Parameters in the file with labeling results.

        {% include [toloka-requester-source-specification-match](../_includes/toloka-requester-source/id-toloka-requester-source/specification-match.md) %}

    1. In the **Settings for displaying field tasks** section, configure the settings which affect the task display on the map.

        - The **Title format** and **Short description format** are used to help a Toloker distinguish one task from another when they select a task on the map. These fields contain links to the input data fields to show the name of the point and its coordinates. You can leave these fields unchanged.

        - The **Map provider for tasks** field sets which map a Toloker will use when performing your tasks.

1. {% include [toloka-requester-source-instructions](../_includes/toloka-requester-source/id-toloka-requester-source/instructions.md) %}

    {% include [toloka-requester-source-instruction-check](../_includes/toloka-requester-source/id-toloka-requester-source/instruction-check.md) %}

    Field task instructions should be easy to read on a mobile phone screen.

    {% include [toloka-requester-source-instruction-note](../_includes/toloka-requester-source/id-toloka-requester-source/instruction-note.md) %}

1. To save your data and continue, click {% if locale == "en-com" %}**Create a project**{% endif %}.

    {% include [tutorials-create-project-image](../_includes/tutorials/create-project-image.md) %}

## Create a pool {#pool}

{% include [toloka-requester-source-what-is-pool](../_includes/toloka-requester-source/id-toloka-requester-source/what-is-pool.md) %}

1. Click {% if locale == "en-com" %}**Create new pool**{% endif %}.

1. Under {% if locale == "en-com" %}**General information**{% endif %}, set the {% if locale == "en-com" %}**Pool name**{% endif %}.

1. {% include [toloka-requester-source-audience-settings](../_includes/toloka-requester-source/id-toloka-requester-source/audience-settings.md) %}

    1. Clear {% if locale == "en-com" %}**My tasks may contain shocking or pornographic content**{% endif %} if your project has none of those.

    1. {% include [toloka-requester-source-filters](../_includes/toloka-requester-source/id-toloka-requester-source/filters.md) %}

        [![Create a pool. Languages filter](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/monitoring-field-objects/monitoring-field-objects-language-filter.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/monitoring-field-objects/monitoring-field-objects-language-filter.png)

    1. Tasks in pools are available in the web version of Toloka and the mobile app by default. Make your tasks available in the mobile app only: add the {% if locale == "en-com" %}**Client**{% endif %} filter and select the {% if locale == "en-com" %}**Toloka for mobile**{% endif %} option.

    1. Use the {% if locale == "en-com" %}**Speed/quality balance**{% endif %} slider to change the number of Tolokers who can see your tasks. Move the slider to the right to exclude Tolokers with lower ratings from participating in your project.

        {% include [tutorials-speed-filter-image](../_includes/tutorials/speed-filter-image.md) %}

1. Under {% if locale == "en-com" %}**Quality control**{% endif %}, set quality control rules for more accurate results.

    1. Click the {% if locale == "en-com" %}**Non-automatic acceptance**{% endif %} toggle, and specify the number of days for checking the task in the {% if locale == "en-com" %}**Review period in days**{% endif %} field (for example, 7).

        {% include [tutorials-na-acceptance](../_includes/tutorials/na-acceptance.md) %}

    1. Click {% if locale == "en-com" %}**Add a quality control rule → Results of assignment review**{% endif %}, and enter the following values:

        [![Create a pool. Results of assignment review rule](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/monitoring-field-objects/monitoring-field-objects-results-rule.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/monitoring-field-objects/monitoring-field-objects-results-rule.png)

        This means that if more than 35% of a Toloker's responses are rejected, the Toloker is banned and can't access your tasks for 15 days. The rule takes effect after 3 responses of the Toloker are reviewed.

    1. Add the {% if locale == "en-com" %}**Processing rejected and accepted assignments**{% endif %} rule.

        [![Create a pool. Processing rejected and accepted assignments rule](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/monitoring-field-objects/monitoring-field-objects-rejected.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/monitoring-field-objects/monitoring-field-objects-rejected.png)

        This means that if you reject assignments during the review, they’ll be sent for re-completion to another Toloker.

1. Click {% if locale == "en-com" %}**Show advanced settings**{% endif %}. In the {% if locale == "en-com" %}**Additional settings**{% endif %}, specify {% if locale == "en-com" %}**Time per task suite, sec**{% endif %}. It should be long enough to get to the place, find the specified point and object, and upload the photos. For field tasks, this time is usually 86,400 seconds (24 hours).

1. {% include [toloka-requester-source-price-settings](../_includes/toloka-requester-source/id-toloka-requester-source/price-settings.md) %}

    1. In {% if locale == "en-com" %}**Price per task suite**{% endif %}, set the amount of money to pay per task suite done by one Toloker. A task suite is a page with a number of tasks.

        For this type of project, a task suite must contain only one task. You will set the number of tasks per suite later in this tutorial.

    1. {% include [toloka-requester-source-overlap-settings](../_includes/toloka-requester-source/id-toloka-requester-source/overlap-settings.md) %}

        For field tasks, it is usually 1. This means that each task will have 1 response.

1. To save the settings and continue, click {% if locale == "en-com" %}**Create pool**{% endif %}.

## Upload data {#upload}

At this step, upload your task data to Toloka.

1. Click {% if locale == "en-com" %}**Upload data**{% endif %}.

1. Create the tasks for Tolokers:

    1. To download a template, click one of the buttons:

        - {% if locale == "en-com" %}**Template in XLSX**{% endif %}

        - {% if locale == "en-com" %}**Template in TSV**{% endif %}

        - {% if locale == "en-com" %}**Template in JSON**{% endif %}

        For this type of project, the file with tasks must contain seven parameters:

        - `INPUT:name`: A string with the task title.

        - `INPUT:image`: A string with the link to the photo of the field object that the Toloker should find.

        - `INPUT:address`: A string with the task address.

        - `INPUT:product`: A string with the field object description.

        - `INPUT:coordinates`: A string with the coordinates of the point that the Toloker should go to.

        - `AI:latitude`, `AI:longitude`: The latitude and longitude from the `INPUT:coordinates` parameter presented separately. The values of `INPUT:coordinates`, `AI:latitude` and `AI:longitude` should have the same accuracy, that is have the same number of digits after the decimal separator.

        ```plaintext
        INPUT:name	INPUT:image	INPUT:address	INPUT:product	INPUT:coordinates	AI:latitude	AI:longitude
        Title-1	https://yastatic.net/s3/toloka/p/toloka-requester-page-project-preview/877a55555a5f199dff16.jpg	Address-1	Object-1	53.947516,27.669428	53.947516	27.669428
        Title-2	https://tlk.s3.yandex.net/dataset/cats_vs_dogs/dogs/048e5760fc5a46faa434922b2447a527.jpg	Address-2	Object-2	53.947517,27.669429	53.947517	27.669429
        Title-3	https://tlk.s3.yandex.net/dataset/cats_vs_dogs/dogs/05334365c060421ab25264166bbb4fd1.jpg	Address-3	Object-3	53.947518,27.669428	53.947518	27.669428
        ```

    1. Open the downloaded file, and replace the sample values with your data. You can use a service like Google Maps to get the coordinates.

    1. Click {% if locale == "en-com" %}**Drop file here or select**{% endif %}, and upload the file you’ve just made.

    1. Click {% if locale == "en-com" %}**Continue**{% endif %}.

1. {% include [toloka-requester-source-task-suits](../_includes/toloka-requester-source/id-toloka-requester-source/task-suits.md) %}

    1. Go to the {% if locale == "en-com" %}**Set manually**{% endif %} tab.

    1. In this type of project, the task suite must contain only one task:

        [![Upload data. Tasks per suite](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/monitoring-field-objects/monitoring-field-objects-number-tasks.png =570x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/monitoring-field-objects/monitoring-field-objects-number-tasks.png)

1. Click {% if locale == "en-com" %}**Combine tasks into suites**{% endif %}.

## Start labeling {#labeling}

1. Make sure you have [topped up your account](../concepts/refill.md).

1. {% include [toloka-requester-source-start-button](../_includes/toloka-requester-source/id-toloka-requester-source/start-button.md) %}

    [![Start labeling](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/monitoring-field-objects/monitoring-field-objects-start-labeling-step-2.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/monitoring-field-objects/monitoring-field-objects-start-labeling-step-2.png)

1. In the pop-up panel, review the budget and click {% if locale == "en-com" %}**Launch**{% endif %}.

## See the results {#results}

Track the labeling progress on the pool page. You can start the review when the first results are received.

After the time period specified in step 4.1 of [creating the pool](#pool), all responses are automatically accepted, regardless of their quality.

1. Go to the pool, and click {% if locale == "en-com" %}**Review assignments**{% endif %}.

    [![See the results. Review assignments](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/monitoring-field-objects/monitoring-field-objects-review-results.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/monitoring-field-objects/monitoring-field-objects-review-results.png)

1. Choose an assignment.

1. Check the responses, and click {% if locale == "en-com" %}**Accept**{% endif %} or {% if locale == "en-com" %}**Decline**{% endif %}. For rejected responses, enter a comment to specify the reason.

    {% note info %}

    To learn about other ways of review, see the [Reviewing Tolokers' responses](../concepts/accept.md) section.

    {% endnote %}

1. After checking all the assignments, click {% if locale == "en-com" %}**Download results**{% endif %}.

    [![See the results. Download results](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/monitoring-field-objects/monitoring-field-objects-results-download.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/monitoring-field-objects/monitoring-field-objects-results-download.png)

    You will get the TSV file with the labeling results.

1. To download the files Tolokers attached to the tasks, click the arrow next to the {% if locale == "en-com" %}**Download results**{% endif %} button. Choose {% if locale == "en-com" %}**Download attachments**{% endif %} from the drop-down menu.

    [![See the results. Download attachments](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/monitoring-field-objects/monitoring-field-objects-results-download-attachments.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/monitoring-field-objects/monitoring-field-objects-results-download-attachments.png)

## Troubleshooting {#troubleshooting}

{% cut "Can I limit the source of the photo to camera-only in a field task so that the Toloker can't upload a photo from anywhere else?" %}

The `accept` property of the `field.media-file` component adds different buttons for four types of uploads. To prohibit using any sources except of the camera, use the `"photo": true` property only, like it is done in the [example](https://tb.yandex.net/editor?config=N4Igxg9gdgZglgcxALhMAOlABF9IBucApgO57JYbY64gAuAngA5Hm2GkB0ANnAM508AGkw1acOkQC2fNgG1RYyoqW1GLNng4lOAQ25EAToJAjqqvJCiTrbKqrF51rFO2I7JADxNmHNS9A2JhR4ALLQEhCGcFAIWPBE3AAmWBAARgBWRGB0siAqSgC+vg5OABbSLiEgMTAQeAU4xY3K5kpOzFVuXF4+LTh43LppiZogACoSBsjC-bRWQXZzA-SdY0m6dLqcMUwArn1tFiBMm2VjULpSLnOFLc1HrX4dGq5a7pxJcIRJRg2PD1U9lKq1e1W0nF6s0eKyGI24YwAgkkkoYiHw+DNTHMAtYiLZXMDnqCungNlsdlB9oc-CtTnRzm8QLoUWiMf8-HcASUxET2iSxhCvj8-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-R1HFhMhSek91gy-wslROiEuFcEBQBHVr9bhOqN67IjUg353pWm9ae0u7TAI2W5AtbtkdvEDYFfXk0PtuP5-JAjkzjtZEBlAfdEWI+cSrJDBdAM2fArggXpUQOswHCswpdzrthSLPyfZAOisYWLCzIBLHiglC6iV7BJVWMlFL3lUtrPWOl1bGXu2ZapXQ-LEgcq5fHvgvLMiT8FbOFyjYXKThFTETg4qq7e4XbK+V1sjVl56xXjnu2BUoOuF8fVhrzq9aCmR0K4vKuS5JjRk+tqJty+m00xELq+GcaB4W6J7R6six7cqSBraVbC5BpgBnShoVaUYnARpVo1pC6M4IbP4v5UZs4ZplINYkJMi5r5ox6rxEbnZlouKPZdDD4xrwowGu4Hzu4RItp1Jn7G5Sym5JJ1TcZmh8BO6baCbsG65VIe6sG14+7VBJIqhgQdSHpAEDJRJQAjxcbWC6AxB3QJRmy1grz56GAfQMKDohRvIoiah1jqHcAlw5xECl7O7wqMGapQYwxbATy15M6E6v4jQ1bprf6YYBBSA8Ya4bb0E2Ksxpx2KcgdxuK4g9pP7M6VRDbv6ja2rKIOpOCRp4CLwtxpE6KwaIH7yaq4FzoEGujsCWIUI2IRFoxEJ4BOIuIDaToygfC8ACA5F+KGan47ZMGiEsGzqG6VSSG0AtJtIgQKEerB5x4oQJ6HqArAp-z0RxAwajIaj6DcCzKRjogLKbqmw-SrJdLZhbIZIkDbFPojIKZlwYiVy2GCHa7CGQYX46rX4GpwBH7nZ9bmr5H4EHzS6f70bo7y43x-5bAAFjGep55zFhwLF8BQFIYwErDBoIFYFdFjGoHxzoFCbuFTaFHeFoZTZ+E1BSB5pLwgocrZHH7l5dGUEVpH4UC0F2FlIOFV49Ge5sFdGDHJJ+4h5uo-ggFW5gEYjrEO6pAzF8k24CkQEJ6PJYDJ4ICp5RBgpYQvELGPx54F6zLVrF68ZQrkkqq3FdEiFcDIq17165j5hN4t74qErEqkpNi97QyeDUqD5LbD6oSj5wysrsqcrSASlz58qenL6r7r6ipb4Sr9HEjskgByoKpH70mBKV4VLapX56rPGvH37bz9afGMbfHDa0a-Gy5hmVTXzOrAllCAFB68kh78klwSkwn0HnYImuJ4koGuB0nonsGYkS5VZmQUgEJ4FZn4nEFLxVlBHMLsFUnUGol0FlIMHxnWjMEskSF75cE8EBF8ECF1l6lIEGk6D66slIERnjD6FHrxAxApCPokBlAfR5KDznHlxgrvKzIsBgAPJXl-gTx8C54aF5L4Zmi1nuadFbn3FT6QjOEwZuGYHxFZnYk9m1Z9k1z4k-mEZC61qhFMxZR1rRHUaxENHIbWjWopGWE5GYwNxNzBqrwlJlZ5FImWpsJFEFlSj4nBweRWLdZVGRFLS1Hojlo4WeFJg8DeJtHqg-YAUs7blhJiF9G74dpjBJJAmuoB5B5LKmzbIkA7qF4QmgoZ5LEPl5Lvm54XkfS3SQDOJJDKGmwTwAFDJ7K+ramxlgyMmIrNE170X8gmnVCN44qt5Wmd42nkqUoOkD60rOkMqulLZj77SL7T7emz7z4ZCRUuQHgb5iqhlSUm7VBRmH5KobkiVfGOEPFJk34vF37sHvFi6QU0UVI-HjZ-FTZFlMhyUAEKXAFerqWGAkn3kQojm2L1lwEhqNmdlZrNm0loHQEYHlbUWiW0U4ns4v7EKlF4CDlkTzEuSLxkWLRtmUkPaVotkjXTlCH6lMnToSVe5CYRnDH+7clPQVl3RVmCmR4imVlinVnx7Px3Yylynp5xCKnZ4Z656ApqlF4l62U3E5VQWHVeJpjGnZgN5mmeWWnt7Wnd62n+WOlBX0oj5hXukT6ekz48p+kX4uQBlr5JUhk76nVLnpUH7bV2XeyzljCJm6qFWpklUP4ZkTW5VyI5kf7VX5n-E-6An-6llNU8ktU3VPWTGQFdVwm0ANk8Uggok7VomjUYkQUeFdm4zTVwVmJc4LWEkkHDk6mgZjlbU0lRpK17WbmTWOVHW9EnXsFnVJKhDvKbBRCrK8HWD8HA3ZX2F01NE20LkuXtppVDFyrcoaEGUURURcYmVmXjzrKWXerWValBEzl3EJkPHQauGB0hgdmzU4Ga2+E62HyrlIXK0s3pkfHs1g2VVc2jYy6TYDX81jBsaQScaIW8ZS0oXKphExbhRsU0A91FAFCD2BhZpxwIB0odHbYapsI2x7AT1xRY0VSDDvSWQWp4CpinljDagegJQTROAWwsaRiEEUDLjziMwAgFB2JhGFCmA1BUgHAoBoDoDRhtCZEF5jDjDOHLG4DoDv10J-0gAnlT6zCv1SgARATWgeXN6ljdKVjViBVNjhVqQ9jFRDhGCjgTgzgLgrhrgbjbi7j7hHgnhngXhXg3h3gPigMFB4CkEex4Bf3eA-1-20PDmAPAPJDUNv0nAehegUJybf3AxjK-1Zq8PQIsNAPspcMNJkwMTCLVAHgHicBbizgHgXjLgMyNhjg7iKNCB7icBjjzjLi47LgXi7jLjLhjjLgNCv232FBAA&locale=en).

If you allow Tolokers to use the mobile device gallery, you can prohibit adding images without geotags to limit uploading photos taken from the Internet. To do that, specify the `"requiredCoordinates": true` property.

To learn more about setting up the `field.media-file` component, see the [Template Builder Help](../../template-builder/reference/field.media-file.md).

{% endcut %}

{% cut "How do I check the task display in the mobile Toloka app?" %}

To check the task's look-and-feel on the mobile phone screen, you can use the following buttons:

- **Preview task** on the project settings page.

- **Preview** on the pool settings page.

You can also use the mobile version of the sandbox. [Write to support](../troubleshooting/support.md#support-work-toloka) to get access to it.

{% endcut %}

## See also {#seealso}

- [Instructions](https://toloka.ai/knowledgebase/instruction/)
- [Quality control](https://toloka.ai/knowledgebase/quality-control/)
- [Pricing](https://toloka.ai/knowledgebase/pricing/)
- [Toloka-Kit — spatial crowdsourcing example](https://github.com/Toloka/toloka-kit/blob/main/examples/2.spatial_crowdsourcing/0.simplest_example/spatial_crowdsourcing.ipynb)

{% include [contact-support](../_includes/contact-support-help.md) %}