
Чтобы получить значение из конкретного элемента массива, укажите в пути его порядковый номер, начиная с нуля.

Например, во входных данных указан массив ссылок на изображения:
```json
{
  "images": [
    "https://cdn.stocksnap.io/img-thumbs/960w/surfer-wave_3DBOYBPB3X.jpg",
    "https://cdn.stocksnap.io/img-thumbs/960w/fisherman-silhouette_UADULRRHEK.jpg",
    "https://cdn.stocksnap.io/img-thumbs/960w/old-photo_GEQ27OWZVV.jpg"
  ]
}
```
Сослаться на конкретный элемент массива можно так:
```json
"url": {
  "type": "data.input",
  "path": "images.<Номер элемента, начиная с нуля>"
}
```

[![](../../../../_images/buttons/view-example.svg)](https://ya.cc/t/ER1ZQcx63YEySx)
