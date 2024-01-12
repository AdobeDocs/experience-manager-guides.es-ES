---
title: Creación de un mapa
description: AEM Cree un mapa con el Editor de mapas en las Guías de. Busque los pasos para crear un archivo de mapa basado en una plantilla de mapa.
exl-id: b9cda118-ab6f-4d6b-9616-a083180ba069
feature: Authoring, Map Editor
role: User
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '469'
ht-degree: 0%

---

# Creación de un mapa {#id176FEN0D05Z}

AEM Guías de proporciona dos plantillas de mapa predeterminadas: DITA map y Bookmap. También puede crear sus propias plantillas de mapa y compartirlas con sus autores para crear archivos de mapa.

Realice los siguientes pasos para crear un archivo de asignación:

1. En la interfaz de usuario de Assets, vaya a la ubicación en la que desea crear el archivo de asignación.

1. Clic **Crear** \> **Mapa DITA**.

1. En la página Modelo, seleccione el tipo de plantillas de mapa que desea utilizar y haga clic en **Siguiente**.

   >[!NOTE]
   >
   > La forma en que se hace referencia a los temas en un archivo de mapa depende de la plantilla de mapa. Por ejemplo, si selecciona la plantilla Mapa, el tema hace referencia a \(`topicref`\) se utilizan para hacer referencia a temas. En el caso de un Bookmap, las referencias temáticas se crean utilizando la variable `chapter` en DITA.

   ![](images/map-template.png){width="650" align="left"}

1. En la página Propiedades, especifique el mapa **Título**.

1. \(Opcional\) Especifique el archivo **Nombre**.

   Si el administrador ha configurado un nombre de archivo automático basado en la configuración de UUID, no verá la opción para especificar el nombre del archivo. Se asigna automáticamente un nombre de archivo basado en UUID al archivo.

   Si la opción de nomenclatura de archivos está disponible, también el nombre se sugiere automáticamente en función del Título del mapa. Si desea especificar manualmente el nombre del archivo de asignación, asegúrese de que el nombre del archivo no contiene espacios, apóstrofos ni llaves y termina con `.ditamap`.

1. Haga clic en **Crear**.

   Aparecerá el mensaje Crear mapa.

   Todos los archivos de asignación nuevos que cree desde la interfaz de usuario de Assets **Crear** \> **Mapa DITA** o al editor web se le asigna un ID de mapa único. Además, la nueva asignación se guarda como la última copia de trabajo en DAM. Hasta que guarde una revisión de una asignación recién creada, no verá ningún número de versión en el Historial de versiones. Si abre el mapa para editarlo, la información de la versión se muestra en la esquina superior derecha de la pestaña del archivo de mapa:

   ![](images/first-version-map-none.png){width="650" align="left"}

   La información de versión de un mapa recién creado se muestra como *ninguno*. Al guardar una nueva versión, se le asigna un número de versión como 1.0. Para obtener más información sobre cómo guardar una nueva versión, consulte [Guardar como nueva versión](web-editor-features.md#save-as-new-version-id209ME400GXA).

   AEM Puede elegir abrir la asignación para editarla en el editor de asignaciones configurado o guardar el archivo de asignación en el repositorio de mapas.

   >[!NOTE]
   >
   > Para utilizar el Editor de mapas avanzado, acceda al archivo de asignación en el Editor web. Si el administrador ha configurado el Editor de mapas avanzado como editor por defecto en los ficheros de mapa, el fichero de mapa se abrirá directamente en el Editor de mapas avanzado para editarlo. Consulte *Establecer el Editor de mapas avanzado como predeterminado* en Instalar y configurar las guías de Adobe Experience Manager as a Cloud Service.


**Tema principal:**[ Trabajo con el editor de mapas](map-editor.md)
