---
title: Activar el nuevo motor de PDF
description: Obtenga información sobre cómo habilitar el nuevo motor de PDF en Experience Manager Guides
feature: Web Editor Configuration
role: Admin
level: Experienced
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
    internal-label: Configuration
subfeature_v2:
  - id: b0521e56-a0b2-40b6-bf47-ebc98751f9ba
    internal-label: Web Editor configuration
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: f89becea89888f7dec81e18c9220dcabda8f4e7d
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 4%
---

# Configuración del motor de PDF nativo v2

El nuevo motor de publicación para PDF nativo, es decir _Native PDF engine v2_, proporciona funciones actualizadas de procesamiento de PDF y correcciones para los problemas de _Native PDF engine v1_.

>[!BEGINTABS]
>[!TAB Cloud Service]

Siga las instrucciones indicadas en [Anulaciones de configuración](../install-conf-guide/download-install-config-override.md) para crear el archivo de configuración. En el archivo de configuración, proporcione los siguientes detalles (propiedad):

| PID | Clave de propiedad | Valor de propiedad |
|-----|--------------|----------------|
| `com.adobe.fmdita.publish.config.GuidesPublishConfiguratorService` | `guides.publish.config` | `{"PDF_ENGINE": "v2"}` <br> Valor predeterminado: `v1` |

>[!TAB Local]


Para implementaciones On-Premise, su disponibilidad depende de las versiones de AEM y Java.

El _motor nativo de PDF v2_ requiere **Java 17 o posterior**.

- **AEM 6.5:** No se admite el motor nativo de publicación de PDF v2 porque AEM 6.5 se ejecuta en Java 8.
- **AEM 6.5 LTS:** El motor nativo de publicación de PDF v2 está habilitado de manera predeterminada. No se requiere ninguna configuración adicional.

Si prefiere volver al _motor nativo de PDF v2_ con AEM 6.5 LTS, desinstale el paquete del editor de PDF:
`/crx/packmgr/index.jsp#/etc/packages/com.adobe.guides/pdf-publisher-package-3.0.0.zip` del Administrador de paquetes de CRX.

>[!ENDTABS]

