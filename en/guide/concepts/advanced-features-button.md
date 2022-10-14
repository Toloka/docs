# Add a button

If you have multiple response buttons, you can add another one. For example, in the “Photos of product and price tag” task, you can add the response option “There is a different store at this address”.

Let's add a new button to the “Photos of product and price tag” task template, in which the Toloker will need to upload several photos and write a comment.

#### What does it look like?

Before:
![](../_images/tutorials/advanced-features/af-button-1.png)
After:
![](../_images/tutorials/advanced-features/af-button-2.png)
When the Toloker clicks the new button:
![](../_images/tutorials/advanced-features/af-button-3.png)

For your convenience, here is ready-made code with the new button for the “Photos of product and price tag” template. Use this code for self-check. You can find our additions to the code by searching for the word “customization”.

#### Ready-made code

#### HTML block
 {% if locale == "en-com" %}
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
            {{#if (equal verdict "no_price")}}
                <div class="header-review__btn header-review__btn_red">
                    not_var{{texts.btn_no_price.title}}
                </div>
            {{/if}}
            {{#if (equal verdict "no_item")}}
                <div class="header-review__btn header-review__btn_red">
                    not_var{{texts.btn_no_item.title}}
                </div>
            {{/if}}
            {{#if (equal verdict "no_shop")}}
                <div class="header-review__btn header-review__btn_red">
                    not_var{{texts.btn_no_shop.title}}
                </div>
            {{/if}}

            <!-- customization fragment start -->
            <!-- New verdict for the interface header -->
            {{#if (equal verdict "new_verdict")}}
              <div class="header-review__btn header-review__btn_red">
                not_var{{texts.btn_new.title}}
              </div>
            {{/if}}
            <!-- customization fragment end -->

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
    <div class="info__block">
        <div class="info__content">
            <a href=not_var{{image}} target="_blank" class="info__link">Link to product image</a>
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
                    {{#each imgs_facade}}
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
                <div class="review__imgs-grid">
                    {{#each imgs_item}}
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
                    not_var{{texts.btn_ok.question_3.title}}
                </div>
                <div class="review__imgs-grid">
                    {{#each imgs_price}}
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
        {{/if}}
        {{#if (equal verdict "no_price")}}
            <div class="review__block">
                <div class="review__title">
                    not_var{{texts.btn_no_price.question_1.title}}
                </div>
                <div class="review__imgs-grid">
                    {{#each imgs_facade}}
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
                    not_var{{texts.btn_no_price.question_2.title}}
                </div>
                <div class="review__imgs-grid">
                    {{#each imgs_item}}
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
        {{/if}}
        {{#if (equal verdict "no_item")}}
            <div class="review__block">
                <div class="review__title">
                    not_var{{texts.btn_no_item.question_1.title}}
                </div>
                <div class="review__imgs-grid">
                    {{#each imgs_facade}}
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
                    not_var{{texts.btn_no_item.question_2.title}}
                </div>
                <div class="review__imgs-grid">
                    {{#each imgs_shelf}}
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
                        not_var{{texts.btn_no_item.question_3.title}}
                    </div>
                    <div class="review__comment">
                        {{field type="textarea" name="comment" width="100%" rows=5}}
                    </div>
                </div>
            {{/if}}
        {{/if}}
        {{#if (equal verdict "no_shop")}}
            <div class="review__block">
                <div class="review__title">
                    not_var{{texts.btn_no_shop.question_1.title}}
                </div>
                <div class="review__imgs-grid">
                    {{#each imgs_around}}
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
                    not_var{{texts.btn_no_shop.question_2.title}}
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
                    not_var{{texts.btn_no_shop.question_3.title}}
                </div>
                <div class="review__comment">
                    {{field type="textarea" name="comment" width="100%" rows=5}}
                </div>
            </div>

            <!-- customization fragment start -->
            <!-- New verdict with uploaded data -->
            {{#if (equal verdict "new_verdict")}}
              <div class="review__block">
                <div class="review__title">
                  not_var{{texts.btn_new.question_1.title}}
                </div>
                <div class="review__imgs-grid">
                  {{#each imgs}}
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
                  not_var{{texts.btn_new.question_2.title}}
                </div>
                <div class="review__comment">
                  {{field type="textarea" name="new_comment" width="100%" rows=5}}
                </div>
              </div>
            {{/if}}
            <!-- customization fragment end -->

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
                            {{field type="file-img" name="imgs_facade" camera=true preview=true compress=false validation-show="top-left"}}
                        </div>
                    </div>
                    <div class="main__content-block">
                        <div class="main__content-title main__content-title_req">
                            not_var{{texts.btn_ok.question_2.title}}
                        </div>
                        <div class="main__text">
                            not_var{{texts.btn_ok.question_2.description}}
                        </div>
                        <div class="main__ex">
                            <a href="not_var{{texts.btn_ok.question_2.example_link_1}}" target="_blank" class="main__ex-link">Example</a>
                        </div>
                        <div class="main__imgs">
                            {{field type="file-img" name="imgs_item" camera=true preview=true compress=false validation-show="top-left"}}
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
                            {{field type="file-img" name="imgs_price" camera=true preview=true compress=false validation-show="top-left"}}
                        </div>
                    </div>
                </div>
            </div>
            <div class="main__block">
                <div class="main__btn main__btn_red">
                    not_var{{texts.btn_no_price.title}}
                </div>
                <div class="main__content">
                    <div class="main__content-block">
                        <div class="main__content-title main__content-title_req">
                            not_var{{texts.btn_no_price.question_1.title}}
                        </div>
                        <div class="main__text">
                            not_var{{texts.btn_no_price.question_1.description}}
                        </div>
                        <div class="main__ex">
                            <a href="not_var{{texts.btn_no_price.question_1.example_link_1}}" target="_blank" class="main__ex-link">Example</a>
                        </div>
                        <div class="main__imgs">
                            {{field type="file-img" name="imgs_facade" camera=true validation-show="top-left"}}
                        </div>
                    </div>
                    <div class="main__content-block">
                        <div class="main__content-title main__content-title_req">
                            not_var{{texts.btn_no_price.question_2.title}}
                        </div>
                        <div class="main__text">
                            not_var{{texts.btn_no_price.question_2.description}}
                        </div>
                        <div class="main__ex">
                            <a href="not_var{{texts.btn_no_price.question_2.example_link_1}}" target="_blank" class="main__ex-link">Example</a>
                        </div>
                        <div class="main__imgs">
                            {{field type="file-img" name="imgs_item" camera=true validation-show="top-left"}}
                        </div>
                    </div>
                </div>
            </div>
            <div class="main__block">
                <div class="main__btn main__btn_red">
                    not_var{{texts.btn_no_item.title}}
                </div>
                <div class="main__content">
                    <div class="main__content-block">
                        <div class="main__content-title main__content-title_req">
                            not_var{{texts.btn_no_item.question_1.title}}
                        </div>
                        <div class="main__text">
                            not_var{{texts.btn_no_item.question_1.description}}
                        </div>
                        <div class="main__ex">
                            <a href="not_var{{texts.btn_no_item.question_1.example_link_1}}" target="_blank" class="main__ex-link">Example</a>
                        </div>
                        <div class="main__imgs">
                            {{field type="file-img" name="imgs_facade" camera=true validation-show="top-left"}}
                        </div>
                    </div>
                    <div class="main__content-block">
                        <div class="main__content-title main__content-title_req">
                            not_var{{texts.btn_no_item.question_2.title}}
                        </div>
                        <div class="main__text">
                            not_var{{texts.btn_no_item.question_2.description}}
                        </div>
                        <div class="main__ex">
                            <a href="not_var{{texts.btn_no_item.question_2.example_link_1}}" target="_blank" class="main__ex-link">Example</a>
                        </div>
                        <div class="main__imgs">
                            {{field type="file-img" name="imgs_shelf" camera=true validation-show="top-left"}}
                        </div>
                    </div>
                    <div class="main__content-block">
                        <div class="main__content-title">
                            not_var{{texts.btn_no_item.question_3.title}}
                        </div>
                        <div class="main__text">
                            not_var{{texts.btn_no_item.question_3.description}}
                        </div>
                        <div class="main__comment">
                            {{field type="textarea" name="comment" width="100%" rows=5 validation-show="top-left"}}
                        </div>
                    </div>
                </div>
            </div>
            <div class="main__block">
                <div class="main__btn main__btn_red">
                    not_var{{texts.btn_no_shop.title}}
                </div>
                <div class="main__content">
                    <div class="main__content-block">
                        <div class="main__text main__text_req">
                            not_var{{texts.btn_no_shop.question_1.description}}
                        </div>
                        <div class="main__imgs">
                            {{field type="file-img" name="imgs_around" camera=true validation-show="top-left"}}
                        </div>
                    </div>
                    <div class="main__content-block">
                        <div class="main__text main__text_req">
                            not_var{{texts.btn_no_shop.question_2.description}}
                        </div>
                        <div class="main__ex">
                            <a href="not_var{{texts.btn_no_shop.question_2.example_link_1}}" target="_blank" class="main__ex-link">Example</a>
                        </div>
                        <div class="main__imgs">
                            {{field type="file-img" name="imgs_address" camera=true validation-show="top-left"}}
                        </div>
                    </div>
                    <div class="main__content-block">
                        <div class="main__content-title main__content-title_req">
                            not_var{{texts.btn_no_shop.question_3.title}}
                        </div>
                        <div class="main__text">
                            not_var{{texts.btn_no_shop.question_3.description}}
                        </div>
                        <div class="main__comment">
                            {{field type="textarea" name="comment" width="100%" rows=5 validation-show="top-left"}}
                        </div>
                    </div>
                </div>
            </div>

            <!-- customization fragment start -->
            <div class="main__block">
              <div class="main__btn main__btn_red">
                not_var{{texts.btn_new.title}}
              </div>
              <div class="main__content">
                <div class="main__content-block">
                  <div class="main__content-title main__content-title_req">
                    not_var{{texts.btn_new.question_1.title}}
                  </div>
                  <div class="main__text">
                    not_var{{texts.btn_new.question_1.description}}
                  </div>
                  <div class="main__ex">
                    <a href="not_var{{texts.btn_new.question_1.example_link_1}}" target="_blank" class="main__ex-link">Example</a>
                  </div>
                  <div class="main__imgs">
                    {{field type="file-img" name="imgs" camera=true validation-show="top-left"}}
                  </div>
                </div>
                <div class="main__content-block">
                  <div class="main__content-title main__content-title_req">
                    not_var{{texts.btn_new.question_2.title}}
                  </div>
                  <div class="main__text">
                    not_var{{texts.btn_new.question_2.description}}
                  </div>
                  <div class="main__comment">
                    {{field type="textarea" name="new_comment" width="100%" rows=5 validation-show="top-left"}}
                  </div>
                </div>
              </div>
            </div>
            <!-- customization fragment end -->

        </div>
    </div>
{{/if}}
```
{% endif %}
#### JavaScript block
 {% if locale == "en-com" %}
```javascript
var texts = {
    'task_title': 'Product and price tag photo',
    'info_name': 'Store name:',
    'info_address': 'Store address:',
    'info_description': 'Product description:',
    'btn_ok': {
        'title': 'I found the price tag for the product',
        'question_1': {
            'title': 'Store facade photo',
            'description': 'Take 2 photos of the store's front from different angles so that its sign and name are clearly visible.',
            'example_link_1': 'https://mt-content-public.s3.yandex.net/instructions/toloka_field_templates/price_org_1_4_6-min.png'
        },
        'question_2': {
            'title': 'Product photo',
            'description': 'Take a few photos of the product so that its front side with the name and details is clearly visible.',
            'example_link_1': 'https://mt-content-public.s3.yandex.net/instructions/toloka_field_templates/price_org_2-min.png'
        },
        'question_3': {
            'title': 'Price tag photo',
            'description': 'Take a close-up photo of the product's price tag. The price tag should take up most of the frame. The photo shouldn't be blurry, and all the text should be easy to read.',
            'example_link_1': 'https://mt-content-public.s3.yandex.net/instructions/toloka_field_templates/price_org_3-min.png'
        }
    },
    'btn_no_price': {
        'title': 'I found the product, but the price tag is missing',
        'question_1': {
            'title': 'Store facade photo',
            'description': 'Take 2 photos of the store's front from different angles so that its sign and name are clearly visible.',
            'example_link_1': 'https://mt-content-public.s3.yandex.net/instructions/toloka_field_templates/price_org_1_4_6-min.png'
        },
        'question_2': {
            'title': 'Product photo',
            'description': 'Take a few photos of the price tag holder and the front side of the product with its name and details clearly visible. If the products are placed in several rows, you need to photograph the entire area.',
            'example_link_1': 'https://mt-content-public.s3.yandex.net/instructions/toloka_field_templates/price_org_5-min.png'
        }
    },
    'btn_no_item': {
        'title': 'The product isn't on the shelf',
        'question_1': {
            'title': 'Store's front photo',
            'description': 'Take 2 photos of the store's front from different angles so that its sign and name are clearly visible.',
            'example_link_1': 'https://mt-content-public.s3.yandex.net/instructions/toloka_field_templates/price_org_1_4_6-min.png'
        },
        'question_2': {
            'title': 'Photos of shelves or racks',
            'description': 'Take photos of all shelves and racks with the products of the same category. The names of the products should be clearly visible. Be sure to capture the neighboring shelves to show that the required product is really missing.',
            'example_link_1': 'https://mt-content-public.s3.yandex.net/instructions/toloka_field_templates/price_org_7-min.png'
        },
        'question_3': {
            'title': 'Comments',
            'description': 'Try to find out from the store employees why the product isn't on the shelf and specify the reason in the comments (for example, the product is sold out, the store no longer sells this product, it wasn't delivered, or something else)'
        }
    },
    'btn_no_shop': {
        'title': 'The store is closed or missing',
        'question_1': {
            'title': 'Photos of the building from all sides',
            'description': 'Take photos of the building or place where the store should be from all sides so that they clearly show it's really not there.'
        },
        'question_2': {
            'title': 'Photos of the address plate',
            'description': ''Take a photo of the address plate or information sheet with the store's address at the entrance.',
            'example_link_1': 'https://mt-content-public.s3.yandex.net/instructions/toloka_field_templates/price_org_8-min.png'
        },
        'question_3': {
            'title': ''Mandatory comment',
            'description': ''Specify why the store is closed or missing (for example, under repair, closed, or you couldn't find it).'
        }
    },

    // customization fragment start
    'btn_new': {
      'title': 'New button',
      'question_1': {
        'title': 'Photo',
        'description': 'Take at least 2 photos',
        'example_link_1': 'link to the example of a photo'
      },
      'question_2': {
        'title': 'Mandatory comment',
        'description': 'Please write a comment'
      }
    }
    // customization fragment end

};


// Maximum distance of a Toloker from a store (in kilometers).
var MAX_DISTANCE = 1;

// customization: the 'new_verdict' value for the new button was added to the verdictsOut variable
var verdictsOut = ['ok', 'no_price', 'no_item', 'no_shop', 'new_verdict'];

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

            if (outputValues.imgs_facade && outputValues.imgs_facade.length > 0) {
                data.imgs_facade = [];
                for (var i = 0; i < outputValues.imgs_facade.length; i++) {
                    data.imgs_facade.push(workspaceOptions.apiOrigin + '/api/attachments/' + outputValues.imgs_facade[i] + '/preview');
                }
            }

            if (outputValues.imgs_item && outputValues.imgs_item.length > 0) {
                data.imgs_item = [];
                for (var i = 0; i < outputValues.imgs_item.length; i++) {
                    data.imgs_item.push(workspaceOptions.apiOrigin + '/api/attachments/' + outputValues.imgs_item[i] + '/preview');
                }
            }

            if (outputValues.imgs_price && outputValues.imgs_price.length > 0) {
                data.imgs_price = [];
                for (var i = 0; i < outputValues.imgs_price.length; i++) {
                    data.imgs_price.push(workspaceOptions.apiOrigin + '/api/attachments/' + outputValues.imgs_price[i] + '/preview');
                }
            }

            if (outputValues.imgs_shelf && outputValues.imgs_shelf.length > 0) {
                data.imgs_shelf = [];
                for (var i = 0; i < outputValues.imgs_shelf.length; i++) {
                    data.imgs_shelf.push(workspaceOptions.apiOrigin + '/api/attachments/' + outputValues.imgs_shelf[i] + '/preview');
                }
            }

            if (outputValues.imgs_address && outputValues.imgs_address.length > 0) {
                data.imgs_address = [];
                for (var i = 0; i < outputValues.imgs_address.length; i++) {
                    data.imgs_address.push(workspaceOptions.apiOrigin + '/api/attachments/' + outputValues.imgs_address[i] + '/preview');
                }
            }

            if (outputValues.imgs_around && outputValues.imgs_around.length > 0) {
                data.imgs_around = [];
                for (var i = 0; i < outputValues.imgs_around.length; i++) {
                    data.imgs_around.push(workspaceOptions.apiOrigin + '/api/attachments/' + outputValues.imgs_around[i] + '/preview');
                }
            }

            // customization fragment start
            if (outputValues.imgs && outputValues.imgs.length > 0) {
              data.imgs = [];
              for (var i = 0; i < outputValues.imgs.length; i++) {
                data.imgs.push(workspaceOptions.apiOrigin + '/api/attachments/' + outputValues.imgs[i] + '/preview');
              }
            }
            // customization fragment end

            if (outputValues.comment) {
                data.comment = outputValues.comment;
            }

            if (outputValues.verdict) {
                data.verdict = outputValues.verdict;
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
                iconContent: 'Store'
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
        var Earth = 6371;
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
                    for (var i = 0; i < fields.length; i++) {
                        fields[i].showError(error);
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
            if (!solution.output_values.imgs_facade || solution.output_values.imgs_facade.length === 0) {
                this.errors = this.addError('Attach photos of the store', "imgs_facade", this.errors);
            } else if (solution.output_values.imgs_facade.length < 2) {
                this.errors = this.addError('There must be at least 2 photos of the store', "imgs_facade", this.errors);
            }

            if (!solution.output_values.imgs_item || solution.output_values.imgs_item.length === 0) {
                this.errors = this.addError('Attach photos of the product', "imgs_item", this.errors);
            } else if (solution.output_values.imgs_item.length < 2) {
                this.errors = this.addError('There must be at least 2 photos of the product', "imgs_item", this.errors);
            }

            if (!solution.output_values.imgs_price || solution.output_values.imgs_price.length === 0) {
                this.errors = this.addError('Attach a photo of the price tag', "imgs_price", this.errors);
            }
        } else if (solution.output_values.verdict === 'no_price') {
            if (!solution.output_values.imgs_facade || solution.output_values.imgs_facade.length === 0) {
                this.errors = this.addError('Attach photos of the store', "imgs_facade", this.errors);
            } else if (solution.output_values.imgs_facade.length < 2) {
                this.errors = this.addError('There must be at least 2 photos of the store', "imgs_facade", this.errors);
            }

            if (!solution.output_values.imgs_item || solution.output_values.imgs_item.length === 0) {
                this.errors = this.addError('Attach photos of the product', "imgs_item", this.errors);
            } else if (solution.output_values.imgs_item.length < 2) {
                this.errors = this.addError('There must be at least 2 photos of the product', "imgs_item", this.errors);
            }
        } else if (solution.output_values.verdict === 'no_item') {
            if (!solution.output_values.imgs_facade || solution.output_values.imgs_facade.length === 0) {
                this.errors = this.addError('Attach photos of the store', "imgs_facade", this.errors);
            } else if (solution.output_values.imgs_facade.length < 2) {
                this.errors = this.addError('There must be at least 2 photos of the store', "imgs_facade", this.errors);
            }

            if (!solution.output_values.imgs_shelf || solution.output_values.imgs_shelf.length === 0) {
                this.errors = this.addError('Attach photos of shelves or racks', "imgs_shelf", this.errors);
            } else if (solution.output_values.imgs_shelf.length < 2) {
                this.errors = this.addError('There must be at least 2 photos of shelves or racks', "imgs_shelf", this.errors);
            }
        } else if (solution.output_values.verdict === 'no_shop') {
            if (!solution.output_values.imgs_around || solution.output_values.imgs_around.length === 0) {
                this.errors = this.addError('Attach photos of the surroundings', "imgs_around", this.errors);
            } else if (solution.output_values.imgs_around.length < 4) {
                this.errors = this.addError('There must be at least 4 photos of the surroundings', "imgs_around", this.errors);
            }

            if (!solution.output_values.imgs_address || solution.output_values.imgs_address.length === 0) {
                this.errors = this.addError('Attach a photo of the address plate', "imgs_address", this.errors);
            }

            if (!solution.output_values.comment || solution.output_values.comment.trim() === '') {
                this.errors = this.addError('Write a comment', "comment", this.errors);
            }
        }

        // customization fragment start
        else if (solution.output_values.verdict === 'new_verdict') {
          if (!solution.output_values.imgs || solution.output_values.imgs.length === 0) {
            this.errors = this.addError('Attach photos', "imgs", this.errors);
          } else if (solution.output_values.imgs.length < 2) {
            this.errors = this.addError('There must be at least 2 photos', "imgs", this.errors);
          }

          if (!solution.output_values.new_comment || solution.output_values.new_comment.trim() === '') {
            this.errors = this.addError('Write a comment', "new_comment", this.errors);
          }
        }
        // customization fragment end

        if (this.checkUserPosition.call(this, input_values, solution.output_values)) {
            this.errors = this.addError('You're too far from the store', "__TASK__", this.errors);
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
{% endif %}

#### Editing the output specification

Add 2 new fields to the output data specification:

`imgs` — An array of files with photos.

`new_comment` — A mandatory comment string.

#### Editing HTML

1. The HTML code consists of blocks describing various interface elements. Each block may contain other blocks within it. There may be several nesting levels. For example, the block with a response button description contains other blocks with input fields. Each field contains other elements, such as a title and a comment field.

    Each block looks like this:
    {% if locale == "en-com" %}
    ```html
    `<div class="block_name">`
    <!-- code for the block that may contain nested blocks -->
    ...
    </div>
    ```
    {% endif %}
1. Find the `main` block (it starts with `<div class="main">`). It contains several `main_block` blocks within it, each describing one of the buttons. For example, the “Photos of product and price tag” template has 4 response buttons, which means that its `main` block contains 4 `main_block` blocks for each of the buttons.

    Each button has a name for accessing its properties. For example, the buttons in the “Photos of product and price tag” template are named `btn_ok`, `btn_no_price`, `btn_no_item`, and `btn_no_shop`. Add a new button with the name `btn_new`. To do this, paste the following code after the last `main__block` block. It will add a new button for uploading photos and writing a comment.
    {% if locale == "en-com" %}
    ```html
    <div class="main__block">
    <div class="main__btn main__btn_red">
    not_var{{texts.btn_new.title}}
    </div>
    <div class="main__content">
    <div class="main__content-block">
    <div class="main__content-title main__content-title_req">
    not_var{{texts.btn_new.question_1.title}}
    </div>
    <div class="main__text">
    not_var{{texts.btn_new.question_1.description}}
    </div>
    <div class="main__ex">
    <a href="not_var{{texts.btn_new.question_1.example_link_1}}" target="_blank" class="main__ex-link">Example</a>
    </div>
    <div class="main__imgs">
    {{field type="file-img" name="imgs" camera=true validation-show="top-left"}}
    </div>
    </div>
    <div class="main__content-block">
    <div class="main__content-title main__content-title_req">
    not_var{{texts.btn_new.question_2.title}}
    </div>
    <div class="main__text">
    not_var{{texts.btn_new.question_2.description}}
    </div>
    <div class="main__comment">
    {{field type="textarea" name="new_comment" width="100%" rows=5 validation-show="top-left"}}
    </div>
    </div>
    </div>
    </div>
    ```
    {% endif %}
1. Update the acceptance mode.

    The `review` block contains the code for each button in the acceptance mode. This code is located in the following blocks:
    {% if locale == "en-com" %}
    ```
    {{#if (equal verdict "ok")}}
    <!-- code for the "ok" button in acceptance mode -->
    <div class="review__block">
    <!-- code for the "ok" button field in acceptance mode -->
    ...
    </div>
    ...
    {{/if}}
    ```
    {% endif %}
    The value of the response button selected by the Toloker is passed to the `verdict` variable specified in the output specification.

    For example, in the “Photos of product and price tag” template, 4 values are described for 4 buttons: `ok`, `no_price`, `no_item`, and `no_shop`. Let's add a `new_verdict` output value for the new button `btn_new`.

    Find the desired button by searching for the string `{{#if (equal verdict "response_button_value")}}` then find the `review`field where you want to add a new field and insert the following code after it:
    {% if locale == "en-com" %}
    ```html
    <!-- New verdict with uploaded data -->
    {{#if (equal verdict "new_verdict")}}
    <div class="review__block">
    <div class="review__title">
    not_var{{texts.btn_new.question_1.title}}
    </div>
    <div class="review__imgs-grid">
    {{#each imgs}}
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
    not_var{{texts.btn_new.question_2.title}}
    </div>
    <div class="review__comment">
    {{field type="textarea" name="new_comment" width="100%" rows=5}}
    </div>
    </div>
    {{/if}}
    ```
    {% endif %}
    Update the interface header in the acceptance mode. Find the `header-review` block that contains such blocks for each button:

    ```
    {{#if (equal verdict "ok")}}
    <div class="header-review__btn header-review__btn_green">
    not_var{{texts.btn_ok.title}}
    </div>
    {{/if}}
    ```

    This block describes the `btn_ok` button and its output value `ok`. Paste the following code after the last button block:
    {% if locale == "en-com" %}
    ```html
    <!-- New verdict for the interface header -->
    {{#if (equal verdict "new_verdict")}}
    <div class="header-review__btn header-review__btn_red">
    not_var{{texts.btn_new.title}}
    </div>
    {{/if}}
    ```
    {% endif %}

#### Editing JS

1. The JS code consists of blocks describing various interface elements. These blocks can be nested (buttons contain a set of fields, fields contain a set of elements, and so on). Each block is enclosed in curly brackets.

    The elements are described as follows:
    {% if locale == "en-com" %}
    ```
    'property': 'value'
    ```
    {% endif %}
    The value can also consist of several properties, in which case it is enclosed in curly brackets and forms the next level of nesting.

1. The `texts` constant at the very beginning of the file stores all texts for each button.

    Each button has a name for accessing its properties. For example, the buttons in the “Photos of product and price tag” template are named `btn_ok`, `btn_no_price`, `btn_no_item`, and `btn_no_shop`.

    For example, in the “Photos of product and price tag” template, the texts for the `btn_ok` button are located in the following code block:
    {% if locale == "en-com" %}
    ```
    var texts = {
    //<common header text>
    'btn_ok': {
    'title': 'I found the price tag for the product',
    'question_1': {
    //<texts for the first field (photos of the store's front)>
    },
    'question_2': {
    //<texts for the second field (product photos)>
    },
    'question_3': {
    //<texts for the third field (photo of the price tag)>
    }
    },
    ```
    {% endif %}
1. To add the texts for the new `btn_new` button, put a comma after the curly bracket that closes the last button block and insert the following code:
    {% if locale == "en-com" %}
    ```javascript
    'btn_new': {
    'title': 'New button',
    'question_1': {
    'title': 'Photos',
    'description': 'Take at least 2 photos',
    'example_link_1': 'link to an example of a photo'
    },
    'question_2': {
    'title': 'Mandatory comment',
    'description': 'Please write a comment'
    }
    }
    ```
    {% endif %}Change the values of the `title`, `description`, and `example_link_1` properties. The `title` property contains a title displayed above the field; the `description` property contains a question or a hint for Tolokers, and the `example_link_1` property contains a link to the example of an image.
1. Find the `verdictsOut` variable. In the “Photos of product and price tag” template, it looks like this:

    ```
    var verdictsOut = ['ok', 'no_price', 'no_item', 'no_shop'];
    ```

    Add the `new_verdict` output value to the new button like this:

    ```
    var verdictsOut = ['ok', 'no_price', 'no_item', 'no_shop', 'new_verdict'];
    ```

1. Find the `getTemplateData` function. It contains several blocks that look like this:
    {% if locale == "en-com" %}
    ```
    if (<field checking condition>) {
    ...
    <code for displaying the uploaded data>
    ...
    }
    ```
    {% endif %}
    Paste the following code after any of these blocks. It is used to send the photos uploaded by the Toloker to the input data. You need this to display the data in the acceptance mode:

    ```javascript
    if (outputValues.imgs && outputValues.imgs.length > 0) {
    data.imgs = [];
    for (var i = 0; i < outputValues.imgs.length; i++) {
    data.imgs.push(workspaceOptions.apiOrigin + '/api/attachments/' + outputValues.imgs[i] + '/preview');
    }
    }
    ```

1. Add validation.

    Find the `validate` function. It contains the code for checking whether the fields in each of the buttons are filled in. For example, in the “Photos of product and price tag” template, the code looks like this:
    {% if locale == "en-com" %}
    ```
    else if (solution.output_values.verdict === 'ok') {
    // code for checking the ok button fields
    if (!solution.output_values.imgs_facade || solution.output_values.imgs_facade.length === 0) {
    // code for checking the imgs_facade field
    }

    if (!solution.output_values.imgs_item || solution.output_values.imgs_item.length === 0) {
    // code for checking the imgs_item field
    }

    if (!solution.output_values.imgs_price || solution.output_values.imgs_price.length === 0) {
    // code for checking the imgs_price field
    }

    } else if (solution.output_values.verdict === 'no_price') {
    //  code for checking the no_price button fields
    }
    } else if (solution.output_values.verdict === 'no_item') {
    //  code for checking the no_item button fields
    }
    } else if (solution.output_values.verdict === 'no_shop') {
    // code for checking the no_shop button fields
    }

    ```
    {% endif %}
    Paste the following code after the closing curly bracket with the verdict for the last button:
    {% if locale == "en-com" %}
    ```javascript
    else if (solution.output_values.verdict === 'new_verdict') {
    if (!solution.output_values.imgs || solution.output_values.imgs.length === 0) {
    this.errors = this.addError('Attach photos', "imgs", this.errors);
    } else if (solution.output_values.imgs.length < 2) {
    this.errors = this.addError('There must be at least 2 photos', "imgs", this.errors);
    }

    if (!solution.output_values.new_comment || solution.output_values.new_comment.trim() === '') {
    this.errors = this.addError('Write a comment', "new_comment", this.errors);
    }
    }
    ```
    {% endif %}

{% include [contact-support](../_includes/contact-support-help.md) %}