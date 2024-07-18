---
title: API de REST para registrar un conector de fuente de datos
description: Obtenga información acerca de la API de REST para registrar un conector de fuente de datos
exl-id: e2811892-c3cf-41f5-94d8-c2b37823a53a
feature: Rest API Data Source
role: Developer
level: Experienced
source-git-commit: b4762314ec5269abe62b622184f1724762a6cfa0
workflow-type: tm+mt
source-wordcount: '81'
ht-degree: 7%

---

# API de REST para registrar un conector de fuente de datos {#id236LG0Y0CXA}

La siguiente API de REST le permite registrar un conector de fuente de datos.

## Registrar un conector de origen de datos

Método de GET que registra un conector de origen de datos.

**URL de solicitud**:
`http://server:port/bin/guides/v1/konnect/config/register?path=<uploaded file path>`

**Parámetro**:

| Nombre | Tipo | Requerido | Descripción |
|----|----|--------|-----------|
| `path` | Cadena | Sí | AEM Una cadena que señala a una ruta en el repositorio de. Puede ser una ruta de acceso en `/content/dam or /var/dxml`. |

**Ejemplo**:\
`http://host:4502/bin/guides/v1/konnect/config/register?path=/var/dxml/konnect/jira.json`
