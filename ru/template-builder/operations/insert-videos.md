# Вставить видео

{% include [deprecate](../../_includes/deprecate.md) %}

В этом разделе описано, как [вставить видео](#insert-videos) и [убедиться, что исполнитель его посмотрел](#condition.played).

## Вставить видео {#insert-video}

Чтобы добавить видеофайл в интерфейс задания, используйте компонент [view.video](../reference/view.video.md). В свойстве `url` укажите прямую ссылку на файл или компонент, который её возвращает. Чтобы подставить ссылку из входных данных, используйте компонент [data.input](work-with-data.md).

Если вы хотите добавить несколько видео на страницу, посмотрите примеры в разделе [Сравнить видеоклипы](sbs-video.md).

{% include [toloka-tb-source-add-media](../_includes/toloka-tb-source/id-toloka-tb-source/add-media.md) %}

[![](../_images/buttons/view-example.svg)](https://ya.cc/t/T6s_9l6I3tvLFS)

## Убедиться, что исполнитель посмотрел видео {#condition.played}

{% list tabs %}

- Начал смотреть

  Чтобы убедиться, что исполнитель запускал видео, в свойстве `validation` используйте компонент `condition.played`.

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/3hZrRnKo3tvLeY)

- Посмотрел до конца

  Чтобы убедиться, что исполнитель посмотрел видео полностью, в свойстве `validation` используйте компонент `condition.played-fully`.

  [![](../_images/buttons/view-example.svg)](https://ya.cc/t/vLFe4mDm3tvLuX)

{% endlist %}

[![](../_images/buttons/contact-support.svg)](../concepts/support.md)