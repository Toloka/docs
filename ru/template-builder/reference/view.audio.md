# view.audio

Компонент воспроизводит аудио.

Поддержка форматов зависит от браузера, ОС и устройства пользователя. Рекомендуем использовать формат MP3.

## Свойства компонента {#properties}

| Название                                 | Тип                                                                                    | Описание                                                 |
| ---------------------------------------- | -------------------------------------------------------------------------------------- | -------------------------------------------------------- |
| `type`<span style="color: red">\*</span> | "view.audio"                                                                           | <p>Задает тип компонента.</p>                            |
| `label`                                  | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Надпись над компонентом.</p>                          |
| `hint`                                   | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Текст подсказки.</p>                                  |
| `loop`                                   | <a class="xref popup-link" href="../concepts/types.dita#types/boolean">boolean</a>     | <p>Автоматически повторять аудио.</p>                    |
| `url`<span style="color: red">\*</span>  | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Ссылка на аудио.</p>                                  |
| `validation`                             | <a class="xref popup-link" href="../concepts/types.dita#types/condition">condition</a> | <p>Валидация на основе условия <em>(condition)</em>.</p> |
