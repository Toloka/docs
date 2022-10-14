# Writing instructions

When selecting a task, the Toloker is first shown the instructions that you wrote. Describe what needs to be done and give examples in them.

## Why instructions are important {#section_fj5_tl3_bnb}

Good instructions help the Toloker complete the task correctly. The clarity and completeness of the instructions affect response quality and the [project's rating](project_rating_stat.md). Unclear or overly complex instructions, on the contrary, will scare off Tolokers.

If the Toloker completed the task according to the instructions, and you rejected it, they can file an appeal. It is important to make the instructions both clear and accurate.

Learn more about how to write simple and clear instructions on the [Toloka]({{ toloka-instruction }}) website.

## Creating instructions {#create}

Write text, format it, and insert pictures, links and tables in the visual editor or using [HTML markup](#html). To switch modes, click ![](../_images/code.svg).

To expand the editor to full screen, click ![](../_images/fullscreen.svg).

To view the instructions as seen by the Toloker, click ![](../_images/preview.svg).

## HTML markup {#html}

The HTML markup mode allows you to create user-friendly instructions. Declare and apply [CSS styles](#css) and use [allowed HTML tags](#html-yes).

#### CSS styles
Declare styles in the `style` container or use the `style` attribute in tags to assign a style.

{% note info %}

The `style` container can be placed at the beginning or at the end of the instructions.

{% endnote %}


#### Supported HTML tags

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
|| a  
b  
big  
blockquote  
br  
center  
cite  
code |
col  
colgroup  
dd  
div  
dl  
dt  
em  
font |
h1  
h2  
h3  
h4  
h5  
h6  
hr  
i |
img  
li  
map  
ol  
p  
pre  
samp  
small |
span  
strike  
strong  
style  
sub  
sup  
table  
tbody |
td  
tfoot  
th  
thead  
tr  
u  
ul ||
|#

{% endcut %}

#### Unsupported HTML tags
You can't insert the following in the instructions:
- Scripts.
- Frames.
- Objects, audio players, or video players (the `object`, `audio` and `video` elements).

    {% note info %}

    You can provide links to audio and video.

    {% endnote %}

Tags that are not supported are removed from the instructions when saving the [project](../../glossary.md#project-ru).

## Editing the instructions {#edit}

To change the instructions, go to project editing, make changes and save the project.

{% note info %}

If you edit instructions in a project that already has completed tasks, you should [notify Tolokers](qa-assign.md).

{% endnote %}


## What's next {#what_next}

- [Create a task pool in the project](pool-main.md).
- Learn more about how to set up a project:
    - [Input and output data](incoming.md).
    - [Task interface](spec.md).
    - [Adapt a task for mobile devices](mobile.md).
    - [Setting up quality control](project-qa.md).



## Troubleshooting {#troubleshooting}

{% cut "How do I show my instructions to the Toloker inside the task so that they don't need to open or close it?" %}

There are three options:
- Put your instructions inside the task, but make sure that it doesn't clutter the interface.
- Use [a side window]({{ instr-in-form-of-side-window }}) for your instructions so that the Toloker can quickly expand or collapse them.
- [Hide the instructions in an expandable section]({{ hints-questions }}) or add hints for the individual interface elements.
For best results, we recommend that you pre-select the Tolokers that meet your requirements and set up the quality control rules.

{% endcut %}

{% cut "Can I add a video player or audio player to my instructions?" %}

No, but you can add links to them.

{% endcut %}

{% cut "Some tags disappear after I save the instructions." %}

You can't use unsupported tags because they are deleted when you save the project. [List of supported tags](instruction.md#html).

{% endcut %}

{% cut "How do I create different instructions for the training pool and main pools?" %}

By default, the project instructions are displayed in the training pool. To use separate instructions for the training pool, deselect **Use project instructions**. Don't forget to update the training instructions if you change something in the general task instructions.

{% endcut %}

{% cut "What do I do if the radio button attributes are displayed correctly in the preview, but disappear after saving?" %}

If the tags or attributes disappear after you save the instructions (for example, `checked="true"`), it means that they are not supported. For the full list of tags that can be used in the instructions, see the [Guide](instruction.md#html-yes).

{% endcut %}

{% include [contact-support](../_includes/contact-support-help.md) %}
