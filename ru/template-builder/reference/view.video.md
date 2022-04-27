# view.video

Плеер для воспроизведения видео.

Плеер — это прямоугольный блок с рамкой и кнопками для управления видео. Размер блока можно настроить с помощью свойств `ratio`, `fullHeight`, `minWidth` и `maxWidth`.

Разрешение видео на размер блока не влияет — видео будет вписано в блок и не обрежется.

## Свойства компонента {#properties}

| Название                                 | Тип                                                                                    | Описание                                                                                                                                         |
| ---------------------------------------- | -------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------ |
| `type`<span style="color: red">\*</span> | "view.video"                                                                           | <p>Задает тип компонента.</p>                                                                                                                    |
| `label`                                  | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Надпись над компонентом.</p>                                                                                                                  |
| `fullHeight`                             | <a class="xref popup-link" href="../concepts/types.dita#types/boolean">boolean</a>     | <p>Если `true`, элемент занимает все свободное пространство по вертикали. При этом элементу устанавливается минимальная высота 400 пикселей.</p> |
| `hint`                                   | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Текст подсказки.</p>                                                                                                                          |
| `maxWidth`                               | <a class="xref popup-link" href="../concepts/types.dita#types/number">number</a>       | <p>Максимальная ширина элемента в пикселях, которая не может быть меньше `minWidth`.</p>                                                         |
| `minWidth`                               | <a class="xref popup-link" href="../concepts/types.dita#types/number">number</a>       | <p>Минимальная ширина элемента в пикселях. Имеет приоритет над `maxWidth`.</p>                                                                   |
| `ratio`                                  | <a class="xref popup-link" href="../concepts/types.dita#types/array">array</a>         | <p>Соотношение сторон блока с видео. Массив из двух чисел: первое устанавливает ширину блока, второе — его высоту.</p>                           |
| `ratio[]`                                | <a class="xref popup-link" href="../concepts/types.dita#types/number">number</a>       | <p>Относительный размер одной стороны.</p>                                                                                                       |
| `url`<span style="color: red">\*</span>  | <a class="xref popup-link" href="../concepts/types.dita#types/string">string</a>       | <p>Ссылка на видеофайл.</p>                                                                                                                      |
| `validation`                             | <a class="xref popup-link" href="../concepts/types.dita#types/condition">condition</a> | <p>Валидация на основе условия <em>(condition)</em>.</p>                                                                                         |
