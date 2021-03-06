---
title: Implementación de un reproductor de vídeo
description: En este artículo se explica cómo implementar una aplicación de reproductor de vídeo mediante Xamarin.Forms.
ms.prod: xamarin
ms.assetid: 0CE9BEE7-4F81-4A00-B9B3-5E2535CD3050
ms.technology: xamarin-forms
author: davidbritch
ms.author: dabritch
ms.date: 02/12/2018
ms.openlocfilehash: 1677f86379310ee6d5e0973108f85db2a328cd23
ms.sourcegitcommit: be6f6a8f77679bb9675077ed25b5d2c753580b74
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/07/2018
ms.locfileid: "53048836"
---
# <a name="implementing-a-video-player"></a>Implementación de un reproductor de vídeo

[![Descargar ejemplo](~/media/shared/download.png) Descargar el ejemplo](https://developer.xamarin.com/samples/xamarin-forms/customrenderers/VideoPlayerDemos/)

A veces es conveniente reproducir archivos de vídeo en una aplicación de Xamarin.Forms. En esta serie de artículos se explica cómo escribir representadores personalizados para iOS, Android y la plataforma Universal de Windows (UWP) para una clase de Xamarin.Forms denominada `VideoPlayer`.

En el ejemplo [**VideoPlayerDemos**](https://developer.xamarin.com/samples/xamarin-forms/customrenderers/VideoPlayerDemos/), todos los archivos que implementan y admiten `VideoPlayer` están en carpetas denominadas `FormsVideoLibrary` y se identifican con el espacio de nombres `FormsVideoLibrary` o los espacios de nombres que empiezan por `FormsVideoLibrary`. Esta organización y nomenclatura debería hacer que resulte más fácil copiar los archivos del reproductor de vídeo en su propia solución de Xamarin.Forms.

`VideoPlayer` puede reproducir archivos de vídeo de tres tipos de orígenes:

- Internet mediante una dirección URL
- Un recurso insertado en la aplicación de plataforma
- La biblioteca de vídeos del dispositivo

Los reproductores de vídeo necesitan *controles de transporte*, que son botones para reproducir y pausar el vídeo, y una barra de posición que muestra el progreso a través del vídeo y permite al usuario ir rápidamente a una ubicación diferente. `VideoPlayer` puede usar los controles de transporte y la barra de posición proporcionados por la plataforma (como se muestra más adelante), o puede proporcionar controles de transporte personalizados y una barra de posición. Este es el programa que se ejecuta en iOS, Android y la Plataforma universal de Windows:

[![Reproducir vídeo web](web-videos-images/playwebvideo-small.png "Reproducir vídeo web")](web-videos-images/playwebvideo-large.png#lightbox "Reproducir vídeo web")

Por supuesto, puede colocar el teléfono en horizontal para tener una vista más grande.

Un reproductor de vídeo más sofisticado tendría algunas características adicionales, como un control de volumen, un mecanismo para interrumpir el vídeo cuando entra una llamada telefónica y una manera de mantener la pantalla activa durante la reproducción.

En los siguientes artículos se muestra progresivamente cómo se compilan los representadores de plataforma y las clases auxiliares:

## <a name="creating-the-platform-video-playersplayer-creationmd"></a>[Creación de reproductores de vídeo de la plataforma](player-creation.md)

Cada plataforma necesita una clase `VideoPlayerRenderer` que crea y mantiene un control de reproductor de vídeo compatible con la plataforma. En este artículo se muestra la estructura de las clases del representador y cómo se crean los reproductores.

## <a name="playing-a-web-videoweb-videosmd"></a>[Reproducir vídeo web](web-videos.md)

Probablemente el origen más común de vídeos para cualquier reproductor de vídeo es Internet. En este artículo se describe cómo se puede hacer referencia a un vídeo web y cómo usarlo como origen para el reproductor de vídeo.

## <a name="binding-video-sources-to-the-playersource-bindingsmd"></a>[Enlazar orígenes de vídeo con el reproductor](source-bindings.md)

En este artículo se usa `ListView` para presentar una colección de vídeos para reproducirlos. Un programa muestra cómo el archivo de código subyacente puede establecer el origen de vídeo del reproductor de vídeo, pero un segundo programa muestra cómo puede usar el enlace de datos entre `ListView` y el reproductor de vídeo.

## <a name="loading-application-resource-videosloading-resourcesmd"></a>[Cargar vídeos de recursos de aplicación](loading-resources.md)

Los vídeos se pueden insertar como recursos en los proyectos de plataforma. En este artículo se muestra cómo almacenar esos recursos y después cargarlos en el programa para reproducirlos en el reproductor de vídeo.

## <a name="accessing-the-devices-video-libraryaccessing-librarymd"></a>[Acceder a la biblioteca de vídeos del dispositivo](accessing-library.md)

Cuando se crea un vídeo con la cámara del dispositivo, el archivo de vídeo se almacena en la biblioteca de imágenes del dispositivo. En este artículo se muestra cómo acceder al selector de imágenes del dispositivo para seleccionar el vídeo y, luego, reproducirlo con el reproductor de vídeo.

## <a name="custom-video-transport-controlscustom-transportmd"></a>[Controles de transporte de vídeo personalizados](custom-transport.md)

Aunque los reproductores de vídeo en cada plataforma proporcionan sus propios controles de transporte en forma de botones para **reproducir** y **pausar**, puede suprimir la presentación de estos botones y proporcionar los suyos propios. En este artículo se muestra cómo hacerlo.

## <a name="custom-video-positioningcustom-positioningmd"></a>[Barra de posición de vídeo personalizada](custom-positioning.md)

Todos los reproductores de vídeo de la plataforma tienen una barra de posición que muestra el progreso del vídeo y permite avanzar o retroceder a una posición determinada. En este artículo se muestra cómo sustituir esa barra de posición por un control personalizado.





## <a name="related-links"></a>Vínculos relacionados

- [Demostraciones de reproductor de vídeo (ejemplo)](https://developer.xamarin.com/samples/xamarin-forms/customrenderers/VideoPlayerDemos/)
