# Writing instructions

When selecting a [task](../../glossary.md#task), the Toloker is first shown the instructions that you wrote. Describe what needs to be done and give examples in them.

## Why instructions are important {#section_fj5_tl3_bnb}

Good instructions help the Toloker complete the task correctly. The clarity and completeness of the instructions affect response quality and the [project's rating](project_rating_stat.md). Unclear or overly complex instructions, on the contrary, will scare off Tolokers.

If the Toloker completed the task according to the instructions, and you rejected it, they can file an [appeal](accept.md#appeal). It is important to make the instructions both clear and accurate.

Learn more about how to write simple and clear instructions on the [Toloka]({{ toloka-instruction }}) website.

## Creating instructions {#create}

When creating or editing the [project](../../glossary.md#project), enter the instructions in the **Instructions for Tolokers** editor. If necessary, insert pictures, links and tables in the visual editor or using [HTML markup](#html). To switch modes, click ![](../_images/code.svg).

To expand the editor to full screen, click ![](../_images/fullscreen.svg).

To view the instructions as seen by the Toloker, click ![](../_images/preview.svg).

## HTML markup {#html}

The HTML markup mode allows you to create user-friendly instructions. Declare and apply [CSS styles](#css) and use [allowed HTML tags](#allowed-tags).

### CSS styles {#css}

Declare styles in the `style` container or use the `style` attribute in tags to assign a style.

{% note info %}

The `style` container can be placed at the beginning or at the end of the instructions.

{% endnote %}

### Supported HTML tags {#allowed-tags}

The HTML markup supports basic tags:

- Headers from `h1` to `h6`.
- Paragraph `p` and the `div`, `pre`, and `blockquote` blocks.
- The `ol`, `ul`, and `dl` lists.
- The `table` tag for tables.
- The `a` tag for links.
- The `img` and `map` pictures.
- Text layout. For example: `span`, `strong`, `em`.

{% cut "Full list of supported tags" %}

#|
||`a`|`col`|`h1`|`img`|`span`|`td`||
||`b`|`colgroup`|`h2`|`li`|`strike`|`tfoot`||
||`big`|`dd`|`h3`|`map`|`strong`|`th`||
||`blockquote`|`div`|`h4`|`ol`|`style`|`thead`||
||`br`|`dl`|`h5`|`p`|`sub`|`tr`||
||`center`|`dt`|`h6`|`pre`|`sup`|`u`||
||`cite`|`em`|`hr`|`samp`|`table`|`ul`||
||`code`|`font`|`i`|`small`|`tbody`| ||
|#

{% endcut %}

### Unsupported HTML tags {#unsupported-tags}

You can't insert the following in the instructions:

- Scripts.
- Frames.
- Objects, audio players, or video players (the `object`, `audio` and `video` elements).

    {% note tip %}

    You can provide links to audio and video.

    {% endnote %}

Tags that are not supported are removed from the instructions when saving the project.

## Editing the instructions {#edit}

To change the instructions, go to [project editing](edit-project.md), make changes and save the project.

{% note info %}

If you edit instructions in a project that already has completed tasks, you should [notify Tolokers](qa-assign.md).

{% endnote %}

## What's next {#what_next}

- [Create a task pool](pool-main.md) in the project.
- Learn more about how to set up a project:

    - [Input and output data](incoming.md).
    - [Task interface](spec.md).
    - [Adapt a task for mobile devices](mobile.md).
    - [Setting up quality control](project-qa.md).

## See also {#see-also}

- [{#T}](edit-project.md)
- [Efficiency indicators: Quality of instructions](./efficiency-metrics/instruction-quality.md)

## Troubleshooting {#troubleshooting}

{% cut "How do I show my instructions to the Toloker inside the task so that they don't need to open or close it?" %}

There are three options:

- Put your instructions inside the task, but make sure that it doesn't clutter the interface.
- Use a side window for your instructions so that the Toloker can quickly expand or collapse them.
- Hide the instructions in an expandable section or add hints for the individual interface elements.

For best results, we recommend that you pre-select the Tolokers that meet your requirements and set up the quality control rules.

{% endcut %}

{% include [faq-video-player](../_includes/faq/project-settings/video-player.md) %}

{% include [troubleshooting-tags-disappear](../_includes/troubleshooting/project-settings/tags-disappear.md) %}

{% include [faq-different-instructions](../_includes/faq/project-settings/different-instructions.md) %}

{% include [troubleshooting-radio-attr-disappear](../_includes/troubleshooting/project-settings/radio-attr-disappear.md) %}

{% include [contact-support](../_includes/contact-support.md) %}