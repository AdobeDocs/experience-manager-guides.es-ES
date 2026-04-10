---
title: PDF nativo | Configuración del proceso de nodos para la publicación nativa de PDF
description: Obtenga información sobre cómo configurar el proceso de nodo para la publicación nativa de PDF
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 453da51a42984b912547570f2e1de70806b41171
workflow-type: tm+mt
source-wordcount: '121'
ht-degree: 1%

---

# Configuración del proceso de nodos para la publicación nativa de PDF para Cloud Service

La publicación nativa de PDF inicia un proceso NodeJs independiente para convertir los archivos generados en el proceso de publicación en un PDF final. Es posible que tenga que modificar las configuraciones de este proceso de nodo ejecutando la publicación nativa de PDF para admitir diferentes escenarios. Por ejemplo, para ejecutar cargas de trabajo más grandes debe aumentar el tamaño máximo de pila disponible para el proceso NodeJs generado.

Siga las instrucciones indicadas en [Anulaciones de configuración](../install-conf-guide/download-install-config-override.md) para crear el archivo de configuración. En el archivo de configuración, proporcione los siguientes detalles (propiedad):

| PID | Clave de propiedad | Valor de propiedad |
|---|---|---|
| `com.adobe.fmdita.config.ConfigManager` | `native.pdf.node.opts` | Valor de cadena para establecer cualquier estándar `NODE_OPTIONS`.<BR> Valor predeterminado: &quot;&quot; |
