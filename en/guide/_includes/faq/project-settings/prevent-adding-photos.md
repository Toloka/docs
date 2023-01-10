{% cut "How do I prevent adding photos from the gallery so that when the Toloker clicks the add photo button the camera opens, rather than the gallery/camera choice?" %}

Add `sources="CAMERA"` to the attributes of the image loading component. This disables adding photos from the gallery.

{% endcut %}