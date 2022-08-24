# Searching for product characteristics

{% note info %}

Run the project in the [Sandbox]({{ sandbox }}) first. This helps you avoid making mistakes and spending money on a task that isn't working right.

{% endnote %}


In projects of this type, Tolokers search for an item or for information about it online. You can use them for:
- Searching for an item, such as a product or service, by its description.
- Searching for information on a specific website, such as cities where products can be delivered on a store's website.
- Searching for information about an item online, such as a company's contact information.

In these instructions, you'll create a task in which Tolokers will search for data about businesses. Let's say you have a list of companies and you need to find their phone numbers and email addresses. In this task, Tolokers see company names and links to their websites and search for the required information about them.

## Create a project {#create-project}

#### In the interface:

1. Choose a template:

    1. Click {% if locale == "en-com" %}**Create project**{% endif %}.

    1. Select the {% if locale == "en-com" %}**Searching for product characteristics**{% endif %} template.

1. Provide general information:

    1. Enter a clear name and a short description for the project. Tolokers will see this in the task list.

    1. Optionally add a **Private comment**.

    1. Click **Save**.

1. Edit the task interface in the editor you selected:

    #### Template Builder

    1. The task interface describes how the elements should be arranged in the task.

    Use the {% if locale == "en-com" %}[ready-made code](https://clck.ru/VC555){% endif %} for this project with pre-configured validation and task layout.

    [Learn more about setting up conditions]({{ tb-conditions }}) in Template Builder.

    1. Click **Show specifications** to see the input and output data fields.

    Input data fields are created from the code on the **Example of input data** tab.

    The output data fields depend on the components that use `data.output` and values supported by it.

    Learn more about [input and output data fields]({{ tb-create-specs }}) in the Template Builder Help.

    - Input data fields:
    - `title` — A string with the name of the organization.

    - `url` — The organization's website `URL`.

    - Output data fields:
    - `phone` — A string for entering the organization's phone number.
    - `email` — A string for entering the organization's email address.
    - `not_found` — A flag indicating that the organization has no contact information.

    1. Save the changes.

    #### HTML/CSS/JS editor

    In the **Data specification** section, you can configure the input and output fields.

    #### What are input and output data?

    **Input data** is types of objects that are passed to the Toloker for completing the task. For example, this could be a text, an image, or geographic coordinates.

    **Output data** is types of objects that you receive after the task is completed. For example, this could be one of several response options, typed text, or an uploaded file.

    Learn more about [input and output data fields](incoming.md).

    {% note info %}

    You can set up validation of output data using [regular expressions](incoming.md#section_y2v_qqq_tlb). This lets you formalize user responses. The example below uses regular expressions that set the required format for email addresses and phone numbers.

    Regular expressions let you run a project with an overlap greater than one so that each task is completed by several people. In this case, you can skip reviewing assignments and checking each assignment's results and trust average data.

    {% endnote %}

    1. Click ![](../_images/other/code.png) to switch graphic mode to JSON format.

    1. In the {% if locale == "en-com" %}**Input data**{% endif %} field, enter the following code:

    ```json
    {
    "url": {
    "type": "url",
    "hidden": false,
    "required": true
    },
    "title": {
    "type": "string",
    "hidden": false,
    "required": false
    }
    }
    ```

    1. In the {% if locale == "en-com" %}**Output data**{% endif %} field, enter the following code:

    ```json
    {
    "email": {
    "type": "string",
    "hidden": false,
    "pattern": "^[a-zA-Zа-яА-ЯёЁ0-9\\._-]+@[a-zA-Zа-яА-ЯёЁ0-9\\._-]+\\.[a-zA-Zа-яА-ЯёЁ]{2,}$",
    "required": false
    },
    "phone": {
    "type": "string",
    "hidden": false,
    "pattern": "^\\+?[0-9()\\s-]{4,}$",
    "required": false
    },
    "not_found": {
    "type": "boolean",
    "hidden": false,
    "required": false
    }
    }
    ```

    1. In the {% if locale == "en-com" %}**Task interface**{% endif %} section, you can customize the appearance of tasks for Tolokers.

    Learn more about the [task interface](spec.md).

    Fill in the **HTML**, **JS**, and **CSS** blocks.

    #### Code for the **HTML** block
    {% if locale == "en-com" %}
    ```html
    <!-- Buttons to go to the company's website and search for the company's name in Yandex -->
    <div class="left">
    <div class="title">{{title}}
    </div>
    <div class="site-buttons">
    {{button label="Go to site" action=false href=url}}
    <a href="https://yandex.ru/search/?text={{title}}" target="_blank" class="btn_ya">Search Yandex</a>
    </div>
    <!-- Fields for phone numbers and email addresses. The data format is checked using regular expressions. The expression is written in the "Pattern" parameter of the "phone" and "email" output fields. -->
    <div class="output-fields">
    <label><span>Phone</span>{{field type="input" name="phone" placeholder="8 800 800 88 88"}}</label>
    <!-- The Toloker can only enter numbers, hyphens, plus sign (+), spaces, and brackets. The "+" symbol is only allowed in the first position. General format: +7(459)123-45-67, 8 800 123 45 67 -->
    <label><span>Email</span>{{field type="input" name="email" placeholder="example@example.com"}}</label>
    <!-- The Toloker can only enter Latin letters, dots, plus and minus signs, and underscores. General format: test.example@example.com -->
    </div>
    <Checkbox>
    {{field class="site-buttons"type="checkbox" name="not_found" label="No contacts"}}
    </div>
    ```
    {% endif %}
    #### Code for the **JS** block
    {% if locale == "en-com" %}
    ```javascript
    exports.Task = extend(TolokaHandlebarsTask, function (options) {
    TolokaHandlebarsTask.call(this, options);
    }, {
    // Show an error message if the data is entered incorrectly or fields are empty.
    _addError: function (message, field, errors) {
    errors || (errors = {
    task_id: this.getOptions().task.id,
    errors: {}
    }});

    errors.errors[field] = {
    message: message
    };

    return errors;
    },

    // Add `https://` at the beginning of the link, if none.
    _prepareURL: function (url) {
    if (!/^\s*https?:\/\//i.test(url)) {
    url = 'http://' + url.trim();
    }

    return url;
    },

    // Set the field status.
    _renderField: function(values) {
    if (this.getWorkspaceOptions().isReadOnly) return;

    for (const field of ['email', 'phone']) {
    if (this.getField(field)) {
    const impl = this.getField(field).getImplementation();
    if (impl.options.disabled !== values.not_found) {
    impl.options.disabled = values.not_found;
    impl.render();
    }

    $('[name="' + field + '"]', this.getDOMElement())
    .parents('.field')
    .toggleClass('field_readonly', values.not_found);
    }
    }
    $('.popup_type_error', this.getDOMElement()).removeClass('popup_visible');
    },

    setSolutionOutputValues: function (values) {
    this._renderField(values);

    TolokaHandlebarsTask.prototype.setSolutionOutputValues.call(this, values);
    },

    onRender: function() {
    this._renderField(this.getSolution().output_values);
    },

    // This data will be passed to the Handlebars part of the template.
    getTemplateData: function () {
    const data = TolokaHandlebarsTask.prototype.getTemplateData.call(this);

    // Add `http://` to the beginning of the link, if necessary.
    data.url = this._prepareURL(data.url);

    return data;
    },

    // We check the responses when the task is submitted.
    validate: function (solution) {
    let errors;
    const output = solution.output_values;

    if (output.not_found) {
    delete output.email;
    delete output.phone;

    } else {
    const fields = ['email', 'phone'];

    // We show an error if none of the fields are filled in.
    if (!Object.entries(solution.output_values).find(e => fields.includes(e[0]) && e[1])) {
    for (const field of fields) {
    errors = this._addError(this.getWorkspaceOptions().translations['field:error:REQUIRED'], field, errors);
    }
    }

    delete output.not_found;
    }

    solution.output_values = output;
    return errors || TolokaHandlebarsTask.prototype.validate.call(this, solution);
    }
    }});

    function extend(ParentClass, constructorFunction, prototypeHash) {
    constructorFunction = constructorFunction || function () { };
    prototypeHash = prototypeHash || {};

    if (ParentClass) {
    constructorFunction.prototype = Object.create(ParentClass.prototype);
    }

    for (var i in prototypeHash) {
    constructorFunction.prototype[i] = prototypeHash[i];
    }

    return constructorFunction;
    }
    ```
    {% endif %}
    #### Code for the **CSS** block
    {% if locale == "en-com" %}
    ```css
    /* Task on the page */
    .task {
    width: 450px;
    }

    /* The "Find in Yandex" button */
    .btn_ya {
    font-size: 13px;
    margin-left: 10px;
    color: #0065D9;
    }

    /* Title with the organization name */
    .title {
    padding: 10px;
    border-radius: 5px;
    font-size: 18px;
    line-height: 24px;
    }

    /* Phone and email input fields*/
    . output-fields {
    display: table;
    font-size: 13px;
    border-spacing: 0 5px;
    }

    .output-fields > label {
    display: table-row;
    margin-bottom: 5px;
    }

    .output-fields > label > span {
    display: table-cell;
    text-align: left;
    padding-right: 10px;
    padding-left: 10px;
    }

    .output-fields > label > .field {
    margin: 0;
    display: table-cell;
    width: 100%;
    }

    /* Button to go to the organization's website*/
    . site-buttons {
    margin: 10px;
    margin-left: 5;
    }

    /* Task display on mobile devices. */

    @media (pointer: coarse) {
    .field__hotkey {
    display:none;
    }
    }

    @media (max-width: 980px) {
    .task {
    width: initial;
    }
    .popup__text {
    width: auto;
    }
    }

    ```
    {% endif %}

    1. Click ![](../_images/tutorials/image-segmentation/preview-button.png) to see the Toloker's view of the task.

    {% note info %}

    The project preview shows one task with standard data. You can define the number of tasks to show on the page later.

    {% endnote %}

    1. In the window that opens, check if the task options work correctly:

    1. Answer the question.

    1. In the lower-right corner, click {% if locale == "en-com" %}**Submit**{% endif %}.

    1. Exit preview mode.

    1. Save the changes.

1. 1. Write short and clear instructions. Describe what needs to be done and give examples in them.

    You can prepare instructions in HTML format, then copy and paste into the editor. Click **<>** to switch to HTML mode.

    1. Click **Finish**.

Learn more about working with the project in the [Project](project.md) section.

## Create a pool {#create-pool}

A pool is a set of paid tasks sent out for completion at the same time.

1. Open the page of the project for searching for information online.

1. Click the {% if locale == "en-com" %}**Add a pool**{% endif %} button.

1. Specify the {% if locale == "en-com" %}**Pool name**{% endif %}.

1. Filter Tolokers in the {% if locale == "en-com" %}**Audience**{% endif %} block in the {% if locale == "en-com" %}**Tolokers**{% endif %} section.

    To make the task available only to Tolokers who speak Russian:

    1. Click {% if locale == "en-com" %}**Add filter**{% endif %}.

    1. Find the {% if locale == "en-com" %}**Audience presets**{% endif %} block in the list and choose the {% if locale == "en-com" %}**Russian speaking users**{% endif %} set of filters.

    1. Assign a [skill](../../glossary.md#skill-ru) to Tolokers who participate in the project to search for information online. This ensures that completed assignments are only checked by Tolokers without a skill, meaning those who haven't completed any tasks in this project.

    Click {% if locale == "en-com" %}**+Add skill**{% endif %} and specify the skill name, such as `Search for information`.

    Tasks in pools will automatically be available in the web version of Toloka and the mobile app. If you want to change the default settings and limit the visibility of the task for any of the versions, add the {% if locale == "en-com" %}**Client**{% endif %} filter and select the desired value: {% if locale == "en-com" %}**Toloka web version**{% endif %} or {% if locale == "en-com" %}**Toloka for mobile**{% endif %}.

1. (optional) In the {% if locale == "en-com" %}**Speed/quality balance**{% endif %} section, specify the desired quality level. Improving quality may reduce the speed of task completion because the pool will be available to fewer Tolokers. Learn more in the [Speed/quality balance](adjust.md) section.

1. In the {% if locale == "en-com" %}**Price**{% endif %} block, find the {% if locale == "en-com" %}**Price per task suite**{% endif %} field and specify the price. For example, `0.01`.

    #### What is a task suite?

    A task suite can contain one or several tasks that are shown on the same page. If the tasks are simple, you can add 10-20 tasks per suite. Don't make task suites too long because it slows down loading speed for Tolokers.

    Tolokers get paid for completing the entire task suite.

    The number of tasks per suite is set when [uploading tasks](#tasks_upload).

    Learn more about how to set a [fair price](dynamic-pricing.md#section_wb1_lhl_vlb).

1. [Quality control rules](../../glossary.md#quality-control-ru) allow you to filter out careless Tolokers.

    #### For a project with an overlap greater than one

    In the {% if locale == "en-com" %}**Quality control**{% endif %} block, set the {% if locale == "en-com" %}**Captcha frequency**{% endif %}, for example, to {% if locale == "en-com" %}**Middle**{% endif %}.

    Add the following quality control rules:

    1. {% if locale == "en-com" %}**Control tasks**{% endif %} — filters out Tolokers who often make mistakes in the control tasks.

    1. Click {% if locale == "en-com" %}**Add a quality control rule**{% endif %}.

    1. Find the {% if locale == "en-com" %}**Rules**{% endif %} block in the list and choose {% if locale == "en-com" %}**Control tasks**{% endif %}.

    1. Set a rule for the control task: if the {% if locale == "en-com" %}**number of responses**{% endif %} to the control questions is **≥ 3** and {% if locale == "en-com" %}**correct responses (%)**{% endif %} to the control questions is **< 60**, then {% if locale == "en-com" %}**ban**{% endif %} the Toloker {% if locale == "en-com" %}**from the project**{% endif %} for {% if locale == "en-com" %}**10 days**{% endif %}. Specify **Control task** as a reason.

    This means that if a Toloker completed more than three control tasks and gave incorrect answers in more than 60% of them, they will be blocked and won't be able to complete tasks on this project for 10 days.

    1. {% if locale == "en-com" %}**Fast responses**{% endif %} —Filters out Tolokers who respond too quickly.

    1. In the {% if locale == "en-com" %}**Recent task suites to use**{% endif %} field, enter the number of the Toloker's recently completed assignments. For example, `10`.
    1. In the {% if locale == "en-com" %}**Minimum time per task suite**{% endif %} field, enter the time in seconds. For example, `20`.
    1. Set a rule for a fast response: if the {% if locale == "en-com" %}**number of fast responses**{% endif %}** ≥ 1**, then {% if locale == "en-com" %}**ban**{% endif %} {% if locale == "en-com" %}**on requester**{% endif %} for {% if locale == "en-com" %}**10 days**{% endif %}. In the {% if locale == "en-com" %}**Reason**{% endif %} field, enter **Fast responses**.

    This means that a user who completes at least one assignment in less than 20 seconds won't be able to access your tasks for 10 days.

    1. {% if locale == "en-com" %}**Captcha**{% endif %} — Prevents robots from completing tasks.

    1. In the field {% if locale == "en-com" %}**Recent captchas to use**{% endif %} enter the number of recent task suites completed by the Toloker. For example, `10`.
    1. Set a captcha rule: if the {% if locale == "en-com" %}**number of responses**{% endif %}** ≥ 5** and {% if locale == "en-com" %}**correct responses (%) **{% endif %}**< 65**, then {% if locale == "en-com" %}**ban**{% endif %} {% if locale == "en-com" %}**on project**{% endif %} for {% if locale == "en-com" %}**10 days**{% endif %}. In the {% if locale == "en-com" %}**Reason**{% endif %} field, enter **Captcha**.

    This means that if a Toloker enters captchas correctly in less than 65% of cases, they won't be able to access tasks in the project for 10 days.

    1. {% if locale == "en-com" %}**Skipped assignments**{% endif %} — Filters out Tolokers who skip multiple assignments in a row.

    Set a rule for [skipped tasks](pool_statistic-pool.md#skipped-tasks) : if {% if locale == "en-com" %}**task suites skipped in a row**{% endif %}** ≥ 4**, then {% if locale == "en-com" %}**suspend**{% endif %} {% if locale == "en-com" %}**in pool**{% endif %} for {% if locale == "en-com" %}**10 days**{% endif %}. In {% if locale == "en-com" %}**Reason**{% endif %}, enter **Skipped assignments**.

    This means that a user who skips four or more assignments won't be able to access the pool for 10 days.

    1. Set overlap, which is the number of Tolokers to complete the same task. In the {% if locale == "en-com" %}**Task overlap**{% endif %} section of the {% if locale == "en-com" %}**Quality control**{% endif %} block, specify the value of the {% if locale == "en-com" %}**The number of Tolokers to complete every task**{% endif %} field. For tasks of this type it is usually `3-5`.

    #### For a project with tasks that are reviewed

    In the {% if locale == "en-com" %}**Quality control**{% endif %} block, turn on the {% if locale == "en-com" %}**Non-automatic acceptance**{% endif %} option.

    #### What is non-automatic acceptance (assignment review)?

    The [non-automatic acceptance](offline-accept.md) option allows you to review [completed assignments](../../glossary.md#submitted-answers-ru) before accepting them and paying for them. If the Toloker didn't follow instructions, you can reject the assignment. The maximum allowed period for the review is set in the **Deadline** field.

    In the {% if locale == "en-com" %}**Review period in days**{% endif %} field, specify the number of days for checking the task.

    Add the following quality control blocks:

    - {% if locale == "en-com" %}**Recompletion of rejected assignments**{% endif %} — sends the tasks you rejected to other Tolokers according to the specified rules.

    1. Click {% if locale == "en-com" %}**Add a quality control rule**{% endif %}.

    1. Find the {% if locale == "en-com" %}**Rules**{% endif %} block in the list and select {% if locale == "en-com" %}**Processing rejected and accepted assignments**{% endif %}.

    1. Set a rule for rejected assignments: if {% if locale == "en-com" %}**assignment becomes rejected**{% endif %}, then {% if locale == "en-com" %}**extend overlap by**{% endif %} **1**. Turn on the {% if locale == "en-com" %}**Open pool if closed**{% endif %} option.

    This means that the rejected task will be returned to the pool and shown to another Toloker.

    - {% if locale == "en-com" %}**Results of assignment review**{% endif %} — restricts the pool access for Tolokers who often make mistakes.

    Set a rule for rejected tasks: if {% if locale == "en-com" %}**total reviewed responses**{% endif %} **≥ 3** and {% if locale == "en-com" %}**rejected responses (%)**{% endif %} **> 35**, then {% if locale == "en-com" %}** ban**{% endif %} {% if locale == "en-com" %}** on requester**{% endif %} for {% if locale == "en-com" %}** 15 days**{% endif %}.

    This means that if 35% or more of a Toloker's responses are rejected, the Toloker is banned and can't access your tasks for 15 days. The rule takes effect after 3 responses of the Toloker are reviewed.

    {% note info %}

    You can copy quality control settings from another pool. To do this, in the {% if locale == "en-com" %}**Tolokers**{% endif %} section of the {% if locale == "en-com" %}**Audience**{% endif %} block, click {% if locale == "en-com" %}**copy them from another pool**{% endif %}.

    {% endnote %}

1. Adjust the pool {% if locale == "en-com" %}**parameters**{% endif %}.

    In the **Additional settings** block, specify {% if locale == "en-com" %}**Time per task suite**{% endif %}. This should give Tolokers enough time to read the instructions, load the task, search for information, and respond. For example, `1200` seconds.

1. Click {% if locale == "en-com" %}**Create a pool**{% endif %}.


## Upload tasks {#upload-file}
 {% if locale == "en-com" %}
Download the sample upload file. You can find it on the pool page. There are links to **files** with regular, control, and training tasks. Use it to prepare your own [file](../../glossary.md#tsv-file-definition-ru) with tasks.
{% endif %}
1. On the pool page, click {% if locale == "en-com" %}**Upload**{% endif %}. In the window that opens, you can also download a sample file.

1. In the window that opens, configure the file upload settings.

    #### For a project with an overlap greater than one

    1. 1. Choose {% if locale == "en-com" %}**Smart mixing**{% endif %}.

    1. In the {% if locale == "en-com" %}**General tasks**{% endif %} field, specify `9`.

    1. In the {% if locale == "en-com" %}**Training tasks**{% endif %} field, specify `0`.

    1. In the {% if locale == "en-com" %}**Control tasks**{% endif %} field, specify `1`.

    1. Click {% if locale == "en-com" %}**Upload**{% endif %}.

    1. In the window that opens, choose the file with tasks to upload and click {% if locale == "en-com" %}**Open**{% endif %}.

    1. In the window that opens, check the number of tasks and click {% if locale == "en-com" %}**Add**{% endif %}.

    1. Create a [control task](../../glossary.md#control-task-ru).

    1. Click {% if locale == "en-com" %}**Edit**{% endif %}.

    {% note info %}

    If you selected something else instead of **smart mixing**, click **Edit**. If this button is missing, delete the file and upload it again.

    {% endnote %}

    1. In the window that opens, click {% if locale == "en-com" %}**Create control tasks**{% endif %}.

    1. In the window that opens, in the {% if locale == "en-com" %}**Create control task**{% endif %} section, mark the **result** item on the left.

    1. Choose the correct answer to the question.

    1. Click {% if locale == "en-com" %}**Save and go to next**{% endif %}.

    1. Exit the task editing mode.

    {% note info %}

    In small pools, control tasks should be 10% of all tasks. Include different versions of correct responses in equal amounts. View the distribution of responses on the {% if locale == "en-com" %}**Edit tasks**{% endif %} page, {% if locale == "en-com" %}**Control tasks**{% endif %} tab.

    {% endnote %}

    #### For a project with tasks that are reviewed

    1. Choose {% if locale == "en-com" %}**Set manually**{% endif %}.

    1. In the {% if locale == "en-com" %}**Tasks per suite**{% endif %} field, specify `1`.

    1. Click {% if locale == "en-com" %}**Upload**{% endif %}.

    1. In the window that opens, choose the file with tasks to upload and click {% if locale == "en-com" %}**Open**{% endif %}.

    1. In the window that opens, check the number of tasks and click {% if locale == "en-com" %}**Add**{% endif %}.

    Click ![](../_images/other/b-start-pool.png) to start the pool.


## Get the results {#get-results}

After Tolokers complete your tasks, get the results.

#### For a project with an overlap greater than one

On the pool page, click {% if locale == "en-com" %}**Download results**{% endif %}. In the window that opens, click {% if locale == "en-com" %}**Download results**{% endif %}.

#### For a project with tasks that are reviewed

1. On the pool page, click {% if locale == "en-com" %}**Download results**{% endif %}. In the window that opens:

    1. In {% if locale == "en-com" %}**Status**{% endif %} leave only the {% if locale == "en-com" %}**Submitted**{% endif %} option enabled.

    1. In {% if locale == "en-com" %}**Columns**{% endif %} leave only the {% if locale == "en-com" %}**assignment ID**{% endif %} option enabled.

    1. Disable the {% if locale == "en-com" %}**Separate assignments with empty row**{% endif %} option.

    1. Click {% if locale == "en-com" %}**Download results**{% endif %}.

## Let Tolokers check the responses {#check-up-project}

If you used {% if locale == "en-com" %}**Non-automatic acceptance**{% endif %} in the project for searching for information online, send the results to Tolokers for the review as tasks. [Learn more](offline-accept.md) about non-automatic acceptance.

1. Create another project using the [Blank]({{ blank }}) template. See below what settings should be specified for this project.
1. Create a task interface that shows:
    - Company name.
    - Email address and phone number of the company.
    - Response options:

1. Add a pool and set {% if locale == "en-com" %}**Overlap**{% endif %} to 3 in it.
1. To make this task available to Tolokers who didn't search the web for information on your project, use a {% if locale == "en-com" %}**filter**{% endif %}.

    1. In the {% if locale == "en-com" %}**Tolokers**{% endif %} section, click {% if locale == "en-com" %}**Add filter**{% endif %}.

    1. Find {% if locale == "en-com" %}**Skills**{% endif %} in the list and choose {% if locale == "en-com" %}**Choose skill**{% endif %}.

    1. In the {% if locale == "en-com" %}**Choose a skill**{% endif %} field, choose **Search for information**.

    1. In the **?** field specify `=`. Leave the {% if locale == "en-com" %}**Missing**{% endif %} field blank.

1. Upload tasks to the pool and start it.
1. When the pool is fully completed, start [aggregation of results](result-aggregation.md).
1. Accept tasks for information search that were completed without errors. Reject the rest, specifying the reason. As soon as you reject the tasks, they are sent for re-completion.


## Troubleshooting {#troubleshooting}

#### How do I use different numbers of response options for different questions?

Use [concatenation](t-components/helpers.md#concat), for example:
```
{{field type="checkbox" name=(concat "result." @index ) label=(concat "checkbox –
          " @index) size="L"}}
```

#### How can I do it in JS so that if the checkbox is selected, the link is not required, but if the link is inserted, the checkbox is cleared?

1. See how this is implemented in the  template.
1. To solve the second problem, you can add another validation like this:{% if locale == "en-com" %}
    ```
    if (solution.output_values.url && solution.output_values.check) {return {task_id:
    this.getTask().id,errors: {'url': {code: ''Insert a link or check the box if the site doesn't exist'}}}}
    ```
    {% endif %}

#### How do I enable loading audio files in preview mode?

You can't check loading of audio files in the preview mode, but you can do it in the sandbox if you do your task. To do this, register in the sandbox as a Toloker and add the Toloker username to your trusted list on the **Tolokers** page. For more information, see [this post](sandbox.md).

#### My Tolokers can't upload a file with the assignment

If none of the Tolokers can submit the assignment, the most likely reason is JS validation. Run JS validation again.

Export your project to the sandbox and try to complete the task in the sandbox yourself.

#### How do I deselect a radio button?

You can't deselect a radio button. You can only select another radio button as a different response option.

#### What do I do if the radio button attributes are displayed correctly in the preview, but disappear after saving?

If the tags or attributes disappear after you save the instructions (for example, `checked="true"`), it means that they are not supported. For the full list of tags that can be used in the instructions, see the [Guide](instruction.md#html-yes).


{% include [contact-support](../_includes/contact-support-help.md) %}
