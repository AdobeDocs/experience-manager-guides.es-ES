---
title: Tipos de ajustes preestablecidos de PDF
description: Obtenga información acerca de los tipos de ajustes preestablecidos de PDF que puede crear con Adobe Experience Manager Guides.
exl-id: f12c91fd-3f95-478e-a9cd-68d037206ee8
feature: Publishing
role: User
TQID: https://experienceleague.adobe.com/RN5CYho8TpklBivMgK6ifb--eTwlBQgD-1jNU8HvF7E
product_v2: id: fae5e35a-80c9-4b94-9352-1a060a6aab1did: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: a3bd6397-2eb2-4908-a61c-226e26855dca
subfeature_v2: id: d5ea0417-7932-4688-a3e2-4d3b2e7076a3id: d6596f3f-92a7-43ec-b444-237db6adad05id: f9dbea21-a714-40dd-bc90-080d8046c93f
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 330
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





**Tema principal:**[ Explicación de los ajustes preestablecidos de salida](generate-output-understand-presets.md)
