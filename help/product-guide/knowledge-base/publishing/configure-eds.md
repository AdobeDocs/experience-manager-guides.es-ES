---
title: Experience Manager Guides y Edge Delivery Services (Beta)
description: Descubra cómo Edge Delivery Services (Beta) amplía las posibilidades de creación y publicación de Experience Manager Guides.
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 7ca2eeb0356f3c82a8d970f291006fc6d19aca23
workflow-type: tm+mt
source-wordcount: '1532'
ht-degree: 0%

---

# Experience Manager Guides y Edge Delivery Services (Beta)

Adobe Experience Manager Guides le permite publicar el contenido DITA directamente en Edge Delivery Services (EDS), disponible actualmente en *Beta*, a través de un perfil de publicación basado en GitHub. Esta capacidad permite a las organizaciones ofrecer experiencias de documentación de alto rendimiento y adaptables mientras mantienen los flujos de trabajo de creación basados en DITA en Experience Manager Guides.

Para obtener más información sobre el uso de EDS en Adobe Experience Manager, vea [Información general de Edge Delivery Services](https://experienceleague.adobe.com/es/docs/experience-manager-cloud-service/content/edge-delivery/overview).

Para habilitar la publicación desde Experience Manager Guides a EDS (Beta), debe completar una serie de pasos de configuración en GitHub y Experience Manager Guides. Las secciones siguientes describen cada paso en secuencia y explican cómo funcionan juntos en el flujo de trabajo general de publicación.

1. [Configuración de GitHub para EDS (Beta)](#set-up-and-configure-github-for-eds-beta)
2. [Creación y configuración de un perfil de publicación para EDS (Beta) en Experience Manager Guides](#create-and-configure-a-publish-profile-for-eds-beta-in-experience-manager)
3. [Personalización de la salida mediante bloques EDS](#customize-output-using-eds-blocks)

Para ver un tutorial rápido en vídeo, vea [Publicación en AEM Guides](https://experienceleague.adobe.com/en/docs/experience-manager-guides/using/knowledge-base/expert-session/publishing-in-aem-guides-aug25).



## Configuración de GitHub para EDS (Beta)

En esta sección se describe cómo configurar GitHub para utilizarlo con EDS (Beta). Abarca la creación de un repositorio con la plantilla de Adobe, la conexión de GitHub a Adobe Experience Manager a través de la sincronización de código de AEM, la configuración de las aplicaciones de GitHub y OAuth necesarias y la definición del punto de montaje del repositorio utilizado para publicar contenido.

### Creación de un repositorio de GitHub para EDS (Beta)

EDS (Beta) requiere un repositorio de GitHub con una estructura predefinida. Adobe proporciona un repositorio oficial de plantillas diseñado específicamente para los usuarios de Experience Manager Guides.

Siga estos pasos para crear su repositorio:

1. Abra el repositorio de plantillas de plantillas de plantillas de plantillas de plantillas de Experience Manager Guides [`aem-guides-boilerplate`](https://github.com/adobe/aem-guides-boilerplate).
   ![](assets/eds-boilerplate-template.png){align="left"}

2. Cree un nuevo repositorio con esta plantilla. Más información acerca de [Crear un repositorio a partir de una plantilla](https://docs.github.com/en/repositories/creating-and-managing-repositories/creating-a-repository-from-a-template). Asegúrese de que la visibilidad del repositorio esté establecida en *Public* para que EDS pueda acceder a ella.

   ![](assets/eds-create-new-repo.png){align="left"}

El repositorio ahora se crea y se alinea con la estructura de plantillas de plantillas de plantillas.

![](assets/eds-repo-created-github-view.png){align="left"}

### Conectar GitHub a Adobe mediante la sincronización de código de AEM

Adobe Experience Manager usa una aplicación de GitHub llamada **AEM Code Sync** para insertar contenido de Experience Manager Guides en GitHub.

Realice los siguientes pasos para instalar y configurar la aplicación *AEM Code Sync*:

1. Vaya a la página [Sincronización de código AEM](https://github.com/apps/aem-code-sync) y seleccione **Instalar**.
2. *AEM Code Sync* supervisa los cambios en el repositorio y garantiza que las actualizaciones se inserten correctamente en GitHub.

   >[!NOTE]
   >
   > Al instalar la aplicación, asegúrese de utilizar la misma cuenta de GitHub que posee el repositorio.

   ![](assets/eds-aem-code-sync-page.png){align="left"}
3. En la página siguiente, conceda acceso al repositorio que ha creado. Para ello, seleccione la opción **Seleccionar solo repositorios** y luego seleccione su repositorio en el menú desplegable.

   ![](assets/eds-aem-code-sync-install-authorize.png){width="350" align="left"}
4. Seleccione **Instalar y autorizar**.

Se le redirigirá a la página de configuración de GitHub, lo que confirma el registro correcto de la aplicación *AEM Code Sync*. También puede guardar las direcciones URL de vista previa y en directo del sitio web desde esta página.

![](assets/eds-aem-code-sync-registered.png){align="left"}

### Crear una nueva aplicación de GitHub

1. En GitHub, vaya a la barra lateral izquierda y seleccione **Configuración de desarrollador**.
2. En la barra lateral izquierda, seleccione **Aplicaciones de GitHub**.
3. Seleccione **Nueva aplicación de GitHub**.

   ![](assets/eds-new-github-app.png){width="650" align="left"}
4. En la página **Registrar nueva aplicación de GitHub**, proporcione los siguientes detalles:
   - **Nombre de aplicación de GitHub**: escriba un nombre para su aplicación. Por ejemplo, `USERNAME-eds-app` donde USERNAME es su nombre de usuario de GitHub.
   - **URL de la página principal**: escriba la URL de la instancia de Experience Manager Guides.

     URL de ejemplo (formato): `https://<aem-author-url>/libs/fmdita/clientlibs/xmleditor/page.html`

     URL de ejemplo: `https://author-p16602-e335172-cmstg.adobeaemcloud.com/libs/fmdita/clientlibs/xmleditor/page.html`
   - **URL de devolución de llamada**: Igual que la URL de la página principal.
   - **URL de webhook**: Deshabilite esta opción.
   - **Permisos de repositorio**: establezca **permisos de lectura y escritura** para *Acciones, administración y atestación*.
5. Seleccione **Crear aplicación de GitHub**.

La aplicación ya está lista. Se le redirigirá a la página **Configuración** de su aplicación de GitHub.

![](assets/eds-github-app-registered-page.png){align="left"}

### Crear una nueva aplicación de OAuth

Se requiere una aplicación OAuth para autenticar a los usuarios al crear un perfil de publicación EDS (Beta) en Experience Manager Guides. Habilita un flujo de inicio de sesión seguro mediante *ID de cliente* y *Secreto de cliente*.

Siga estos pasos para crear una nueva aplicación de OAuth:

1. En GitHub, vaya a la barra lateral izquierda y seleccione **Configuración de desarrollador**.
2. En la barra lateral izquierda, seleccione **Aplicaciones OAuth**.
3. Seleccione **Nueva aplicación de OAuth**.

   ![](assets/eds-new-oauth-app.png){width="650" align="left"}
4. Registre la solicitud proporcionando los siguientes detalles obligatorios:
   - **Nombre de aplicación**: escriba el nombre del repositorio EDS
   - **URL de la página principal**: escriba la URL de la instancia de Experience Manager Guides. (Para ver el formato de URL de ejemplo, consulte el paso 4 de [Crear una nueva aplicación de GitHub](#create-a-new-github-app) sección).
   - **URL de devolución de llamada de autorización**: Igual que la URL de la página principal
5. Seleccione la opción **Habilitar flujo de dispositivo** y, a continuación, seleccione **Registrar aplicación** para completar el registro.

   ![](assets/eds-new-github-app-register.png){width="650" align="left"}

La aplicación ya está lista. Observe el *ID de cliente*. Puede generar hasta cinco *secretos de cliente* ahora o más tarde al configurar el perfil de publicación en Experience Manager Guides.

![](assets/eds-new-oauth-app-page.png){align="left"}


### Configuración de la URL de punto de montaje en el repositorio EDS (Beta)

EDS (Beta) lee el contenido de una ruta de acceso al repositorio de GitHub definida como una URL de *punto de montaje* en el archivo `fstab.yaml`.

Para configurar la dirección URL del punto de montaje en el archivo `fstab.yaml`:

1. Abra el archivo `fstab.yaml` en el repositorio y actualice lo siguiente:
   - `your-user-name`
   - `your-repo-name`

   >[!NOTE]
   >
   > En la dirección URL de punto de montaje, `main` indica la rama en la que desea publicar el contenido y `docs` indica la carpeta raíz del repositorio EDS (Beta) en el que está trabajando. Si prefiere cambiar el nombre de la rama en GitHub, debe actualizar el mismo nombre de rama en la URL *mountpoint* (en el archivo `fstab.yaml`) y el perfil de publicación EDS correspondiente en Experience Manager Guides.

   ![](assets/eds-fstab-yaml-file.png){width="650" align="left"}
2. Seleccione **Confirmar cambios**, introduzca los detalles de confirmación y confirme.
3. Vuelva a [Configuración de desarrollador](https://github.com/settings/apps), busque su aplicación y seleccione **Editar**.

   ![](assets/eds-edit-github-app.png){width="650" align="left"}
4. Vaya a la página **Instalar aplicación** y seleccione **Instalar**.

   ![](assets/eds-install-eds-app.png){width="650" align="left"}
5. Repita los pasos 2 y 3 de [Conecte GitHub a Adobe a través de la sección AEM Code Sync](#connect-github-to-adobe-via-aem-code-sync) para autorizar el repositorio.

## Creación y configuración de un perfil de publicación para EDS (Beta) en Experience Manager

Las secciones siguientes describen cada paso en secuencia y explican cómo configurar el perfil de publicación de EDS (Beta), configurar un ajuste preestablecido de salida y generar resultados mediante EDS (Beta) en Experience Manager Guides.

### Creación del perfil de publicación de EDS (Beta)

1. Vaya a **[Configuración de Workspace](/help/product-guide/cs-install-guide/workspace-settings.md)** **>** **Publicar perfiles**.
2. Seleccione el icono **+** para crear un nuevo perfil de publicación y proporcione los siguientes detalles:
   - **Tipo de servidor**: seleccione **GitHub Edge Delivery Services (Beta)** en el menú desplegable.
   - **Nombre**: escriba un nombre para este perfil
   - **Nombre del repositorio**: Utilice el nombre del repositorio de GitHub creado a partir de la plantilla.
   - **Nombre de usuario**: Escriba su nombre de usuario de GitHub.
   - **Rama principal**: establecida en principal (predeterminada).
   - **Carpeta raíz**: establecida en documentos (predeterminada).
   - **ID de cliente y secreto de cliente**: búsquelos de su aplicación GitHub (consulte la sección [Crear una nueva aplicación OAuth](#create-a-new-oauth-app) para obtener detalles).
3. Seleccione **Iniciar sesión** para autenticarse.

   ![](assets/eds-publish-profile.png){width="650" align="left"}
4. Si la autenticación se realiza correctamente, seleccione **Guardar**.

Su perfil de publicación de EDS (Beta) ya está configurado.

### Cree un ajuste preestablecido de salida para EDS (Beta) y genere la salida

1. Abra el mapa en la consola Mapa.
2. En la pestaña **Ajustes preestablecidos de salida**, seleccione **+** para crear un nuevo ajuste preestablecido de salida.
3. En el cuadro de diálogo **Nuevo ajuste preestablecido de salida**, proporcione los siguientes detalles:
   - **Tipo**: Seleccione **Servicio Edge Delivery (Beta)**
   - **Nombre**: proporcione un nombre para este ajuste preestablecido
4. Seleccione **Añadir**.

   ![](assets/eds-output-preset.png){width="650" align="left"}
5. Abra el ajuste preestablecido de salida EDS (Beta) recién creado y vaya a la pestaña **Config**.
   - Seleccione el perfil de publicación creado en el paso anterior.
   - Habilitar **Push para la activación**.

   Cuando **Push to live** está habilitado, la salida generada se confirma en GitHub y las actualizaciones correspondientes se propagan inmediatamente al sitio web activo.

   ![](assets/eds-output-preset-config-tab.png){width="650" align="left"}

6. Seleccione **Guardar** y, a continuación, **Generar salida**.

>[!NOTE]
>
> El resultado generado se almacena en la carpeta **docs** del repositorio EDS (Beta).

La salida EDS (Beta) se genera ahora. El contenido se presenta en un diseño limpio y adaptable. Incluye elementos regulares como el título de la página, las rutas de exploración, el contenido del cuerpo y cualquier bloque utilizado en el tema. El índice de la izquierda (generado a partir del mapa) le ayuda a desplazarse por los temas, mientras que un mini índice de la derecha resalta las secciones de la página actual. Toda la salida es totalmente adaptable, lo que garantiza una experiencia de lectura optimizada y coherente en todos los dispositivos.

![](assets/eds-site-output.png){align="left"}

## Personalización de la salida mediante bloques EDS

EDS usa `blocks` para controlar cómo se diseñan y muestran las diferentes partes del contenido. Puede modificar bloques existentes o crear bloques personalizados.

Los ejemplos descritos a continuación le guían a través de la personalización de un bloque existente y la creación de un nuevo bloque para dar estilo a la salida EDS (Beta) final en Experience Manager Guides.

### Personalización de un bloque de ruta de exploración para actualizar el color del texto

Las rutas de exploración se utilizan en todas las páginas para ayudar a los usuarios a comprender dónde se encuentran en la documentación. Dado que este bloque aparece de forma coherente en todo el sitio web, la actualización de su estilo permite una actualización de diseño unificada.

Siga estos pasos para personalizar un bloque de ruta de exploración y actualizar su color de texto:

1. Vaya al repositorio de GitHub y abra la carpeta `blocks`.
2. Seleccione el bloque **rutas**.

   ![](assets/eds-breadcrumbs.png){width="650" align="left"}
3. Abra el archivo `css` y actualice el color del texto.
4. Confirme los cambios en GitHub.
5. Actualice el sitio web activo para ver las actualizaciones.

### Actualizar scripts EDS (Beta) para crear elementos personalizados en la salida publicada

En algunos casos, es posible que solo desee aplicar estilo a una parte específica del contenido. Realice los siguientes pasos para conseguirlo utilizando un bloque personalizado.

1. Abra el archivo de tema y seleccione el texto dentro de un elemento de etiqueta.

   En la siguiente captura de pantalla, se selecciona el contenido dentro de la etiqueta `example`.
   ![](assets/eds-example-tag-org-output.png){width="650" align="left"}
2. Para configurar el texto dentro de la etiqueta `example`:
   - Vaya a **Propiedades de contenido**.
   - Agregue el atributo `outputclass`.
   - Establezca su valor en `example eds-force-block`.
   - Seleccione **Añadir**.
     ![](assets/eds-example-tag.png){width="650" align="left"}
3. Guarde y vuelva a generar la salida.
4. Cree una nueva carpeta con el mismo nombre que `outputclass` dentro del directorio `blocks`. Obtenga información acerca de [agregar archivos a un repositorio](https://docs.github.com/en/repositories/working-with-files/managing-files/adding-a-file-to-a-repository#adding-a-file-to-a-repository-using-the-command-line).

   ![](assets/eds-example-folder.png){width="650" align="left"}
5. Agregue los `css` necesarios y los `js` archivos opcionales.

   ![](assets/eds-example-folder-subfolders.png){width="650" align="left"}
6. Confirme los cambios y vuelva a generar la salida.

El contenido seleccionado ahora muestra el estilo personalizado definido en el bloque.

![](assets/eds-example-output.png){width="650" align="left"}