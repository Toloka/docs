# @yandex-toloka/helper.proxy

{% include [deprecate](../../_includes/deprecate.md) %}

Компонент позволяет загружать файлы с Яндекс Диска.

Чтобы использовать `@yandex-toloka/helper.proxy`, подключите Яндекс Диск к своему аккаунту в Толоке и добавьте прокси по [инструкции](../../guide/concepts/prepare-data.md).

Выберите компонент, который хотите добавить. Например, [view.image](view.image.md) — для картинки или [view.audio](view.audio.md) — для аудиофайла. В свойстве `url` этого компонента выберите тип `@yandex-toloka/helper.proxy`.

[![Посмотреть пример в песочнице](../_images/buttons/view-example.svg)](https://ya.cc/t/_XrwbL4V3ttEhW)

## Свойства компонента {#properties}

#|
|| **Название** | **Тип** | **Описание** ||
|| `type`<span style="color: red">\*</span> | "@yandex-toloka/helper.proxy" | Задает тип компонента. ||
|| `path`<span style="color: red">\*</span> | _string_ | Путь к файлу в формате `/<имя прокси>/<имя файла>.<тип>`. ||
|#
