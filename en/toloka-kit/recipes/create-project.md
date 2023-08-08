# Create project

_Create a minimal working project using Toloka-Kit._

{% note info %}

Normally, it's more convenient to create a project using [Toloka interface](../../guide/concepts/project.md). Nevertheless, it's still possible to create a project, write instructions, set up input and output data fields, and configure the task interface via Toloka-Kit.

{% endnote %}

## Steps to follow

{% include [import](../_includes/recipes/import.md) %}

{% include [instantiate](../_includes/recipes/instantiate.md) %}

### 3. Configure task interface {#step-three}

Configure the task interface using the `view_spec` parameter of the [TaskSpec](../reference/toloka.client.project.task_spec.TaskSpec.md) class, define input and output data. See comments in the code below and the [{#T}](../../guide/concepts/spec.md) section for more information.

- The `image` input field contains URLs of images that need to be labeled.
- The `result` output field will receive color values.

```python
task_spec = toloka.project.task_spec.[TaskSpec](*TaskSpec)(
    # The input data contains URLs to the images you want to label.
    input_spec = {'image': toloka.project.field_spec.[UrlSpec](*UrlSpec)()},
    # The output data contains the 'result' filled with received color values.
    output_spec = {'result': toloka.project.field_spec.[StringSpec](*StringSpec)()},
    # The task interface is created using the HTML/JS/CSS editor. You can select Toloka Template Builder instead if you want.
    view_spec = toloka.project.[ClassicViewSpec](*ClassicViewSpec)(
        # Define the external assets that the interface requires.
        assets = {
            'script_urls': ['library1.js', 'library2.js']
        },
        # Specify the interface markup: image src and dimensions, title text, and input field.
        markup = '''{{img src=image width="400px" height="300px"}}
                    <p class="headerClass">Elephant color:</p>
                    {{field type="input" name="result"}}
                ''',
        # Add scripts and styles.
        script = '',
        styles = '.headerClass { font-size: 22px; };',
        # Configure additional settings.
        settings = {
            'showSkip': True,
            'showTimer': True,
            'showTitle': True,
            'showSubmit': True,
            'showFullscreen': True,
            'showInstructions': True,
            'showFinish': True,
            'showMessage': True,
            'showReward': True
        }
    )
)
```

{% note alert "Important" %}

All the code manipulations at steps 3–4 occur in your device memory. The data will only be sent to the server after calling the `create_project()` method at [step 5](#step-five).

{% endnote %}

### 4. Create project object {#step-four}

Specify a public name, description, and instructions that the Tolokers will see.

```python
new_project = toloka.[Project](*Project)(
    public_name = '<your_project_public_name>',
    public_description = '<your_project_public_description>',
    public_instructions = '<your_project_instructions_for_Tolokers>',
    task_spec = task_spec
)
```

### 5. Create project on platform {#step-five}

This actually creates a project in Toloka.

```python
new_project = toloka_client.[create_project](*create_project)(new_project)
```

### 6. Print created project ID {#step-six}

The `create_project()` request will return the [Project](../reference/toloka.client.project.Project.md) class object. You can use its attributes to print the information you need.

```python
print(new_project.id)
```

You should get an output with the created project ID which looks like this.

```bash
120798
```

## Complete code: Create project {#complete-code}

```python
import toloka.client as toloka

toloka_client = toloka.TolokaClient('PlaceYourRealApiKey_Here', 'PRODUCTION')

task_spec = toloka.project.task_spec.TaskSpec(
    input_spec={'image': toloka.project.field_spec.UrlSpec()},
    output_spec={'result': toloka.project.field_spec.StringSpec()},
    view_spec=toloka.project.ClassicViewSpec(
        assets={
            'script_urls': ['library1.js', 'library2.js']
        },
        markup='''{{img src=image width="400px" height="300px"}}
                    <p class="headerClass">Elephant color:</p>
                    {{field type="input" name="result"}}
                ''',
        script='',
        styles='.headerClass {font-size: 22px;};',
        settings={
            'showSkip': True,
            'showTimer': True,
            'showTitle': True,
            'showSubmit': True,
            'showFullscreen': True,
            'showInstructions': True,
            'showFinish': True,
            'showMessage': True,
            'showReward': True
        }
    )
)

new_project = toloka.project.Project(
    public_name = '<your_project_public_name>',
    public_description = '<your_project_public_description>',
    public_instructions = '<your_project_instructions_for_Tolokers>',
    task_spec = task_spec
)
new_project = toloka_client.create_project(new_project)
print(new_project.id)
```

{% note tip "List of classes and methods used in this recipe" %}

- _[TolokaClient](../reference/toloka.client.TolokaClient.md) class_
- _[Project](../reference/toloka.client.project.Project.md) class_
- _[TaskSpec](../reference/toloka.client.project.task_spec.TaskSpec.md) class_
- _[UrlSpec](../reference/toloka.client.project.field_spec.UrlSpec.md) class_
- _[StringSpec](../reference/toloka.client.project.field_spec.StringSpec.md) class_
- _[ClassicViewSpec](../reference/toloka.client.project.view_spec.ClassicViewSpec.md) class_
- _[create_project()](../reference/toloka.client.TolokaClient.create_project.md) method_

{% endnote %}

## See also {#see-also}

- [{#T}](../../guide/concepts/overview.md)
- [{#T}](learn-basics.md)
- [{#T}](use-cases.md)
- [{#T}](get-projects.md)
- [Toloka API: Create project](https://toloka.ai/docs/api/api-reference/#post-/projects)

[*TolokaClient]: [TolokaClient](../reference/toloka.client.TolokaClient.md) class
[*Project]: [Project](../reference/toloka.client.project.Project.md) class
[*TaskSpec]: [TaskSpec](../reference/toloka.client.project.task_spec.TaskSpec.md) class
[*UrlSpec]: [UrlSpec](../reference/toloka.client.project.field_spec.UrlSpec.md) class
[*StringSpec]: [StringSpec](../reference/toloka.client.project.field_spec.StringSpec.md) class
[*ClassicViewSpec]: [ClassicViewSpec](../reference/toloka.client.project.view_spec.ClassicViewSpec.md) class
[*create_project]: [create_project()](../reference/toloka.client.TolokaClient.create_project.md) method