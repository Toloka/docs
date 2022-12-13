# Product monitoring

In this tutorial, you will learn how to run a product monitoring project in Toloka. We will use a project preset designed specifically for this type of data labeling.

Product monitoring is intended for field tasks in the Toloka mobile app. The preset is suitable for finding objects indoors, for example, checking how a product category is displayed in stores. A Toloker chooses a point on the map where they should go to check something and take photos.

{% note info %}

You may need additional projects for your task, such as dataset pre-check or checking Tolokers' responses. Learn more about this in [Decomposition of the task](../concepts/solution-architecture.md).

{% endnote %}

## Prerequisites {#prerequisites}

Before you begin:

- {% include [tutorials-register](../_includes/tutorials/register.md) %}

- {% include [tutorials-top-up-tutorial](../_includes/tutorials/top-up-tutorial.md) %}

## Choose a preset {#preset}

{% include [toloka-requester-source-use-preset](../_includes/toloka-requester-source/id-toloka-requester-source/use-preset.md) %}

1. Follow [this link]({{ audit-preset }}), or create a project manually:

    1. {% include [tutorials-create-project-button](../_includes/tutorials/create-project-button.md) %}

        {% include [tutorials-choose-preset-image](../_includes/tutorials/choose-preset-image.md) %}

    1. Select the {% if locale == "en-com" %}**Retail merchandising audits**{% endif %} preset.

1. Click {% if locale == "en-com" %}**Choose this preset**{% endif %} in the pop-up tab.

## Create a project {#project}

{% include [tutorials-who-are-tolokers](../_includes/tutorials/who-are-tolokers.md) %}

1. {% include [tutorials-add-name-description](../_includes/tutorials/add-name-description.md) %}

    - {% if locale == "en-com" %}**Name to show Tolokers**{% endif %}: In 2–5 words, state the general idea of the project.

    - {% if locale == "en-com" %}**Description for Tolokers**{% endif %}: In a couple of sentences, explain what you expect Tolokers to do. This is just an overview. You will write instructions later.

    [![Create a project. Step 1](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audit-place/audit-create-project-step-1.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audit-place/audit-create-project-step-1.png)

1. In the {% if locale == "en-com" %}**Task interface**{% endif %} section, set up what your tasks will look like.

    {% include [toloka-requester-source-tb-or-html](../_includes/toloka-requester-source/id-toloka-requester-source/tb-or-html.md) %}

    1. Copy the code of the [example](https://tb.yandex.net/editor?config=N4Igxg9gdgZglgcxALhMAOlABF9IBucApgO57JYbY64gAuAngA5Hm2GkB0ANnAM508AGkw1acOkQC2fNgG1RYyoqW1GLNng4lOAQ25EAToJAjqqvJCiTrbKqrF51rFO2I7JADxNmHNS9A2JhR4AIIArgAmElgQMFh0ABZEWEzculAQCIa6UrHxTIYQkeFgdHxY0XxpugxEkVhw2EkpAhCGLipKAL6+Dk7JUi4hIE0wEHhdOL1TyuZKTszDblxePrM4eOkARkTcmiAAynTtKVC5RMjCG7RWQXY3m-RLB5G6dLqcTUzh6-MWICY70SB3OQ0m-xo3VmM0h9n6zw0ri07k40UIkSMENUsNU8IBzgO2k4a2ukKeOz2B1CkUiHT4fCuphuAWsRFsrnxCMJyJAbw+XygPz+fieQKSB10tPpshAN2hkNxSi5jkRyxRXHRcExhmxPT6YhV-jVRNRpOZ5NolP2vIACkUSmUsGB3kQEO0GEyDQtwIF2cE5qK1C9efzPt9fmSg3hxSDeYViqUTPKYd6cEanjyRsStTq9WIlYaWSbecTeFAANZRhHhQw2kaJOh0JiMgD0rYYugE7zgYE4UCIdFbfAAzK2TtwIBXdK2mK2OgBHcJEARGVu6ABsG4ALABOABMAAYAIwADl0x5Hh8iAHYRyOb5EAKw33Q30833c3w8wB8bzgAFZMAg1YAnc-oHAAMk0FYJBAqTpJk2S5PmUJpoG3IhtmqK6GUcDQAAtNsvwnFAoE+taByHIkugdFgDAQLWzoQO00TnJIsroU8uF0PhZGco8wZIiMPF8ZwfCDuRAJAgwk5Sg8lqqlmtAAAKdlAmKeARE5TjOYY8BALq8dAqE4lxxphgpQaZlhtD6YxzaRha1m0LGBwkO0FZGAA+pArFNK6sqCQqfiFj6+D6NqPYmQJilCeqvoaRIYn6Da5lPFY0TGVAsoUAocXpoJSm2ayWViYu4RwB0kRSaKeCJE0AZ4AAwrwYCwScWB8DRdEMUxfmGGxgW1X4eCWbFLnFcJdnvJ8DnCiNdWAsC7meT5A1DRxpmiiF1lhX4GaYdNeBqRkmnaRAk7Tq2mXJdAaL8B8UBgC46U+g1HIjH1WC0SkJzwTAtE-SQtRYDARR5C0WCTkZYmLQC4MQFIVmTTZx0gKdGlEFpOnXfpMPRfxRVocTmYTBNqPxa8s2CgtzmUzGK28htAVbXKBUkxzTxSLonhsE+h7E7tfgALopoq6GHYs6M5nAGJYuzZmzFLJbYVw+hGCKCLgZ9GGjartDwHskScMRTaETk0QQAR2SMUw8NWrouz1rQhx7EQTpQx8fCwZAUhpIOfGxEw2VeoJeAQCHfG5Vg+UuYdAKUbyACSYOMRpCTJFghiII2XXJNwMAO6qEXcMuBxTttSscwnFFO1SvKhKkDpJlgJASIkmf8Fg2w5Bn-BQAA5HQsTNFn3V7EX9MuVo+jl7ymTeRI0hV-qxO16qScjAAKuPJx0d3YCThJDTtFgUj8HwTQgdP1mz2XCWL+0N9C4JItvffUXZSj0YG6Vd1QE4BVKq9Ri60A+k1I47snTQBSHETOcCo7QEZM3Xsf1dAIDTuEDSQgsCZFQS9BIGDcH4ITI6OguC2h0SPhAE+nBV7TA-nyWaP8lrKTGjTeaTk3piiZtmIw0QygMKwMLNeloBjSASmMcmqZlbFnYSAAuLBDDiXbnQMAcZzKWC7CueQgkN63GgGVGKFADFowSrdbKnAiBLn0JxUmahyYjErrfX+41TEOPMdTAUXCtao0ZhKUsAjezJi5iIoWPDaD0nCNwAMZiqallRLwAQYCnjLxkHosJhUsnGgUcSHmhgKyRAgCQfikSwJ+l1ngAAVNU20iQIAnAqPAqGDkr6YnyAgrq+8iC1OEdXSmesGZ-wIKiApRSSllM8caHWkDqnb10F5LA+5UgNKaZ0qGVCiCDwqIjawYMIaVDgDAGARh-Q-SgAgAwFQ+DwSSO8Ro5QuqIGwGdPBFwfrUIMLRbgDAsCECvtsAwnBqn9LEYM+JU0Eplhgqkn0tYXb1SbC2ZA7YpB0AIrMgiPwgW9nEiOTg6lNL9kHK2JoAhDBJmjuOS6ulvJG24JEbykh-bpA4rOHOL1vLP28seby25vIbgIhfQBTBLlwtVLMg4ABRTwuQA5goLOUmgkLcklRAAyk2Qxoi6AIvAAwErjSly-nxVhgzpYWKMQAoBNjKrVUNaqCB1Imy4U7kwNZtCNl71OPQxWgyRHKtVLhF6IczXDPdY0pxCRKWsByYw6ZTx3FDPNSM+yvw6aBp9G5XkcApAID4PS3CUpOhxoDQm2gUgYm8QVa4OgMbpn7WsqqrxiSuDjOKaUh1hi2RVJALU+pkbmnxChkZN0Ho+l+tRo2oMzaElqx0O2yZXbWT3F5PMxZKRdBg1IM6Y+RACLhCYKswdXqUg5HahUJoXSOgGAivsiSeFoBdTuTREeUM9kj3aXA4dWde5vLIUmCoajO4tCqu8oYFyGiYg+HAbgl6KhHyID8v5AK4BAqICCxVnMIXlotaaLg5YqyuMmngBFBxGzNjbK2dFmLKkYpxW1fFhKzrYxJUOcldaqXIJpVdXQ9LiCMuZdIGo7KahP0MAgby+5+XCqaJwMVN9M0ZTozKuVrKS2DOnaKWdeHeSas4NquAur9WvVwwQSK-JTUU39XO7txjAHAPtcR-xijGrOo+Bo496yWlZ1He6QwDBfXlq07-YNRBQ3Wf9TGD1bBOOxpsyFpaSbZ0tpGGmxyfiovLUCSMXN+bfKun8wwLDSqzOVtiXAGtFA4sNszTpkZ+TaITM7c5u+iVV0jFqc1JGQxrB8AnbV6Z9W8ljKax2qZpaV0QTXcneIfVDBec9cUoeI87i6CvalLpA4XoMlon86RhgebZVwVKKDg51twawMkDomHJ2TUS3iMzCj9NrF+roZdzCPhhpcwo9LGby28Jy4YqQvXQkJYbQ4sWHNREDO08Tf+39Iu-wUZYsStq7FwqcFGvAi90mY8++9pHbXfucPTdw6ZAS4z8MGiErDMOHAPaiSuKt32jrQqSY9fH6SY5x0psN9VjXCnjY+1KtddSPVDq6W07U36ulbIGzkxnRZJsNdG0LpdrXf6i86wspZKyI3eZ-a0HpOyDmBDN3kaIJyzn7IyFclcz7M4PIkDcl5kHwObq+UhusKH+BoeBaCu7LklcqqewLjnlYPtkd5BRlFaKMVYoY3i0czGsaeDY2SnKnHH05R43SzVQnWWBQ5Wg7lEneX8sFbJ0V4rNdLW17QWV8qDVB72nVsP6N9OGeM7B0zKvjWWZMcm4ZKOrVWMc6Auvv8nWNxdZ5g3nqfPG59SV7DWWwsRY8aWsUMXa31tLSH1UyWAe2Y4T4snmWU3Zty3mgtgMXSYlX-GlX5Xq0t+q-vzT7eVcjbbWNjXSm3aHWtA-aEup6zohW46geg2OS-OMsauzWE2NmU2va66SyC+kum2E83A+ADuby56FYQGHczciYZQl6Y8rQHyfmHonAWAu8ZwFwkuUMAGZB+cjEjKPcKQiGyG-yfu6GtBAAQq0LWH9PBC6CHCIVtkQLnNsO0NfPnHsLgRUJ1N1CUk7m+lnCwSPN3B0KlH8hfAyNfLdjAThj-uHgRrClPjWHWORsilRjRonuELin2CnkSqxgOOxlnpSjnnwHntOPxsbIXiJiuLOIhBAGXpJtJtuNXvJrXoASgZAk3upqvofsPjPCMl3vUEZnqr3h9gPoTKzukaPklOPraiAjVFYfrDPiMKEHPm6mAUvhAZIEVkFgfvESABvnEiftFpGrFp-v6qkYmiwkTj9uqn9uTtvq5HwuILfgVs0R6E-mWi-lWpVu-tGuXIrt-sgarn-uri1u0Q3jUtUt1iDv6P1tAZsUNh3uzrsYgSLipmutvAFnBGDE0KfL8BbnLj0lgMJpOHUA7iQIkH8swS3E6APMPKPHLgXPEG8ggHLH9FnLobctgFeiOj1mcVgAABTjALbYzN5EC4IgmkHaE3KXTvEUJfGnB4LwSTiXJGBdR7CXZJDdxaGEnXYpAgwVD4KYi8C4EBa4Jny3JDDMmXI-FwZEAACUxhlxsB1xBwL22MHwuhH2x+kxumaWpOGWXagOVOwOoOix9OQYhpDgUOwewUb0BiCOVmW+ox6MqO906OcG+OJwoI4Rz8+OqpKaJO5+WplRxo1+7AwSQireoUES8OIA0SsShRPov+OgySl+S03OmSph2xsZBm-++xZmhxfauuKQGB4BxEsGbEmCZ8NQhCgJZyUuEmGQcAAAXoTGwTEg0LsJ8VgTLqSeoQgn8twT7mwSQI8qbrodwL8tSRoWctKV-lcWYZ3gJlqlkT3i3u0fkYjjaTZqfolPZjakuOUdqeAm5rPh5vUSeo0XwLWEUNgsWXwK0Qlu0Z0dGb-Avn0RsTeWZp6WueqTND6f9mqdlrqXgHlgWrROnBUcFu0a-qscsDVjKSmVlmmYupmSrtmWgZuotuAadjKAhK6LEAtgdkdkHFfAgNgMBlWQgDWfWdlKbuhSuBUA8lDP6H3C9BOZTKkXATcXGZYe0dHg2HYaitRgnnRtik4Yxq4Sxunh4ZnhSlxrnrjHxgXiysEb4YUKXjyqeDEQpvcT2okWpjWiYXznKXprOQZvOTkYuWZsudaWkSRiMvaQ5mUU5oAU8NUbQLUYeT9KhY0VRQyJhZINeQMbeWACGl0T+Y+Xvs+X5a+cMauamWMZqd+WuVMUDv+bMZ5UFG0WVisVVusfFsxVsbBeYQuhmUgVlkhdUgALJnTvAejMSnF9YK6TmynTlsXpl7FFUppIWyo1BXqAnAlZzPxkUNmHx7qnwLYGFXyinYlnx4nqa4IXn0kdBAhVS4I0InwCkLbfSQBNkravH9x0BSkXH1UwVenqoKneBvYqmRWWVFExVfkTHxWU4HB+z6khlt5mUWYFEjFWXFGbkT4VEOV7m9oADqOckgblj1-ovlmmEOYSppe0wUNwMNBYXQMNSoMYZccJOUyZoekIH5qN4Q6NJItK04tUWwtQDkrOeAFYbxBwfAYARQw5i0TgXYFYAN2oQOp4h4gsioXQu0UO3QpgowQovwKAaA6Auo8wOOFwBw28ipnx6ActIAYIrA8trxxs1wYtqouaGCCUseVGnY3YvEfY4lo4fhM4c4FUK4kghg64W4e4R4Z4F4V4t494j4L4b4H4X4P4f4gEwEatXQeAKVUtMtiMeQct-t0o1FodIAKtjKvt4tgIoJkC0t3gst8tWhkd0dv1otftvo-k7EuivIT4T4nAN4+4T4X4p4AsI4G4d4hdQgD4nAG4h4p4+4+4p4X494p4p4G4p4kwYtfN3QQAA&locale=en) and paste it to the {% if locale == "en-com" %}**Config**{% endif %} section of your project. This code has validation and task layout pre-configured.

        [![Create a project. Config section](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audit-place/audit-config-section.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audit-place/audit-config-section.png)

    1. You can edit the code. For example, to change the description, replace the sample text with your value in the `content` property.

        [![Create a project. Config text](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audit-place/audit-config-text.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audit-place/audit-config-text.png)

    1. A Toloker will be able to submit a response when they are within 50 meters of the specified location. To change this condition, replace the value of the `max` property with the desired distance:

        [![Create a project. Config distance](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audit-place/audit-config-distance.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audit-place/audit-config-distance.png)

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

        [![Create a pool. Languages filter](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audit-place/audit-language-filter.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audit-place/audit-language-filter.png)

    1. Tasks in pools are available in the web version of Toloka and the mobile app by default. Make your tasks available in the mobile app only: add the {% if locale == "en-com" %}**Client**{% endif %} filter and select the {% if locale == "en-com" %}**Toloka for mobile**{% endif %} option.

    1. Use the {% if locale == "en-com" %}**Speed/quality balance**{% endif %} slider to change the number of Tolokers who can see your tasks. Move the slider to the right to exclude Tolokers with lower ratings from participating in your project.

        {% include [tutorials-speed-filter-image](../_includes/tutorials/speed-filter-image.md) %}

1. Under {% if locale == "en-com" %}**Quality control**{% endif %}, set quality control rules for more accurate results.

    1. Click the {% if locale == "en-com" %}**Non-automatic acceptance**{% endif %} toggle, and specify the number of days for checking the task in the {% if locale == "en-com" %}**Review period in days**{% endif %} field (for example, 7).

        {% include [tutorials-na-acceptance](../_includes/tutorials/na-acceptance.md) %}

    1. Click {% if locale == "en-com" %}**Add a quality control rule → Results of assignment review**{% endif %}, and enter the following values:

        [![Create a pool. Results of assignment review rule](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audit-place/audit-results-rule.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audit-place/audit-results-rule.png)

        This means that if more than 35% of a Toloker's responses are rejected, the Toloker is banned and can't access your tasks for 15 days. The rule takes effect after 3 responses of the Toloker are reviewed.

    1. Add the {% if locale == "en-com" %}**Processing rejected and accepted assignments**{% endif %} rule.

        [![Create a pool. Processing rejected and accepted assignments rule](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audit-place/audit-rejected.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audit-place/audit-rejected.png)

        This means that if you reject assignments during the review, they’ll be sent for re-completion to another Toloker.

1. Click {% if locale == "en-com" %}**Show advanced settings**{% endif %}. In the {% if locale == "en-com" %}**Additional settings**{% endif %}, specify {% if locale == "en-com" %}**Time per task suite, sec**{% endif %}. It should be long enough to get to the place, find the specified point and product, and upload the photos. For field tasks, this time is usually 86,400 seconds (24 hours).

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

        - `INPUT:name`: A string with the store name.

        - `INPUT:image`: A string with the link to the product photo.

        - `INPUT:address`: A string with the store address.

        - `INPUT:product`: A string with the product name.

        - `INPUT:coordinates`: A string with the coordinates of the point that the Toloker should go to.

        - `AI:latitude`, `AI:longitude`: The latitude and longitude from the `INPUT:coordinates` parameter presented separately. The values of `INPUT:coordinates`, `AI:latitude` and `AI:longitude` should have the same accuracy, that is have the same number of digits after the decimal separator.

        ```plaintext
        INPUT:name	INPUT:image	INPUT:address	INPUT:product	INPUT:coordinates	AI:latitude	AI:longitude
        Store-name-1	https://yastatic.net/s3/toloka/p/toloka-requester-page-project-preview/877a55555a5f199dff16.jpg	Address-1	Product-1	53.947516,27.669428	53.947516	27.669428
        Store-name-2	https://tlk.s3.yandex.net/dataset/cats_vs_dogs/dogs/048e5760fc5a46faa434922b2447a527.jpg	Address-2	Product-2	53.947517,27.669429	53.947517	27.669429
        Store-name-3	https://tlk.s3.yandex.net/dataset/cats_vs_dogs/dogs/05334365c060421ab25264166bbb4fd1.jpg	Address-3	Product-3	53.947518,27.669428	53.947518	27.669428
        ```

    1. Open the downloaded file, and replace the sample values with your data. You can use a service like Google Maps to get the coordinates.

    1. Click {% if locale == "en-com" %}**Drop file here or select**{% endif %}, and upload the file you’ve just made.

    1. Click {% if locale == "en-com" %}**Continue**{% endif %}.

1. {% include [toloka-requester-source-task-suits](../_includes/toloka-requester-source/id-toloka-requester-source/task-suits.md) %}

    1. Go to the {% if locale == "en-com" %}**Set manually**{% endif %} tab.

    1. In this type of project, the task suite must contain only one task:

        [![Upload data. Tasks in suite](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audit-place/audit-number-tasks.png =570x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audit-place/audit-number-tasks.png)

1. Click {% if locale == "en-com" %}**Combine tasks into suites**{% endif %}.

## Start labeling {#labeling}

1. Make sure you have [topped up your account](../concepts/refill.md).

1. {% include [toloka-requester-source-start-button](../_includes/toloka-requester-source/id-toloka-requester-source/start-button.md) %}

    [![Start labeling](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audit-place/audit-start-labeling-step-2.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audit-place/audit-start-labeling-step-2.png)

1. In the pop-up panel, review the budget and click {% if locale == "en-com" %}**Launch**{% endif %}.

## See the results {#results}

Track the labeling progress on the pool page. You can start the review when the first results are received.

After the time period specified in step 4.1 of [creating the pool](#pool), all responses are automatically accepted, regardless of their quality.

1. Go to the pool, and click {% if locale == "en-com" %}**Review assignments**{% endif %}.

    [![See the results. Review assignments](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audit-place/audit-review-results.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audit-place/audit-review-results.png)

1. Choose an assignment.

1. Check the responses, and click {% if locale == "en-com" %}**Accept**{% endif %} or {% if locale == "en-com" %}**Decline**{% endif %}. For rejected responses, enter a comment to specify the reason.

    {% note info %}

    To learn about other ways of review, see the [Reviewing Tolokers' responses](../concepts/accept.md) section.

    {% endnote %}

1. After checking all the assignments, click {% if locale == "en-com" %}**Download results**{% endif %}.

    [![See the results. Download results](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audit-place/audit-results-download.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audit-place/audit-results-download.png)

    You will get the TSV file with the labeling results.

1. To download the files Tolokers attached to the tasks, click the arrow next to the {% if locale == "en-com" %}**Download results**{% endif %} button. Choose {% if locale == "en-com" %}**Download attachments**{% endif %} from the drop-down menu.

    [![See the results. Download attachments](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audit-place/audit-results-download-attachments.png =700x)](https://yastatic.net/s3/doc-binary/src/support/toloka/en/guide/tutorials/audit-place/audit-results-download-attachments.png)

## Troubleshooting {#troubleshooting}

{% cut "Can I limit the source of the photo to camera-only in a field task so that the Toloker can't upload a photo from anywhere else?" %}

The `accept` property of the `field.media-file` component adds different buttons for four types of uploads. To prohibit using any sources except of the camera, use the `"photo": true` property only, like it is done in the [example](https://tb.yandex.net/editor?config=N4Igxg9gdgZglgcxALhMAOlABF9IBucApgO57JYbY64gAuAngA5Hm2GkB0ANnAM508AGkw1acOkQC2fNgG1RYyoqW1GLNng4lOAQ25EAToJAjqqvJCiTrbKqrF51rFO2I7JADxNmHNS9A2JhR4AIIArgAmElgQMFh0ABZEWEzculAQCIa6UrHxTIYQkeFgdHxY0XxpugxEkVhw2EkpAhCGLipKAL6+Dk7JUi4hIE0wEHhdOL1TyuZKTszDblxePrM4eOkARkTcmiAAynTtKVC5RMjCG7RWQXY3m-RLB5G6dLqcTUzh6-MWICY70SB3OQ0m-xo3VmM0h9n6zw0ri07k40UIkSMENUsNU8IBzgO2k4a2ukKeOz2B1CkUiHT4fCuphuAWsRFsrnxCMJyJAbw+XygPz+fieQKSB10tPpshAN2hkNxSi5jkRyxRXHRcExhmxPT6YhV-jVRNRpOZ5NolP2vIACkUSmUsGB3kQEO0GEyDQtwIF2cE5qK1C9efzPt9fmSg3hxSDeYViqUTPKYd6cEanjyRsStTq9WIlYaWSbecTeFAANZRhHhQw2kaJOh0JiMgD0rYYugE7zgYE4UCIdFbfAAzK2TtwIBXdK2mK2OgBHcJEARGVu6ABsG4ALABOABMAAYAIwADl0x5Hh8iAHYRyOb5EAKw33Q30833c3w8wB8bzgAFZMAg1YAnc-oHAAMk0FYJBAqTpJk2S5PmUJpoG3IhtmqK6GUcDQAAtNsvwnFAoE+taByHIkugdFgDAQLWzoQO00TnJIsroU8uF0PhZGco8wZIiMPF8ZwfCDuRAJAgwk5Sg8lqqlmtAAAKdlAmKeARE5TjOYY8BALq8dAqE4lxxphgpQaZlhtD6YxzaRha1m0LGBwkO0FZGAA+pArFNK6sqCQqfiFj6+D6NqPYmQJilCeqvoaRIYn6Da5lPFY0TGVAsoUAocXpoJSm2ayWViYu4RwB0kRSaKeCJE0AZ4AAwrwYCwScWB8DRdEMUxfmGGxgW1X4eCWbFLnFcJdnvJ8DnCiNdWAsC7meT5A1DRxpmiiF1lhX4GaYdNeBqRkmnaRAk7Tq2mXJdAaL8B8UBgC46U+g1HIjH1WC0SkJzwTAtE-SQtRYDARR5C0WCTkZYmLQC4MQFIVmTTZx0gKdGlEFpOnXfpMPRfxRVocTmYTBNqPxa8s2CgtzmUzGK28htAVbXKBUkxzTxSLonhsE+h7E7tfgALopoq6GHYs6M5nAGJYuzZmzFLJbYVw+hGCKCLgZ9GGjartDwHskScMRTaETk0QQAR2SMUw8NWrouz1rQhx7EQTpQx8fCwZAUhpIOfGxEw2VeoJeAQCHfG5Vg+UuYdAKUbyACSYOMRpCTJFghiII2XXJNwMAO6qEXcMuBxTttSscwnFFO1SvKhKkDpJlgJASIkmf8Fg2w5Bn-BQAA5HQsTNFn3V7EX9MuVo+jl7ymTeRI0hV-qxO16qScjAAKuPJx0d3YCThJDTtFgUj8HwTQgdP1mz2XCWL+0N9C4JItvffUXZSj0YG6Vd1QE4BVKq9Ri60A+k1I47snTQBSHETOcCo7QEZM3Xsf1dAIDTuEDSQgsCZFQS9BIGDcH4ITI6OguC2h0SPhAE+nBV7TA-nyWaP8lrKTGjTeaTk3piiZtmIw0QygMKwMLNeloBjSASmMcmqZlbFnYSAAuLBDDiXbnQMAcZzKWC7CueQgkN63GgGVGKFADFowSrdbKnAiBLn0JxUmahyYjErrfX+41TEOPMdTAUXCtao0ZhKUsAjezJi5iIoWPDaD0nCNwAMZiqallRLwAQYCnjLxkHosJhUsnGgUcSHmhgKyRAgCQfikSwJ+l1ngAAVNU20iQIAnAqPAqGDkr6YnyAgrq+8iC1OEdXSmesGZ-wIKiApRSSllM8caHWkDqnb10F5LA+5UgNKaZ0qGVCiCDwqIjawYMIaVDgDAGARh-Q-SgAgAwFQ+DwSSO8Ro5QuqIGwGdPBFwfrUIMLRbgDAsCECvtsAwnBqn9LEYM+JU0Eplhgqkn0tYXb1SbC2ZA7YpB0AIrMgiPwgW9nEiOTg6lNL9kHK2JoAhDBJmjuOS6ulvJG24JEbykh-bpA4rOHOL1vLP28seby25vIbgIhfQBTBLlwtVLMg4ABRTwuQA5goLOUmgkLcklRAAyk2Qxoi6AIvAAwErjSly-nxVhgzpYWKMQAoBNjKrVUNaqCB1Imy4U7kwNZtCNl71OPQxWgyRHKtVLhF6IczXDPdY0pxCRKWsByYw6ZTx3FDPNSM+yvw6aBp9G5XkcApAID4PS3CUpOhxoDQm2gUgYm8QVa4OgMbpn7WsqqrxiSuDjOKaUh1hi2RVJALU+pkbmnxChkZN0Ho+l+tRo2oMzaElqx0O2yZXbWT3F5PMxZKRdBg1IM6Y+RACLhCYKswdXqUg5HahUJoXSOgGAivsiSeFoBdTuTREeUM9kj3aXA4dWde5vLIUmCoajO4tCqu8oYFyGiYg+HAbgl6KhHyID8v5AK4BAqICCxVnMIXlotaaLg5YqyuMmngBFBxGzNjbK2dFmLKkYpxW1fFhKzrYxJUOcldaqXIJpVdXQ9LiCMuZdIGo7KahP0MAgby+5+XCqaJwMVN9M0ZTozKuVrKS2DOnaKWdeHeSas4NquAur9WvVwwQSK-JTUU39XO7txjAHAPtcR-xijGrOo+Bo496yWlZ1He6QwDBfXlq07-YNRBQ3Wf9TGD1bBOOxpsyFpaSbZ0tpGGmxyfiovLUCSMXN+bfKun8wwLDSqzOVtiXAGtFA4sNszTpkZ+TaITM7c5u+iVV0jFqc1JGQxrB8AnbV6Z9W8ljKax2qZpaV0QTXcneIfVDBec9cUoeI87i6CvalLpA4XoMlon86RhgebZVwVKKDg51twawMkDomHJ2TUS3iMzCj9NrF+roZdzCPhhpcwo9LGby28Jy4YqQvXQkJYbQ4sWHNREDO08Tf+39Iu-wUZYsStq7FwqcFGvAi90mY8++9pHbXfucPTdw6ZAS4z8MGiErDMOHAPaiSuKt32jrQqSY9fH6SY5x0psN9VjXCnjY+1KtddSPVDq6W07U36ulbIGzkxnRZJsNdG0LpdrXf6i86wspZKyI3eZ-a0HpOyDmBDN3kaIJyzn7IyFclcz7M4PIkDcl5kHwObq+UhusKH+BoeBaCu7LklcqqewLjnlYPtkd5BRlFaKMVYoY3i0czGsaeDY2SnKnHH05R43SzVQnWWBQ5Wg7lEneX8sFbJ0V4rNdLW17QWV8qDVB72nVsP6N9OGeM7B0zKvjWWZMcm4ZKOrVWMc6Auvv8nWNxdZ5g3nqfPG59SV7DWWwsRY8aWsUMXa31tLSH1UyWAe2Y4T4snmWU3Zty3mgtgMXSYlX-GlX5Xq0t+q-vzT7eVcjbbWNjXSm3aHWtA-aEup6zohW46geg2OS-OMsauzWE2NmU2va66SyC+kum2E83A+ADuby56FYQGHczciYZQl6Y8rQHyfmHonAWAu8ZwFwkuUMAGZB+cjEjKPcKQiGyG-yfu6GtBAAQq0LWH9PBC6CHCIVtkQLnNsO0NfPnHsLgRUJ1N1CUk7m+lnCwSPN3B0KlH8hfAyNfLdjAThj-uHgRrClPjWHWORsilRjRonuELin2CnkSqxgOOxlnpSjnnwHntOPxsbIXiJiuLOIhBAGXpJtJtuNXvJrXoASgZAk3upqvofsPjPCMl3vUEZnqr3h9gPoTKzukaPklOPraiAjVFYfrDPiMKEHPm6mAUvhAZIEVkFgfvESABvnEiftFpGrFp-v6qkYmiwkTj9uqn9uTtvq5HwuILfgVs0R6E-mWi-lWpVu-tGuXIrt-sgarn-uri1u0Q3jUtUt1iDv6P1tAZsUNh3uzrsYgSLipmutvAFnBGDE0KfL8BbnLj0lgMJpOHUA7iQIkH8swS3E6APMPKPHLgXPEG8ggHLH9FnLobctgFeiOj1mcVgAABTjALbYzN5EC4IgmkHaE3KXTvEUJfGnB4LwSTiXJGBdR7CXZJDdxaGEnXYpAgwVD4KYi8C4EBa4Jny3JDDMmXI-FwZEAACUxhlxsB1xBwL22MHwuhH2x+kxumaWpOGWXagOVOwOoOix9OQYhpDgUOwewUb0BiCOVmW+ox6MqO906OcG+OJwoI4Rz8+OqpKaJO5+WplRxo1+7AwSQireoUES8OIA0SsShRPov+OgySl+S03OmSph2xsZBm-++xZmhxfauuKQGB4BxEsGbEmCZ8NQhCgJZyUuEmGQcAAAXoTGwTEg0LsJ8VgTLqSeoQgn8twT7mwSQI8qbrodwL8tSRoWctKV-lcWYZ3gJlqlkT3i3u0fkYjjaTZqfolPZjakuOUdqeAm5rPh5vUSeo0XwLWEUNgsWXwK0Qlu0Z0dGb-Avn0RsTeWZp6WueqTND6f9mqdlrqXgHlgWrROnBUcFu0a-qscsDVjKSmVlmmYupmSrtmWgZuotuAadjKAhK6LEAtgdkdkHFfAgNgMBlWQgDWfWdlKbuhSuBUA8lDP6H3C9BOZTKkXATcXGZYe0dHg2HYaitRgnnRtik4Yxq4Sxunh4ZnhSlxrnrjHxgXiysEb4YUKXjyqeDEQpvcT2okWpjWiYXznKXprOQZvOTkYuWZsudaWkSRiMvaQ5mUU5oAU8NUbQLUYeT9KhY0VRQyJhZINeQMbeWACGl0T+Y+Xvs+X5a+cMauamWMZqd+WuVMUDv+bMZ5UFG0WVisVVusfFsxVsbBeYQuhmUgVlkhdUgALJnTvAejMSnF9YK6TmynTlsXpl7FFUppIWyo1BXqAnAlZzPxkUNmHx7qnwLYGFXyinYlnx4nqa4IXn0kdBAhVS4I0InwCkLbfSQBNkravH9x0BSkXH1UwVenqoKneBvYqmRWWVFExVfkTHxWU4HB+z6khlt5mUWYFEjFWXFGbkT4VEOV7m9oADqOckgblj1-ovlmmEOYSppe0wUNwMNBYXQMNSoMYZccJOUyZoekIH5qN4Q6NJItK04tUWwtQDkrOeAFYbxBwfAYARQw5i0TgXYFYAN2oQOp4h4gsioXQu0UO3QpgowQovwKAaA6Auo8wOOFwBw28ipnx6ActIAYIrA8trxxs1wYtqouaGCCUseVGnY3YvEfY4lo4fhM4c4FUK4kghg64W4e4R4Z4F4V4t494j4L4b4H4X4P4f4gEwEatXQeAKVUtMtiMeQct-t0o1FodIAKtjKvt4tgIoJkC0t3gst8tWhkd0dv1otftvo-k7EuivIT4T4nAN4+4T4X4p4AsI4G4d4hdQgD4nAG4h4p4+4+4p4X494p4p4G4p4kwYtfN3QQAA&locale=en).

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

{% include [contact-support](../_includes/contact-support.md) %}

{% include [image-styles](../../../_includes/image-styles.md) %}