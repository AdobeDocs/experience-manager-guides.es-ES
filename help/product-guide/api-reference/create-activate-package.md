---
title: API de REST para crear y activar paquetes
description: Obtenga información acerca de la API de REST para crear y activar paquetes
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

La siguiente API de REST le permite crear y activar paquetes de CRX.

## Crear y activar paquete

Método de POST que crea y activa un paquete de CRX.

**URL de solicitud**:
http://*&lt;aem-guides-server\>*: *&lt;port-number\>*/bin/fmdita/activate

**Parámetros**:
La consulta de solicitud consiste en la cadena de reglas JSON. El tipo de contenido de la solicitud del POST debe establecerse en `application/json; charset=UTF-8`.

**Ejemplo**:
El siguiente ejemplo muestra la llamada de API mediante el comando curl:

```XML
curl -u <*username*>:<*password*> -H "Content-Type: application/json; charset=UTF-8"  -k -X POST -d "{[JSON rules string](create-activate-package-java.md#example-create-activate-package-id198JH0B905Z)}" http://<*aem-guides-server*>:<*port-number*>/bin/fmdita/activate
```


**Parámetro opcional**

`activationTarget`

**Valores válidos**

`preview` o `publish` para el Cloud Service y `publish` para el software On-Premise

- Para el Cloud Service, si el parámetro contiene un valor no válido, se produce un error en la activación del paquete.

- Para el software On-Premise, si el parámetro contiene un valor no válido, el error se registra y la publicación se realiza con el valor predeterminado `publish`.

Si no define el parámetro opcional `activationTarget`, se activará usando el agente de publicación predeterminado tanto para el Cloud Service como para el software On-Premise.



El siguiente ejemplo muestra la llamada de API mediante el comando curl con un parámetro opcional:


    &quot;XML
    
    curl -u &lt;*username*>:&lt;*password*> -H &quot;Content-Type: application/json; charset=UTF-8&quot; -k -X POST -d &quot;{[JSON rules string](create-activate-package-java.md#example-create-activate-package-id198JH0B905Z)}&quot; http://&lt;*aem-guides-server*>:&lt;*port-number*>/bin/fmdita/activate?activationTarget=`&lt;validActivation TargetValue>`
    &quot;
