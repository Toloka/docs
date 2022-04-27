# Попарное сравнение аудио

Посмотрите пример — он состоит из двух аудио и кнопок выбора ответа. В нем уже настроена валидация, горячие клавиши и внешний вид задания.

#### Из каких компонентов состоит этот пример

- [view.audio](../reference/view.audio.md) — аудиоплеер;
- [layout.columns](../reference/layout.columns.md) — размещает аудиодорожки справа и слева друг от друга;
- [condition.played](../reference/condition.played.md) — проверяет, что пользователь начал слушать аудио;
- [field.button-radio-group](../reference/field.button-radio-group.md) — кнопки вариантов ответа;
- [condition.required](../reference/condition.required.md) — проверяет, что выбран хотя бы один вариант;
- [plugin.toloka](../reference/plugin.toloka.md) — настраивает внешний вид задания;
- [plugin.hotkeys](../reference/plugin.hotkeys.md) — [горячие клавиши](../best-practices/hotkeys.md).

{% include [toloka-tb-source-add-media](../_includes/toloka-tb-source/id-toloka-tb-source/add-media.md) %}



## Что еще можно настроить {#add-more}

- Добавьте [проверку](../best-practices/conditions.md), что аудио прослушали до конца — замените компонент [condition.played](../reference/condition.played.md) на [condition.played-fully](../reference/condition.played-fully.md).

- Пригодится для коротких аудио — поставьте их на повтор, добавив в свойства компонента [view.audio](../reference/view.audio.md)`loop: true`.

- Добавьте [горячие клавиши](../best-practices/hotkeys.md) с помощью плагина [plugin.hotkeys](../reference/plugin.hotkeys.md) для воспроизведения или остановки аудиозаписи.


Если вам не подходит этот шаблон, посмотрите другие примеры в этом разделе.


## Добавить поле для ввода ответа {#add-text-area}

Если вам нужны комментарии от исполнителя, то добавьте поле для ввода текста с помощью [field.textarea](../reference/field.textarea.md). В этом примере настроена дополнительная валидация, которая обязывает написать текст, если выбрано одно из двух аудио.


## Расположить друг под другом {#top-bottom}

Аудио можно расположить друг под другом. Этот интерфейс лучше подойдет для сравнения более двух аудиозаписей.


## Добавить исходный текст {#add-original-text}

Вы можете добавить поле с исходным текстом с помощью компонента [view.text](../reference/view.text.md). Например, если вы хотите выяснить, какая из аудиозаписей лучше подходит под описание.


## Добавить оформление {#add-color}

Также вы можете цветом оформлять разные типы данных с помощью [view.alert](../reference/view.alert.md), чтобы исполнитель легче в них ориентировался. В этом примере исходный текст выделен синей рамкой, а кнопки — желтой.


[![](../_images/buttons/contact-support.svg)](../concepts/support.md)
