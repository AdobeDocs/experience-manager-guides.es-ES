---
title: Configuración de un conector de fuente de datos con herramientas
description: Obtenga información sobre cómo configurar un conector de fuente de datos con las herramientas.
exl-id: d7cd412b-89ea-43a5-97b3-09944863bbee
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '883'
ht-degree: 0%

---

# Configuración de un conector de fuente de datos desde la interfaz de usuario

Experience Manager Guides viene con la herramienta **Fuentes de datos** que le ayuda a configurar conectores predeterminados para fuentes de datos. Puede configurar los conectores de cliente JIRA, SQL (MySQL, PostgreSQL, Microsoft SQL Server, SQLite, MariaDB, H2DB), Adobe Commerce, Elasticsearch y REST genérico.


Además de estos conectores predeterminados, Experience Manager Guides proporciona los conectores para las fuentes de datos de Salsify, Akeneo y Microsoft Azure DevOps Board (ADO). Puede descargar e instalar estos conectores de código abierto desde el [repositorio de Maven Central](https://central.sonatype.com/search?q=com.adobe.aem.addon.guides). A continuación, los usuarios pueden configurar estos conectores.
Aprenda a [instalar un conector de código abierto](#install-open-source-connector).



También puede conectarse a archivos de datos JSON mediante un conector de archivo. Cargue el archivo JSON desde el equipo o navegue desde los recursos de Adobe Experience Manager. A continuación, cree fragmentos de contenido o temas utilizando los generadores.

Para configurar un conector, realice los siguientes pasos:

1. Seleccione el vínculo **Adobe Experience Manager** de la parte superior y elija Herramientas.
1. Seleccione **Guías** de la lista de herramientas.
1. Seleccione el mosaico **Fuentes de datos**. Se muestra la página **Fuentes de datos**. Puede ver las fuentes de datos conectadas.

   Puede alternar entre la **vista de lista** o la **vista de mosaico** para ver los distintos orígenes de datos conectados como una lista o como mosaicos.

   <img src="./assets/data-sources-create-window.png" alt= "fuentes de datos enumeradas en la página fuentes de datos" width="800">

   *Ver o crear un conector de origen de datos.*

1. Haga clic en **Crear**.
1. Seleccione la base de datos para la que desea crear el conector. Por ejemplo, el conector de Elasticsearch.

   >[!NOTE]
   >
   >Se muestran todas las bases de datos listas para usar disponibles.

1. Haga clic en **Siguiente**.
1. Introduzca los detalles de configuración y conexión según la base de datos.

   >[!TIP]
   >
   >* Pase el ratón sobre <img src="./assets/info-details.svg" alt= "icono de información" width="25"> cerca del campo para ver más detalles al respecto.
   >* Los campos con * son obligatorios. Por ejemplo, puede introducir los siguientes detalles para el conector de Elasticsearch.

   * **Nombre**: escriba el nombre del origen de datos.
   * **Tipo de autenticación**: seleccione el tipo de autenticación en la lista desplegable. Por ejemplo, Autenticación básica de nombre de usuario y contraseña
   * **Nombre de usuario**: Escriba su nombre de usuario.
   * **Contraseña**: Escriba su nombre de usuario y contraseña.
   * **URL**: agregue la URL de la API.


1. Seleccione la opción **Excluir plantillas de fábrica** para excluir las plantillas de fábrica de su uso para generar temas y fragmentos de código. No aparecerán en el menú desplegable **Plantilla de asignación de datos** del cuadro de diálogo **Agregar generador de fragmentos de contenido** o **Agregar generador de temas**.
1. Seleccione **Probar conexión**. Solo podrá ver el botón **Probar conexión** habilitado después de agregar los detalles necesarios. Vea un mensaje de éxito si los detalles de la conexión son correctos. De lo contrario, podría ver un mensaje de error.
1. Seleccione **Guardar** en la parte superior para guardar el conector.     Vea el botón **Guardar** habilitado después de completar todos los detalles y de que la conexión se haya realizado correctamente.


   Si el conector se ha guardado correctamente, puede ver el origen de datos conectado en la página.

**Conectarse a varios recursos**

Puede agregar o utilizar varios recursos basados en distintas direcciones URL para algunos conectores, como Cliente REST genérico, Salsify, Akeneo y Tableros de DevOps de Microsoft Azure (ADO). A continuación, conéctese con ellos para crear fragmentos de contenido o temas utilizando los generadores correspondientes.

Siga estos pasos para crear un recurso:

1. Seleccione ![agregar icono](assets/Add_icon.svg) en la **sección de recursos de URL** para agregar un recurso para cada URL.
1. Configure todos los detalles en el cuadro de diálogo **Agregar recurso**.
1. Haga clic en **Agregar**.
1. Puede editar ![editar icono](assets/edit_pencil_icon.svg) o eliminar ![eliminar](assets/Delete_icon.svg) el recurso de la lista de recursos de la URL.
1. También puede utilizar los recursos predeterminados disponibles para fuentes de datos como Salsify, Akeneo y Microsoft ADO. Cambie las opciones OFF para el recurso que no desee configurar para un origen de datos.

Esto le permite recuperar rápidamente datos de cualquiera de los recursos de una fuente de datos concreta en un solo fragmento de contenido o tema.



## Instalación de un conector de código abierto{#install-open-source-connector}

Para publicar una dependencia presente en el [repositorio de Maven Central](https://central.sonatype.com/search?q=com.adobe.aem.addon.guides) en Cloud Services, debe incluir e incrustar la dependencia para un conector de código abierto.

1. Agregue la dependencia en `all/pom.xml` en su código de proyecto Git de Cloud Manager. Por ejemplo, puede agregar la siguiente dependencia para el conector de fuente de datos de los paneles de DevOps de Microsoft Azure.


   ```
   <dependency>
       <groupId>com.adobe.aem.addon.guides</groupId>
       <artifactId>konnect-azure-devops</artifactId>
       <version>1.0.0</version>
       <type>jar</type>
   </dependency> 
   ```

1. Incruste la dependencia añadida.

   ```
   <embedded>
       <groupId>com.adobe.aem.addon.guides</groupId>
       <artifactId>konnect-azure-devops</artifactId>
       <type>jar</type>
       <target>/apps/aemdoxonaemcsstageprogram-vendor-packages/content/install</target>
   </embedded> 
   ```

1. Ejecute la canalización para aplicar los cambios en Cloud Services.
El conector está instalado en su entorno.


## Funciones disponibles para un conector

* Alterne entre la **vista de lista** o la **vista de mosaico** para ver los distintos orígenes de datos conectados como una lista o como mosaicos.
* Seleccione la casilla de verificación de un solo conector. Haga clic en **Seleccionar todo** para seleccionar todos los conectores. Puede hacer clic en **Anular la selección de todos** cuando todos los conectores estén seleccionados.

<img src="./assets/data-sources-features.png" alt= "características de las fuentes de datos en la página fuentes de datos" width="800">

*Editar, volver a conectar, duplicar o eliminar un conector de origen de datos.*

Puede utilizar las siguientes características para el conector en la página **Fuentes de datos**:

* **Editar**: edite los detalles de configuración del conector seleccionado.

* **Volver a conectar**: vuelva a conectar a un conector desconectado.

* **Duplicate**: cree un nuevo conector duplicado usando el conector actual como base. El conector duplicado se crea con un sufijo (como connectorname_1) de forma predeterminada. Por ejemplo, sample-elastic-search_1.
Se visualiza un error si existe el conector con el mismo nombre.

* **Eliminar**: elimine el conector seleccionado.


Una vez que haya configurado el origen de datos, el conector aparecerá en la lista del **panel Fuentes de datos** del Editor web. A continuación, puede conectarse al origen de datos e insertar un fragmento de contenido en los temas. Para obtener más información, vea [Insertar un fragmento de contenido de su fuente de datos](../user-guide/web-editor-content-snippet.md).
