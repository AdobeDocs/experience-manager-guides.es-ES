---
title: API de REST para crear y activar paquetes
description: Obtenga información acerca de la API de REST para crear y activar paquetes
exl-id: 90686f77-a769-44bc-90eb-116cf9d0341e
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '117'
ht-degree: 0%

---

# API de REST para crear y activar paquetes {#id198CF0260Y4}

La siguiente API de REST le permite crear y activar paquetes CRX.

## Crear y activar paquete

Método de POST que crea y activa el paquete CRX.

**URL de solicitud**: http://*&lt;aem-guides-server>*: *&lt;port-number>*/bin/fmdita/activate

**Parámetros**: la consulta de solicitud consiste en la cadena de reglas JSON. El tipo de contenido de la solicitud del POST debe configurarse como `application/json; charset=UTF-8`.

**Ejemplo**: Los siguientes ejemplos muestran la llamada de API mediante el comando curl:

    &quot;
    curl -u &lt;*username*>:&lt;*password*> -H &quot;Content-Type: application/json; charset=UTF-8&quot; -k -X POST -d &quot;{[JSON rules string](create-activate-package-java.md#example-create-activate-package-id198JH0B905Z)}&quot; http://&lt;*aem-guides-server*>:&lt;*port-number*>/bin/fmdita/activate
    &quot;
