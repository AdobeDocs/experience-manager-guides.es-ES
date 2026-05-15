---
title: API de REST para crear y activar paquetes
description: Obtenga información acerca de la API de REST para crear y activar paquetes
exl-id: 90686f77-a769-44bc-90eb-116cf9d0341e
feature: Rest API Packages
role: Developer
level: Experienced
TQID: https://experienceleague.adobe.com/cJUVS3QdzVhnZjFF7uoHfpOSBefgm5W2jh-kWM1PvmE
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a01bfd36-4ab8-4bf8-9dc0-5b45b890552e
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: c6d09140-3c91-45d3-b7ed-b681af752f43
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 181
ht-degree: 0%

---

# API de REST para crear y activar paquetes {#id198CF0260Y4}

La siguiente API de REST le permite crear y activar paquetes de CRX.

## Crear y activar paquete

Un método POST que crea y activa un paquete de CRX.

**URL de solicitud**:
http://*&lt;aem-guides-server\>*: *&lt;port-number\>*/bin/fmdita/activate

**Parámetros**:
La consulta de solicitud consiste en la cadena de reglas JSON. El tipo de contenido de la petición POST debe establecerse en `application/json; charset=UTF-8`.

**Ejemplo**:
El siguiente ejemplo muestra la llamada de API mediante el comando curl:

```XML
curl -u <*username*>:<*password*> -H "Content-Type: application/json; charset=UTF-8"  -k -X POST -d "{[JSON rules string](create-activate-package-java.md#example-create-activate-package-id198JH0B905Z)}" http://<*aem-guides-server*>:<*port-number*>/bin/fmdita/activate
```


**Parámetro opcional**

`activationTarget`

**Valores válidos**

`preview` o `publish` para Cloud Service y `publish` para software On-Premise

- Para Cloud Service, si el parámetro contiene un valor no válido, se produce un error en la activación del paquete.

- Para el software On-Premise, si el parámetro contiene un valor no válido, el error se registra y la publicación se realiza con el valor predeterminado `publish`.

Si no define el parámetro opcional `activationTarget`, se activará usando el agente de publicación predeterminado tanto para Cloud Service como para el software On-Premise.



El siguiente ejemplo muestra la llamada de API mediante el comando curl con un parámetro opcional:


```XML
curl -u <*username*>:<*password*> -H "Content-Type: application/json; charset=UTF-8"  -k -X POST -d "{[JSON rules string](create-activate-package-java.md#example-create-activate-package-id198JH0B905Z)}" http://<*aem-guides-server*>:<*port-number*>/bin/fmdita/activate?activationTarget=`<validActivationTargetValue>`
```
