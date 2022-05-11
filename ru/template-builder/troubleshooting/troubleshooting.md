# Решение проблем

## Видео и аудио {#media}

#### Не воспроизводится видео или аудио

При воспроизведении медиафайлов по ссылкам могут возникать ошибки. В окне предпросмотра показывается причина этих ошибок. В таблице ниже описано, как их решить.
**Текст ошибки:** воспроизведение было прервано

**Причина и исправление:**
**Причина:** получение и загрузка медиафайла прерваны пользователем.

**Как исправить:** перезагрузите страницу.


**Текст ошибки:** не удалось скачать видео/аудио из-за проблем с сетью

**Причина и исправление:**
**Причина:** не удается загрузить медиафайл из-за обрыва или нестабильности сетевого соединения.

**Как исправить:** проверьте сетевое соединение и перезагрузите страницу.


**Текст ошибки:** формат не поддерживается вашим устройством

**Причина и исправление:**
**Причина:** неудачная попытка декодировать медиафайл.

Например, если формат медиафайла не соответствует кодеку устройства или файл поврежден.

**Как исправить:**
1. Проверьте медиафайл, возможно он поврежден.
1. Переустановить или добавить кодеки операционной системы устройства.


**Текст ошибки:** проблемы с загрузкой видео/аудио, либо по этому адресу находится не видео

**Причина и исправление:** **Возможные причины и решения:**
- **Причина:** отсутствует медиафайл по адресу ссылки.

    **Как исправить:** проверьте, что вы указали верную ссылку на медиафайл.

- **Причина:** не поддерживается формат медиафайла. Поддержка форматов зависит от браузера, ОС и устройства пользователя.
    **Как исправить:** попробуйте использовать файлы в одном из указанных форматов.
    #### Форматы видео

    - [MP4]({{ wiki-mp4 }}) с кодировкой H.264 или H.265 — рекомендуемый формат;
    - [WebM]({{ wiki-webm }});
    - [MPEG]({{ wiki-mpeg }}).

    #### Форматы аудио

    - [FLAC]({{ wiki-flac }});
    - [MP3]({{ wiki-mp3 }}) — рекомендуемый формат;
    - [OGG]({{ wiki-ogg }});
    - [OPUS]({{ wiki-opus }});
    - [WAV]({{ wiki-wav }}).

- **Причина:** сервер, на котором хранится медиафайл, не отправляет его на требуемую страницу, а возвращает пустую или с уведомлением «Доступ запрещен», так как загружаемый файл определяется на неизвестном домене.

    **Как исправить:** исправьте настройки на вашем сервере или замените домен, с которого отправляется запрос на загрузку медиафайла.

- **Причина:** на сервере произошел сбой или сетевое соединение было прервано.

    **Как исправить:** проверьте доступ к серверу, сетевое соединение и повторите загрузку медиафайла.

## Горячие клавиши {#hotkey}

#### Не отображается горячая клавиша

Чтобы в интерфейсе отображалась горячая клавиша, задайте ей то же действие ([action](../reference/actions.md)), которое происходит при нажатии кнопки.

Если для компонента действие не задано, то его необходимо назначить:
- [action.set](../reference/action.set.md) для радио-кнопок;
- [action.toggle](../reference/action.toggle.md) для чекбоксов;
- [action.play-pause](../reference/action.play-pause.md) для управления воспроизведением;
- [action.open-close](../reference/action.open-close.md) для увеличения картинки.

Полный список действий можно посмотреть в разделе [Список действий](../reference/actions.md).

Особенности:

- Тип данных для действий должен совпадать. Например, горячая клавиша будет работать, но не будет отображаться, если кнопка при нажатии записывает в результат строку `“true”`, а для горячей клавиши указано логическое значение `true`.
- Если при нажатии кнопки вызывается несколько действий ([action.bulk](../reference/action.bulk.md)), то их последовательность для горячей клавиши должна быть такой же.
- Если используется условный оператор для выбора действия, например [helper.if](../reference/helper.if.md), то при нажатии горячей клавиши должен вызываться тот же условный оператор (**helper.if**) по тем же правилам.

## Экранирование

#### Как вставить кавычки и слеш в JSON

{% include [json-guide-escaping_json](../_includes/quickstart/id-json-guide/escaping_json.md) %}