# field.media-file

Добавляет кнопки для разных видов загрузки файлов: загрузить фото или видео, выбрать файлы из файлового менеджера или галереи. Настройте в свойстве `accept`, какая из кнопок вам нужна.

По умолчанию разрешает загрузить только один файл, но можно позволить загружать несколько в свойстве `multiple`.

Компонент будет удобен при работе с мобильных устройств. Для загрузки файлов с компьютера лучше использовать [field.file](field.file.md) для более гибкой настройки типов загружаемых файлов.

В режиме проверки задания загруженные изображения появятся автоматически. Изображения можно просматривать, поворачивать и переключаться между ними.

[Посмотреть пример в песочнице](https://clck.ru/S69wM).

## Особенности работы в мобильном приложении Толоки

В мобильном приложении Толоки кнопки для фото и видео откроют камеру, а кнопки галереи и файлового менеджера — соответствующие приложения.

После того как исполнитель отправит задание, файлы сохранятся внутри приложения и при подключении к Wi-Fi постепенно загрузятся в Толоку. Пока подключения нет, задание будет находиться в статусе «Ожидает отправку по Wi-Fi».

## Свойства компонента {#properties}

| Название                                   | Тип                                                                                    | Описание                                                                                                                                                                                                                     |
| ------------------------------------------ | -------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `type`<span style="color: red">\*</span>   | "field.media-file"                                                                     | <p>Задает тип компонента.</p>                                                                                                                                                                                                |
| `data`<span style="color: red">\*</span>   | <a class="xref popup-link" href="../concepts/types.dita#types/writable">writable</a>   | <p>Данные, значения которых будут обработаны или изменены.</p>                                                                                                                                                               |
| `label`                                    | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Надпись над компонентом.</p>                                                                                                                                                                                              |
| `accept`<span style="color: red">\*</span> | <a class="xref popup-link" href="../concepts/types.dita#types/object">object</a>       | <p>Добавляет разные кнопки для четырех видов загрузки. Передайте значение `true` тем из них, которые вам нужны. </p><p>Например, если нужна кнопка загрузки файлов из галереи, то добавьте в свойство `"gallery": true`.</p> |
| `accept.fileSystem`                        | <a class="xref popup-link" href="../concepts/types.dita#types/boolean">boolean</a>     | <p>Добавляет кнопку для загрузки файла из файлового менеджера.</p>                                                                                                                                                           |
| `accept.gallery`                           | <a class="xref popup-link" href="../concepts/types.dita#types/boolean">boolean</a>     | <p>Добавляет кнопку для загрузки файла из галереи.</p>                                                                                                                                                                       |
| `accept.photo`                             | <a class="xref popup-link" href="../concepts/types.dita#types/boolean">boolean</a>     | <p>Добавляет кнопку для загрузки изображения.</p>                                                                                                                                                                            |
| `accept.video`                             | <a class="xref popup-link" href="../concepts/types.dita#types/boolean">boolean</a>     | <p>Добавляет кнопку для загрузки видеофайла.</p>                                                                                                                                                                             |
| `hint`                                     | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Текст подсказки.</p>                                                                                                                                                                                                      |
| `multiple`                                 | <a class="xref popup-link" href="../concepts/types.dita#types/boolean">boolean</a>     | <p>Определяет, разрешено ли загружать несколько файлов:</p><ul><li>`false` (по умолчанию) — запрещено;</li><li>`true` — разрешено.</li></ul>                                                                                 |
| `requiredCoordinates`                      | <a class="xref popup-link" href="../concepts/types.dita#types/boolean">boolean</a>     | <p>Если `true`, то нельзя будет загрузить файл без геотега.</p>                                                                                                                                                              |
| `validation`                               | <a class="xref popup-link" href="../concepts/types.dita#types/condition">condition</a> | <p>Валидация на основе условия <em>(condition)</em>.</p>                                                                                                                                                                     |
