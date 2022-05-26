# @yandex-toloka/helper.proxy

Компонент позволяет загружать файлы с Яндекс&#160;Диска.

Чтобы использовать `@yandex-toloka/helper.proxy`, подключите Яндекс&#160;Диск к своему аккаунту в Толоке и добавьте прокси по [инструкции](https://toloka.ai/ru/docs/guide/concepts/prepare-data.html).

Выберите компонент, который хотите добавить. Например, [view.image](view.image.md) — для картинки или [view.audio](view.audio.md) — для аудиофайла. В свойстве `url` этого компонента выберите тип `@yandex-toloka/helper.proxy`.

[Посмотреть пример в песочнице](https://clck.ru/SP3Bd).

## Свойства компонента {#properties}

#|
|| **Название** | **Тип** | **Описание** ||
|| `type`<span style="color: red">\*</span> | "@yandex-toloka/helper.proxy" | Задает тип компонента. ||
|| `path`<span style="color: red">\*</span> | _string_ | Путь к файлу в формате `/<имя прокси>/<имя файла>.<тип>`. ||
|#
