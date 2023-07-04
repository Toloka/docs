# Добавить кнопку

{% include [deprecate](../../_includes/deprecate.md) %}

Если у вас несколько кнопок выбора, то вы можете добавить еще одну. Например, к кнопкам ответов задания «Фото товара и ценника» можно добавить вариант «По данному адресу расположен другой магазин».

В шаблоне задания «Фото товара и ценника» добавим новую кнопку, в котором исполнителю нужно будет загрузить несколько фотографий и написать обязательный комментарий.

{% cut "Как это выглядит" %}

Было:

![](../_images/tutorials/advanced-features/af-button-1.png)

Стало в списке кнопок:

![](../_images/tutorials/advanced-features/af-button-2.png)

При нажатии на новую кнопку:

![](../_images/tutorials/advanced-features/af-button-3.png)

{% endcut %}

Для вашего удобства мы подготовили код для шаблона «Фото товара и ценника», в котором добавлена новая кнопка. Используйте этот код для самопроверки. Наши вставки в этом коде вы можете найти поиском слова «кастомизация».

{% cut "Готовый код" %}

{% cut "Блок HTML" %}

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

            <!-- кастомизация начало фрагмента -->
            <!-- Новый вердикт для шапки интерфейса -->
            {{#if (equal verdict "new_verdict")}}
              <div class="header-review__btn header-review__btn_red">
                not_var{{texts.btn_new.title}}
              </div>
            {{/if}}
            <!-- кастомизация конец фрагмента -->

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
            <a href=not_var{{image}} target="_blank" class="info__link">Ссылка на изображение товара</a>
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
                                    <span class="review__rotate review__rotate_left">&larr;</span>
                                    <span class="review__rotate review__rotate_right">&rarr;</span>
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
                                    <span class="review__rotate review__rotate_left">&larr;</span>
                                    <span class="review__rotate review__rotate_right">&rarr;</span>
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
                                    <span class="review__rotate review__rotate_left">&larr;</span>
                                    <span class="review__rotate review__rotate_right">&rarr;</span>
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
                                    <span class="review__rotate review__rotate_left">&larr;</span>
                                    <span class="review__rotate review__rotate_right">&rarr;</span>
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
                                    <span class="review__rotate review__rotate_left">&larr;</span>
                                    <span class="review__rotate review__rotate_right">&rarr;</span>
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
                                    <span class="review__rotate review__rotate_left">&larr;</span>
                                    <span class="review__rotate review__rotate_right">&rarr;</span>
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
                                    <span class="review__rotate review__rotate_left">&larr;</span>
                                    <span class="review__rotate review__rotate_right">&rarr;</span>
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
                                    <span class="review__rotate review__rotate_left">&larr;</span>
                                    <span class="review__rotate review__rotate_right">&rarr;</span>
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
                                    <span class="review__rotate review__rotate_left">&larr;</span>
                                    <span class="review__rotate review__rotate_right">&rarr;</span>
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

            <!-- кастомизация начало фрагмента -->
            <!-- Новый вердикт с загруженными данными -->
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
                          <span class="review__rotate review__rotate_left">&larr;</span>
                          <span class="review__rotate review__rotate_right">&rarr;</span>
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
            <!-- кастомизация конец фрагмента -->

        {{/if}}
    </div>
not_var{{else}}
    <div class="main">
        <div class="main__title">
            Выберите вариант выполнения задания:
        </div>
        <div class="main__container">
            <div class="main__popup main__popup_hidden">Не выбран ни один вариант ответа</div>
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
                            <a href="not_var{{texts.btn_ok.question_1.example_link_1}}" target="_blank" class="main__ex-link">Пример</a>
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
                            <a href="not_var{{texts.btn_ok.question_2.example_link_1}}" target="_blank" class="main__ex-link">Пример</a>
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
                            <a href="not_var{{texts.btn_ok.question_3.example_link_1}}" target="_blank" class="main__ex-link">Пример</a>
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
                            <a href="not_var{{texts.btn_no_price.question_1.example_link_1}}" target="_blank" class="main__ex-link">Пример</a>
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
                            <a href="not_var{{texts.btn_no_price.question_2.example_link_1}}" target="_blank" class="main__ex-link">Пример</a>
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
                            <a href="not_var{{texts.btn_no_item.question_1.example_link_1}}" target="_blank" class="main__ex-link">Пример</a>
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
                            <a href="not_var{{texts.btn_no_item.question_2.example_link_1}}" target="_blank" class="main__ex-link">Пример</a>
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
                            <a href="not_var{{texts.btn_no_shop.question_2.example_link_1}}" target="_blank" class="main__ex-link">Пример</a>
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

            <!-- кастомизация начало фрагмента -->
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
                    <a href="not_var{{texts.btn_new.question_1.example_link_1}}" target="_blank" class="main__ex-link">Пример</a>
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
            <!-- кастомизация конец фрагмента -->

        </div>
    </div>
{{/if}}
```

{% endcut %}

{% cut "Блок JS" %}

```javascript
var texts = {
    'task_title': 'Фото товара и ценника',
    'info_name': 'Название магазина:',
    'info_address': 'Адрес магазина:',
    'info_description': 'Описание товара:',
    'btn_ok': {
        'title': 'Я нашел ценник на нужный товар',
        'question_1': {
            'title': 'Фото фасада магазина',
            'description': 'Сделайте 2 фото фасада магазина с разных сторон так, чтобы на фото была видна вывеска и название хорошо читалось.',
            'example_link_1': 'https://mt-content-public.s3.yandex.net/instructions/toloka_field_templates/price_org_1_4_6-min.png'
        },
        'question_2': {
            'title': 'Фото товара',
            'description': 'Сделайте несколько фото, чтобы была видна лицевая сторона с названием и атрибутами товара.',
            'example_link_1': 'https://mt-content-public.s3.yandex.net/instructions/toloka_field_templates/price_org_2-min.png'
        },
        'question_3': {
            'title': 'Фото ценника',
            'description': 'Сделайте крупную фотографию ценника на требуемый товар. Ценник должен занимать большую часть кадра. Сделайте фото так, чтобы оно не было размытым и все надписи легко читались.',
            'example_link_1': 'https://mt-content-public.s3.yandex.net/instructions/toloka_field_templates/price_org_3-min.png'
        }
    },
    'btn_no_price': {
        'title': 'Товар есть, но без ценника',
        'question_1': {
            'title': 'Фото фасада магазина',
            'description': 'Сделайте 2 фото фасада магазина с разных сторон так, чтобы на фото была видна вывеска и название хорошо читалось.',
            'example_link_1': 'https://mt-content-public.s3.yandex.net/instructions/toloka_field_templates/price_org_1_4_6-min.png'
        },
        'question_2': {
            'title': 'Фото товара',
            'description': 'Сделайте несколько фотографий так, чтобы был виден держатель для ценника и лицевая сторона с названием и атрибутами товара. Необходимо сфотографировать всю область, если товар стоит в несколько рядов.',
            'example_link_1': 'https://mt-content-public.s3.yandex.net/instructions/toloka_field_templates/price_org_5-min.png'
        }
    },
    'btn_no_item': {
        'title': 'Товара нет на полке',
        'question_1': {
            'title': 'Фото фасада магазина',
            'description': 'Сделайте 2 фото фасада магазина с разных сторон так, чтобы на фото была видна вывеска и название хорошо читалось.',
            'example_link_1': 'https://mt-content-public.s3.yandex.net/instructions/toloka_field_templates/price_org_1_4_6-min.png'
        },
        'question_2': {
            'title': 'Фото полок или стеллажа',
            'description': 'Сфотографируйте все полки и стеллажи с товарами той же категории. Должно быть видно название товаров. Захватите на фотографии соседние полки — так будет понятно, что нужного товара действительно нет.',
            'example_link_1': 'https://mt-content-public.s3.yandex.net/instructions/toloka_field_templates/price_org_7-min.png'
        },
        'question_3': {
            'title': 'Комментарии',
            'description': 'Попробуйте узнать у сотрудников магазина причину отсутствия товара на полке и укажите в комментарии (например: товар закончился, товар больше не продается, не было поставки и т.п.)'
        }
    },
    'btn_no_shop': {
        'title': 'Магазин закрыт или отсутствует',
        'question_1': {
            'title': 'Фото здания со всех сторон',
            'description': 'Сфотографируйте со всех сторон здание или место, где должен находиться магазин, так, чтобы можно было убедиться, что нужной организации нет. '
        },
        'question_2': {
            'title': 'Фото таблички с адресом',
            'description': 'Сфотографируйте адресную табличку или информационный лист с адресом магазина на входе.',
            'example_link_1': 'https://mt-content-public.s3.yandex.net/instructions/toloka_field_templates/price_org_8-min.png'
        },
        'question_3': {
            'title': 'Обязательный комментарий',
            'description': 'Напишите причину отсутствия или закрытия магазина (например: на ремонте, закрыт, не удалось найти и пр.).'
        }
    },

    // кастомизация начало фрагмента
    'btn_new': {
      'title': 'Новая кнопка',
      'question_1': {
        'title': 'Фото',
        'description': 'Сделайте хотя бы 2 фотографии',
        'example_link_1': 'ссылка на пример фото'
      },
      'question_2': {
        'title': 'Обязательный комментарий',
        'description': 'Пожалуйста, напишите комментарий'
      }
    }
    // кастомизация конец фрагмента

};

// Максимальная удаленность исполнителя от магазина в километрах.
var MAX_DISTANCE = 1;

// кастомизация: в переменную verdictsOut добавлено значение 'new_verdict' для новой кнопки
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

            // кастомизация начало фрагмента
            if (outputValues.imgs && outputValues.imgs.length > 0) {
              data.imgs = [];
              for (var i = 0; i < outputValues.imgs.length; i++) {
                data.imgs.push(workspaceOptions.apiOrigin + '/api/attachments/' + outputValues.imgs[i] + '/preview');
              }
            }
            // кастомизация конец фрагмента

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
                iconContent: 'Магазин'
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
                    iconContent: 'Исполнитель'
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
    // Функция определения расстояния между точками по их широте и долготе.
    _getDistanceBetweenCoords: function(lat1, lon1, lat2, lon2) {
        var Earth = 6371;
        var x =
            (((lon2 - lon1) * Math.PI) / 180) *
            Math.cos((((lat1 + lat2) / 2) * Math.PI) / 180);
        var y = ((lat2 - lat1) * Math.PI) / 180;
        return Earth * Math.sqrt(x * x + y * y);
    },
    // Функция определения расстояния между двумя точками.
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
            this.errors = this.addError('Не выбран ни один вариант ответа', "verdict", this.errors);
        } else if (solution.output_values.verdict === 'ok') {
            if (!solution.output_values.imgs_facade || solution.output_values.imgs_facade.length === 0) {
                this.errors = this.addError('Нужно приложить фото магазина', "imgs_facade", this.errors);
            } else if (solution.output_values.imgs_facade.length < 2) {
                this.errors = this.addError('Должны быть хотя бы 2 фотографии магазина', "imgs_facade", this.errors);
            }

            if (!solution.output_values.imgs_item || solution.output_values.imgs_item.length === 0) {
                this.errors = this.addError('Нужно приложить фото товара', "imgs_item", this.errors);
            } else if (solution.output_values.imgs_item.length < 2) {
                this.errors = this.addError('Должны быть хотя бы 2 фотографии товара', "imgs_item", this.errors);
            }

            if (!solution.output_values.imgs_price || solution.output_values.imgs_price.length === 0) {
                this.errors = this.addError('Нужно приложить фото ценника', "imgs_price", this.errors);
            }
        } else if (solution.output_values.verdict === 'no_price') {
            if (!solution.output_values.imgs_facade || solution.output_values.imgs_facade.length === 0) {
                this.errors = this.addError('Нужно приложить фото магазина', "imgs_facade", this.errors);
            } else if (solution.output_values.imgs_facade.length < 2) {
                this.errors = this.addError('Должно быть хотя бы 2 фото магазина', "imgs_facade", this.errors);
            }

            if (!solution.output_values.imgs_item || solution.output_values.imgs_item.length === 0) {
                this.errors = this.addError('Нужно приложить фото товара', "imgs_item", this.errors);
            } else if (solution.output_values.imgs_item.length < 2) {
                this.errors = this.addError('Должны быть хотя бы 2 фотографии товара', "imgs_item", this.errors);
            }
        } else if (solution.output_values.verdict === 'no_item') {
            if (!solution.output_values.imgs_facade || solution.output_values.imgs_facade.length === 0) {
                this.errors = this.addError('Нужно приложить фото магазина', "imgs_facade", this.errors);
            } else if (solution.output_values.imgs_facade.length < 2) {
                this.errors = this.addError('Должны быть хотя бы 2 фотографии магазина', "imgs_facade", this.errors);
            }

            if (!solution.output_values.imgs_shelf || solution.output_values.imgs_shelf.length === 0) {
                this.errors = this.addError('Нужно приложить фото полок/стеллажей', "imgs_shelf", this.errors);
            } else if (solution.output_values.imgs_shelf.length < 2) {
                this.errors = this.addError('Должны быть хотя бы 2 фотографии полок/стеллажей', "imgs_shelf", this.errors);
            }
        } else if (solution.output_values.verdict === 'no_shop') {
            if (!solution.output_values.imgs_around || solution.output_values.imgs_around.length === 0) {
                this.errors = this.addError('Нужно приложить фотографии окружения', "imgs_around", this.errors);
            } else if (solution.output_values.imgs_around.length < 4) {
                this.errors = this.addError('Должны быть хотя бы 4 фотографии окружения', "imgs_around", this.errors);
            }

            if (!solution.output_values.imgs_address || solution.output_values.imgs_address.length === 0) {
                this.errors = this.addError('Нужно приложить фото адресной таблички', "imgs_address", this.errors);
            }

            if (!solution.output_values.comment || solution.output_values.comment.trim() === '') {
                this.errors = this.addError('Нужно написать комментарий', "comment", this.errors);
            }
        }

        // кастомизация начало фрагмента
        else if (solution.output_values.verdict === 'new_verdict') {
          if (!solution.output_values.imgs || solution.output_values.imgs.length === 0) {
            this.errors = this.addError('Нужно приложить фото', "imgs", this.errors);
          } else if (solution.output_values.imgs.length < 2) {
            this.errors = this.addError('Должно быть хотя бы 2 фото', "imgs", this.errors);
          }

          if (!solution.output_values.new_comment || solution.output_values.new_comment.trim() === '') {
            this.errors = this.addError('Нужно написать комментарий', "new_comment", this.errors);
          }
        }
        // кастомизация конец фрагмента

        if (this.checkUserPosition.call(this, input_values, solution.output_values)) {
            this.errors = this.addError('Вы находитесь слишком далеко от магазина', "__TASK__", this.errors);
        }

        if (!solution.output_values.worker_coordinates) {
            this.errors = this.addError('Не удалось получить ваши координаты. Пожалуйста, включите геолокацию.', "__TASK__", this.errors);
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

#### Редактирование выходной спецификации

В спецификации выходных данных добавьте 2 новых поля:

`imgs` — массив файлов для фотографий;

`new_comment` — обязательная строка для комментария.

#### Редактирование HTML

1. Код HTML состоит из блоков, описывающих различные элементы интерфейса. Каждый блок может содержать внутри себя другие блоки. Таких уровней вложенности может быть несколько. Например, блок с описанием кнопки ответа содержит в себе блоки с полями для заполнения. Каждое поле тоже содержит в себе другие элементы, например, заголовок и поле для комментария.

    Каждый блок оформляется так:

    ```html
    `<div class="наименование_блока">`
    <!-- код блока, может содержать вложенные блоки -->
    ...
    </div>
    ```

1. Найдите блок `main` (он начинается со строки `<div class="main">`). Внутри него расположены блоки `main__block`, каждый из которых описывает одну из кнопок. Например, в шаблоне «Фото товара и ценника» есть 4 кнопки для ответа, значит, в блоке `main` у этого шаблона будет 4 блока `main__block` для каждой из кнопок.

    У каждой из кнопок есть наименование для обращения к ее свойствам. Например, в шаблоне «Фото товара и ценника» 4 кнопки называются `btn_ok`, `btn_no_price`, `btn_no_item` и `btn_no_shop`. Добавьте новую кнопку с названием `btn_new`, для этого после последнего блока `main__block` вставьте следующий код. Он добавит новую кнопку с возможностью загрузить фотографии и написать комментарий.

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
    <a href="not_var{{texts.btn_new.question_1.example_link_1}}" target="_blank" class="main__ex-link">Пример</a>
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

1. Обновите режим приемки.

    Блок `review` содержит в себе код для каждой кнопки в режиме приемки. Этот код расположен в таких блоках:

    ```html
    {{#if (equal verdict "ok")}}
    <!-- код для кнопки "ok" в режиме приемки -->
    <div class="review__block">
    <!-- код для поля внутри кнопки "ok" в режиме приемки -->
    ...
    </div>
    ...
    {{/if}}
    ```

    Переменная `verdict` указана в выходной спецификации, в нее будет передаваться значение ответа для той кнопки, которую нажал исполнитель.

    Например, в шаблоне «Фото товара и ценника» для четырех кнопок описаны четыре значения: `ok`, `no_price`, `no_item` и `no_shop`. Добавим выходное значение`new_verdict` для новой кнопки `btn_new`.

    Найдите в блоке `review` блок с последней кнопкой по строке `{{#if (equal verdict "значение_ответа_кнопки")}}` и вставьте после него следующий код:

    ```html
    <!-- Новый вердикт с загруженными данными -->
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
    <span class="review__rotate review__rotate_left">&larr;</span>
    <span class="review__rotate review__rotate_right">&rarr;</span>
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

    Обновите шапку интерфейса в режиме приемки. Найдите блок `header-review`, который содержит такие блоки для каждой кнопки:

    ```html
    {{#if (equal verdict "ok")}}
    <div class="header-review__btn header-review__btn_green">
    not_var{{texts.btn_ok.title}}
    </div>
    {{/if}}
    ```

    Этот блок описывает кнопку `btn_ok` и ее выходное значение `ok`. Вставьте после блока с последней кнопкой следующий код:

    ```html
    <!-- Новый вердикт для шапки интерфейса -->
    {{#if (equal verdict "new_verdict")}}
    <div class="header-review__btn header-review__btn_red">
    not_var{{texts.btn_new.title}}
    </div>
    {{/if}}
    ```

#### Редактирование JS

1. Код JS состоит из блоков, описывающих различные элементы интерфейса. Эти блоки могут быть вложенными (кнопки содержат набор полей, поля содержат набор элементов и т. д.). Каждый блок заключен в фигурные скобки.

    В общем виде элементы описываются так:

    ```plaintext
    'свойство': 'значение'
    ```

    Значение тоже может состоять из нескольких свойств, в этом случае оно заключается в фигурные скобки и образует следующий уровень вложенности.

1. В самом начале файла находится константа `texts`, в которой хранятся все необходимые для интерфейса тексты для каждой кнопки.

    У каждой из кнопок есть наименование для обращения к ее свойствам. Например, в шаблоне «Фото товара и ценника» 4 кнопки называются `btn_ok`, `btn_no_price`, `btn_no_item` и `btn_no_shop`.

    Например, в шаблоне «Фото товара и ценника» тексты для кнопки `btn_ok` расположены в следующем блоке кода:

    ```javascript
    var texts = {
    //<общий текст для заголовков>
    'btn_ok': {
    'title': 'Я нашел ценник на нужный товар',
    'question_1': {
    //<тексты для первого поля (фото фасада магазина)>
    },
    'question_2': {
    //<тексты для второго поля (фото товара)>
    },
    'question_3': {
    //<тексты для третьего поля (фото ценника)>
    }
    },
    ```

1. Чтобы добавить нужные тексты для новой кнопки `btn_new`, поставьте запятую после закрывающей фигурной скобки последней кнопки и вставьте следующий код:

    ```javascript
    'btn_new': {
    'title': 'Новая кнопка',
    'question_1': {
    'title': 'Фото',
    'description': 'Сделайте хотя бы 2 фотографии',
    'example_link_1': 'ссылка на пример фото'
    },
    'question_2': {
    'title': 'Обязательный комментарий',
    'description': 'Пожалуйста, напишите комментарий'
    }
    }
    ```

    Измените значения свойств `title`, `description` и `example_link_1`. Свойство `title` содержит заголовок, который будет отображаться над полем, `description` — вопрос или подсказку для исполнителя, а `example_link_1` — ссылку на пример картинки.

1. Найдите переменную `verdictsOut`. В шаблоне «Фото товара и ценника» она выглядит так:

    ```javascript
    var verdictsOut = ['ok', 'no_price', 'no_item', 'no_shop'];
    ```

    Добавьте в нее новое выходное значение `new_verdict` для новой кнопки следующим образом:

    ```javascript
    var verdictsOut = ['ok', 'no_price', 'no_item', 'no_shop', 'new_verdict'];
    ```

1. Найдите функцию `getTemplateData`. Она содержит несколько блоков следующего вида:

    ```javascript
    if (<условие проверки заполнения поля>) {
    ...
    <код для отображения загруженных данных>
    ...
    }
    ```

    Вставьте после любого из таких блоков следующий код. Он нужен для того, чтобы отправить загруженные исполнителем фотографии во входные данные. Это понадобится для отображения данных в режиме приемки:

    ```javascript
    if (outputValues.imgs && outputValues.imgs.length > 0) {
    data.imgs = [];
    for (var i = 0; i < outputValues.imgs.length; i++) {
    data.imgs.push(workspaceOptions.apiOrigin + '/api/attachments/' + outputValues.imgs[i] + '/preview');
    }
    }
    ```

1. Добавьте валидацию.

    Найдите функцию `validate`. В ней находится код для проверки заполнения полей для каждой из кнопок. Например, в шаблоне «Фото товара и ценника» этот фрагмент выглядит так:

    ```javascript
    else if (solution.output_values.verdict === 'ok') {
    // код проверки полей кнопки ok
    if (!solution.output_values.imgs_facade || solution.output_values.imgs_facade.length === 0) {
    // код проверки поля imgs_facade
    }

    if (!solution.output_values.imgs_item || solution.output_values.imgs_item.length === 0) {
    // код проверки поля imgs_item
    }

    if (!solution.output_values.imgs_price || solution.output_values.imgs_price.length === 0) {
    // код проверки поля imgs_price
    }

    } else if (solution.output_values.verdict === 'no_price') {
    // код проверки полей кнопки no_price
    }
    } else if (solution.output_values.verdict === 'no_item') {
    // код проверки полей кнопки no_item
    }
    } else if (solution.output_values.verdict === 'no_shop') {
    // код проверки полей кнопки no_shop
    }
    ```

    Вставьте после закрывающей фигурной скобки с вердиктом для последней кнопкой следующий код:

    ```javascript
    else if (solution.output_values.verdict === 'new_verdict') {
    if (!solution.output_values.imgs || solution.output_values.imgs.length === 0) {
    this.errors = this.addError('Нужно приложить фото', "imgs", this.errors);
    } else if (solution.output_values.imgs.length < 2) {
    this.errors = this.addError('Должно быть хотя бы 2 фото', "imgs", this.errors);
    }

    if (!solution.output_values.new_comment || solution.output_values.new_comment.trim() === '') {
    this.errors = this.addError('Нужно написать комментарий', "new_comment", this.errors);
    }
    }
    ```

{% include [contact-support](../_includes/contact-support.md) %}

{% include [image-styles](../../../_includes/image-styles-internal.md) %}