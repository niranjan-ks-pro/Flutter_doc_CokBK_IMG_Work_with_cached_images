# Flutter_doc_CokBK_IMG_Work_with_cached_images
 https://docs.flutter.dev/cookbook/images/cached-images#complete-example
Work with cached images
=======================

1.  [Cookbook](https://docs.flutter.dev/cookbook)
2.  [Images](https://docs.flutter.dev/cookbook/images)
3.  [Work with cached images](https://docs.flutter.dev/cookbook/images/cached-images)

In some cases, it's handy to cache images as they're downloaded from the web, so they can be used offline. For this purpose, use the [`cached_network_image`](https://pub.dev/packages/cached_network_image) package.

info Note: To learn more, watch this short Package of the Week video on the cached_network_image package:

In addition to caching, the `cached_network_image` package also supports placeholders and fading images in as they're loaded.

content_copy

```
CachedNetworkImage(
  imageUrl: 'https://picsum.photos/250?image=9',
);
```

[](https://docs.flutter.dev/cookbook/images/cached-images#adding-a-placeholder)Adding a placeholder
---------------------------------------------------------------------------------------------------

The `cached_network_image` package allows you to use any widget as a placeholder. In this example, display a spinner while the image loads.

content_copy

```
CachedNetworkImage(
  placeholder: (context, url) => const CircularProgressIndicator(),
  imageUrl: 'https://picsum.photos/250?image=9',
),
```

[](https://docs.flutter.dev/cookbook/images/cached-images#complete-example)Complete example
-------------------------------------------------------------------------------------------

content_copy

```
import 'package:cached_network_image/cached_network_image.dart';
import 'package:flutter/material.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    const title = 'Cached Images';

    return MaterialApp(
      title: title,
      home: Scaffold(
        appBar: AppBar(
          title: const Text(title),
        ),
        body: Center(
          child: CachedNetworkImage(
            placeholder: (context, url) => const CircularProgressIndicator(),
            imageUrl: 'https://picsum.photos/250?image=9',
          ),
        ),
      ),
    );
  }
}
```
