---
title: Notas de versión | Notas de la versión de Adobe Experience Manager Guides 5.2.0 Service Pack 4
description: Obtenga información acerca del proceso de actualización y las correcciones de errores en la versión 5.2.0 del Service Pack 4 de Adobe Experience Manager Guides
role: Leader
TQID: https://experienceleague.adobe.com/HEWV5RxPUfqUYf6m6kQW-fU-LiAM0UFGbfzKjtOCZxk
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
source-git-commit: a232c8a03cda9b0ef7ae8114c3d901df5fb5bcb4
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 1%
---
# Notas de la versión del paquete de servicio 4 5.2.0 (noviembre de 2026)

Este artículo proporciona información sobre las instrucciones de actualización, la compatibilidad con Java SDK, los problemas corregidos y los problemas conocidos de la versión 5.2.0 del Service Pack 4 de Adobe Experience Manager Guides.

## Recursos de Java SDK

Utilice los siguientes recursos al desarrollar complementos de Java personalizados o integraciones con Experience Manager Guides. Asegúrese de que la versión de SDK coincida con la versión de Experience Manager Guides instalada.

| Versión | Versión de Java SDK | Maven Central | Referencia de API de Java |
|---|---|---|----|
| Paquete de servicio 4 (UUID) de 5.2.0 | 5.2.2 | [API de AEM Guides SDK 5.2.2](https://central.sonatype.com/artifact/com.adobe.aem/aem-guides-sdk-api/5.2.2/) | [Javadoc 5.2.2](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api/latest/index.html) |

Para obtener más información, vea [Configurar y usar el JAR de API del repositorio de Maven Central](https://experienceleague.adobe.com/es/docs/experience-manager-guides/using/api-reference/introduction).

## Actualice a la versión 5.2.0 del paquete de servicio 4 de Experience Manager Guides

Obtenga información sobre cómo instalar la versión de Experience Manager Guides 5.2.0 Service Pack 4.

>[!NOTE]
>
>Esta versión solo está disponible para AEM 6.5 LTS. El paquete de servicio compatible es AEM 6.5 LTS Service Pack 2.

### Requisitos previos

Antes de iniciar el proceso de actualización del paquete de servicio 4 de Experience Manager Guides 5.2.0, asegúrese de utilizar el paquete de servicio 1 de la versión 5.2.0.

### Proceso de actualización para la versión 5.2.0 del paquete de servicio 4

1. Descargue el paquete de Experience Manager Guides versión 5.2.0 Service Pack 4.
1. Cargue el paquete en su instancia mediante el Administrador de paquetes (`/crx/packmgr`).
1. Instale el paquete. A continuación, compruebe que los paquetes `fmdita` hayan vuelto al estado **Activo**. Puede comprobar el estado del paquete en `/system/console/bundles`.
1. Borre la caché del explorador.

## Problemas solucionados

A continuación se enumeran los errores corregidos en varias áreas:

### Creación

- Cuando arrastra y suelta un recurso en un mapa desde el panel Explorador que no se ha actualizado después de que otro autor moviera ese recurso, se agrega una referencia rota al mapa. (GUIDES-57869)

### Administración de recursos

- Cuando sobrescribe un recurso no DITA existente, como una imagen, mediante la opción **Sobrescribir archivos existentes**, no se crea la nueva versión de la imagen cargada. Como resultado, la salida generada mediante la línea de base contiene el recurso más antiguo. (GUIDES-59287)

- Cuando un recurso no DITA, como una imagen, que se migró de una configuración sin UUID a una configuración de UUID se revierte o bifurca a otra versión, su UUID cambia. Las referencias existentes al recurso ya no se resuelven y la imagen aparece rota en los temas que hacen referencia a él. (GUIDES-58414)

### Publicación

- Al publicar un mapa mientras se exportan otros mapas, la salida utiliza de forma intermitente un formato de imagen de baja calidad en lugar de la imagen vectorial original. (GUIDES-55221)

## Problemas conocidos

Adobe ha identificado el siguiente problema conocido en la versión 5.2.0 del paquete de servicio 4:

- Cuando arrastra y suelta un elemento en una ubicación no válida, el Editor lo mueve a la posición válida más cercana, durante la cual la referencia puede conservar su ruta de acceso al repositorio. Del mismo modo, cuando se reemplaza una referencia existente en un mapa DITA mediante arrastrar y soltar, la nueva referencia puede conservar su ruta de acceso al repositorio. (GUIDES-60688)