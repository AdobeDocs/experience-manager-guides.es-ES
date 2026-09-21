---
title: Notas de versión | Novedades de la versión de Adobe Experience Manager Guides 5.2.0 Service Pack 1
description: Obtenga información acerca de las funciones nuevas y mejoradas de la versión 5.2.0 del paquete de servicio 1 de Adobe Experience Manager Guides
role: Leader
TQID: https://experienceleague.adobe.com/dXXQ1YvVduT11vvF5qyXHLqnuo1xMKkAb5I-EoD2JAA
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
subfeature_v2:
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
    internal-label: Output generation
role_v2:
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
source-git-commit: 788d0b9a2e2f07d2990bcc4f984f3ba4a4aabf17
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 0%
---
# Novedades de la versión 5.2.0 del paquete de servicio 1 (septiembre de 2026)

Este artículo cubre las funciones nuevas y mejoradas introducidas con la versión 5.2.0 del paquete de servicio 1 de Adobe Experience Manager Guides.

Para ver la lista de problemas que se han corregido en esta versión, consulte [Problemas corregidos en la versión 5.2.0 del paquete de servicio 1](fixed-issues-5-2-0-sp1.md).

Obtenga información acerca de [instrucciones de actualización para el Service Pack 1 versión 5.2.0](../release-info/upgrade-instructions-5-2-0-sp1.md).


## Experience Manager Guides añade compatibilidad con MCP

Experience Manager Guides ahora es compatible con el protocolo de contexto de modelo (MCP). Puede conectar sus herramientas de IA como Claude, Cursor y más a Guías sin requerir ningún trabajo personalizado. A través de un único punto final de MCP, en esta versión, los usuarios autenticados pueden utilizar las guías como un sistema sin encabezado y administrar temas y mapas, crear y exportar líneas de base y generar informes, todo mientras operan con sus permisos de AEM existentes. Esto permite a los equipos de documentación trabajar de forma más eficiente mediante aplicaciones y agentes de IA.

Para obtener más información, vea [Usar el servidor MCP de Adobe Experience Manager Guides](../install-conf-guide/conf-aem-guides-mcp.md).


## Ahora se admite la compatibilidad con fuentes de datos externas y citas en el nuevo editor

El nuevo editor ahora admite dos funciones existentes de Experience Manager Guides: la capacidad de conexión con fuentes de datos externas y el uso de citas en los documentos.

Los autores pueden seguir utilizando fuentes de datos externas configuradas al crear o actualizar contenido en el nuevo editor. Las citas también son compatibles, por lo que los autores pueden agregar y administrar referencias en su contenido sin cambiar de editor.

## Compatibilidad con el estilo de cita AMA

Experience Manager Guides ahora admite el estilo de citas de la American Medical Association (AMA), ampliando el marco de citas existente para cumplir con los estándares de documentación requeridos por los clientes en los sectores de salud, regulación y ciencias de la vida.

Cuando se selecciona AMA como estilo de cita en **configuración de Workspace**, las citas se formatean automáticamente según las directrices de AMA, incluida la representación numérica de superíndice, la numeración secuencial y el orden preciso de las listas de referencias. La opción **Analizar cita** en el editor está disponible exclusivamente cuando se selecciona AMA, lo que permite a los autores agregar y analizar citas sin cambiar de contexto.

El estilo de cita AMA es compatible con los formatos de salida nativos de PDF y AEM Sites. Para configurar el estilo de cita, vaya a **Configuración de Workspace** y seleccione AMA en las opciones de estilo de cita. Para obtener detalles, vea [Trabajar con citas](../user-guide/web-editor-apply-citations.md).


