# Data collection: Organizations

In this tutorial, you will learn how to run a project to monitor items at businesses. We will use a project preset designed specifically for this type of data labeling.

Monitoring items at businesses is intended for field tasks in the Toloka mobile app. The preset is suitable for finding objects indoors, for example, checking whether an organization has certain facilities. A Toloker chooses a point on the map where they should go to check something and take photos.

{% note info %}

You may need additional projects for your task, such as dataset pre-check or checking Tolokers' responses. Learn more about this in [Decomposition of the task](../concepts/solution-architecture.md).

{% endnote %}

## Prerequisites {#prerequisites}

Before you begin:

- {% include [tutorials-register](../_includes/tutorials/register.md) %}

- {% include [tutorials-top-up-tutorial](../_includes/tutorials/top-up-tutorial.md) %}

## Choose a preset {#preset}

{% include [toloka-requester-source-use-preset](../_includes/toloka-requester-source/id-toloka-requester-source/use-preset.md) %}

1. Follow [this link]({{ monitoring-in-org-preset }}), or create a project manually:

    1. {% include [tutorials-create-project-button](../_includes/tutorials/create-project-button.md) %}

        {% include [tutorials-choose-preset-image](../_includes/tutorials/choose-preset-image.md) %}

    1. Select the **Monitoring items at businesses** preset.

1. Click  in the pop-up tab.

## Create a project {#project}

{% include [tutorials-who-are-tolokers](../_includes/tutorials/who-are-tolokers.md) %}

1. {% include [tutorials-add-name-description](../_includes/tutorials/add-name-description.md) %}

    - **Name to show Tolokers**: In 2–5 words, state the general idea of the project.

    - **Description for Tolokers**: In a couple of sentences, explain what you expect Tolokers to do. This is just an overview. You will write instructions later.

    [![Create a project. Step 1](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/monitoring/monitoring-create-project-step-1.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/monitoring/monitoring-create-project-step-1.png)

1. In the **Task interface** section, set up what your tasks will look like.

    {% include [toloka-requester-source-tb-or-html](../_includes/toloka-requester-source/id-toloka-requester-source/tb-or-html.md) %}

    1. Copy the code of the [example](https://tb.toloka.dev/editor?config=N4Igxg9gdgZglgcxALhMAOlABF9IBucApgO57JYbY64gAuAngA5Hm2GkB0ANnAM508AGkw1acOkQC2fNgG1RYyoqW1GLNng4lOAQ25EAToJAjqqvJCiTrbKqrF51rFO2I7JADxNmHNS9A2JhR4ALLQEhCGcFAIWBLSfFi6dFgARgCufDFEfHy5eCpKAL6+Dk4AFtIuISAxMBCF5jSlRTj25fTMNW5cXj5t-iDcumlE3JogAMIQUky6UAxYULpSRMjCgzgB1kS2rh1+Tt2TACYpupwxTBkDzRYg83QVkytrTX7Fg633yr-bXQ0ri07k4pzghFORg+JTKYkOSmOQNq2k4-U2-1oIzGE2BIAAgqdToZcnwNqYtrQrEE7JSAc4zhcrlAbnc-ACni88boiSS8jDVF9fj9VAjHICeiCuODIdCQN84TQxUMGXjUeiKZi8NjxpMAJKSKRYKF8MDRJh0ODQcmK8XUvbBP7stQnPHnOiXa63DHOvCcyZMQwQU4ZMAmSlCwW2p2dVUo0EyuBQwwClrR5X013xri8KAAax9nQyhlxtQqdDoTDJAHpqwxdAIUnAwJwoEQ6NW+ABmat0CDcCB53TVpjVkkARwyuUkhmrugAbPOACwATgATAAGACMAA5dFuuxvTgB2Ltd4+nACsx90x53x5Xx43MHP884ACsmAhCw97ftagAMjEeZYH2WCBsGoapHAUi6AgLgKoMGYusivQ6LoYZWlAAC0mQVtAP6IsMoy6niADKFS6CSWAMBAxZYJAUTgiskiyJqRwgBhloEQcdIoZKnGYdAnD5Gy7J+roDADjytKYuKca0AAAvWUBQp42F9gOQ7Vu6lwDmATY8XxIriSAumyc6maoXgumcHRlbeuxlkSc8kwkFEeZGAA+oxhjMSkBTynJWCRg4JkPPg+hJoZUAWaZCk7OC3FQHo3C4tGdrQElWFsRQCjBe0fHyVmVJZRIWGcBOGRwCSpyEb6IAVDEjp4FMvBgCBYF8JR1G0fRvn+ax9WmeZvEFURCVmUy9mssNDX+ni7mGJ5hg+RATExAFbFFS0O3heyyEPJNykLGpGn9oOw5WNlwngo2UBgC4GWdE1-60H1yTUX2EBYDAVHJCQkm-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-npkJuql-EZtqpbqZibofLwBZrouHhHm1k7u-Fap-N-Nbu7s1A6k6h5hDoOu3ifnyATilAXgzt2qHmEtZrTFHuXjHimv3omgnrQUXsnslhmjtt9jmllgWrAUQGfF5HwaSEIWWhQUVtWmXtGtnH3oztXoRrXpkvXq-pgcUmUpDrPpesWGbOarEG0rfhYVXhQUPjYR2qPvYTrniFPj7u3mJugiQFUF9M7KnJehUiEuvGMHXCjvoNwJeg9iBjjjctBHQEfivM+pvLkcOs3PwFgCSOkUsP3PeicoHpVpYX4RrGbsQRblbmZrbs1gPt9pNAwSlC7iweIXgB7rQF7lwc4U9q4YYO4cxPmvUTIa-qIfbqZNwcTNHuYbHq-vFkMY-mmhNkwjseodnroTMTliPJpjhq-sYaXj0BXj4fflYZtidrYUERgSESukUjMFIGsNYF4bgY0YoTXrOiPgukXg4SABMoYEsGBPAEnPZFgNEdCT5u+IesvNvB3HEE8ggBCHAs7JUVctgDEJXO7D8akOBg0JvOjOpkQFgqkNAAcnwGJgwHXIDHwFANHKkFCLwLNl-PBrUQiW8okfkPBknFct7FADBnThcRQgCUns0YQWiOjB6JUYDjZPId0YPhrOmpNmnulrZrMKSQYXVlpj0jVjhsZMwlou1jossTZi-EYhVF1twBYj0r1q8APOskNtsXGm1tqQcT6Y8BnnLN4pwtKYKEtuNEErkFWraUdhCjmIBkNntq4IkjTPgUCW2i8aCQVuCautMqsV5i4ZkJbrMRvIvhhODNEScrvhhhvokXSukNDvsukZkSaDkXesnI+h8iWK+hUiQE3AUZUWlNUZUsnAHt4Q0b4YCaqgqebqQe0RQeZnbonikvQQ6YwZOMwbqY1Owa5pwS6gWb7uDHwG4XRB4XMUaYsWACGmIYupHm6lFhsQsd2t6RHnGX6Zmneenq5EIscVRGefSp6WGTKd2tcaVlIU+SzLKaubscdv9q8RQbmWEboDPpMXoQvloWWavuvkhpvgiRIC6msgjkjslAUehcfvyZfgsI9FKXfiCo8XLJCvmKqW-iWBRtzl-rznRvzgxoLgAaxqLsAeLqStxtLpAQJtAYykvrxvAefIgcgagRropm8SpniNgaVnRUkumTOdrAZq0fOeQUXkuV0YdnaYYuavZkwY5qwbQCMXgGMQeRMZXORZkYTvMZORQUsSuUkhFg+esRVs+RQa+XQbBcNsoTqWPhxEcdlloToeRZeaBSXuBWYQFVBVOXKdYcCVmSxbmUUqEKdCkFEI+gaQ6H8cBfVqTNpU8fBdmTBbmVKmJkSYiTWfvrsuUcQu6l-GWeibvFgOSVEFgFSfrnXInMmBUSFroDVKBiQqcHXANR9JAEkeyUejEOvBIJKROYbtBT5aFfpv0G8roCxcFdOQJB+aoeGjmiScDgFq-sZUat5T0Y7uuf0VZa7pFS9LubUAAOrRCSDJAMQlXWDuWG4NqmmXwEyUhmklBFBQ0mR+hZzYkob7bNDKhtZMoZCI1ohUqHV2LaiST2Rhp4B5irWTCmhBhpQwxOCuxfVJg-kUA7gbjczChFChQ1bFCmB1Asi3AoBoDoApjND9YvKTAzxKl7JGjoAS0gAk4S14C-SEGbD83igwRwQCRc6Iq1j1iNhAZi7dgy7aSjhVTThGBziLiribi7j7iHgnhngXjXi3j3iPjPivgfhfgK1FAh7z4hyzyi0o4y2cSe1+1y3axu0C2PBBi4L-wi3eBi24CS04JQSB1qoh2ZQbQsTqK0CXiXicDHhriXiPg7hcxdjziniZ1CDnicDzgbg7hrhrg7iPhng7g7jzg7iFD83s3FBAA&locale=en) and paste it to the **Config** section of your project. This code has validation and task layout pre-configured.

        [![Create a project. Config section](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/monitoring/monitoring-config-section.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/monitoring/monitoring-config-section.png)

    1. You can edit the code. For example, to change the description, replace the sample text with your value in the `content` property.

        [![Create a project. Config text](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/monitoring/monitoring-config-text.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/monitoring/monitoring-config-text.png)

    1. A Toloker will be able to submit a response when they are within 50 meters of the specified location. To change this condition, replace the value of the `max` property with the desired distance:

        [![Create a project. Config distance](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/monitoring/monitoring-config-distance.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/monitoring/monitoring-config-distance.png)

        {% note info %}

        To learn about other properties of the **Config** section, their possible values and the impact on the task interface, see the [Template Builder Help](../../template-builder/reference/index.md).

        {% endnote %}

    1. {% include [toloka-requester-source-specification-definition](../_includes/toloka-requester-source/id-toloka-requester-source/specification-definition.md) %}

        {% include [toloka-requester-source-click-show-specifications](../_includes/toloka-requester-source/id-toloka-requester-source/click-show-specifications.md) %}

        - **Input data**: Parameters in the file with raw task data.

        - **Output data**: Parameters in the file with labeling results.

        {% include [toloka-requester-source-specification-match](../_includes/toloka-requester-source/id-toloka-requester-source/specification-match.md) %}

    1. In the **Settings for displaying field tasks** section, configure the settings which affect the task display on the map.

        - The **Title format** and **Short description format** are used to help a Toloker distinguish one task from another when they select a task on the map. These fields contain links to the input data fields to show the name of the point and its coordinates. You can leave these fields unchanged.

        - The **Map provider for tasks** field sets which map a Toloker will use when performing your tasks.

1. {% include [toloka-requester-source-instructions](../_includes/toloka-requester-source/id-toloka-requester-source/instructions.md) %}

    {% include [toloka-requester-source-instruction-check](../_includes/toloka-requester-source/id-toloka-requester-source/instruction-check.md) %}

    Field task instructions should be easy to read on a mobile phone screen.

    {% include [toloka-requester-source-instruction-note](../_includes/toloka-requester-source/id-toloka-requester-source/instruction-note.md) %}

1. {% include [save-project](../_includes/tutorials/save-project.md) %}

## Create a pool {#pool}

{% include [toloka-requester-source-what-is-pool](../_includes/toloka-requester-source/id-toloka-requester-source/what-is-pool.md) %}

1. Click **Add a pool** on the project page.

1. {% include [toloka-requester-pool-type](../_includes/toloka-requester-source/id-toloka-requester-source/pool-type.md) %}

1. {% include [toloka-requester-pool-name](../_includes/toloka-requester-source/id-toloka-requester-source/pool-name.md) %}

1. {% include [toloka-requester-pool-description](../_includes/toloka-requester-source/id-toloka-requester-source/pool-description.md) %}

1. Click **Create**.

1. {% include [toloka-requester-source-audience-settings](../_includes/toloka-requester-source/id-toloka-requester-source/audience-settings.md) %}

    1. Clear **My tasks may contain shocking or pornographic content** if your project has none of those.

    1. {% include [toloka-requester-source-filters](../_includes/toloka-requester-source/id-toloka-requester-source/filters.md) %}

        [![Create a pool. Languages filter](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/monitoring/monitoring-language-filter.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/monitoring/monitoring-language-filter.png)

    1. Tasks in pools are available in the web version of Toloka and the mobile app by default. Make your tasks available in the mobile app only: add the **Client** filter and select the **Toloka for mobile** option.

    1. Use the **Speed/quality balance** slider to change the number of Tolokers who can see your tasks. Move the slider to the right to exclude Tolokers with lower ratings from participating in your project.

        {% include [tutorials-speed-filter-image](../_includes/tutorials/speed-filter-image.md) %}

1. {% include [tutorials-quality-control](../_includes/tutorials/quality-control.md) %}

    1. Click the **Review task responses manually** toggle, and specify the number of days for checking the task in the **Review period in days** field (for example, 21).

        {% include [tutorials-na-acceptance](../_includes/tutorials/na-acceptance.md) %}

    1. Click **Add a quality control rule → Results of assignment review**, and enter the following values:

        [![Create a pool. Results of assignment review rule](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/monitoring/monitoring-results-rule.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/monitoring/monitoring-results-rule.png)

        This means that if more than 35% of a Toloker's responses are rejected, the Toloker is banned and can't access your tasks for 15 days. The rule takes effect after 3 responses of the Toloker are reviewed.

    1. Add the **Processing rejected and accepted assignments** rule.

        [![Create a pool. Processing rejected and accepted assignments rule](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/monitoring/monitoring-rejected.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/monitoring/monitoring-rejected.png)

        This means that if you reject assignments during the review, they’ll be sent for re-completion to another Toloker.

1. {% include [tutorials-time-per-task-suite](../_includes/tutorials/time-per-task-suite.md) %}

    It should be long enough to get to the place, find the specified point and object, and upload the photos. For field tasks, this time is usually 86,400 seconds (24 hours).

1. {% include [toloka-requester-source-price-settings](../_includes/toloka-requester-source/id-toloka-requester-source/price-settings.md) %}

    1. In **Price per task suite**, set the amount of money to pay per task suite done by one Toloker. A task suite is a page with a number of tasks.

        For this type of project, a task suite must contain only one task. You will set the number of tasks per suite later in this tutorial.

    1. {% include [toloka-requester-source-overlap-settings](../_includes/toloka-requester-source/id-toloka-requester-source/overlap-settings.md) %}

        For field tasks, it is usually 1. This means that each task will have 1 response.

1. {% include [tutorials-upload-tasks](../_includes/tutorials/upload-tasks.md) %}

    1. Create the tasks for Tolokers:

        1. To download a template, click one of the buttons:

            - **Template in XLSX**

            - **Template in TSV**

            - **Template in JSON**

            For this type of project, the file with tasks must contain seven parameters:

            - `INPUT:name`: A string with the company name.

            - `INPUT:image`: A string with the link to the photo of the item that the Toloker should find.

            - `INPUT:address`: A string with the company address.

            - `INPUT:product`: A string with the item name.

            - `INPUT:coordinates`: A string with the coordinates of the point that the Toloker should go to.

            - `AI:latitude`, `AI:longitude`: The latitude and longitude from the `INPUT:coordinates` parameter presented separately. The values of `INPUT:coordinates`, `AI:latitude` and `AI:longitude` should have the same accuracy, that is have the same number of digits after the decimal separator.

            ```plaintext
            INPUT:name	INPUT:image	INPUT:address	INPUT:product	INPUT:coordinates	AI:latitude	AI:longitude
            Company-name-1	https://yastatic.net/s3/toloka/p/toloka-requester-page-project-preview/877a55555a5f199dff16.jpg	Address-1	Item-1	53.947516,27.669428	53.947516	27.669428
            Company-name-2	https://tlk.s3.yandex.net/dataset/cats_vs_dogs/dogs/048e5760fc5a46faa434922b2447a527.jpg	Address-2	Item-2	53.947517,27.669429	53.947517	27.669429
            Company-name-3	https://tlk.s3.yandex.net/dataset/cats_vs_dogs/dogs/05334365c060421ab25264166bbb4fd1.jpg	Address-3	Item-3	53.947518,27.669428	53.947518	27.669428
            ```

        1. Open the downloaded file, and replace the sample values with your data. You can use a service like Google Maps to get the coordinates.

        1. Click **Drop file here or select**, and upload the file you’ve just made.

        1. Click **Continue**.

    1. {% include [toloka-requester-source-task-suits](../_includes/toloka-requester-source/id-toloka-requester-source/task-suits.md) %}

        1. Go to the **Set manually** tab.

        1. In this type of project, the task suite must contain only one task:

            [![Upload data. Tasks per suite](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/monitoring/monitoring-number-tasks.png =570x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/monitoring/monitoring-number-tasks.png)

    1. Click **Combine tasks into suites**.

1. {% include [tutorials-upload-tasks](../_includes/tutorials/double-check.md) %}

    {% include [toloka-requester-source-step-enabled](../_includes/toloka-requester-source/id-toloka-requester-source/step-enabled.md) %}

{% include [toloka-requester-source-pool-is-ready](../_includes/toloka-requester-source/id-toloka-requester-source/pool-is-ready.md) %}

## Start labeling {#labeling}

1. Make sure you have [topped up your account](../concepts/refill.md).

1. {% include [toloka-requester-source-start-button](../_includes/toloka-requester-source/id-toloka-requester-source/start-button.md) %}

    [![Start labeling](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/monitoring/monitoring-start-labeling-step-2.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/monitoring/monitoring-start-labeling-step-2.png)

1. In the pop-up panel, review the budget and click **Launch**.

## See the results {#results}

Track the labeling progress on the pool page. You can start the review when the first results are received.

After the time period specified in step 4.1 of [creating the pool](#pool), all responses are automatically accepted, regardless of their quality.

1. Go to the pool, and click **Review assignments**.

    [![See the results. Review assignments](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/monitoring/monitoring-review-results.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/monitoring/monitoring-review-results.png)

1. Choose an assignment.

1. Check the responses, and click **Accept** or **Decline**. For rejected responses, enter a comment to specify the reason.

    {% note info %}

    To learn about other ways of review, see the [Reviewing Tolokers' responses](../concepts/accept.md) section.

    {% endnote %}

1. After checking all the assignments, click **Download results**.

    [![See the results. Download results](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/monitoring/monitoring-results-download.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/monitoring/monitoring-results-download.png)

    You will get the TSV file with the labeling results.

1. To download the files Tolokers attached to the tasks, click the arrow next to the **Download results** button. Choose **Download attachments** from the drop-down menu.

    [![See the results. Download attachments](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/monitoring/monitoring-results-download-attachments.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/monitoring/monitoring-results-download-attachments.png)

## Troubleshooting {#troubleshooting}

{% cut "Can I limit the source of the photo to camera-only in a field task so that the Toloker can't upload a photo from anywhere else?" %}

The `accept` property of the `field.media-file` component adds different buttons for four types of uploads. To prohibit using any sources except of the camera, use the `"photo": true` property only, like it is done in the [example](https://tb.toloka.dev/editor?config=N4Igxg9gdgZglgcxALhMAOlABF9IBucApgO57JYbY64gAuAngA5Hm2GkB0ANnAM508AGkw1acOkQC2fNgG1RYyoqW1GLNng4lOAQ25EAToJAjqqvJCiTrbKqrF51rFO2I7JADxNmHNS9A2JhR4ALLQEhCGcFAIWBLSfFi6dFgARgCufDFEfHy5eCpKAL6+Dk4AFtIuISAxMBCF5jSlRTj25fTMNW5cXj5t-iDcumlE3JogAMIQUky6UAxYULpSRMjCgzgB1kS2rh1+Tt2TACYpupwxTBkDzRYg83QVkytrTX7Fg633yr-bXQ0ri07k4pzghFORg+JTKYkOSmOQNq2k4-U2-1oIzGE2BIAAgqdToZcnwNqYtrQrEE7JSAc4zhcrlAbnc-ACni88boiSS8jDVF9fj9VAjHICeiCuODIdCQN84TQxUMGXjUeiKZi8NjxpMAJKSKRYKF8MDRJh0ODQcmK8XUvbBP7stQnPHnOiXa63DHOvCcyZMQwQU4ZMAmSlCwW2p2dVUo0EyuBQwwClrR5X013xri8KAAax9nQyhlxtQqdDoTDJAHpqwxdAIUnAwJwoEQ6NW+ABmat0CDcCB53TVpjVkkARwyuUkhmrugAbPOACwATgATAAGACMAA5dFuuxvTgB2Ltd4+nACsx90x53x5Xx43MHP884ACsmAhCw97ftagAMjEeZYH2WCBsGoapHAUi6AgLgKoMGYusivQ6LoYZWlAAC0mQVtAP6IsMoy6niADKFS6CSWAMBAxZYJAUTgiskiyJqRwgBhloEQcdIoZKnGYdAnD5Gy7J+roDADjytKYuKca0AAAvWUBQp42F9gOQ7Vu6lwDmATY8XxIriSAumyc6maoXgumcHRlbeuxlkSc8kwkFEeZGAA+oxhjMSkBTynJWCRg4JkPPg+hJoZUAWaZCk7OC3FQHo3C4tGdrQElWFsRQCjBe0fHyVmVJZRIWGcBOGRwCSpyEb6IAVDEjp4FMvBgCBYF8JR1G0fRvn+ax9WmeZvEFURCVmUy9mssNDX+ni7mGJ5hg+RATExAFbFFS0O3heyyEPJNykLGpGn9oOw5WNlwngo2UBgC4GWdE1-60H1yTUX2EBYDAVHJCQkm-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-npkJuql-EZtqpbqZibofLwBZrouHhHm1k7u-Fap-N-Nbu7s1A6k6h5hDoOu3ifnyATilAXgzt2qHmEtZrTFHuXjHimv3omgnrQUXsnslhmjtt9jmllgWrAUQGfF5HwaSEIWWhQUVtWmXtGtnH3oztXoRrXpkvXq-pgcUmUpDrPpesWGbOarEG0rfhYVXhQUPjYR2qPvYTrniFPj7u3mJugiQFUF9M7KnJehUiEuvGMHXCjvoNwJeg9iBjjjctBHQEfivM+pvLkcOs3PwFgCSOkUsP3PeicoHpVpYX4RrGbsQRblbmZrbs1gPt9pNAwSlC7iweIXgB7rQF7lwc4U9q4YYO4cxPmvUTIa-qIfbqZNwcTNHuYbHq-vFkMY-mmhNkwjseodnroTMTliPJpjhq-sYaXj0BXj4fflYZtidrYUERgSESukUjMFIGsNYF4bgY0YoTXrOiPgukXg4SABMoYEsGBPAEnPZFgNEdCT5u+IesvNvB3HEE8ggBCHAs7JUVctgDEJXO7D8akOBg0JvOjOpkQFgqkNAAcnwGJgwHXIDHwFANHKkFCLwLNl-PBrUQiW8okfkPBknFct7FADBnThcRQgCUns0YQWiOjB6JUYDjZPId0YPhrOmpNmnulrZrMKSQYXVlpj0jVjhsZMwlou1jossTZi-EYhVF1twBYj0r1q8APOskNtsXGm1tqQcT6Y8BnnLN4pwtKYKEtuNEErkFWraUdhCjmIBkNntq4IkjTPgUCW2i8aCQVuCautMqsV5i4ZkJbrMRvIvhhODNEScrvhhhvokXSukNDvsukZkSaDkXesnI+h8iWK+hUiQE3AUZUWlNUZUsnAHt4Q0b4YCaqgqebqQe0RQeZnbonikvQQ6YwZOMwbqY1Owa5pwS6gWb7uDHwG4XRB4XMUaYsWACGmIYupHm6lFhsQsd2t6RHnGX6Zmneenq5EIscVRGefSp6WGTKd2tcaVlIU+SzLKaubscdv9q8RQbmWEboDPpMXoQvloWWavuvkhpvgiRIC6msgjkjslAUehcfvyZfgsI9FKXfiCo8XLJCvmKqW-iWBRtzl-rznRvzgxoLgAaxqLsAeLqStxtLpAQJtAYykvrxvAefIgcgagRropm8SpniNgaVnRUkumTOdrAZq0fOeQUXkuV0YdnaYYuavZkwY5qwbQCMXgGMQeRMZXORZkYTvMZORQUsSuUkhFg+esRVs+RQa+XQbBcNsoTqWPhxEcdlloToeRZeaBSXuBWYQFVBVOXKdYcCVmSxbmUUqEKdCkFEI+gaQ6H8cBfVqTNpU8fBdmTBbmVKmJkSYiTWfvrsuUcQu6l-GWeibvFgOSVEFgFSfrnXInMmBUSFroDVKBiQqcHXANR9JAEkeyUejEOvBIJKROYbtBT5aFfpv0G8roCxcFdOQJB+aoeGjmiScDgFq-sZUat5T0Y7uuf0VZa7pFS9LubUAAOrRCSDJAMQlXWDuWG4NqmmXwEyUhmklBFBQ0mR+hZzYkob7bNDKhtZMoZCI1ohUqHV2LaiST2Rhp4B5irWTCmhBhpQwxOCuxfVJg-kUA7gbjczChFChQ1bFCmB1Asi3AoBoDoApjND9YvKTAzxKl7JGjoAS0gAk4S14C-SEGbD83igwRwQCRc6Iq1j1iNhAZi7dgy7aSjhVTThGBziLiribi7j7iHgnhngXjXi3j3iPjPivgfhfgK1FAh7z4hyzyi0o4y2cSe1+1y3axu0C2PBBi4L-wi3eBi24CS04JQSB1qoh2ZQbQsTqK0CXiXicDHhriXiPg7hcxdjziniZ1CDnicDzgbg7hrhrg7iPhng7g7jzg7iFD83s3FBAA&locale=en).

If you allow Tolokers to use the mobile device gallery, you can prohibit adding images without geotags to limit uploading photos taken from the Internet. To do that, specify the `"requiredCoordinates": true` property.

To learn more about setting up the `field.media-file` component, see the [Template Builder Help](../../template-builder/reference/field.media-file.md).

{% endcut %}

{% cut "How do I check the task display in the mobile Toloka app?" %}

To check the task's look-and-feel on the mobile phone screen, you can use the following buttons:

- **Preview task** on the project settings page.

- **Preview** on the pool settings page.

You can also use the mobile version of the sandbox. [Write to support](../troubleshooting/support.md#support-work-toloka) to get access to it.

{% endcut %}

## See also {#see-also}

- [Crowdsourcing concepts: Instructions](https://toloka.ai/knowledgebase/instruction/)
- [Crowdsourcing concepts: Quality control](https://toloka.ai/knowledgebase/quality-control/)
- [Crowdsourcing concepts: Pricing](https://toloka.ai/knowledgebase/pricing/)

## For developers {#for-developers}

- [Toloka-Kit: Spatial crowdsourcing example](https://github.com/Toloka/toloka-kit/blob/main/examples/2.spatial_crowdsourcing/0.simplest_example/spatial_crowdsourcing.ipynb)

{% include [contact-support](../_includes/contact-support.md) %}

{% include [image-styles](../../../_includes/image-styles.md) %}