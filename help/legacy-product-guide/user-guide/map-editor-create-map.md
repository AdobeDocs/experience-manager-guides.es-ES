---
title: Creación de un mapa
description: Cree un mapa con el Editor de mapas en AEM Guides. Busque los pasos para crear un archivo de mapa basado en una plantilla de mapa.
feature: Authoring, Map Editor
role: User
hide: true
exl-id: 981ecaeb-9b1f-4c7a-8336-7746a739bedc
TQID: https://experienceleague.adobe.com/ezadQbcoT3y2-owiIZ5MgsnBbNegmCb2lCIwxgwhcAE
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: ab01a588-7dea-43f2-a699-0b3f128465d6
subfeature_v2:
  - id: a7bba4a6-624b-4427-a9b8-dd411a1bfd41
  - id: ad602516-aca3-4247-9ae8-f393d958efa9
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
source-git-commit: 8ed5c9cb07c56b84b36ef56a55af8738989a6d3f
workflow-type: tm+mt
source-wordcount: 472
ht-degree: 0%

---

# Creación de un mapa {#id176FEN0D05Z}

AEM Guides proporciona dos plantillas de mapas integradas: DITA map y Bookmap. También puede crear sus propias plantillas de mapa y compartirlas con sus autores para crear archivos de mapa.

Realice los siguientes pasos para crear un archivo de asignación:

1. En la interfaz de usuario de Assets, vaya a la ubicación en la que desea crear el archivo de asignación.

1. Haga clic en **Crear** \> **Mapa DITA**.

1. En la página Modelo, seleccione el tipo de plantillas de mapa que desee usar y haga clic en **Siguiente**.

   >[!NOTE]
   >
   > La forma en que se hace referencia a los temas en un archivo de mapa depende de la plantilla de mapa. Por ejemplo, si selecciona la plantilla Mapa, las referencias del tema \(`topicref`\) se utilizarán para hacer referencia a los temas. En el caso de un mapa de libros, las referencias de temas se crean utilizando el elemento `chapter` en DITA.

   ![](images/map-template.png){width="650"}

1. En la página Propiedades, especifique el mapa **Title**.

1. \(Opcional\) Especifique el archivo **Nombre**.

   Si el administrador ha configurado un nombre de archivo automático basado en la configuración de UUID, no verá la opción para especificar el nombre del archivo. Se asigna automáticamente un nombre de archivo basado en UUID al archivo.

   Si la opción de nomenclatura de archivos está disponible, también el nombre se sugiere automáticamente en función del Título del mapa. Si desea especificar manualmente el nombre del archivo de asignación, asegúrese de que el nombre del archivo no contenga espacios, apóstrofos ni llaves y termine con `.ditamap`.

1. Haga clic en **Crear**.

   Aparecerá el mensaje Crear mapa.

   A cada nuevo archivo de asignación que cree desde la interfaz de usuario de Assets **Create** \> **DITA Map** o el Editor web se le asigna un ID de mapa único. Además, la nueva asignación se guarda como la última copia de trabajo en DAM. Hasta que guarde una revisión de una asignación recién creada, no verá ningún número de versión en el Historial de versiones. Si abre el mapa para editarlo, la información de la versión se muestra en la esquina superior derecha de la pestaña del archivo de mapa:

   ![](images/first-version-map-none.png){width="650"}

   La información de versión de un mapa recién creado se muestra como *none*. Al guardar una nueva versión, se le asigna un número de versión como 1.0. Para obtener más información acerca de cómo guardar una nueva versión, vea [Guardar como nueva versión](web-editor-features.md#save-as-new-version-id209ME400GXA).

   Puede elegir abrir la asignación para editarla en el editor de asignaciones configurado o guardar el archivo de asignación en el repositorio de AEM.

   >[!NOTE]
   >
   > Para utilizar el Editor de mapas avanzado, acceda al archivo de asignación en el Editor web. Si el administrador ha configurado el Editor de mapas avanzado como editor por defecto en los ficheros de mapa, el fichero de mapa se abrirá directamente en el Editor de mapas avanzado para editarlo. Consulte la sección *Establecer el editor de mapas avanzado como predeterminado* en Instalar y configurar Adobe Experience Manager Guides as a Cloud Service.


**Tema principal:**&#x200B;[&#x200B; Trabajar con el editor de mapas](map-editor.md)
