---
title: Tipos de ajustes preestablecidos de PDF
description: Obtenga información acerca de los tipos de ajustes preestablecidos de PDF que puede crear con Adobe Experience Manager Guides.
exl-id: f12c91fd-3f95-478e-a9cd-68d037206ee8
feature: Publishing
role: User
source-git-commit: 558cc1a724a483353eb5d912354e1ab37dab348a
workflow-type: tm+mt
source-wordcount: '324'
ht-degree: 0%

---

# Información general sobre ajustes preestablecidos de salida PDF {#id205BE600HAH}

Con Experience Manager Guides, puede crear ajustes preestablecidos de PDF para generar PDF de temas individuales o un archivo de mapa completo. Puede publicar el contenido en formato PDF mediante uno de los tres métodos siguientes:

**DITA-OT**

Utilice este método para generar una salida de PDF para un mapa desde la consola Mapa o el panel Mapa. Puede establecer las propiedades de publicación antes de generar PDF creando un ajuste preestablecido de salida para el mapa que esté abierto en la consola de mapas o en el panel de mapas.

Para obtener más información sobre cómo crear un ajuste preestablecido de salida de PDF mediante el método DITA-OT, vea [Crear ajuste preestablecido de salida de PDF DITA-OT](./generate-output-pdf-dita-ot.md)

**FrameMaker Publishing Server (FMPS)**

>[!NOTE]
>
> La opción de publicación FMPS solo está disponible en el panel de mapas.

Utilice este método para generar una salida de PDF no solo a partir del contenido DITA, sino también de los documentos de FrameMaker (.book y .fm) disponibles en su repositorio de AEM. El PDF se puede crear configurando un ajuste preestablecido de salida y publicándolo con FrameMaker Publishing Server (FMPS). Puede diseñar y configurar el aspecto de la salida para PDF y otros formatos, y almacenarla en un archivo de configuración (.sts). Este fichero de configuración lo utiliza FMPS para generar la salida de un fichero .book o de mapa DITA. Para crear o editar un ajuste preestablecido de salida, vea [Explicación de los ajustes preestablecidos de salida](../user-guide/generate-output-understand-presets.md).

Para obtener más información sobre la configuración de FMPS, consulte [Generar resultados a partir de documentos de FrameMaker](../user-guide/fm-output-generatation.md).

**PDF nativo**

Utilice este método para generar una salida de PDF con numerosas funciones basadas en los estándares de medios paginados CSS3 y CSS del W3C. Con las publicaciones nativas de PDF, puede utilizar plantillas para establecer el diseño y el estilo del contenido y aplicar varias configuraciones para ajustar mejor el PDF. Además, puede modificar y crear sus propias plantillas con el editor de plantillas.

Para obtener más información sobre la creación de ajustes preestablecidos nativos de PDF, vea [Crear ajustes preestablecidos de salida nativos de PDF](../web-editor/native-pdf-web-editor.md).





**Tema principal:**&#x200B;[ Explicación de los ajustes preestablecidos de salida](generate-output-understand-presets.md)
