# @yandex-toloka/helper.proxy

Компонент позволяет загружать файлы с Яндекс.Диска.

Чтобы использовать `@yandex-toloka/helper.proxy`, подключите Яндекс.Диск к своему аккаунту в Толоке и добавьте прокси по [инструкции](https://toloka.ai/ru/docs/guide/concepts/prepare-data.html).

Выберите компонент, который хотите добавить. Например, [view.image](view.image.md) — для картинки или [view.audio](view.audio.md) — для аудиофайла. В свойстве `url` этого компонента выберите тип `@yandex-toloka/helper.proxy`.

[Посмотреть пример в песочнице](https://clck.ru/SP3Bd).

## Свойства компонента {#properties}

| Название                                 | Тип                                                                              | Описание                                                                           |
| ---------------------------------------- | -------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------- |
| `type`<span style="color: red">\*</span> | "@yandex-toloka/helper.proxy"                                                    | <p>Задает тип компонента.</p>                                                      |
| `path`<span style="color: red">\*</span> | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a> | <p>Путь к файлу в формате `/&lt;имя прокси&gt;/&lt;имя файла&gt;.&lt;тип&gt;`.</p> |
