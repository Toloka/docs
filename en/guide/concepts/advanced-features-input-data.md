# Add description fields

You may need to change the input specification by adding new fields to it. For example, if the location is far away or difficult to find, you can add a field for describing the location in detail. Or you can provide any other additional information that is needed in each task.

{% cut "What it looks like" %}

Before:

![](../_images/tutorials/advanced-features/af-input-data-1.png)

After:

![](../_images/tutorials/advanced-features/af-input-data-2.png)

{% endcut %}

For your convenience, here is ready-made code for the “Monitoring field objects” template with two new input fields added. Use it to check your own code. You can find our additions to the code by searching for the word “customization”.

{% cut "Ready-made code" %}

{% cut "HTML block" %}

```html
{{#if reviewMode}}
    <div class="header-review">
        <div class="header-review__title">
            not_var{{texts.task_title}}
        </div>
        <div class="header-review__buttons">
            {{#if (equal verdict "ok")}}
                <div class="header-review__btn header-review__btn_green">
                    not_var{{texts.btn_ok.title}}
                </div>
            {{/if}}
            {{#if (equal verdict "no_obj")}}
                <div class="header-review__btn header-review__btn_red">
                    not_var{{texts.btn_no_obj.title}}
                </div>
            {{/if}}
            {{#if (equal verdict "no_access")}}
                <div class="header-review__btn header-review__btn_red">
                    not_var{{texts.btn_no_access.title}}
                </div>
            {{/if}}
        </div>
    </div>
not_var{{else}}
    <div class="header">
        not_var{{texts.task_title}}
    </div>
{{/if}}

<div class="info">
    {{#if reviewMode}}
        <div class="info__review">
            <div class="info__review-block">
                <div class="info__title">
                    not_var{{texts.info_name}}
                </div>
                <div class="info__content">
                    not_var{{name}}
                </div>
            </div>
            <div class="info__review-block">
                <div class="info__title">
                    not_var{{texts.info_address}}
                </div>
                <div class="info__content">
                    not_var{{address}}
                </div>
            </div>
        </div>
    not_var{{else}}
        <div class="info__block">
            <div class="info__title">
                not_var{{texts.info_name}}
            </div>
            <div class="info__content">
                not_var{{name}}
            </div>
        </div>
        <div class="info__block">
            <div class="info__title">
                not_var{{texts.info_address}}
            </div>
            <div class="info__content">
                not_var{{address}}
            </div>
        </div>
    {{/if}}
    <div class="info__block">
        <div class="info__title">
            not_var{{texts.info_description}}
        </div>
        <div class="info__content">
            not_var{{product}}
        </div>
    </div>

    <!-- customization fragment start -->
    <div class="info__block">
      <div class="info__title">
        not_var{{texts.new_input_1__title}}
      </div>
      <div class="info__content">
        not_var{{new_input_1}}
      </div>
    </div>
    <div class="info__block">
      <div class="info__title">
        not_var{{texts.new_input_2__title}}
      </div>
      <div class="info__content">
        not_var{{new_input_2}}
      </div>
    </div>
    <!-- customization fragment end -->

    <div class="info__block">
        <div class="info__content">
            <a href=not_var{{image}} target="_blank" class="info__link">Link to an object image</a>
        </div>
    </div>
</div>

{{#if reviewMode}}
    <div class="review">
        <div class="review__map">
            <div id="{{concat 'map_' id}}" style="width: 100%; height: 400px;"></div>
        </div>
        {{#if (equal verdict "ok")}}
            <div class="review__block">
                <div class="review__title">
                    not_var{{texts.btn_ok.question_1.title}}
                </div>
                <div class="review__imgs-grid">
                    {{#each imgs_obj}}
                        <div class="review__grid-item">
                            <div class="review__grid-inner">
                                <img src="not_var{{this}}" class="review__img" data-rotationdeg="0">
                                <div class="review__rotate-panel">
                                    <span class="review__rotate review__rotate_left">←</span>
                                    <span class="review__rotate review__rotate_right">→</span>
                                </div>
                            </div>
                        </div>
                    {{/each}}
                </div>
            </div>
            <div class="review__block">
                <div class="review__title">
                    not_var{{texts.btn_ok.question_2.title}}
                </div>
                <div class="review__comment">
                    {{field type="textarea" name="more_info.comment" width="100%" rows=5}}
                </div>
            </div>
            <div class="review__block">
                <div class="review__title">
                    not_var{{texts.btn_ok.question_2.radios.title}}
                </div>
                <div class="review__fields">
                    {{#each texts.btn_ok.question_2.radios.items}}
                        <div>{{field type="radio" name=this.name label=this.label value=this.value size="L" validation-show="top-left"}}</div>
                    {{/each}}
                </div>
            </div>
            <div class="review__block">
                <div class="review__title">
                    not_var{{texts.btn_ok.question_2.checkboxes.title}}
                </div>
                <div class="review__fields">
                    {{#each texts.btn_ok.question_2.checkboxes.items}}
                        <div>{{field type="checkbox" name=this.name label=this.label size="L" validation-show="top-left"}}</div>
                    {{/each}}
                </div>
            </div>
            <div class="review__block">
                <div class="review__title">
                    not_var{{texts.btn_ok.question_3.title}}
                </div>
                <div class="review__imgs-grid">
                    {{#each imgs_address}}
                        <div class="review__grid-item">
                            <div class="review__grid-inner">
                                <img src="not_var{{this}}" class="review__img" data-rotationdeg="0">
                                <div class="review__rotate-panel">
                                    <span class="review__rotate review__rotate_left">←</span>
                                    <span class="review__rotate review__rotate_right">→</span>
                                </div>
                            </div>
                        </div>
                    {{/each}}
                </div>
            </div>
            {{#if comment}}
                <div class="review__block">
                    <div class="review__title">
                        not_var{{texts.btn_ok.question_4.title}}
                    </div>
                    <div class="review__comment">
                        {{field type="textarea" name="comment" width="100%" rows=5}}
                    </div>
                </div>
            {{/if}}
        {{/if}}
        {{#if (equal verdict "no_obj")}}
            <div class="review__block">
                <div class="review__title">
                    not_var{{texts.btn_no_obj.question_1.title}}
                </div>
                <div class="review__imgs-grid">
                    {{#each imgs_around_obj}}
                        <div class="review__grid-item">
                            <div class="review__grid-inner">
                                <img src="not_var{{this}}" class="review__img" data-rotationdeg="0">
                                <div class="review__rotate-panel">
                                    <span class="review__rotate review__rotate_left">←</span>
                                    <span class="review__rotate review__rotate_right">→</span>
                                </div>
                            </div>
                        </div>
                    {{/each}}
                </div>
            </div>
            <div class="review__block">
                <div class="review__title">
                    not_var{{texts.btn_no_obj.question_2.title}}
                </div>
                <div class="review__imgs-grid">
                    {{#each imgs_address}}
                        <div class="review__grid-item">
                            <div class="review__grid-inner">
                                <img src="not_var{{this}}" class="review__img" data-rotationdeg="0">
                                <div class="review__rotate-panel">
                                    <span class="review__rotate review__rotate_left">←</span>
                                    <span class="review__rotate review__rotate_right">→</span>
                                </div>
                            </div>
                        </div>
                    {{/each}}
                </div>
            </div>
            {{#if comment}}
                <div class="review__block">
                    <div class="review__title">
                        not_var{{texts.btn_no_obj.question_3.title}}
                    </div>
                    <div class="review__comment">
                        {{field type="textarea" name="comment" width="100%" rows=5}}
                    </div>
                </div>
            {{/if}}
        {{/if}}
        {{#if (equal verdict "no_access")}}
            <div class="review__block">
                <div class="review__title">
                    not_var{{texts.btn_no_access.question_1.title}}
                </div>
                <div class="review__imgs-grid">
                    {{#each imgs_around_no_access}}
                        <div class="review__grid-item">
                            <div class="review__grid-inner">
                                <img src="not_var{{this}}" class="review__img" data-rotationdeg="0">
                                <div class="review__rotate-panel">
                                    <span class="review__rotate review__rotate_left">←</span>
                                    <span class="review__rotate review__rotate_right">→</span>
                                </div>
                            </div>
                        </div>
                    {{/each}}
                </div>
            </div>
            <div class="review__block">
                <div class="review__title">
                    not_var{{texts.btn_no_access.question_2.title}}
                </div>
                <div class="review__imgs-grid">
                    {{#each imgs_address}}
                        <div class="review__grid-item">
                            <div class="review__grid-inner">
                                <img src="not_var{{this}}" class="review__img" data-rotationdeg="0">
                                <div class="review__rotate-panel">
                                    <span class="review__rotate review__rotate_left">←</span>
                                    <span class="review__rotate review__rotate_right">→</span>
                                </div>
                            </div>
                        </div>
                    {{/each}}
                </div>
            </div>
            <div class="review__block">
                <div class="review__title">
                    not_var{{texts.btn_no_access.question_3.title}}
                </div>
                <div class="review__comment">
                    {{field type="textarea" name="comment" width="100%" rows=5}}
                </div>
            </div>
        {{/if}}
    </div>
not_var{{else}}
    <div class="main">
        <div class="main__title">
            Select a task completion option:
        </div>
        <div class="main__container">
            <div class="main__popup main__popup_hidden">No answer selected</div>
            <div class="main__block">
                <div class="main__btn main__btn_green">
                    not_var{{texts.btn_ok.title}}
                </div>
                <div class="main__content">
                    <div class="main__content-block">
                        <div class="main__content-title main__content-title_req">
                            not_var{{texts.btn_ok.question_1.title}}
                        </div>
                        <div class="main__text">
                            not_var{{texts.btn_ok.question_1.description}}
                        </div>
                        <div class="main__ex">
                            <a href="not_var{{texts.btn_ok.question_1.example_link_1}}" target="_blank" class="main__ex-link">Example</a>
                        </div>
                        <div class="main__imgs">
                            {{field type="file-img" name="imgs_obj" camera=true preview=true compress=false validation-show="top-left"}}
                        </div>
                    </div>
                    <div class="main__content-block">
                        <div class="main__content-title main__content-title_req">
                            not_var{{texts.btn_ok.question_2.title}}
                        </div>
                        <div class="main__text">
                            not_var{{texts.btn_ok.question_2.description}}
                        </div>
                        <div class="main__comment">
                            {{field type="textarea" name="more_info.comment" width="100%" rows=5 validation-show="top-left"}}
                        </div>
                        <div class="main__fields">
                            <div class="main__radios-title">
                                not_var{{texts.btn_ok.question_2.radios.title}}
                            </div>
                            <div class="main__radios-items">
                                {{#each texts.btn_ok.question_2.radios.items}}
                                    <div>{{field type="radio" name=this.name label=this.label value=this.value size="L" validation-show="top-left"}}</div>
                                {{/each}}
                            </div>
                        </div>
                        <div class="main__fields">
                            <div class="main__checkboxes-title">
                                not_var{{texts.btn_ok.question_2.checkboxes.title}}
                            </div>
                            <div class="main__checkboxes-items">
                                {{#each texts.btn_ok.question_2.checkboxes.items}}
                                    <div>{{field type="checkbox" name=this.name label=this.label size="L" validation-show="top-left"}}</div>
                                {{/each}}
                            </div>
                        </div>
                    </div>
                    <div class="main__content-block">
                        <div class="main__content-title main__content-title_req">
                            not_var{{texts.btn_ok.question_3.title}}
                        </div>
                        <div class="main__text">
                            not_var{{texts.btn_ok.question_3.description}}
                        </div>
                        <div class="main__ex">
                            <a href="not_var{{texts.btn_ok.question_3.example_link_1}}" target="_blank" class="main__ex-link">Example</a>
                        </div>
                        <div class="main__imgs">
                            {{field type="file-img" name="imgs_address" camera=true validation-show="top-left"}}
                        </div>
                    </div>
                    <div class="main__content-block">
                        <div class="main__content-title">
                            not_var{{texts.btn_ok.question_4.title}}
                        </div>
                        <div class="main__text">
                            not_var{{texts.btn_ok.question_4.description}}
                        </div>
                        <div class="main__comment">
                            {{field type="textarea" name="comment" width="100%" rows=5 validation-show="top-left"}}
                        </div>
                    </div>
                </div>
            </div>
            <div class="main__block">
                <div class="main__btn main__btn_red">
                    not_var{{texts.btn_no_obj.title}}
                </div>
                <div class="main__content">
                    <div class="main__content-block">
                        <div class="main__text main__text_req">
                            not_var{{texts.btn_no_obj.question_1.description}}
                        </div>
                        <div class="main__imgs">
                            {{field type="file-img" name="imgs_around_obj" camera=true validation-show="top-left"}}
                        </div>
                    </div>
                    <div class="main__content-block">
                        <div class="main__text main__text_req">
                            not_var{{texts.btn_no_obj.question_2.description}}
                        </div>
                        <div class="main__ex">
                            <a href="not_var{{texts.btn_no_obj.question_2.example_link_1}}" target="_blank" class="main__ex-link">Example</a>
                        </div>
                        <div class="main__imgs">
                            {{field type="file-img" name="imgs_address" camera=true validation-show="top-left"}}
                        </div>
                    </div>
                    <div class="main__content-block">
                        <div class="main__content-title">
                            not_var{{texts.btn_no_obj.question_3.title}}
                        </div>
                        <div class="main__text">
                            not_var{{texts.btn_no_obj.question_3.description}}
                        </div>
                        <div class="main__comment">
                            {{field type="textarea" name="comment" width="100%" rows=5 validation-show="top-left"}}
                        </div>
                    </div>
                </div>
            </div>
            <div class="main__block">
                <div class="main__btn main__btn_red main__btn_no-access">
                    not_var{{texts.btn_no_access.title}}
                </div>
                <div class="main__content">
                    <div class="main__content-block">
                        <div class="main__text main__text_req">
                            not_var{{texts.btn_no_access.question_1.description}}
                        </div>
                        <div class="main__ex">
                            <a href="not_var{{texts.btn_no_access.question_1.example_link_1}}" target="_blank" class="main__ex-link">Example</a>
                        </div>
                        <div class="main__imgs">
                            {{field type="file-img" name="imgs_around_no_access" camera=true validation-show="top-left"}}
                        </div>
                    </div>
                    <div class="main__content-block">
                        <div class="main__text main__text_req">
                            not_var{{texts.btn_no_access.question_2.description}}
                        </div>
                        <div class="main__ex">
                            <a href="not_var{{texts.btn_no_access.question_2.example_link_1}}" target="_blank" class="main__ex-link">Example</a>
                        </div>
                        <div class="main__imgs">
                            {{field type="file-img" name="imgs_address" camera=true validation-show="top-left"}}
                        </div>
                    </div>
                    <div class="main__content-block">
                        <div class="main__content-title main__content-title_req">
                            not_var{{texts.btn_no_access.question_3.title}}
                        </div>
                        <div class="main__text">
                            not_var{{texts.btn_no_access.question_3.description}}
                        </div>
                        <div class="main__comment">
                            {{field type="textarea" name="comment" width="100%" rows=5 validation-show="top-left"}}
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </div>
{{/if}}
```

{% endcut %}

{% cut "JavaScript block" %}

```javascript
var texts = {
    'task_title': 'Field objects monitoring',
    'info_name': 'Name:',
    'info_address': 'Address:',
    'info_description': 'Object description:',

    // customization fragment start
    'new_input_1__title': 'Input field 1:',
    'new_input_2__title': 'Input field 2:',
    // customization fragment end

    'btn_ok': {
        'title': 'I found the object',
        'question_1': {
            'title': 'Object photo',
            'description': 'Take at least 4 photos of the object from different sides so that they clearly show the object, its attributes, contents (if any), and location in relation to the surrounding area.',
            'example_link_1': 'https://mt-content-public.s3.yandex.net/instructions/toloka_field_templates/obj_field_1-min.png'
        },
        'question_2': {
            'title': 'Additional information',
            'description': 'Here's the text that asks the Toloker to enter the relevant information about the object or its characteristics in the field below.',
            'radios': {
                'title': 'This is a single choice question:',
                'items': [
                    {
                        'name': 'more_info.radio',
                        'value': 'radio_1',
                        'label': 'Option 1'
                    },
                    {
                        'name': 'more_info.radio',
                        'value': 'radio_2',
                        'label': 'Option 2'
                    },
                    {
                        'name': 'more_info.radio',
                        'value': 'radio_3',
                        'label': 'Option 3'
                    }
                ]
            },
            'checkboxes': {
                'title': 'This is a multiple choice question:',
                'items': [
                    {
                        'name': 'more_info.checkboxes.checkboxe_1',
                        'label': 'Option 1'
                    },
                    {
                        'name': 'more_info.checkboxes.checkboxe_2',
                        'label': 'Option 2'
                    },
                    {
                        'name': 'more_info.checkboxes.checkboxe_3',
                        'label': 'Option 3'
                    }
                ]
            }
        },
        'question_3': {
            'title': 'Photo of the address plate',
            'description': 'Take a photo of the information address sign or the address plate of the neighboring building on the same street.',
            'example_link_1': 'https://mt-content-public.s3.yandex.net/instructions/toloka_field_templates/obj_field_2_3_4-min.png'
        },
        'question_4': {
            'title': 'Comment',
            'description': 'If your photos don't contain all the necessary information, add details here.'
        }
    },
    'btn_no_obj': {
        'title': 'I'm here, but the object is missing',
        'question_1': {
            'title': 'Photos of the place from all sides',
            'description': 'Takes photos of the place or the surrounding area from all sides so that they clearly show that the object is missing.'
        },
        'question_2': {
            'title': 'Photo of the address plate',
            'description': 'Take a photo of the information address sign or the address plate of the neighboring building on the same street.',
            'example_link_1': 'https://mt-content-public.s3.yandex.net/instructions/toloka_field_templates/obj_field_2_3_4-min.png'
        },
        'question_3': {
            'title': 'Comment',
            'description': 'Try to find out why the object is missing and specify the reason in the comment.'
        }
    },
    'btn_no_access': {
        'title': 'The object can't be reached',
        'question_1': {
            'title': 'Photo of the surrounding area',
            'description': 'Attach a photo that shows the surrounding area and the reason why you couldn't reach the object.',
            'example_link_1': 'https://mt-content-public.s3.yandex.net/instructions/toloka_field_templates/obj_field_5-min.png'
        },
        'question_2': {
            'title': 'Photo of the address plate',
            'description': 'Take a photo of the information address sign or the address plate of the neighboring building on the same street.',
            'example_link_1': 'https://mt-content-public.s3.yandex.net/instructions/toloka_field_templates/obj_field_2_3_4-min.png'
        },
        'question_3': {
            'title': 'Mandatory comment',
            'description': 'Specify the reason why you couldn't reach the object.'
        }
    }
};

// Maximum distance of a Toloker from a store (in kilometers).
var MAX_DISTANCE = 1;

var verdictsOut = ['ok', 'no_obj', 'no_access'];

var injectMaps = function(locale) {
    return new Promise(function(resolve, reject) {
        var script = document.createElement('script');

        script.async = true;
        script.src = "https://api-maps.yandex.ru/2.1/?load=package.full,vectorEngine.preload&lang=" + locale + "_" + locale.toUpperCase() + "&csp=true";
        script.addEventListener('load', resolve);
        script.addEventListener('error', reject);
        script.addEventListener('abort', reject);

        document.head.appendChild(script);
    });
};

var map;

exports.Assignment = extend(TolokaAssignment, function (options) {
    TolokaAssignment.call(this, options);

    var workspaceOptions = this.getWorkspaceOptions();

    if (workspaceOptions.isReviewMode) {
        map = injectMaps('ru');
    }
}, {});

exports.Task = extend(TolokaHandlebarsTask, function (options) {
    TolokaHandlebarsTask.call(this, options);
}, {
    getTemplateData: function() {
        var data = TolokaHandlebarsTask.prototype.getTemplateData.apply(this, arguments);
        var workspaceOptions = this.getWorkspaceOptions();
        var outputValues = this.getSolution().output_values;

        this.setSolutionOutputValue('coordinates', data.coordinates);
        this.setSolutionOutputValue('address', data.address);

        data.id = this.getTask().id;
        data.texts = texts;

        if (workspaceOptions.isReviewMode) {
            data.reviewMode = true;

            if (outputValues.imgs_obj && outputValues.imgs_obj.length > 0) {
                data.imgs_obj = [];
                for (var i = 0; i < outputValues.imgs_obj.length; i++) {
                    data.imgs_obj.push(workspaceOptions.apiOrigin + '/api/attachments/' + outputValues.imgs_obj[i] + '/preview');
                }
            }

            if (outputValues.imgs_address && outputValues.imgs_address.length > 0) {
                data.imgs_address = [];
                for (var i = 0; i < outputValues.imgs_address.length; i++) {
                    data.imgs_address.push(workspaceOptions.apiOrigin + '/api/attachments/' + outputValues.imgs_address[i] + '/preview');
                }
            }

            if (outputValues.imgs_around_obj && outputValues.imgs_around_obj.length > 0) {
                data.imgs_around_obj = [];
                for (var i = 0; i < outputValues.imgs_around_obj.length; i++) {
                    data.imgs_around_obj.push(workspaceOptions.apiOrigin + '/api/attachments/' + outputValues.imgs_around_obj[i] + '/preview');
                }
            }

            if (outputValues.imgs_around_no_access && outputValues.imgs_around_no_access.length > 0) {
                data.imgs_around_no_access = [];
                for (var i = 0; i < outputValues.imgs_around_no_access.length; i++) {
                    data.imgs_around_no_access.push(workspaceOptions.apiOrigin + '/api/attachments/' + outputValues.imgs_around_no_access[i] + '/preview');
                }
            }

            if (outputValues.comment) {
                data.comment = outputValues.comment;
            }

            if (outputValues.verdict) {
                data.verdict = outputValues.verdict;
            }

            if (outputValues.more_info) {
                data.more_info = $.extend({}, outputValues.more_info);
            }
        } else {
            data.reviewMode = false;

            var assId = this.getOptions().assignment._options.assignment.id;
            var taskID = this.getTask().id;
            var solutionStorage = this.storage.getItem('solution_' + assId);

            if (solutionStorage && solutionStorage[taskID]) {
                this.setSolutionOutputValue('verdict', solutionStorage[taskID].verdict);
            }
        }

        return data;
    },
    initFastFileSelector: function() {
        var $el = $(this.getDOMElement()),
            sources = [],
            type = '',
            audioRecorder = $el.find('.audioRecorder');

        $el.find('.field_file-img__upload_camera').each(function (i,el) {
            $(el).on('click',function () {
                sources = ['CAMERA'];
                type = 'IMAGE';
            })
        });

        $el.find(".field_file-img__label").prepend($("<span/>", {class: "field_file-img__upload gallery"}));

        $el.find('.gallery').on('click',function () {
            sources = ['GALLERY'];
            type = 'IMAGE';
        });

        var baseGetFile = this.file.getFile.bind(this.file);
        this.file.getFile = function(options) {
            var promise = baseGetFile(
                _.extend(options, {
                    sources: _.isEmpty(sources) ? ["GALLERY", "CAMERA"] : sources
                })
            );
            sources = ["GALLERY", "CAMERA"];

            return promise;
        };
    },
    setSolution: function(solution) {
        TolokaHandlebarsTask.prototype.setSolution.apply(this, arguments);

        var workspaceOptions = this.getWorkspaceOptions();
        var assId = this.getOptions().assignment._options.assignment.id;
        var taskID = this.getTask().id;

        if (this.rendered) {
            if (!workspaceOptions.isReviewMode && !workspaceOptions.isReadOnly) {
                var isEmpty = true;
                var radiosName = '';
                var checkboxesName = '';

                if (texts.btn_ok.question_2.radios && texts.btn_ok.question_2.radios.items && texts.btn_ok.question_2.radios.items.length > 0) {
                    radiosName = texts.btn_ok.question_2.radios.items[0].name.split('.')[1];
                }

                if (texts.btn_ok.question_2.checkboxes && texts.btn_ok.question_2.checkboxes.items && texts.btn_ok.question_2.checkboxes.items.length > 0) {
                    checkboxesName = texts.btn_ok.question_2.checkboxes.items[0].name.split('.')[1];
                }

                if (checkboxesName !== '') {
                    for (var i in solution.output_values.more_info[checkboxesName]) {
                        if (solution.output_values.more_info[checkboxesName][i]) {
                            isEmpty = false;
                        }
                    }

                    if (!isEmpty) {
                        this.getFields()[texts.btn_ok.question_2.checkboxes.items[0].name][0].hideError();
                    }
                }

                if (!solution.output_values.verdict || solution.output_values.verdict === '') {
                    var newMoreInfo = {};

                    if (checkboxesName !== '') {
                        newMoreInfo[checkboxesName] = {};

                        for (var i in solution.output_values.more_info[checkboxesName]) {
                            newMoreInfo[checkboxesName][i] = false;
                        }
                    }

                    if (radiosName !== '') {
                        newMoreInfo[radiosName] = '';
                    }

                    if (solution.output_values.more_info && solution.output_values.more_info.comment) {
                        newMoreInfo.comment = '';
                    }

                    if (solution.output_values.more_info) {
                        this.setSolutionOutputValue('more_info', newMoreInfo);
                    }

                    if (checkboxesName !== '') {
                        for (var i in solution.output_values.more_info[checkboxesName]) {
                            this.getField('more_info.' + checkboxesName + '.' + i).getImplementation().render();
                        }
                    }

                    if (radiosName !== '') {
                        var radios = this.getField('more_info.' + radiosName);

                        for (var i = 0; i < radios.length; i++) {
                            radios[i].getImplementation().render();
                        }
                    }

                    if (newMoreInfo.comment === '') {
                        this.getField('more_info.comment').getImplementation().render();
                    }
                }
            }
        }
    },
    onRender: function() {
        this.rendered = true;

        var task = this.getDOMElement();
        var that = this;
        var workspaceOptions = this.getWorkspaceOptions();
        var outputValues = this.getSolution().output_values;

        if (workspaceOptions.isReviewMode) {
            var reviewImgs = task.querySelectorAll('.review__grid-item');
            var initMap = this.initMap.bind(this);

            for (var i = 0; i < reviewImgs.length; i++) {
                reviewImgs[i].addEventListener('click', this.handleImg);
            }

            map.then(function() {
                ymaps.ready(initMap);
            });
        } else if (workspaceOptions.isReadOnly) {
            var mainBlocks = task.querySelectorAll('.main__block');
            var selectedBtnId = verdictsOut.indexOf(outputValues.verdict);

            for (var f = 0; f < mainBlocks.length; f++) {
                if (f === selectedBtnId) {
                    mainBlocks[f].querySelector('.main__content').classList.add('main__content_active');
                    mainBlocks[f].querySelector('.main__btn').classList.add('main__btn_active');
                } else {
                    mainBlocks[f].classList.add('main__block_hidden');
                }
            }

            this.initFastFileSelector();

        } else {
            var btns = task.querySelectorAll('.main__btn');
            var mainBlocks = task.querySelectorAll('.main__block');
            var assId = this.getOptions().assignment._options.assignment.id;
            var taskID = this.getTask().id;
            var solutionStorage = this.storage.getItem('solution_' + assId);

            if (solutionStorage && solutionStorage[taskID]) {
                if (solutionStorage[taskID].selectedBtnId >= 0) {
                    var selectedBtnId = solutionStorage[taskID].selectedBtnId;

                    for (var f = 0; f < mainBlocks.length; f++) {
                        if (f === selectedBtnId) {
                            mainBlocks[f].querySelector('.main__content').classList.add('main__content_active');
                            mainBlocks[f].querySelector('.main__btn').classList.add('main__btn_active');
                        } else {
                            mainBlocks[f].classList.add('main__block_hidden');
                        }
                    }
                }
            }

            for (var i = 0; i < btns.length; i++) {
                btns[i].addEventListener('click', this.handleBtn.bind(this, i, mainBlocks));
            }

            this.initFastFileSelector();

            task.querySelector('.main__popup').addEventListener('click', this.handleMainPopup);
        }
    },
    initMap: function() {
        var inputValues = this.getTask().input_values;
        var outputValues = this.getSolution().output_values;

        if (!inputValues.coordinates || inputValues.coordinates === '') {
            return;
        }

        var coordinates = inputValues.coordinates.split(',');

        var myMap = new ymaps.Map('map_' + inputValues.id, {
            center: coordinates,
            zoom: 15
        });

        var shop = new ymaps.GeoObject({
            geometry: {
                type: "Point",
                coordinates: coordinates
            },
            properties: {
                iconContent: 'Object'
            }
        }, {
            preset: 'islands#greenStretchyIcon'
        });

        myMap.geoObjects.add(shop);

        if (outputValues.worker_coordinates) {
            var workerCoordinates = outputValues.worker_coordinates.split(',');

            var worker = new ymaps.GeoObject({
                geometry: {
                    type: "Point",
                    coordinates: workerCoordinates
                },
                properties: {
                    iconContent: 'Toloker'
                }
            }, {
                preset: 'islands#blueStretchyIcon'
            });

            myMap.geoObjects.add(worker);
        }
    },
    handleImg: function(e) {
        var img = e.currentTarget.querySelector('.review__img');

        if (e.target.classList.contains('review__rotate_left')) {
            img.dataset.rotationdeg = parseInt(img.dataset.rotationdeg, 10) - 90;
            img.style.transform = 'rotate(' + img.dataset.rotationdeg + 'deg)';
        } else if (e.target.classList.contains('review__rotate_right')) {
            img.dataset.rotationdeg = parseInt(img.dataset.rotationdeg, 10) + 90;
            img.style.transform = 'rotate(' + img.dataset.rotationdeg + 'deg)';
        }

        if (e.target.classList.contains('review__img') || e.target.classList.contains('review__grid-inner')) {
            e.currentTarget.querySelector('.review__grid-inner').classList.toggle('review__grid-inner_zoomed');
        }
    },
    handleBtn: function(i, mainBlocks, e) {
        var mainContent = e.currentTarget.parentNode.querySelector('.main__content');
        var outputValues = this.getSolution().output_values;
        var task = this.getDOMElement();
        var assId = this.getOptions().assignment._options.assignment.id;
        var taskID = this.getTask().id;
        var solutionStorage = this.storage.getItem('solution_' + assId);
        var newSolution = {};
        newSolution[taskID] = {};

        if (!e.currentTarget.classList.contains('main__btn_active')) {
            task.querySelector('.main__popup').classList.add('main__popup_hidden');

            this.setSolutionOutputValue('verdict', verdictsOut[i]);

            e.currentTarget.classList.add('main__btn_active');
            mainContent.classList.add('main__content_active');
            for (var j = 0; j < mainBlocks.length; j++) {
                if (j !== i) {
                    mainBlocks[j].classList.add('main__block_hidden');
                }
            }

            if (assId) {
                if (!solutionStorage) {
                    newSolution[taskID].selectedBtnId = i;
                    newSolution[taskID].verdict = verdictsOut[i];

                    this.storage.setItem('solution_' + assId, newSolution, new Date().getTime() + 21600000);
                } else {
                    if (!solutionStorage[taskID]) {
                        solutionStorage[taskID] = {};
                    }

                    solutionStorage[taskID].selectedBtnId = i;
                    solutionStorage[taskID].verdict = verdictsOut[i];

                    this.storage.setItem('solution_' + assId, solutionStorage, new Date().getTime() + 21600000);
                }
            }
        } else {
            var fields = this._fields;
            var deleteBtnsLength = task.querySelectorAll('.main .file__delete').length;

            for (var h = 0; h < deleteBtnsLength; h++) {
                $(task).find('.main .file__delete').first().trigger('click');
            }

            this.setSolutionOutputValue('verdict', '');
            this.setSolutionOutputValue('comment', '');

            e.currentTarget.classList.remove('main__btn_active');
            mainContent.classList.remove('main__content_active');

            for (var key in fields) {
                if (fields.hasOwnProperty(key)) {
                    for (var p = 0; p < fields[key].length; p++) {
                        fields[key][p].hideError();
                    }
                }
            }

            for (var j = 0; j < mainBlocks.length; j++) {
                if (j !== i) {
                    mainBlocks[j].classList.remove('main__block_hidden');
                }
            }

            if (assId) {
                if (!solutionStorage) {
                    newSolution[taskID].selectedBtnId = -1;
                    newSolution[taskID].verdict = '';
                    this.storage.setItem('solution_' + assId, newSolution, new Date().getTime() + 21600000);
                } else {
                    if (!solutionStorage[taskID]) {
                        solutionStorage[taskID] = {};
                    }

                    solutionStorage[taskID].selectedBtnId = -1;
                    solutionStorage[taskID].verdict = '';
                    this.storage.setItem('solution_' + assId, solutionStorage, new Date().getTime() + 21600000);
                }
            }
        }
    },
    // A function for determining the distance between points by their latitude and longitude.
    _getDistanceBetweenCoords: function(lat1, lon1, lat2, lon2) {
        var Earth = 6371; // Radius of the Earth in km
        var x =
            (((lon2 - lon1) * Math.PI) / 180) *
            Math.cos((((lat1 + lat2) / 2) * Math.PI) / 180);
        var y = ((lat2 - lat1) * Math.PI) / 180;
        return Earth * Math.sqrt(x * x + y * y);
    },
    // A function for determining the distance between two points.
    _getDistance: function(coords1, coords2) {
        var coordFirst = {
            lat: parseFloat(coords1.split(",")[0]),
            lon: parseFloat(coords1.split(",")[1])
        };
        var coordSecond = {
            lat: parseFloat(coords2.split(",")[0]),
            lon: parseFloat(coords2.split(",")[1])
        };

        var dist = this._getDistanceBetweenCoords(
            coordFirst.lat,
            coordFirst.lon,
            coordSecond.lat,
            coordSecond.lon
        );
        return dist;
    },
    checkUserPosition: function(inputValues, outputValues) {
        if (outputValues["worker_coordinates"] &&
            inputValues["coordinates"] && this._getDistance(outputValues["worker_coordinates"], inputValues["coordinates"]) > MAX_DISTANCE) {
            return true;
        } else {
            return false;
        }
    },
    addError: function (message, field, errors) {
        errors || (errors = {
            task_id: this.getOptions().task.id,
            errors: {}
        });
        errors.errors[field] = {
            message: message
        };

        return errors;
    },
    onValidationFail: function (errors) {
        TolokaTask.prototype.onValidationFail.call(this, errors);

        var task = this.getDOMElement();

        _.each(errors.errors, function (error, fieldName) {
            if (fieldName === '__TASK__') {
                this.showTaskError(error.message);
            } else if (fieldName === 'verdict') {
                task.querySelector('.main__popup').classList.remove('main__popup_hidden');
            } else {
                var fields = this._fields[fieldName];

                if (fields) {
                    if (fields[0].el.classList.contains('field_type_radio')) {
                        fields[0].showError(error);
                    } else {
                        for (var i = 0; i < fields.length; i++) {
                            fields[i].showError(error);
                        }
                    }
                }
            }
        }.bind(this));
    },
    handleMainPopup: function(e) {
        e.currentTarget.classList.add('main__popup_hidden');
    },
    validate: function (solution) {
        this.errors = null;
        var task = this.getDOMElement();
        var input_values = this.getTask().input_values;

        if (!solution.output_values.verdict || solution.output_values.verdict === '') {
            this.errors = this.addError('No answer selected', "verdict", this.errors);
        } else if (solution.output_values.verdict === 'ok') {
            var isEmpty = true;
            var radiosName = '';
            var checkboxesName = '';

            if (texts.btn_ok.question_2.radios && texts.btn_ok.question_2.radios.items && texts.btn_ok.question_2.radios.items.length > 0) {
                radiosName = texts.btn_ok.question_2.radios.items[0].name.split('.')[1];
            }

            if (texts.btn_ok.question_2.checkboxes && texts.btn_ok.question_2.checkboxes.items && texts.btn_ok.question_2.checkboxes.items.length > 0) {
                checkboxesName = texts.btn_ok.question_2.checkboxes.items[0].name.split('.')[1];
            }

            if (!solution.output_values.imgs_obj || solution.output_values.imgs_obj.length === 0) {
                this.errors = this.addError('Attach photos of the object', "imgs_obj", this.errors);
            } else if (solution.output_values.imgs_obj.length < 4) {
                this.errors = this.addError('There must be at least 4 photos of the object', "imgs_obj", this.errors);
            }

            if (!solution.output_values.more_info || !solution.output_values.more_info.comment || solution.output_values.more_info.comment.trim() === '') {
                this.errors = this.addError('Write a comment', "more_info.comment", this.errors);
            }

            if (radiosName !== '') {
                if (!solution.output_values.more_info[radiosName]) {
                    this.errors = this.addError('Select an answer', "more_info." + radiosName, this.errors);
                }
            }

            if (checkboxesName !== '') {
                for (var i in solution.output_values.more_info[checkboxesName]) {
                    if (solution.output_values.more_info[checkboxesName][i]) {
                        isEmpty = false;
                    }
                }

                if (isEmpty) {
                    this.errors = this.addError('Select an answer', texts.btn_ok.question_2.checkboxes.items[0].name, this.errors);
                }
            }

            if (!solution.output_values.imgs_address || solution.output_values.imgs_address.length === 0) {
                this.errors = this.addError('Attach a photo of the address plate', "imgs_address", this.errors);
            }
        } else if (solution.output_values.verdict === 'no_obj') {
            if (!solution.output_values.imgs_around_obj || solution.output_values.imgs_around_obj.length === 0) {
                this.errors = this.addError('Attach photos of the surrounding area', "imgs_around_obj", this.errors);
            } else if (solution.output_values.imgs_around_obj.length < 4) {
                this.errors = this.addError('There must be at least 4 photos of the surrounding area', "imgs_around_obj", this.errors);
            }

            if (!solution.output_values.imgs_address || solution.output_values.imgs_address.length === 0) {
                this.errors = this.addError('Attach a photo of the address plate', "imgs_address", this.errors);
            }
        } else if (solution.output_values.verdict === 'no_access') {
            if (!solution.output_values.imgs_around_no_access || solution.output_values.imgs_around_no_access.length === 0) {
                this.errors = this.addError('Attach photos of the location', "imgs_around_no_access", this.errors);
            } else if (solution.output_values.imgs_around_no_access.length < 4) {
                this.errors = this.addError('There must be at least 4 photos of the location', "imgs_around_no_access", this.errors);
            }

            if (!solution.output_values.imgs_address || solution.output_values.imgs_address.length === 0) {
                this.errors = this.addError('Attach a photo of the address plate', "imgs_address", this.errors);
            }

            if (!solution.output_values.comment || solution.output_values.comment.trim() === '') {
                this.errors = this.addError('Write a comment', "comment", this.errors);
            }
        }

        if (this.checkUserPosition.call(this, input_values, solution.output_values)) {
            this.errors = this.addError('You are too far from the organization', "__TASK__", this.errors);
        }

        if (!solution.output_values.worker_coordinates) {
            this.errors = this.addError('Couldn't get your coordinates. Please enable location tracking.', "__TASK__", this.errors);
        }

        return this.errors || TolokaHandlebarsTask.prototype.validate.call(this, solution);
    },
    onDestroy: function() {

    }
});

exports.TaskSuite = extend(TolokaHandlebarsTaskSuite, function (options) {
    TolokaHandlebarsTaskSuite.call(this, options);
}, {
    onValidationFail: function (errors) {
        TolokaTaskSuite.prototype.onValidationFail.call(this, errors);

        var tasks = this.getDOMElement().querySelectorAll('.task');

        if (errors && errors.length > 0) {
            var firstError;

            for (var i = 0; i < errors.length; i++) {
                if (errors[i]) {
                    firstError = errors[i];
                    break;
                }
            }

            var firstTaskWithError = tasks[parseInt(firstError.task_id, 10)];
            this.focusTask(parseInt(firstError.task_id, 10));

            _.each(firstError.errors, function (error, fieldName) {
                if (fieldName === '__TASK__') {
                    firstTaskWithError.querySelector('.task__error').scrollIntoView();
                } else if (fieldName === 'verdict') {
                    firstTaskWithError.querySelector('.main__popup').scrollIntoView();
                } else {
                    firstTaskWithError.querySelector('.main__btn_active').parentNode.querySelector('.popup_visible').scrollIntoView();
                }
            }.bind(this));
        }
    },
    focusTask: function(index) {
        TolokaTaskSuite.prototype.focusTask.call(this, index, 'withoutScroll');
    }
});

function extend(ParentClass, constructorFunction, prototypeHash) {
    constructorFunction = constructorFunction || function () {};
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

{% endcut %}

{% endcut %}

Now let's see how to add these fields manually.

#### Editing the input specification

Add two new strings to the input data specification:

`new_input_1` — The first string with new input data.

`new_input_2` — The second string with new input data.

#### Editing HTML

1. The HTML code consists of blocks describing various interface elements. Each block may contain other blocks within it. There may be several nesting levels. For example, the block with a response button description contains other blocks with input fields. Each field contains other elements, such as a title and a comment field.

    Each block looks like this:

    ```html
    `<div class="block_name">`
    <!-- code for the block that may contain nested blocks -->
    ...
    </div>
    ```

1. Find the `info` block responsible for displaying the input specification. It contains the `info__block` blocks that describe individual fields within the input specification. Paste the following code after the required field:

    ```html
    <div class="info__block">
    <div class="info__title">
    not_var{{texts.new_input_1__title}}
    </div>
    <div class="info__content">
    not_var{{new_input_1}}
    </div>
    </div>
    <div class="info__block">
    <div class="info__title">
    not_var{{texts.new_input_2__title}}
    </div>
    <div class="info__content">
    not_var{{new_input_2}}
    </div>
    </div>
    ```

    This code places the new input fields one after another both in the Toloker mode and in the acceptance mode.

1. There is also a second option when two fields are displayed one after another for the Toloker, and next to each other for the requester.

    In the `info` block, find the `info__review` block that contains several `info__review-block` blocks. After the desired `info__review-block` block, insert the blocks with new input fields:

    ```html
    <!-- In one line in acceptance mode -->
    <div class="info__review-block">
    <div class="info__title">
    not_var{{texts.new_input_1__title}}
    </div>
    <div class="info__content">
    not_var{{new_input_1}}
    </div>
    </div>
    <div class="info__review-block">
    <div class="info__title">
    not_var{{texts.new_input_2__title}}
    </div>
    <div class="info__content">
    not_var{{new_input_2}}
    </div>
    </div>
    ```

    In the `info` block, find the `info__block` blocks between the strings `not_var{{else}}` and `{{/if}}`. After the desired `info__review-block` block, insert the blocks with new input fields:

    ```html
    <!-- One after another in Toloker mode -->
    <div class="info__block">
    <div class="info__title">
    not_var{{texts.new_input_1__title}}
    </div>
    <div class="info__content">
    not_var{{new_input_1}}
    </div>
    </div>
    <div class="info__block">
    <div class="info__title">
    not_var{{texts.new_input_2__title}}
    </div>
    <div class="info__content">
    not_var{{new_input_2}}
    </div>
    </div>
    ```

#### Editing JS

1. The JS code consists of blocks describing various interface elements. These blocks can be nested (buttons contain a set of fields, fields contain a set of elements, and so on). Each block is enclosed in curly brackets.

    The elements are described as follows:

    ```plaintext
    'property': 'value'
    ```

    The value can also consist of several properties, in which case it is enclosed in curly brackets and forms the next level of nesting.

1. The `texts` constant at the very beginning of the file stores all interface texts. Add the titles of the new fields to it:

    ```javascript
    'new_input_1__title': 'Input field 1:',
    'new_input_2__title': 'Input field 2:',
    ```

{% include [contact-support](../_includes/contact-support.md) %}