
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

[Посмотреть пример в песочнице](https://tb.yandex.net/editor?config=N4Igxg9gdgZglgcxALhMAOlABF9IBucApgO57JYbY64gAuAngA5Hm2GkB0ANnAM508AGkw1acOkQC2fNgG1RYyoqW1GLNng4lOcKQEMErECOqq8AVwBO3NlVVi864xTwATfXX26oTC4JMVBzwmTwALTRA9QyI+TgAGPCCxAF9krBTTVXtg+mYXdmIdaKNhdJxLGztymid8yI8vHz8ArIcKkFC6CJRxAyM4gEYksyU00ZxM9JzzPI1erSLdfuM22etbXpnc5wbPbzhffzKJpRDwyJLYzgAmEfbx1UeaAF1FcZSTKKO6FDRFPBXWS9BSjPBhOh0Jh8ZAAelhYDcUE4AggYAA1nwoPomLoILC9AgALTdCxSABGfFhAE4AGzxEiwvjWGBEKxEkj6fBEAD6AGYACIAIQA8gBNIUABSFfIAGpwAFZMBAnRwgCFQmHwxHI1EYrE4vEEqTE0kUql0hmw+B8MJsgxQIl8ODcMIQCxESG8gCqAEEBd6ADIAJWDAAkAKIAaUVytVtXVkOhcIRSJRdDRmOxuLg+MJJLCZMpNPpjIg3DcRKYbozPIA4hGAIo3ADsIoA6gAtABq3djKpAijeUE+KSAA).
