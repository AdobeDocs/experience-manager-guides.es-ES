---
title: API de REST para crear y activar paquetes
description: Obtenga información sobre la API de REST para crear y activar paquetes
exl-id: 90686f77-a769-44bc-90eb-116cf9d0341e
feature: Rest API Packages
role: Developer
level: Experienced
source-git-commit: b95a64ca2e8ebffebec3d8ff8704f76f7faceca2
workflow-type: tm+mt
source-wordcount: '205'
ht-degree: 0%

---

# API de REST para crear y activar paquetes {#id198CF0260Y4}

La siguiente API de REST le permite crear y activar paquetes CRX.

## Crear y activar el paquete

Una método POST que crea y activa el paquete CRX.

**Solicitar URL**:
http://*&lt;aem-guides-server\>*: *&lt;port-number\>*/bin/fmdita/activate&lt;/port-number\>&lt;/aem-guides-server\>

**Parámetros**:
El solicitud consulta consiste en la cadena de reglas JSON. La tipo de contenido del petición POST debe establecerse en `application/json; charset=UTF-8`.

**Ejemplo**:
En el siguiente ejemplo se muestra la llamada a la API mediante el comando curl:

```XML
curl -u <*username*>:<*password*> -H "Content-Type: application/json; charset=UTF-8"  -k -X POST -d "{[JSON rules string](create-activate-package-java.md#example-create-activate-package-id198JH0B905Z)}" http://<*aem-guides-server*>:<*port-number*>/bin/fmdita/activate
```


**Parámetro opcional**

`activationTarget`

**Valores válidos**

`preview` o `publish` para Cloud Service y `publish` para software local

- Por Cloud Service, si el parámetro contiene un valor no válido, se produce un error en el activación del paquete.

- En el caso del software local, si el parámetro contiene un valor no válido, se registra el error y la publicación se realiza utilizando el valor predeterminado, `publish`.

Si no define el parámetro opcional, `activationTarget`, se activa utilizando el agente de publicar predeterminado tanto para el software Cloud Service como para el local.



El siguiente ejemplo muestra la llamada a la API utilizando el comando curl con el parámetro opcional:


    &#39;&#39;&#39;XML
    
    curl -u &lt;*username*>:&lt;*password*> -H &quot;Content-Type: aplicación/json; charset=UTF-8&quot; -k -X POST -d &quot;{[JSON rules string](create-activate-package-java.md#example-create-activate-package-id198JH0B905Z)}&quot; http://&lt;*aem-guides-server*>:&lt;*port-number*>/bin/fmdita/activate?activationTarget=&#39;&lt;validActivationTargetValue>&#39;
    &#39;&#39;&#39;
&lt;/validActivationTargetValue>&lt;/*port-number*>&lt;/*aem-guides-server*>&lt;/*password*>&lt;/*username*>