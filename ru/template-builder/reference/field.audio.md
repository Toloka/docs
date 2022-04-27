# field.audio

Компонент для записи аудио. Работает в приложении [Яндекс.Толока для мобильных](https://toloka.ai/tolokers/docs/mobile/?lang=ru). В браузере открывает окно для загрузки аудиофайла.

[Посмотреть пример в песочнице](https://clck.ru/Sbxas).

## Свойства компонента {#properties}

| Название                                 | Тип                                                                                    | Описание                                                                                                                                                     |
| ---------------------------------------- | -------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `type`<span style="color: red">\*</span> | "field.audio"                                                                          | <p>Задает тип компонента.</p>                                                                                                                                |
| `data`<span style="color: red">\*</span> | <a class="xref popup-link" href="../concepts/types.dita#types/writable">writable</a>   | <p>Данные, значения которых будут обработаны или изменены.</p>                                                                                               |
| `label`                                  | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Надпись над компонентом.</p>                                                                                                                              |
| `hint`                                   | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Текст подсказки.</p>                                                                                                                                      |
| `multiple`                               | <a class="xref popup-link" href="../concepts/types.dita#types/boolean">boolean</a>     | <p>Определяет, разрешено ли записывать (или загружать) несколько аудио:</p><ul><li>`false` (по умолчанию) — запрещено;</li><li>`true` — разрешено.</li></ul> |
| `validation`                             | <a class="xref popup-link" href="../concepts/types.dita#types/condition">condition</a> | <p>Валидация на основе условия <em>(condition)</em>.</p>                                                                                                     |
