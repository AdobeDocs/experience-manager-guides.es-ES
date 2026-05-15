---
title: PDF nativo | Configuración del proceso de nodos para la publicación nativa de PDF
description: Obtenga información sobre cómo configurar el proceso de nodo para la publicación nativa de PDF
feature: Output Generation
role: Admin
level: Experienced
exl-id: f470939b-a5cb-4d28-92d1-7a0a52c4c637
TQID: https://experienceleague.adobe.com/7i-6SjvI5FuSNsWPy9sX96UsXld9fJjAjHNKDKzo824
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: d6596f3f-92a7-43ec-b444-237db6adad05
  - id: fd6cc9e1-e5e5-494e-b7b1-a32f2d6cd7c9
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 122
ht-degree: 1%

---

# Configuración del proceso de nodos para la publicación nativa de PDF para Cloud Service

La publicación nativa de PDF inicia un proceso NodeJs independiente para convertir los archivos generados en el proceso de publicación en un PDF final. Es posible que tenga que modificar las configuraciones de este proceso de nodo ejecutando la publicación nativa de PDF para admitir diferentes escenarios. Por ejemplo, para ejecutar cargas de trabajo más grandes debe aumentar el tamaño máximo de pila disponible para el proceso NodeJs generado.

Siga las instrucciones indicadas en [Anulaciones de configuración](../install-conf-guide/download-install-config-override.md) para crear el archivo de configuración.En el archivo de configuración, proporcione los siguientes detalles (propiedad):

| PID | Clave de propiedad | Valor de propiedad |
|---|---|---|
| `com.adobe.fmdita.config.ConfigManager` | `native.pdf.node.opts` | Valor de cadena para establecer cualquier estándar `NODE_OPTIONS`.<BR> Valor predeterminado: |
