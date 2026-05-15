---
title: API de REST para registrar un conector de fuente de datos
description: Obtenga información acerca de la API de REST para registrar un conector de fuente de datos
exl-id: e2811892-c3cf-41f5-94d8-c2b37823a53a
feature: Rest API Data Source
role: Developer
level: Experienced
TQID: https://experienceleague.adobe.com/WkCyxrOF9CD7KpD9J2255WepzYLLJo8ilvB2keTxgJ0
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: bce87dde-a4ab-44c9-8a18-ad66e4ddb377
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 81
ht-degree: 7%

---

# API de REST para registrar un conector de fuente de datos {#id236LG0Y0CXA}

La siguiente API de REST le permite registrar un conector de fuente de datos.

## Registrar un conector de origen de datos

Método de GET que registra un conector de origen de datos.

**URL de solicitud**:

`http://server:port/bin/guides/v1/konnect/config/register?path=<uploaded file path>`

**Parámetros**:

| Nombre | Tipo | Requerido | Descripción |
|----|----|--------|-----------|
| `path` | Cadena | Sí | Una cadena que señala a una ruta en el repositorio de AEM. Puede ser una ruta de acceso en `/content/dam or /var/dxml`. |

**Ejemplo**:

`http://host:4502/bin/guides/v1/konnect/config/register?path=/var/dxml/konnect/jira.json`
