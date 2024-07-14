---
title: Configuración de un conector de fuente de datos con herramientas
description: Obtenga información sobre cómo configurar un conector de fuente de datos con las herramientas.
exl-id: 2a0ac0a0-b2a9-453e-851b-fb04c8903526
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '521'
ht-degree: 0%

---

# Configuración de un conector de fuente de datos desde la interfaz de usuario

Experience Manager Guides viene con la herramienta **Fuentes de datos** que le ayuda a configurar conectores predeterminados para fuentes de datos. Puede configurar conectores para bases de datos JIRA, SQL (MySQL, PostgreSQL, Microsoft SQL Server, SQLite, MariaDB, H2DB), Adobe Commerce y Elasticsearch.

Para configurar un conector, realice los siguientes pasos:

1. Seleccione el vínculo **Adobe Experience Manager** de la parte superior y elija Herramientas.
1. Seleccione **Guías** de la lista de herramientas.
1. Seleccione el mosaico **Fuentes de datos**. Se muestra la página **Fuentes de datos**. Puede ver las fuentes de datos conectadas.

   Puede alternar entre la **vista de lista** o la **vista de mosaico** para ver los distintos orígenes de datos conectados como una lista o como mosaicos.

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
   >* Pase el ratón sobre <img src="./assets/info-details.svg" alt= "icono de información" width="25"> cerca del campo para ver más detalles al respecto.
   > * Los campos con * son obligatorios. Por ejemplo, puede introducir los siguientes detalles para el conector del Elasticsearch.

   * **Nombre**: escriba el nombre del origen de datos.
   * Tipo de autenticación: seleccione el tipo de autenticación de la lista desplegable. Por ejemplo, Autenticación básica de nombre de usuario y contraseña
   * **Nombre de usuario**: Escriba su nombre de usuario.
   * **Contraseña**: Escriba su nombre de usuario y contraseña.
   * **URL**: agregue la URL de la API.

1. Seleccione **Probar conexión**. Solo podrá ver el botón **Probar conexión** habilitado después de agregar los detalles necesarios. Vea un mensaje de éxito si los detalles de la conexión son correctos. De lo contrario, podría ver un mensaje de error.



1. Seleccione **Guardar** en la parte superior para guardar el conector.     Vea el botón **Guardar** habilitado después de completar todos los detalles y de que la conexión se haya realizado correctamente.


   Si el conector se ha guardado correctamente, puede ver el origen de datos conectado en la página.

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
