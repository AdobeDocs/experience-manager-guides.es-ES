---
title: Configuración de un conector de fuente de datos con herramientas
description: Obtenga información sobre cómo configurar un conector de fuente de datos con las herramientas.
exl-id: d7cd412b-89ea-43a5-97b3-09944863bbee
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: acd16f23a7b3023a62b3c15007b03d4f3b2cfb4f
workflow-type: tm+mt
source-wordcount: '788'
ht-degree: 0%

---

# Configuración de un conector de fuente de datos desde la interfaz de usuario

Las guías del Experience Manager vienen con el **Fuentes de datos** que le ayuda a configurar conectores predeterminados para fuentes de datos. Puede configurar los conectores de cliente JIRA, SQL (MySQL, PostgreSQL, Microsoft SQL Server, SQLite, MariaDB, H2DB), Adobe Commerce, Elasticsearch y REST genérico.

Además de estos conectores predeterminados, las guías del Experience Manager proporcionan los conectores para las fuentes de datos de Salsify, Akeneo y Microsoft Azure DevOps Boards (ADO). Puede descargarlos e instalarlos. A continuación, los usuarios pueden configurar estos conectores.

También puede conectarse a archivos de datos JSON mediante un conector de archivo. Cargue el archivo JSON desde el equipo o navegue desde los recursos de Adobe Experience Manager. A continuación, cree fragmentos de contenido o temas utilizando los generadores.

Para configurar un conector, realice los siguientes pasos:

1. Seleccione el **Adobe Experience Manager** en la parte superior y seleccione Herramientas.
1. Seleccionar **Guías** de la lista de herramientas.
1. Seleccione el **Fuentes de datos** mosaico. El **Fuentes de datos** se muestra la página. Puede ver las fuentes de datos conectadas.

   Puede alternar entre las **Vista de lista** o **Vista en mosaico** para ver las distintas fuentes de datos conectadas como una lista o como mosaicos.

   <img src="./assets/data-sources-create-window.png" alt= "fuentes de datos enumeradas en la página fuentes de datos" width="800">

   *Ver o crear un conector de origen de datos.*
1. Haga clic en **Crear**.
1. Seleccione la base de datos para la que desea crear el conector. Por ejemplo, el conector del Elasticsearch.
   >[!NOTE]
   >
   >Se muestran todas las bases de datos listas para usar disponibles.

1. Haga clic en **Siguiente**.
1. Introduzca los detalles de configuración y conexión según la base de datos.

   >[!TIP]
   >
   >* Pase el ratón sobre <img src="./assets/info-details.svg" alt= "icono de información" width="25"> cerca del campo para ver más detalles sobre él.
   > * Los campos con * son obligatorios. Por ejemplo, puede introducir los siguientes detalles para el conector del Elasticsearch.

   * **Nombre**: introduzca el nombre de la fuente de datos.
   * **Tipo de autenticación**: seleccione el tipo de autenticación de la lista desplegable. Por ejemplo, Autenticación básica de nombre de usuario y contraseña
   * **Nombre de usuario**: introduzca su nombre de usuario.
   * **Contraseña**: introduzca su nombre de usuario y contraseña.
   * **URL**: Añada la dirección URL de la API.


1. Seleccione el **Excluir plantillas de fábrica** para excluir las plantillas de fábrica de la utilización para la generación de temas y fragmentos de código. No aparecerán debajo de la etiqueta **Plantilla de asignación de datos** menú desplegable en  **Añadir generador de fragmentos de contenido** o el **Agregar generador de temas** Cuadro de diálogo.


1. Seleccionar **Probar conexión**. Puede ver el **Probar conexión** botón habilitado solo después de agregar los detalles necesarios. Vea un mensaje de éxito si los detalles de la conexión son correctos. De lo contrario, podría ver un mensaje de error.



1. Seleccionar **Guardar** en la parte superior para guardar el conector.     Ver el **Guardar** botón habilitado después de completar todos los detalles y de que la conexión se haya realizado correctamente.


   Si el conector se ha guardado correctamente, puede ver el origen de datos conectado en la página.

**Conexión a varios recursos**

Puede agregar o utilizar varios recursos basados en distintas direcciones URL para algunos conectores, como Cliente REST genérico, Salsify, Akeneo y Tableros de DevOps de Microsoft Azure (ADO). A continuación, conéctese con ellos para crear fragmentos de contenido o temas utilizando los generadores correspondientes.

Siga estos pasos para crear un recurso:

1. Seleccionar ![añadir icono](assets/Add_icon.svg) en el **sección de recurso de URL** para añadir un recurso para cada URL.
1. Configure todos los detalles en la variable **Añadir recurso** Cuadro de diálogo.
1. Clic **Añadir**.
1. Puede editar ![icono de edición](assets/edit_pencil_icon.svg) o eliminar ![eliminar](assets/Delete_icon.svg) el recurso de la lista de recursos de URL.

1. También puede utilizar los recursos predeterminados disponibles para fuentes de datos como Salsify, Akeneo y Microsoft ADO. Cambie las opciones OFF para el recurso que no desee configurar para un origen de datos.

Esto le permite recuperar rápidamente datos de cualquiera de los recursos de una fuente de datos concreta en un solo fragmento de contenido o tema.

## Funciones disponibles para un conector

* Alternar entre **Vista de lista** o **Vista en mosaico**  para ver las distintas fuentes de datos conectadas como una lista o como mosaicos.
* Seleccione la casilla de verificación de un solo conector. Clic **Seleccionar todo** para seleccionar todos los conectores. Puede hacer clic en **Deseleccionar todo** cuando se seleccionan todos los conectores.

<img src="./assets/data-sources-features.png" alt= "características de las fuentes de datos en la página fuentes de datos" width="800">

*Editar, volver a conectar, duplicar o eliminar un conector de origen de datos.*

Puede utilizar las siguientes funciones para el conector en la **Fuentes de datos** página:

* **Editar**: edite los detalles de configuración del conector seleccionado.

* **Volver a conectar**: vuelva a conectar a un conector desconectado.

* **Duplicar**: cree un nuevo conector duplicado utilizando el conector actual como base. El conector duplicado se crea con un sufijo (como connectorname_1) de forma predeterminada. Por ejemplo, sample-elastic-search_1.
Se visualiza un error si existe el conector con el mismo nombre.

* **Eliminar**: elimine el conector seleccionado.


Una vez configurada la fuente de datos, el conector se enumera en la sección **Panel Fuentes de datos** en el Editor web. A continuación, puede conectarse al origen de datos e insertar un fragmento de contenido en los temas. Para obtener más información, consulte [Inserción de un fragmento de contenido desde la fuente de datos](../user-guide/web-editor-content-snippet.md).
