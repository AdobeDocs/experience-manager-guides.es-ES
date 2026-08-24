---
title: Configuración de un conector Git en AEM Guides
description: Obtenga información sobre cómo configurar un Git en Experience Manager Guides.
feature: Web Editor Configuration
role: Admin
level: Experienced
source-git-commit: b73e904c7e0a6f398e471be6fc874de30742e519
workflow-type: tm+mt
source-wordcount: '568'
ht-degree: 0%

---

# Crear y configurar el conector Git desde la interfaz de usuario de

>[!NOTE]
>
> Esta función está desactivada de forma predeterminada. Para habilitarlo en su entorno, póngase en contacto con el equipo de éxito del cliente.

Utilice la herramienta Fuentes de datos de Experience Manager Guides para crear y configurar un conector Git desde la interfaz de usuario. Después de configurar el conector correctamente, puede utilizarlo para importar contenido de un repositorio Git a Experience Manager Guides.

>[!NOTE]
>
> Antes de empezar, asegúrese de que el conector Git se implementa en el proyecto de Cloud Manager. Para obtener más información, vea [Agregar el conector Git al proyecto de Cloud Manager.](#add-git-connector-to-your-cloud-manager-project)


1. Seleccione el vínculo **Adobe Experience Manager** de la parte superior y elija **Herramientas**.
1. Seleccione **Guías** de la lista de herramientas.
1. Seleccione el mosaico **Fuentes de datos**. Se muestra la página **Fuentes de datos**.
1. Seleccione **Crear**.
1. En la lista de conectores de origen de datos, seleccione **GitHub**.

   ![](assets/github-connector-tile.png){width="600"}

1. Seleccione **Siguiente**.
1. Introduzca los detalles de configuración y conexión.

   ![](assets/conf-git-connector.png){width="600"}

   >[!TIP]
   >
   >* Pase el ratón sobre <img src="./assets/info-details.svg" alt= "icono de información" width="25"> cerca del campo para ver más detalles al respecto.
   >* Los campos con * son obligatorios. Por ejemplo, puede introducir los siguientes detalles para el conector Git.

   - **Nombre**: escriba el nombre del origen de datos.
   - **Ruta de acceso raíz de AEM de destino**: escriba la ruta de acceso en el repositorio de AEM donde se debe almacenar el contenido importado de Git.
   - **Filtro de tipo de archivo (inclusión)**: especifique los tipos de archivo que se incluirán durante la importación.
   - **Ruta de acceso excluida (regex)**: especifique los patrones de ruta que se excluirán de la importación.
   - **Tipo de autenticación**: seleccione el tipo de autenticación en la lista desplegable. Actualmente, **token de acceso personal (PAT)** es el único método de autenticación compatible. Introduzca la RUTA durante la configuración del conector para autenticar y acceder al repositorio Git.

     Aprenda a [generar un token de acceso personal de GitHub](https://docs.github.com/en/authentication/keeping-your-account-and-data-secure/managing-your-personal-access-tokens#creating-a-personal-access-token-classic).

     Al seleccionar ámbitos durante la generación de rutas en GitHub, asegúrese de habilitar los siguientes ámbitos:
     - **repositorio**: seleccione la casilla de verificación de nivel superior. Todos los subámbitos se seleccionan automáticamente, lo que concede acceso al contenido del repositorio, el estado de confirmación y las implementaciones.
     - **admin:org**: Seleccione solo **leer:org**. Esto es necesario para resolver la organización y la pertenencia al equipo.
   * **URL del repositorio**: introduzca la URL del repositorio Git desde la que se debe importar el contenido.
   * **Rama**: escriba la rama que se usará para importar contenido.

1. Compruebe la conexión. El botón **Probar conexión** solo se habilita después de que haya especificado los detalles necesarios. Si los detalles de conexión son correctos, aparecerá un mensaje de éxito. De lo contrario, aparecerá un mensaje de error.

   ![](assets/git-connector-test-connection.png){width="600"}

1. Seleccione **Guardar** en la parte superior para guardar el conector.

   El botón Guardar solo se activa después de introducir todos los detalles necesarios y de que la conexión se haya realizado correctamente. Si el conector se guarda correctamente, puede ver el conector de Github configurado en la página **Fuentes de datos**.

   ![](assets/git-connector-connected.png){width="600"}

## Añadir el conector Git al proyecto de Cloud Manager

Antes de que el conector Git esté disponible para configurarse desde la página **Fuentes de datos**, debe incrustarse como dependencia en el proyecto de AEM. Siga estos pasos para agregar la dependencia:

>[!NOTE]
>
> Para ver las versiones disponibles del conector Git, consulte [Repositorio central de Maven](https://central.sonatype.com/artifact/com.adobe.aem.addon.guides/konnect-github).

1. En `all/pom.xml` de su proyecto de AEM, agregue el conector Git como dependencia en `<dependencies>`:

   ```xml
   <dependency>
       <groupId>com.adobe.aem.addon.guides</groupId>
       <artifactId>konnect-github</artifactId>
       <version>1.0.1</version>
   </dependency>
   ```

1. En el mismo `pom.xml`, agregue la dependencia a la sección `<embeddeds>` de la configuración `filevault-package-maven-plugin`:

   ```xml
   <embedded>
       <groupId>com.adobe.aem.addon.guides</groupId>
       <artifactId>konnect-github</artifactId>
       <type>jar</type>
       <target>/apps/YOUR-vendor-packages/content/install</target>
   </embedded>
   ```

   Reemplace `YOUR-vendor-packages` con el nombre del paquete de proveedor de su proyecto.

1. Confirme y envíe los cambios al repositorio de Git de Cloud Manager y, a continuación, ejecute la canalización para implementarlos.

Una vez finalizada la canalización, el conector Git está instalado en su entorno y disponible para configurar desde la página **Fuentes de datos**.





