---
title: Integración de editores XML basados en escritorio
description: Aprenda a integrar editores XML basados en escritorio
feature: Publishing FrameMaker Documents
role: Admin
level: Experienced
source-git-commit: b3ae1c02d3055fe15257d5de0365d30e7af21afb
workflow-type: tm+mt
source-wordcount: '363'
ht-degree: 1%

---

# Integración de editores XML basados en escritorio

Hay muchos editores XML disponibles en el mercado, y es posible que ya esté utilizando uno. Adobe FrameMaker AEM es uno de los editores XML más poderosos, que viene con conector de la. AEM Con el conector de la en FrameMaker AEM, puede conectarse fácilmente con el repositorio de la, extraer y archivar archivos, y editar archivos directamente en FrameMaker. También puede configurar Experience Manager Guides para que inicie el FrameMaker desde el Editor web. Una vez que haya abierto el archivo en el FrameMaker AEM, puede editarlo y volver a registrarlo en el repositorio de.

## Habilitar la edición de archivos en el FrameMaker desde el Editor web

Puede utilizar el FrameMaker o cualquier otro editor DITA para crear y actualizar contenido DITA. Sin embargo, si su organización utiliza el FrameMaker como editor DITA, puede ofrecer a los usuarios una opción para abrir documentos DITA directamente en el FrameMaker AEM desde el punto de vista de la.


De manera predeterminada, los usuarios no ven el botón **Abrir en el FrameMaker AEM** en la barra de herramientas de la barra de herramientas de la aplicación de la barra de herramientas de la aplicación de la. AEM Siga estos pasos para agregar este botón en la barra de herramientas de la barra de herramientas de la:

Siga las instrucciones indicadas en [Anulaciones de configuración](download-install-additional-config-override.md#) para crear el archivo de configuración. AEM En el archivo de configuración, proporcione los siguientes detalles \(property\) para agregar este botón en la barra de herramientas de la:


| PID | Clave de propiedad | Valor de propiedad |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.openinframebuttonshow` | Boolean \(true/false\). Si desea mostrar el botón **Abrir en el FrameMaker**, establezca esta propiedad en true. <br> **Valor predeterminado**: false |



Si usa la versión 2409 y la actualización 3 de septiembre de FrameMaker 2022, debe habilitar la configuración de **FrameMaker versión 2022 actualización 3 o superior** para que los usuarios pasen los detalles del servidor de Experience Manager Guides al FrameMaker.  De forma predeterminada, está desactivada.


| PID | Clave de propiedad | Valor de propiedad |
|---|------------|--------------|
| `com.adobe.fmdita.xmleditor.config.XmlEditorConfig` | `xmleditor.openinframe2022above` | Boolean \(true/false\). Si está utilizando la actualización 3 de septiembre de 2022 del FrameMaker de trabajo, establezca esta propiedad en true. <br> **Valor predeterminado**: false |



Cuando establece la propiedad *openinframebuttonshow* en true, se muestra el botón **Abrir en el FrameMaker AEM** al seleccionar cualquier archivo DITA en el repositorio de la. Si esta propiedad no se establece en *true*, el botón **Abrir en el FrameMaker** solo se muestra al seleccionar un archivo .fm o .book en el repositorio.



