---
title: Administración de archivos y carpetas
description: AEM Obtenga información sobre cómo administrar archivos y carpetas en las guías de. Copiar y pegar, arrastrar y soltar, eliminar, mover archivos y carpetas de forma masiva y buscar contenido DITA.
exl-id: e5b44286-7ac3-49e4-9e6f-7bc8ae2fc935
source-git-commit: 5e0584f1bf0216b8b00f00b9fe46fa682c244e08
workflow-type: tm+mt
source-wordcount: '3108'
ht-degree: 0%

---

# Administración de archivos y carpetas {#id2116G0L08XA}

AEM En esta sección se explica cómo las guías de la aplicación administran las operaciones básicas de archivo, como copiar, pegar, arrastrar y soltar y eliminar archivos. Los siguientes escenarios son posibles:

## Copiar y pegar archivos

**Si el archivo tiene un nombre de archivo legible en lenguaje natural**

- *Si el archivo con el mismo nombre no existe en la carpeta de destino*: se crea una copia nueva del archivo y también se le asigna un UUID. En este caso, el nombre de archivo es el mismo que el nombre de archivo original.
- *Si el archivo con el mismo nombre ya existe en la carpeta de destino*: se crea una nueva copia del archivo con el sufijo \(como filename0.extension\). También se asigna un UUID al archivo recién creado.


**Si el nombre del archivo se basa en un patrón UUID**

- *Si el archivo con el mismo nombre no existe en la carpeta de destino*: se crea una copia nueva del archivo y también se le asigna un nuevo UUID en la nueva ubicación. En este caso, el nombre de archivo es el mismo que el UUID.
- *Si el archivo con el mismo nombre ya existe en la carpeta de destino*: se crea una copia nueva del archivo y también se le asigna un nuevo UUID. El nombre de archivo es el mismo que el UUID.


## Copiar y pegar carpetas

**Copiar y pegar la carpeta en la misma ubicación**

- *La carpeta tiene archivos con nombres de archivo legibles en lenguaje natural*: Se crea una nueva copia de la carpeta con el sufijo \(como foldername0\). También se asigna un nuevo UUID a los archivos de la carpeta. Sin embargo, no hay cambios en los nombres de archivo.

- *La carpeta tiene archivos con nombres de archivo basados en un patrón UUID*: Se crea una nueva copia de la carpeta con el sufijo \(como foldername0\). También se asigna un nuevo UUID a todos los archivos de la nueva carpeta. Los nombres de archivo también cambian; los nombres de archivo son los mismos que el nuevo UUID.


**Copiar y pegar la carpeta en otra ubicación**

- *La carpeta tiene archivos con nombres de archivo legibles en lenguaje natural*: se crea una copia nueva de la carpeta y también se asigna un nuevo UUID a todos los archivos de la carpeta en la nueva ubicación. Aquí no hay ningún cambio en los nombres de carpeta o archivo.

- *La carpeta tiene archivos con nombres de archivo basados en un patrón UUID*: se crea una copia nueva de la carpeta con el mismo nombre que la carpeta original. También se asigna un nuevo UUID a todos los archivos de la nueva carpeta. Los nombres de archivo también cambian; los nombres de archivo son los mismos que el nuevo UUID.


## Arrastrar y soltar archivos

**Arrastrar y soltar con nombres de archivo legibles por humanos**

- *Arrastrar y soltar en la misma ubicación*: se le dan las opciones para **Sobrescribir archivo existente\(s\)**, **Mantener ambos archivos\(s\)** y una opción para crear una versión de la copia de trabajo existente.

  ![](images/uuid-human-readable-drag-drop-same-location.PNG){width="650" align="center"}

  Si elige la **Sobrescribir archivo existente\(s\)** , el archivo que se está cargando reemplaza la versión de trabajo actual del archivo existente en la ubicación original. El UUID no se crea ni cambia.

  Si elige la **Mantener ambos archivos\(s\)** , se crea una copia nueva del archivo con el sufijo \(como filename0.extension\). También se asigna un nuevo UUID al archivo recién copiado.

  Con la opción Sobrescribir archivo existente\(s\), si elige la opción para crear una versión a partir de la copia de trabajo existente, también se crea una nueva versión a partir de la copia de trabajo del documento.

  >[!NOTE]
  >
  > **Crear nueva versión para el archivo cargado** El administrador debe activar esta función. Si esta función está habilitada, se crea una nueva versión para el archivo cargado. Si la opción no está seleccionada, no se crea una versión del archivo cargado. Para obtener más información, consulte *Crear nueva versión para el archivo cargado* de la sección Instalar y configurar las guías de Adobe Experience Manager as a Cloud Service.

  Si un archivo ya está desprotegido para ediciones por otro usuario e intenta cargar y sobrescribir el archivo existente, se producirá un error y se mostrará un error.

  >[!NOTE]
  >
  >El **Sobrescribir archivo retirado al cargar** el administrador debe desactivar esta función. Si esta característica está habilitada, puede sobrescribir los archivos desprotegidos. Si la función no está habilitada, no se podrá sobrescribir un archivo desprotegido. Para obtener más información, consulte *Sobrescribir archivo retirado al cargar* de la sección Instalar y configurar las guías de Adobe Experience Manager as a Cloud Service.


- *Arrastrar y soltar archivos en una ubicación diferente*: se crea una copia nueva del archivo y también se le asigna un nuevo UUID en la nueva ubicación. En este caso, el nombre de archivo es el mismo que el nombre de archivo original.


**Arrastrar y soltar con nombres de archivo basados en un patrón UUID**

*Arrastre y suelte el archivo en la misma ubicación*: se le dan las opciones para **Sobrescribir archivo existente\(s\)** junto con la opción de crear una versión de la copia de trabajo existente.

![](images/uuid-drag-drop-same-location.PNG){width="650" align="center"}

Cuando se sobrescribe el archivo, no se produce ningún cambio en el nombre del archivo o en su UUID.

Si selecciona la opción **Crear versión para la copia de trabajo existente** opción, entonces se crea una nueva versión de la copia de trabajo del documento; se carga el nuevo fichero, también se crea una nueva versión del fichero y se realiza como copia de trabajo del documento.

**Crear nueva versión para el archivo cargado** El administrador debe activar esta función. Si esta función está habilitada, se crea una nueva versión para el archivo cargado. Si la opción no está seleccionada, no se crea una versión del archivo cargado. Para obtener más información, consulte *Crear nueva versión para el archivo cargado* de la sección Instalar y configurar las guías de Adobe Experience Manager as a Cloud Service.


*Arrastrar y soltar archivo en una ubicación diferente*: se le dan las opciones para **Sobrescribir archivo existente\(s\)**, **Mover archivo\(s\) a nueva ubicación** y una opción para crear una versión de la copia de trabajo existente.

![](images/uuid-drag-drop-different-location.PNG){width="650" align="center"}

Si elige la **Sobrescribir archivo existente\(s\)** , el archivo que se está cargando reemplaza al archivo existente en la ubicación original. El UUID no se crea ni cambia.

Si elige la **Mover archivo\(s\) a nueva ubicación** , el archivo existente se mueve a la ubicación actual y, a continuación, se sobrescribe con el archivo que se está cargando. Al mover un archivo a la nueva ubicación, no se rompen las referencias existentes desde o hacia el archivo.

Con reemplazar o mover los archivos, si elige la opción de crear una versión a partir de la copia existente, se crea una nueva versión a partir de la copia de trabajo del documento; el nuevo archivo se reemplaza en la ubicación existente o se mueve a la nueva ubicación.


## Mover archivos por lotes {#move-files-bulk}

AEM Guías de guía viene con la herramienta de movimiento masivo que ayuda a un administrador a mover una carpeta que tiene un gran número de archivos de una ubicación a otra. AEM Esta herramienta puede mover fácilmente archivos dentro de una o más carpetas a una carpeta diferente en su repositorio de carpetas. Una de las características principales de esta herramienta es que no solo mueve un gran número de archivos, sino que también mantiene las referencias hacia y desde los archivos que se mueven. Puede modificar el número de archivos que puede mover por lotes sin obstaculizar las tareas de creación y publicación.

>[!NOTE]
>
> La herramienta de movimiento masivo solo funciona en el nivel de carpeta. AEM Si desea mover archivos de tema o asignación individuales, utilice la herramienta de movimiento normal de la interfaz de usuario de Assets.

Estas son algunas de las funciones que proporciona la herramienta de movimiento masivo:

- Puede modificar el número de archivos para procesar en cada lote. Esto puede requerir la ejecución de algunas pruebas antes de obtener un número óptimo que el sistema pueda gestionar fácilmente.
- Los servicios de creación y publicación se ejecutan sin problemas ni interrupciones durante la operación de movimiento.
- Tener control total sobre el intervalo de tiempo entre los siguientes procesos por lotes \(ejecución de\). Este intervalo de tiempo garantiza que la operación posterior al procesamiento se complete antes de iniciar el siguiente lote de archivos.

- Gestión automática de carpetas con el mismo nombre. Esta función garantiza que, aunque haya carpetas con el mismo nombre en movimiento, no se sobrescriban.

- Gestión automática de referencias desde y hacia los archivos que se están moviendo.


Debe tener en cuenta los siguientes puntos antes de ejecutar el proceso por lotes:

- Si planea mover temas que están actualmente en revisión, debe cerrar el proceso de revisión de todos esos temas antes de moverlos. Si no se cierra la tarea de revisión, se interrumpirá el proceso de revisión.
- Sólo debe ejecutar una operación de movimiento masivo en el sistema en cualquier momento. Esto garantiza el manejo adecuado de las referencias hacia y desde los temas que se están moviendo.


Para mover archivos de forma masiva, realice los siguientes pasos:

1. Haga clic en el vínculo Adobe Experience Manager en la parte superior y elija **Herramientas**.
1. Seleccionar **Guías** de la lista de herramientas.
1. Haga clic en **Herramienta Mover masivamente** mosaico.
1. La página Herramienta de movimiento en lote se muestra en función de la configuración. Proporcione los siguientes detalles sobre la **Herramienta Mover masivamente** página:

   <details>

   <summary> Cloud Service y sistema de archivos basado en UUID On-Premise </summary>

   ![](images/bulk-move-tool-uuid.png){width="650" align="center"}

   >[!TIP]
   >
   > Seleccionar <img src="images/info-icon.svg" width="25">   cerca de cualquier campo para ver más detalles sobre él.


   - **Añadir sufijo a carpetas duplicadas**: Si está moviendo carpetas que tienen el mismo nombre, debe seleccionar esta opción. Por ejemplo, en la captura de pantalla anterior, **Ruta de origen** contiene el nombre de las carpetas que se van a mover. La carpeta denominada tema existe en dos ubicaciones diferentes: prueba A y prueba B. Al seleccionar esta opción, las carpetas se moverán correctamente. La primera carpeta que se mueva recibirá el nombre de tema, mientras que la segunda carpeta recibirá el nombre de tema0. La operación de mover agrega un sufijo en la serie secuencial \(0, 1, 2, etc.\) a las carpetas con el mismo nombre.

     Si está moviendo carpetas con el mismo nombre sin seleccionar esta opción, la operación se anulará con un mensaje.

   - **Ruta de origen\(s\)**: especifique la ubicación de las carpetas que desea mover.

      - Seleccionar  **Examinar carpeta**  <img src="images/browse-folder-icon.svg" width="25">    para abrir el cuadro de diálogo examinar archivo. Seleccione las carpetas que desee mover y haga clic en **Seleccionar** para completar el proceso.

      - También puede escribir o copiar y pegar la ubicación de origen. Pulse Intro para añadir la carpeta a la lista.

        Las carpetas seleccionadas se muestran junto con su ruta. Pase el ratón sobre la etiqueta de carpeta para ver la ruta completa.
      - También puede quitar cualquier carpeta haciendo clic en **Eliminar** <img src="images/remove-folder.svg" width="25"> cerca de la carpeta.


   - **Ruta de destino**: especifique la ubicación a la que desea mover las carpetas de origen.

      - Seleccionar  **Examinar carpeta** <img src="images/browse-folder-icon.svg" width="25"> para abrir el cuadro de diálogo examinar archivo. Seleccione la ubicación a la que desea mover las carpetas de origen. y haga clic en Seleccionar para completar el proceso.
      - También puede escribir o copiar y pegar la ruta de destino.

     La carpeta seleccionada se muestra junto con su ruta en el cuadro de texto.


   - Clic **Movimiento masivo**.

     El sistema comienza a mover archivos desde la ubicación de origen a la de destino. Una vez finalizado el proceso, se muestra un resumen del proceso de movimiento a la derecha de la página.

     ![](images/bulk-move-summary-uuid.png){width="650" align="center"}

   </details>

   <details>

   <summary> Sistema de archivos local no basado en UUID </summary>

   ![](images/bulk-move-tool-non-uuid.png){width="650" align="center"}

   >[!TIP]
   >
   > Seleccionar <img src="images/info-icon.svg" width="25">   cerca de cualquier campo para ver más detalles sobre él.

   - **Tamaño del lote**: especifique el número de archivos que desea mover en un solo lote. Los valores predeterminados son 50 archivos.
   - **Intervalo de suspensión**: especifique el tiempo en segundos que el proceso esperará antes de iniciar el siguiente lote. Durante este intervalo de tiempo de suspensión, el sistema corrige las referencias hacia y desde los archivos movidos. El intervalo de suspensión predeterminado es de 60 segundos.


   - **Añadir sufijo a carpetas duplicadas**: Si está moviendo carpetas que tienen el mismo nombre, debe seleccionar esta opción. Por ejemplo, en la captura de pantalla anterior, **Ruta de origen** contiene el nombre de las carpetas que se van a mover. La carpeta denominada tema existe en dos ubicaciones diferentes: prueba A y prueba B. Al seleccionar esta opción, las carpetas se moverán correctamente. La primera carpeta que se mueva recibirá el nombre de tema, mientras que la segunda carpeta recibirá el nombre de tema0. La operación de mover agrega un sufijo en la serie secuencial \(0, 1, 2, etc.\) a las carpetas con el mismo nombre.

     Si está moviendo carpetas con el mismo nombre sin seleccionar esta opción, la operación se anulará con un mensaje.

   - **Actualizar referencias de archivos desprotegidos**: Si va a mover carpetas que contengan archivos desprotegidos, se recomienda seleccionar esta opción. Si selecciona esta opción, todos los ficheros extraídos se guardarán y archivarán con una nueva revisión. Esta nueva revisión se mueve a la ubicación de destino.

     Si no selecciona esta opción, los archivos desprotegidos se mueven a la carpeta de destino con el mismo estado de desprotección. Sin embargo, podría haber alguna pérdida de datos en este proceso de movimiento.


   - **Ruta de origen\(s\)**: especifique la ubicación de las carpetas que desea mover.

      - Seleccionar  **Examinar carpeta**  <img src="images/browse-folder-icon.svg" width="25">    para abrir el cuadro de diálogo examinar archivo. Seleccione las carpetas que desee mover y haga clic en **Seleccionar** para completar el proceso.

      - También puede escribir o copiar y pegar la ubicación de origen. Pulse Intro para añadir la carpeta a la lista.

        Las carpetas seleccionadas se muestran junto con su ruta. Pase el ratón sobre la etiqueta de carpeta para ver la ruta completa.
      - También puede quitar cualquier carpeta haciendo clic en **Eliminar** <img src="images/remove-folder.svg" width="25"> cerca de la carpeta.


   - **Ruta de destino**: especifique la ubicación a la que desea mover las carpetas de origen.

      - Seleccionar  **Examinar carpeta** <img src="images/browse-folder-icon.svg" width="25"> para abrir el cuadro de diálogo examinar archivo. Seleccione la ubicación a la que desea mover las carpetas de origen. y haga clic en Seleccionar para completar el proceso.
      - También puede escribir o copiar y pegar la ruta de destino.

        La carpeta seleccionada se muestra junto con su ruta en el cuadro de texto.

   - Clic **Movimiento masivo**.

     El sistema comienza a mover archivos desde la ubicación de origen a la de destino. Una vez finalizado el proceso, se muestra un resumen del proceso de movimiento a la derecha de la página.
     ![](images/bulk-move-summary-non-uuid.png){width="650" align="center"}
</details>

## Buscar contenido DITA

AEM De forma predeterminada, no reconoce contenido DITA, por lo que no proporciona ningún mecanismo para buscar contenido DITA en su repositorio. AEM AEM AEM Guías de añade una capa sobre la parte superior de la, que permite a los usuarios de comprender y procesar el contenido DITA. AEM AEM La función Buscar contenido DITA de las Guías de permite buscar contenido DITA en el repositorio de la aplicación de.

>[!NOTE]
>
>El administrador del sistema puede configurar la variable **Elemento DITA** y, a continuación, puede utilizar la función desde la interfaz de usuario de AEM Assets. Para obtener más información, consulte *Añadir el componente de búsqueda Elemento DITA en la IU de Assets* en Instalar y configurar las guías de Adobe Experience Manager as a Cloud Service.

Con la función de búsqueda, puede:

- Buscar contenido DITA basado en un valor de elemento; por ejemplo, `author`= xml
- Buscar contenido DITA en función de un valor de atributo; por ejemplo, `@platform`= windows
- Utilice una combinación de elemento DITA y valor de atributo; por ejemplo, `author`= xml `AND` `@platform`= windows

AEM Realice los siguientes pasos para buscar contenido DITA dentro de un repositorio de:

1. Abra la interfaz de usuario de Assets.

1. En el carril izquierdo, seleccione **Filtros**.

   ![](images/left-rail-filter.png){width="450" align="center"}

   Las opciones de filtrado de contenido se muestran en el carril izquierdo. También encontrará la opción de filtrado Elemento DITA, que se utiliza para filtrar contenido DITA.

   ![](images/dita-element-search.png){width="450" align="center"}

1. *\(Opcional\)* En el **Seleccionar directorio de búsqueda** , busque la ubicación en la que desea buscar.

1. En el **Elemento DITA** filtro, proporcione el **Nombre de elemento**, **Atributo** y un valor que desee buscar. Por ejemplo, para buscar documentos que tengan `author` elemento que es de `@type` creador: debe proporcionar la información que se muestra en la siguiente captura de pantalla:

   ![](images/search-params.png){width="650" align="center"}

   Los criterios de búsqueda introducidos en **Elemento DITA** Este filtro se muestra en la parte superior de la barra de búsqueda. Los archivos que coinciden con los criterios de búsqueda se muestran en la **Resultados de búsqueda** área.

   Tenga en cuenta los siguientes puntos al especificar los criterios de búsqueda:

   - Para buscar una frase exacta, introduzca la frase en el campo Value entre comillas `"`búsqueda de frases`"`.
   - Se pueden añadir hasta tres criterios de búsqueda de elementos DITA.
   - Si especifica varios criterios de búsqueda, todos se combinarán con la lógica AND.
   - No puede utilizar caracteres comodín en los criterios de búsqueda. Por ejemplo, para buscar la plataforma \(attribute\) con el valor de Windows, no puede especificar \*form o Windows?.

**Filtro de estado de extracción en la búsqueda**

AEM Además del filtro Elemento DITA, Guías de la aplicación también le permite buscar contenido en función de su estado de cierre de compra. Esto resulta útil cuando desea filtrar rápidamente los archivos que está desprotegiendo actualmente y desea volver a protegerlos.

Realice los siguientes pasos para buscar archivos en función de su estado de cierre de compra:

1. Abra la interfaz de usuario de Assets.

1. Clic **Filtrar** en el carril izquierdo.
1. Escriba la palabra clave de búsqueda en la barra de búsqueda.
1. Aplique los filtros necesarios desde el carril izquierdo.

   Por ejemplo, puede aplicar **Estado de cierre** filtre para mostrar los temas desprotegidos o protegidos. Puede restringir aún más esta lista eligiendo el usuario o grupo de la lista Extraído por.

   Se muestra el resultado de la búsqueda.


## Eliminar archivos

AEM La eliminación de archivos del repositorio de es una función restringida, que controla el administrador del sistema. En función de las configuraciones, la eliminación de archivos podría restringirse si:

- Desprotegido
- Tener referencias entrantes o salientes

También puede eliminar archivos sólo si pertenece a un grupo de usuarios específico que tenga privilegios para eliminar archivos.

>[!NOTE]
>
> Para obtener más información sobre las configuraciones de administración de archivos, consulte *Impedir la eliminación de archivos desprotegidos* y *Impedir la eliminación de archivos referenciados* secciones en el as a Cloud Service Instalar y configurar las guías de Adobe Experience Manager.

Si el administrador ha concedido el permiso de eliminación de archivos a todos los usuarios, se mostrará el siguiente mensaje cuando elimine archivos que contengan referencias:

![](images/allow_unsafe_delete-force-delete.PNG){width="650" align="center"}

En esta situación, puede eliminar archivos a la fuerza sin quitar las referencias entrantes o salientes de los archivos.

Si se conceden permisos de eliminación a un grupo de usuarios específico, también aparecerá el mensaje anterior para los usuarios que pertenezcan a ese grupo. Sin embargo, para otros usuarios, se muestra el siguiente mensaje:

![](images/allow_unsafe_delete_for_delete_assets_group.PNG){width="650" align="center"}

En esta situación, los usuarios no podrán eliminar archivos hasta que se hayan eliminado todas las referencias entrantes y salientes.

## Trabajo con archivos multimedia

Los archivos multimedia, como imágenes y vídeos, son parte integral del contenido. Mientras carga y administra el contenido, también puede trabajar con archivos multimedia.

Si el archivo multimedia ha sufrido algún cambio, puede buscar y previsualizar los archivos en la **Historial de versiones**.Para averiguar los cambios en las distintas versiones de un archivo multimedia:

1. Acceso al archivo en **IU de Assets**.
1. Seleccione el archivo para el que desea ver el historial de versiones.
1. En el carril izquierdo, haga clic en **Historial de versiones** y seleccione una versión.
1. También puede ver las miniaturas de las diferentes versiones en Historial de versiones.

   ![](images/media-version-history-icon.png){width="800" align="center"}

1. En las versiones enumeradas, seleccione la que desee utilizar como versión base y haga clic en **Previsualizar versión**. La vista previa de la versión seleccionada se muestra en la ventana Version Preview.

   ![](images/media-version-preview.png){width="650" align="center"}


**Tema principal:**[ Administrar contenido](authoring.md)
