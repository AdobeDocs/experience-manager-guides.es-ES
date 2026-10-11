---
title: PDF nativo | Configuración del proceso de nodos para la publicación nativa de PDF
description: Obtenga información sobre cómo configurar el proceso de nodo para la publicación nativa de PDF
feature: Output Generation
role: Admin
level: Experienced
exl-id: 5321c785-8259-4ee2-9ada-ee70fb99b4fd
product_v2:
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
    internal-label: Experience Manager
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
    internal-label: Experience Manager Guides
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
    internal-label: Publishing
subfeature_v2:
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
    internal-label: Output generation
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
level_v2:
  - id: d378ca77-2da1-4f39-ad92-1917fe974a38
    internal-label: Experienced
source-git-commit: 81a0e7f0736ba4970673dd87a888a4c60d3c1b4e
workflow-type: tm+mt
source-wordcount: '122'
ht-degree: 1%
---
# Configuración del proceso de nodos para la publicación nativa de PDF para Cloud Service

La publicación nativa de PDF inicia un proceso NodeJs independiente para convertir los archivos generados en el proceso de publicación en un PDF final. Es posible que tenga que modificar las configuraciones de este proceso de nodo ejecutando la publicación nativa de PDF para admitir diferentes escenarios. Por ejemplo, para ejecutar cargas de trabajo más grandes debe aumentar el tamaño máximo de pila disponible para el proceso NodeJs generado.

Siga las instrucciones indicadas en [Anulaciones de configuración](../install-conf-guide/download-install-config-override.md) para crear el archivo de configuración.En el archivo de configuración, proporcione los siguientes detalles (propiedad):

| PID | Clave de propiedad | Valor de propiedad |
|---|---|---|
| `com.adobe.fmdita.config.ConfigManager` | `native.pdf.node.opts` | Valor de cadena para establecer cualquier estándar `NODE_OPTIONS`.<BR> Valor predeterminado: |
