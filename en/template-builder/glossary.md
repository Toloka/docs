# Terms and definitions

## General terms {#common}

Component

: The task interface consists of ready-made components representing JSON objects with a specified structure. Components are categorized depending on their purpose, such as data entry fields, conditions, or actions. The name of the component is specified in the `type` property in the format `<category>.<name>`.

: [ List of components](reference/index.md)

Configuration

: Description of your interface in the JSON format. This is also the name of the panel in the editor where you write this code.

Input and output data {#input-output-data}

: _Input data_ is the source data you want to display or use. For example, links to images that will be shown to performers. Use the `data.input` component to access the input data.

: _Output_ is the data you receive after the task is completed, like the performer's answers to your questions. Use the `data.output` component to access the output data.

: See the [Read and write](operations/input-output-data.md) instructions to learn about working with data.

Internal data

: The data available only from within the task. This data is not saved to the results. Use this data to calculate or store intermediate values. To access the internal data, use the `data.internal` component.

: See the [Read and write](operations/input-output-data.md) instructions to learn about working with data.

Pool {#pool}

: A set of paid tasks sent out for completion at the same time.

Task

: Task performed in [Toloka]({{ toloka }}). In Template Builder, you can create an interface for such tasks.

## Categories of components {#components}

Action

: A category of components that perform actions, such as open a link, display a message, or play a video. Some components work with data. For example, they can change the value from `true` to `false`.

: [List of actions](reference/actions.md)

Condition

: Component category to check whether the expression matches the specified condition. You can use them to check that the text is entered in a field.

: [List of conditions](reference/conditions.md)

Data entry field

: Category of components that create data entry fields, such as text fields or drop-down lists.

: [List of data entry fields](reference/fields.md)

Element layout

: Category of components used to arrange the interface elements, such as in columns or side-by-side.

: [List of layout options](reference/layouts.md)

Helper

: Category of components for auxiliary operations, such as working with arrays.

: [List of helpers](reference/helpers.md)

Plugin

: Category of components to enable advanced features. For example, `plugin.hotkeys` lets you set up shortcuts.

: [List of plugins](reference/plugins.md)

View

: Category of components for creating visual interface elements. Examples include text, list, audio player, or image.

: [List of views](reference/views.md)

[![](_images/buttons/contact-support.svg)](concepts/support.md)