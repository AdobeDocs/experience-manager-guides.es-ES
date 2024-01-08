---
title: Complemento de oxígeno para guías de Adobe Experience Manager
description: Aprenda a utilizar el complemento Oxygen para las guías de Adobe Experience Manager para crear y administrar su contenido.
hide: true
hidefromtoc: true
exl-id: 9a140564-27eb-404e-93a5-f5c81364e7f7
source-git-commit: 0e19b870541e8e65dc371eb01fc3256f172c1a91
workflow-type: tm+mt
source-wordcount: '6294'
ht-degree: 0%

---

# Complemento de oxígeno para guías de Adobe Experience Manager {#id1645H6010Q5}

El complemento Oxygen para Adobe Experience Manager AEM Guides \(más adelante denominado complemento Oxygen para guías de la guía) le permite conectar Oxygen XML Author con el repositorio Adobe Experience Manager AEM \(\) para crear y administrar contenido. AEM Puede utilizar el complemento para examinar, buscar y abrir archivos, desproteger y proteger archivos, cargar carpetas y archivos en el repositorio de. AEM AEM El panel Guías de la aplicación de escritorio de le permite marcar las carpetas deseadas \(del repositorio de\) a la lista de carpetas favoritas para acceder rápidamente a ellas. AEM AEM Además, puede instalar un paquete en la interfaz web y abrir los archivos DITA en Oxygen XML Author directamente desde la interfaz web de la.

## Descargar e instalar {#id1826M0L0PUI}

AEM El complemento Oxygen para guías de está disponible a través de su portal de distribución de software de Adobe. Busque &quot;oxígeno&quot; en la pestaña Experience Manager y, a continuación, descargue el programa de instalación del complemento desde su [Portal de distribución de software de Adobe](https://experience.adobe.com/#/downloads/content/software-distribution/en/general.html).

>[!NOTE]
>
>Compruebe la compatibilidad de la versión del conector de oxígeno en las notas de la versión para las guías específicas de Adobe Experience Manager.

Una vez que tenga el instalador, instálelo en el equipo local donde esté instalado Oxygen XML Author. AEM Antes de comenzar el proceso de instalación, debe asegurarse de que su sistema cumpla los requisitos técnicos para instalar el complemento de oxígeno para guías de la.

### Requisitos técnicos

- Oxygen XML Author versión 25.1

- Guías de Adobe Experience Manager versión 4.3 o superior

- Adobe Experience Manager versión 6.5 con Service Pack 14, 15, 16 y 17

- Sistema operativo compatible con Oxygen XML Author versión 25.1

- Java Development Kit
   - Oracle SE 8 JRE 1.8

### Instalación del complemento en Windows

>[!IMPORTANT]
>
>Si tiene una versión anterior del complemento instalado en el sistema, asegúrese de desinstalarlo antes de iniciar el proceso de instalación. Consulte la **Desinstalación de paquetes** de la sección [Cómo trabajar con paquetes](https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/package-manager.html) artículo para obtener instrucciones de desinstalación.

Realice los siguientes pasos en el sistema donde está instalado Oxygen XML Author:

1. Inicie el del instalador `.exe` archivo.

   Aparecerá la pantalla de bienvenida del asistente de instalación.

1. Clic **Siguiente** y busque la ubicación donde esté disponible el archivo .exe de Oxygen XML Author.

1. Seleccione el archivo y haga clic en **Abrir**.

   La ubicación del archivo seleccionado se agrega en el asistente de instalación.

1. Haga clic en **Siguiente**.

1. Clic **Instalar**.

1. Clic **Finalizar** para cerrar el asistente de instalación.
1. Inicie Oxygen XML Author.

   AEM El panel Guías de la se muestra en Oxygen XML Author.

   ![AEM conector de](images/oxygen-aem-connector.png){width="800" align="left"}

   >[!NOTE]
   >
   >AEM Si no ve el panel Guías de, consulte las soluciones en la sección Solución de problemas:[AEM Falta el panel Guías de](#id192BH200ZAX).


### Instalación del complemento en Mac

>[!IMPORTANT]
>
>Si tiene una versión anterior del complemento instalado en el sistema, asegúrese de desinstalarlo antes de iniciar el proceso de instalación. Consulte la **Desinstalación de paquetes** de la sección [Cómo trabajar con paquetes](https://helpx.adobe.com/experience-manager/6-4/sites/administering/using/package-manager.html) instrucciones de desinstalación del artículo.

Realice los siguientes pasos en el sistema donde está instalado Oxygen XML Author:

1. Localice el archivo .dmg del complemento en su sistema.

1. Haga doble clic en el archivo .dmg para abrir el contenido del archivo.

   El archivo .dmg contiene una carpeta aem-connector-x.x y un archivo aem-connector-x.x-setup.

   >[!NOTE]
   >
   >x.x en los nombres de archivo es el número de versión del complemento.

1. Copie la carpeta aem-connector-x.x en la carpeta de complementos de Oxygen XML Author.
1. Haga doble clic en el archivo aem-connector-x.x-setup para iniciar el instalador.

1. Inicie Oxygen XML Author.

   AEM El panel Guías de la se muestra en Oxygen XML Author.

   ![AEM conector Mac de](images/oxygen-aem-connector-mac.png) {width="800" align="left"}

   >[!NOTE]
   >
   >AEM Si no ve el panel Guías de, consulte las soluciones en la sección Solución de problemas:[AEM Falta el panel Guías de](#id192BH200ZAX).


### AEM Instale el paquete para habilitar la función de edición de documentos desde la interfaz web de {#id182CE0Q0TY4}

AEM Como autor, puede abrir y editar sus mapas o temas DITA en Oxygen XML Author directamente desde la interfaz web de la. AEM AEM AEM Para habilitar esta función en interfaz web, el administrador de la debe instalar un paquete en la instancia de creación de la aplicación.

AEM Como administrador de la, realice los siguientes pasos para instalar el paquete:

1. Obtenga el archivo .zip del paquete de su equipo de TI.
1. AEM Inicie sesión en la instancia de *\(como administrador\)* y vaya al Administrador de paquetes CRX. La URL predeterminada para acceder al administrador de paquetes es

   `http://<server name>:<port>/crx/packmgr/index.jsp`

   AEM El Administrador de paquetes administra los paquetes en la instalación local de la. Para obtener más información sobre cómo trabajar con el Administrador de paquetes, consulte [Cómo trabajar con paquetes](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/content/implementing/developer-tools/package-manager.html?lang=en) AEM en la documentación de.

   ![Administrador de paquetes](images/package-manager.png) {width="650" align="left"}

1. Para cargar el paquete Oxygen, haga clic en **Cargar paquete**.
1. En el cuadro de diálogo Cargar paquete, vaya al archivo del paquete Oxygen que descargó en el paso 1 y haga clic en Aceptar.

   AEM El paquete se cargará en la instancia de la.

1. Para iniciar el proceso de instalación, haga clic en **Instalar**.

   ![Paquete de oxígeno](images/oxygen-package.png){width="650" align="left"}

1. En el diálogo Instalar paquete, haga clic en **Instalar**.
1. Una vez finalizada la instalación, haga clic en el botón Inicio en la esquina superior izquierda del Administrador de paquetes CRX.
1. Seleccione un archivo DITA en la carpeta de recursos.

   **Editar en oxígeno** está disponible en la barra de herramientas. Para obtener más información sobre esta opción, consulte [AEM Abrir el tema DITA en Oxygen XML Author desde la interfaz web de la interfaz de usuario de](#id182CE0I905Z).

   >[!NOTE]
   >
   >El **Editar en oxígeno** Esta opción está visible al seleccionar un tema DITA. Si selecciona varios temas, la opción no estará visible.


## AEM Configuración del complemento Oxygen para guías de {#id1826KF00AHS}

Después de descargar e instalar el complemento, debe configurar lo siguiente para trabajar con el complemento:

- **Configuración de autenticación web** AEM : Configuración para la autenticación SSO en el complemento para guías de.
- **Configuración general** AEM : Configuración de conexión para el complemento, como la URL del servidor de, detalles de inicio de sesión, etc.
- **Preferencia para la personalización de atributos de perfil y nombres de archivo en referencias cruzadas**: Esta configuración es necesaria para los esquemas de atributos de generación de perfiles de los conjuntos de documentación.

### Configuración de autenticación web

JxBrowser se utiliza para la autenticación SSO mediante el complemento Conector de oxígeno. Es un navegador basado en cromo. Para java 9+, se requiere acceso a las API no públicas y el usuario debe conceder explícitamente este acceso a JxBrowser. Para obtener más información, consulte [Solución de problemas de JxBrowser](https://jxbrowser-support.teamdev.com/docs/guides/troubleshooting/issues.html).

AEM Actualice los archivos dados para configurar los ajustes de autenticación web en el complemento Oxygen para guías de usuario de la red (Oxygen Plugin for Guides):

>[!NOTE]
>
>Realice una copia de seguridad del archivo antes de actualizarlo.

**Para Mac y Oxygen 25.1**

Añada las siguientes líneas en env.sh

```java
--illegal-access=permit\
--add-opens=java.desktop/javax.swing.plaf.basic=ALL-UNNAMED\
--add-exports=javafx.controls/com.sun.javafx.scene.control=ALL-UNNAMED\
--add-exports=javafx.graphics/com.sun.javafx.stage=ALL-UNNAMED\
--add-exports=javafx.graphics/com.sun.javafx.scene=ALL-UNNAMED\
--add-exports=javafx.graphics/com.sun.javafx.scene.traversal=ALL-UNNAMED\
--add-exports=javafx.graphics/com.sun.javafx.tk=ALL-UNNAMED\
--add-exports=javafx.graphics/com.sun.glass.ui=ALL-UNNAMED\
--add-opens=javafx.graphics/com.sun.glass.ui=ALL-UNNAMED\
--add-opens=javafx.graphics/javafx.stage=ALL-UNNAMED\
--add-opens=javafx.graphics/com.sun.javafx.tk.quantum=ALL-UNNAMED\
--add-exports=java.desktop/sun.awt=ALL-UNNAMED\
--add-opens javafx.swing/javafx.embed.swing=ALL-UNNAMED
```

Añada las siguientes líneas en oxygenAuthor.sh

```java
-Djdk.module.illegalAccess=permit\-Djava.ipc.external=true\
```

**Para Windows y oxígeno 25.1**

Añada las siguientes líneas en env.bat

```java
--illegal-access=permit --add-opens=java.desktop/javax.swing.plaf.basic=ALL-UNNAMED --add-exports=javafx.controls/com.sun.javafx.scene.control=ALL-UNNAMED --add-exports=javafx.graphics/com.sun.javafx.stage=ALL-UNNAMED --add-exports=javafx.graphics/com.sun.javafx.scene=ALL-UNNAMED --add-exports=javafx.graphics/com.sun.javafx.scene.traversal=ALL-UNNAMED --add-exports=javafx.graphics/com.sun.javafx.tk=ALL-UNNAMED --add-exports=javafx.graphics/com.sun.glass.ui=ALL-UNNAMED --add-opens=javafx.graphics/com.sun.glass.ui=ALL-UNNAMED --add-opens=javafx.graphics/javafx.stage=ALL-UNNAMED --add-opens=javafx.graphics/com.sun.javafx.tk.quantum=ALL-UNNAMED --add-exports=java.desktop/sun.awt=ALL-UNNAMED --add-opens javafx.swing/javafx.embed.swing=ALL-UNNAMED
```

Añada las siguientes líneas en oxygenAuthor.bat

```java
-Djdk.module.illegalAccess=permit -Djava.ipc.external=true
```

>[!NOTE]
>
>Debe ejecutar oxígeno desde oxygenAuthor.sh para Mac y oxygenAuthor.bat para Windows como administrador.

### Configuración general

Realice los siguientes pasos para configurar las opciones de conexión en el complemento Oxygen para Adobe Experience Manager Guides:

1. AEM En el panel Guías de, haga clic en el icono de configuración y, a continuación, seleccione **Configuración**.

   ![Configuración de conexión ](images/settings.png){width="800" align="left"}

1. Especifique los siguientes detalles:
   - **URL del servidor** AEM : URL del servidor de, por ejemplo:

     ```http
     http[s]://<host>:<port>
     ```

     AEM En la URL anterior, especifique el nombre de host y el puerto del servidor en el que está implementado el servidor de la unidad de administración de datos ().

     >[!IMPORTANT]
     >
     >AEM Si el servidor de está implementado en el puerto 80 o 443, no es necesario especificarlo en la dirección URL.

   - **Autenticación:** Elegir entre **Básico \(Nombre de usuario/Contraseña\)** o **Autenticación web**. En caso de seleccionar **Básico** autenticación debe introducir el **Nombre de usuario** y **Contraseña** en el cuadro de diálogo Preferencias.

     AEM Si selecciona Autenticación web, aparecerá la pantalla Inicio de sesión de la sesión de la página de inicio de sesión de la página de la aplicación. Introduzca sus credenciales de inicio de sesión y haga clic en **Iniciar sesión** botón. AEM AEM AEM Cuando el inicio de sesión se realiza correctamente, la pantalla Inicio de sesión de la se cierra y el panel Guías de la muestra la lista de archivos del servidor.

   - **Tiempo de espera de conexión** AEM : especifique el tiempo en segundos que el cliente esperará una respuesta del servidor de. Si no se recibe ninguna respuesta del servidor en el tiempo especificado, se finaliza la solicitud. El valor predeterminado es 20 segundos.

   - **Carpeta local** AEM : Ubicación del equipo local en la que se almacenan los archivos del repositorio de tras la desprotección. Si especifica una ubicación que no existe en la unidad, el complemento crea esa ubicación.
   - **Abrir archivo cuando está desprotegido**: si se selecciona, abre los archivos en el cierre de compra.
   - **Cerrar archivo al protegerlo**: si se selecciona, cierra los archivos al registrarse. Antes de cerrar el archivo, aparece una ventana emergente en la que puede especificar los comentarios de la versión.
   - **Mostrar cuadro de diálogo Registrar al cerrar el archivo**: si se selecciona, aparece una ventana emergente al cerrar un archivo. En la ventana emergente, puede elegir proteger el archivo o cerrarlo sin protegerlo.
   - **Archivo de desprotección automática al abrir**: si se selecciona, al hacer doble clic en un archivo, se extrae automáticamente y se abre para su edición. En caso de que el archivo ya esté desprotegido, simplemente se abrirá para editarlo. Si esta opción no está seleccionada, al abrir un archivo sin bloqueo se abre en modo de solo lectura.
1. Haga clic en **Aceptar**.

### Preferencia para la personalización de atributos de perfil y nombres de archivo en referencias cruzadas {#id1827K0D0OHT}

AEM Es necesario configurar las preferencias en Oxygen XML Author para utilizar el atributo de generación de perfiles asociado a los temas DITA en el repositorio de la. También debe configurar la preferencia para mostrar los nombres de archivo en lugar de los GUID en las referencias cruzadas.

Realice los siguientes pasos para configurar atributos de generación de perfiles y referencias cruzadas:

1. Haga clic en Oxygen XML Author **Opciones** \> **Preferencias**.
1. En el **Asociación de tipo de documento** pestaña, seleccione **DITA** y haga clic en **Ampliar**.

   ![asociación de tipo de documento](images/document_type_association.png){width="650" align="left"}

1. En el **Classpath** pestaña, seleccione `com.adobe.o2.connector` en el **Usar el cargador de clase principal del complemento con ID** menú desplegable.

   ![Pestaña Ruta de clase](images/dita-extension.png){width="650" align="left"}

1. En el **Extensiones** , realice los cambios siguientes:

   - Clic **Elegir** junto al **Paquete de extensiones** y seleccione   `LinkResolverExtensionBundle - com.adobe.o2.framework.extn` en el **Clase** lista. Haga clic en **Aceptar**.
     ![Extensión configurada para temas DITA](images/dita-map-extenstion-link-resolve.png) {width="650" align="left"}
   - Clic **Elegir** junto al **Escuchador de estado de extensión de autor** bajo **Extensiones individuales** y seleccione `CustomAuthorExtensionStateListener - com.adobe.o2.framework.extn` en el **Clase** lista. Haga clic en **Aceptar**.
   - Clic **Elegir** junto al **Editor de valores de atributos personalizados de autor** bajo **Extensiones individuales** y seleccione `CustomValueEditor - com.adobe.o2.framework.extn` en el **Clase** lista. Haga clic en **Aceptar**.
   - Clic **Elegir** junto al **Controlador de inserción de objeto externo de autor** bajo **Extensiones individuales** y seleccione `CustomURLInsertionHandler - com.adobe.o2.ui ` en el **Clase** lista. Haga clic en **Aceptar**.


   La siguiente captura de pantalla muestra el **Extensión** Ficha para temas de DITA:
   <img src="images/dita-topic-extension-tab.png" alt="Extensión configurada para temas DITA" width="650" border="2px">
1. Clic **OK** en todos los cuadros de diálogo para guardar los cambios.

### Configuración de la extensión de mapa DITA

AEM La configuración de la extensión de mapa DITA es necesaria para permitir la apertura de archivos de mapa en Oxygen XML Author directamente desde la interfaz web de la. Estas configuraciones son similares a las configuraciones de generación de perfiles de atributos realizadas en el procedimiento anterior.

Siga estos pasos para configurar la extensión de mapa DITA:

1. Haga clic en Oxygen XML Author **Opciones** \> **Preferencias**.
1. En el **Asociación de tipo de documento** pestaña, seleccione **Mapa DITA** y haga clic en **Ampliar**.
1. En el **Classpath** pestaña, seleccione com.adobe.o2.connector en la **Usar el cargador de clase principal del complemento con ID** menú desplegable.
1. En el **Extensiones** , realice los cambios siguientes:
   - Clic **Elegir** junto al **Paquete de extensiones** y seleccione   `com.adobe.o2.framework.extn.LinkResolverDITAMapExtensionBundle` en el **Clase** lista. Haga clic en **Aceptar**.

   - Clic **Elegir** junto al **Escuchador de estado de extensión de autor** bajo **Extensiones individuales** y seleccione `CustomDITAMapAuthorExtensionStateListener - com.adobe.o2.framework.extn` en el **Clase** lista. Haga clic en **Aceptar**.

   - Clic **Elegir** junto al **Controlador de inserción de objeto externo de autor** bajo **Extensiones individuales** y seleccione `CustomURLInsertionHandler - com.adobe.o2.ui ` en el **Clase** lista. Haga clic en **Aceptar**.

   - Clic **Elegir** junto al **Editor de valores de atributos personalizados de autor** bajo **Extensiones individuales** y seleccione `CustomValueEditor - com.adobe.o2.framework.extn` en el **Clase** lista. Haga clic en **Aceptar**.

   - Clic **Elegir** junto al **Resolución de referencias** bajo **Extensiones individuales** y seleccione `CustomDITAMapReferenceResolver - com.adobe.o2` en el **Clase** lista. Haga clic en **Aceptar**.
   - *\(Opcional\)* Si no desea resolver las referencias al abrir un archivo de asignación, debe realizar la siguiente configuración adicional:

   La siguiente captura de pantalla muestra el **Extensión** pestaña:
   <img src="images/dita-map-extension-tab.png" alt="Extensión configurada para el mapa DITA" width="650" border="2px">

1. Clic **OK** en todos los cuadros de diálogo para guardar los cambios.

## AEM Trabajar con el complemento de oxígeno para guías de {#id1826JG00WY4}

### AEM Panel Guías de

AEM En la siguiente pantalla se muestra el panel Guías de.

![panel conector](images/connector-panel.png){width="550" align="left"}

**A**\) Muestra la barra de búsqueda.

**B**\) Muestra la carpeta Favoritos. De forma predeterminada, está vacío. AEM Puede añadir carpetas del repositorio de la como favoritas; a continuación, las carpetas favoritas se muestran aquí.

**C** AEM \) La carpeta DAM muestra el repositorio de. Puede expandir y contraer la vista de carpetas.

**D**\) El icono Configuración \(engranaje\) con las siguientes opciones:

- **Connect** AEM : seleccione esta opción para conectarse al servidor de la. AEM La opción se desactiva cuando Oxygen XML Author está conectado al servidor de la.
- **Actualizar** AEM : seleccione esta opción para obtener el estado más reciente de los archivos y la carpeta del repositorio de.

  >[!NOTE]
  >
  >Asegúrese de guardar los archivos antes de actualizarlos. Al seleccionar **Actualizar** , recibirá una advertencia para guardar los archivos antes de actualizarlos. Si no ha guardado los archivos, puede hacer clic en **Cancelar** y los salvas.

- **Configuración**: Puede utilizar esta opción para abrir el cuadro de diálogo Preferencias generales del complemento.
- **Cerrar sesión** AEM : seleccione esta opción para cerrar la conexión con el servidor de. Esta opción solo está disponible si utiliza el modo Autenticación web.

### Funciones del menú contextual

AEM AEM Las funciones del complemento Oxygen para guías de están disponibles al hacer clic con el botón derecho en una carpeta o archivo del repositorio de. Las funciones disponibles para las carpetas son diferentes de los archivos. AEM A continuación se muestra una lista completa de funciones en el menú contextual del Complemento de oxígeno para guías de:

- **Abrir**: abre el archivo seleccionado o expande la carpeta seleccionada.
- **Abrir en** AEM : puede elegir abrir el archivo seleccionado en el Editor web de las guías de la aplicación, en el Tablero de mapas o en el Editor de mapas de las guías de la aplicación. Para obtener más información sobre estas opciones, consulte [AEM Abrir archivo en el editor de Guías de](#id195GH0V30KX).
- **Fecha de salida** AEM : extrae un archivo del repositorio de la. Para obtener más información, consulte [Archivos de desprotección](#id195HC020TS4).
- **Salida con dependientes**: extrae un archivo con sus referencias directas. Para obtener más información, consulte [Archivos de desprotección](#id195HC020TS4).
- **Cierre de compra con dependientes de solo lectura**: extrae el archivo seleccionado junto con sus dependientes. No puede realizar ningún cambio en los archivos dependientes. Para obtener más información, consulte [Archivos de desprotección](#id195HC020TS4).
- **Cancelar desprotección**: cancela el archivo desprotegido, cierra el archivo desde el editor y revierte los cambios a la última versión del archivo guardado en el servidor.
- **Actualizar** AEM : En el caso de un archivo, obtiene la última copia del archivo del repositorio de la. Para una carpeta, recupera la estructura de carpetas y el estado del archivo. AEM Esto significa que se agrega un archivo y, a continuación, se mostrará en la vista Guías de la vista de la vista de la vista de la vista de la vista de la vista de la vista de la vista de la. AEM Además, si un archivo está desprotegido en el servidor, al realizar una actualización en Oxygen Author, se mostrará el archivo como desprotegido. Sin embargo, esto no actualiza la lista de archivos en la *AEM Archivos desprotegidos en las guías de la* Ver.
- **Actualizar archivos desprotegidos**: actualiza la lista de archivos desprotegidos en la *AEM Archivos desprotegidos en las guías de la* Ver. AEM Si un archivo está desprotegido en el servidor, al realizar una actualización, se actualizará la lista de archivos desprotegidos en el servidor de *AEM Archivos desprotegidos en las guías de la* Ver. AEM Sin embargo, si se ha agregado un nuevo archivo o si el estado de un archivo ha cambiado, no se actualiza en la vista de árbol Guías de la. AEM Para actualizar el estado de los archivos en el momento de la actualización, debe realizar una actualización.
- **Check-in**: protege los archivos que ha desprotegido. Para obtener más información, consulte [Proteger un archivo](#id182CF0J0FHS).
- **Registro de entrada con dependientes**: Si ha retirado archivos con dependientes, esta opción protege el archivo principal junto con sus dependientes. Para obtener más información, consulte [Proteger un archivo](#id182CF0J0FHS).
- **Crear carpeta** AEM : crea una carpeta en el repositorio de. Esta opción solo está disponible en el nivel de carpeta.
- **Cargar archivo\(s\)**: carga uno o varios archivos. Para obtener más información, consulte [Carga de archivos y carpetas](#id195HC03F03J).
- **Cargar con dependientes**: carga archivos DITA \(XML, DITA, Book map o DITA map\) con sus dependientes. Para obtener más información, consulte [Carga de archivos y carpetas](#id195HC03F03J).
- **Cargar carpeta** AEM : carga una carpeta en el repositorio de. Para obtener más información, consulte [Carga de archivos y carpetas](#id195HC03F03J).
- **Añadir a Favoritos**: añade una carpeta a *Favoritos* AEM en el panel Guías de la. AEM Se recomienda agregar la carpeta de trabajo aquí, lo que facilita la sincronización de archivos y el estado del archivo desde el punto de vista de la vista de la vista de la vista de la vista de los archivos
- **Eliminar de Favoritos**: quita una carpeta de *Favoritos*. Para obtener más información, consulte [Agregar o quitar Favoritos](#id195HC04405P).
- **Ver metadatos**: muestra metadatos como la clase DITA, el título, el tipo, el UUID y otra información del documento asociada a un archivo. Para obtener más información, consulte [Visualización de los metadatos de un archivo](#id195GHN0H05C).
- **Ver versiones**: muestra el historial de versiones de un archivo. Para obtener más información, consulte [Ver el historial de versiones de un archivo](#id195GI000D5Q).

### Abra un archivo en Oxygen XML Author {#id195GHJ0A0UB}

AEM Una vez que se haya conectado al repositorio de, puede abrir los archivos para editarlos en Oxygen XML Author. Realice los siguientes pasos para abrir un archivo para editarlo en Oxygen XML Author:

1. AEM Haga clic con el botón secundario del mouse (ratón) en un archivo del panel Guías de la aplicación que desee abrir para editarlo.

1. Seleccionar **Abrir** en el menú contextual.

   El archivo se abre en el editor de Oxygen XML Author.

   ![Guid en la ficha de archivo](images/guid-in-file-tab.png) {width="800" align="left"}

   Cuando pasa el puntero del ratón sobre la pestaña de un archivo, se muestra la ruta del servidor junto con su UUID. En la captura de pantalla anterior, se resalta el UUID del documento.


Si ha seleccionado la variable **Archivo de desprotección automática al abrir** opción \(en el cuadro de diálogo Preferencias\) y, al abrir un archivo, el archivo se desprotege automáticamente y está disponible para su edición. Para abrir un archivo, puede hacer doble clic en su nombre o hacer clic con el botón derecho en el nombre del archivo y elegir **Abrir** en el menú contextual. Si no se selecciona esta opción, el archivo se abre en modo de solo lectura.

>[!NOTE]
>
>También puede hacer doble clic en un archivo para abrirlo.

### AEM Abrir archivo en el editor de Guías de {#id195GH0V30KX}

AEM Si desea utilizar los editores disponibles en las Guías de, puede hacerlo seleccionando la opción requerida en el menú contextual. AEM Realice los siguientes pasos para utilizar el editor de las guías de la aplicación en lugar del editor de Oxygen XML Author:

1. AEM Haga clic con el botón secundario del mouse (ratón) en un archivo del panel Guías de la aplicación que desee abrir para editarlo.

1. Seleccionar **Abrir en** en el menú contextual, elija una de las siguientes opciones:

   - **Editor de temas web**: Si el archivo que está abriendo es un archivo .xml o .dita, puede abrirlo para editarlo en el Editor Web. Elija la **Editor de temas web** para abrir el archivo seleccionado y editarlo en el Editor Web.

   - **Tablero de mapas**: puede elegir editar un archivo .ditamap en el panel de asignaciones, donde puede realizar varias operaciones en el archivo de asignación. Estas operaciones dependen de la función o el grupo al que pertenezca.

   - **Editor de mapas DITA web**: si desea abrir el archivo .ditamap para editarlo en el Editor de mapas, elija esta opción. Con la opción Editor de mapas DITA, se pueden añadir o quitar temas, añadir tablas de relación y realizar otras operaciones en el mapa.


### Archivos de desprotección {#id195HC020TS4}

AEM Cuando se retira un archivo, se almacena localmente en el sistema y se bloquea para su edición en el repositorio de. Realice los siguientes pasos para desproteger un archivo:

1. Puede desproteger los archivos de una de las siguientes maneras:
   - AEM Haga clic con el botón secundario en un archivo en el panel Guías de.
   - Pulse con el botón derecho del ratón en la ficha de asignación del panel Administrador de mapas DITA.
   - Haga clic con el botón derecho en un archivo del panel Administrador de mapas DITA.
   - Haga clic con el botón secundario en la ficha del archivo cuando abra un mapa o tema en el Editor.

1. Seleccione una de las siguientes opciones:
   - **Salida:** AEM Extrae un archivo del repositorio de la aplicación y lo pone a disposición de los usuarios para que lo editen.
   - **Salida con dependientes**: extrae un archivo con sus referencias directas. Puede realizar cambios en las páginas principales y secundarias mediante esta opción. AEM Oxygen Plugin for Guides admite la comprobación de un nivel de dependientes. Por ejemplo, el Mapa A hace referencia al Tema A y el Tema A hace referencia al Tema B. Si se retira el Mapa A, se retirará el Tema A independientemente de su nivel en la jerarquía del índice. Sin embargo, no comprobará el Tema B porque no está directamente vinculado desde el Mapa A.
   - **Cierre de compra con dependientes de solo lectura**: retira un archivo y descarga sus dependientes en el equipo local como copias de solo lectura. No puede realizar ningún cambio en los archivos dependientes.

Si ha seleccionado la variable **Abrir archivos al cerrar la compra** opción \(en el cuadro de diálogo Preferencias\) y, a continuación, al retirar un archivo, este se abrirá automáticamente para editarlo.

Si ha seleccionado la variable **Archivo de desprotección automática al abrir** opción \(en el cuadro de diálogo Preferencias\) y, al abrir el archivo, el archivo se desprotege automáticamente y está disponible para su edición. Para abrir un archivo, puede hacer doble clic en su nombre o hacer clic con el botón derecho en el nombre del archivo y elegir **Abrir** en el menú contextual.

Cuando un archivo está desprotegido, el icono del archivo cambia para mostrar su estado bloqueado.

![Desproteger un archivo](images/check-out-file.png){width="650" align="left"}

En la captura de pantalla anterior, se muestra un archivo desprotegido por otro usuario con un icono de candado de color negro \(A\). El archivo desprotegido por el usuario actual se muestra con un candado \(B\) de color verde.

>[!NOTE]
>
>AEM Si el archivo desprotegido se elimina o se mueve a cualquier otra carpeta de la lista de carpetas, aparecerá un mensaje de error al proteger el archivo. AEM Asegúrese de que el archivo desprotegido no se mueve ni se elimina mediante la interfaz Web de la interfaz de usuario de la aplicación de seguridad de la aplicación de seguridad de la aplicación de seguridad de la aplicación (Web).

### Proteger un archivo {#id182CF0J0FHS}

AEM Cuando se protege un archivo, la copia local del sistema se almacena en el repositorio de la y se elimina el bloqueo del archivo. Siga estos pasos para proteger un archivo:

1. Guarde el archivo haciendo clic en **Archivo** \> **Guardar**.

1. Haga clic con el botón secundario del mouse (ratón) en un archivo o mapa desprotegido en una de las ubicaciones siguientes:
   - AEM Panel Guías de
   - Panel Administrador de mapas DITA
   - Ficha del archivo cuando se abre un mapa o un tema en el Editor.
   - La ficha Mapa del panel Administrador de mapas DITA.

1. Elija entre las dos opciones siguientes:

   - **Check-In** AEM : Incorpora el archivo seleccionado del sistema local en el repositorio de.
   - **Registro con dependientes:** Si ha retirado un archivo junto con sus dependientes, utilice esta opción para proteger todos los archivos dependientes en una sola operación. Al seleccionar esta opción, se muestra el cuadro de diálogo Proteger con todos los archivos dependientes. Haga clic en Aceptar para proteger todos los archivos a la vez.

   Si no ha desprotegido los archivos dependientes y elige esta opción, sólo se desprotegerán los archivos dependientes que tenga \(por separado\). Se mostrará una lista de archivos que no se pudieron proteger:

   ![errores de registro](images/check-in-error.png){width="800" align="left"}

   Se recomienda no mover un archivo desprotegido. Sin embargo, si un archivo desprotegido se mueve a una ubicación diferente, deberá cancelar la desprotección de dicho archivo. Si desea realizar actualizaciones en ese archivo, vuelva a desprotegerlo, realice cambios y vuelva a protegerlo. Si intenta proteger un archivo que se ha movido desde su ubicación original, obtendrá un error.

   AEM Si se extrae un archivo dependiente en el modo de archivo, la opción Registrar con dependientes no mostrará el archivo dependiente en el cuadro de diálogo Registrar. AEM Para obtener una lista de los archivos dependientes desprotegidos en el archivo de datos, debe realizar una actualización de la carpeta.

   AEM Del mismo modo, si ha protegido un archivo dependiente a través de la opción de archivo, la lista de archivos no se actualiza en Oxygen Author hasta que realice una operación de actualización de carpeta y actualización de archivos desprotegidos. AEM Si realiza un registro con dependientes con algunos archivos registrados a través de la opción de registro, obtendrá un error que enumera los archivos que no se han podido registrar.

1. \(Opcional\) En el **Check-In** o el **Registro de entrada con dependientes** diálogo, añadir un comentario en **Comentarios de versión** cuadro de texto.

   >[!NOTE]
   >
   >AEM Este comentario se muestra en el historial de versiones del archivo en el que se ha realizado la.

1. Añadir etiqueta(s) en **Etiqueta** cuadro de texto en la **Check-In** o el **Registro de entrada con dependientes** diálogo . Introduzca una etiqueta y pulse Intro. Por ejemplo, *Versión 2307*.

   Si el administrador ha predefinido una lista de etiquetas y las ha cargado en `label.json` , esas etiquetas se mostrarán como una lista desplegable. Puede elegir una o más etiquetas de la lista desplegable.

   ![Cuadro de diálogo Proteger](images/checkin-dropdown-labels.png){width="550" align="left"}

   Puede agregar varias etiquetas (separadas por comas) a la misma versión de un tema.  Por ejemplo, *Adobe*, *AEM*, *Guías*.
Sin embargo, no se puede agregar la misma etiqueta a las distintas versiones de un tema. Si agrega una etiqueta que ya ha agregado a una versión anterior, se agrega a la versión más reciente y se elimina de la versión anterior.

   >[!NOTE]
   > 
   > AEM Estas etiquetas se muestran en el historial de versiones del archivo en el que se ha realizado la.


1. Haga clic en **Aceptar**.

>[!NOTE]
>
>AEM Si el archivo desprotegido se elimina o se mueve a cualquier otra carpeta de la lista de carpetas, aparecerá un mensaje de error al proteger el archivo. AEM Asegúrese de que el archivo desprotegido no se mueve ni se elimina mediante la interfaz Web de la interfaz de usuario de la aplicación de seguridad de la aplicación de seguridad de la aplicación de seguridad de la aplicación (Web).

### AEM Archivos desprotegidos en la vista Guías de la

Cuando tiene archivos en varias carpetas, no es fácil averiguar cuántos archivos están desprotegidos en una vista. AEM AEM Guías de proporciona Archivos desprotegidos en la Vista de guías de la aplicación de la que se proporciona una instantánea completa de los archivos desprotegidos actualmente. AEM AEM Con esta vista, puede averiguar fácilmente qué archivos ha comprobado en el repositorio de mediante las guías de la. Siga estos pasos para acceder a esta vista y trabajar con ella:

1. Clic **Ventana** \> **Mostrar vista** \> **AEM Archivos desprotegidos en las guías de la**.

   AEM Se mostrarán los archivos desprotegidos en la vista Guías de recursos de la aplicación de datos de la aplicación.

   ![archivos retirados](images/files-checkedout-view.png){width="550" align="left"}

1. Haga clic con el botón derecho en un archivo de esta vista para obtener las siguientes opciones:

   - [Abrir](#id195GH0V30KX)
   - [Abrir en](#id195GH0V30KX)
   - Cancelar desprotección
   - [Check-In](#id182CF0J0FHS)
   - [Registro de entrada con dependientes](#id182CF0J0FHS)
   - [Ver metadatos](#id195GHN0H05C)
   - [Ver versiones](#id195GI000D5Q)

**AEM Notas sobre los archivos desprotegidos en la vista Guías de la aplicación de la vista de las guías de la aplicación:**

- El *AEM Archivos desprotegidos en las guías de la* La vista mantiene las sesiones del usuario. Esto significa que los archivos desprotegidos por el usuario actual se almacenan y mantienen en la vista en las sesiones \(o caché\) del mismo usuario.

- AEM Si el usuario cambia las credenciales de inicio de sesión o el servidor de, se restablecerán los datos \(o caché\) del archivo desprotegido en la vista. El usuario debe ejecutar manualmente una *Actualizar archivos desprotegidos* en cada carpeta desde la que se desprotegieron los archivos anteriormente. Para simplificar esto, se recomienda agregar las carpetas de trabajo a *Favoritos* desde donde puede realizar rápidamente una actualización de carpetas.

- Puede ordenar la lista de archivos según sus nombres de archivo, título o ruta de acceso. Si se desprotege un nuevo archivo, éste aparece ordenado en la vista.


### Carga de archivos y carpetas {#id195HC03F03J}

Siga estos pasos para cargar archivos o carpetas:

1. AEM Haga clic con el botón secundario en una carpeta del panel Guías de la.
1. Seleccione una de las siguientes opciones:
   - **Cargar archivo\(s\)** AEM : seleccione esta opción para cargar uno o varios archivos en la carpeta seleccionada en el repositorio de. En el diálogo Seleccionar archivos \(s\) para cargar, seleccione los archivos y haga clic en **Abrir**.
   - **Cargar con dependientes**: seleccione esta opción para cargar un fichero DITA con sus dependientes. En el diálogo Seleccionar archivo para cargar, seleccione los archivos y haga clic en **Abrir**.
   - **Cargar carpeta** AEM : seleccione esta opción para cargar una carpeta en el repositorio de la. En el cuadro de diálogo Elegir, seleccione la carpeta y haga clic en **Elegir**.

**Notas adicionales sobre cómo trabajar con archivos basados en UUID**:

AEM Se deben tener en cuenta los siguientes puntos al mover o copiar contenido del sistema local a un repositorio de datos de la base de datos de la base de datos de la base de datos de la base de datos de:

- Al cargar uno o más archivos, se genera un nuevo UUID para los archivos que no tienen ningún UUID. Este UUID se añade en la variable `topic id` de un fichero DITA.

- Al copiar una carpeta, las referencias a los ficheros \(dentro de la carpeta\) se actualizan automáticamente en todas las asignaciones DITA que hacen referencia a ficheros de dicha carpeta.

- Al copiar un fichero de mapa DITA, las referencias UUID dentro del fichero de mapa no cambian.

- Si un archivo o una carpeta tiene un conflicto o un duplicado, se generará un nombre de archivo único para el nuevo archivo que se está copiando o moviendo.

- Dos archivos no pueden tener el mismo UUID. Se asigna un UUID único a todos los archivos nuevos.

- Si dos usuarios diferentes están cargando un archivo al mismo tiempo, el archivo que se procese más adelante sobrescribirá el archivo anterior. Sin embargo, esa práctica debería evitarse.

- AEM Cuando extraiga contenido del repositorio de y realice cambios en el sistema local, asegúrese de que el nombre del archivo no cambie en el momento de cargarlo.

- Al insertar una referencia en el Administrador de mapas DITA o en el Editor, se muestra el título del archivo y no el UUID. Si el título no está presente, se muestra el nombre del archivo.

### Agregar o quitar Favoritos {#id195HC04405P}

AEM Realice los siguientes pasos para agregar o quitar una carpeta a la carpeta Favoritos en el panel Guías de:

- Haga clic con el botón derecho en una carpeta y seleccione **Añadir a Favoritos**. Puede agregar una carpeta a Favoritos si no está en Favoritos.
- Puede quitar una carpeta de favoritos de las siguientes maneras:
   - Haga clic con el botón derecho en una carpeta de **Favoritos** carpeta y seleccione **Eliminar de Favoritos**.
   - AEM Haga clic con el botón derecho en una carpeta del repositorio de en **DAM** carpeta que ya se ha añadido como favorita y seleccione **Eliminar de Favoritos**.

### Ver el historial de versiones de un archivo {#id195GI000D5Q}

Siga estos pasos para ver el historial de versiones de un archivo:

1. AEM Haga clic con el botón derecho en un archivo en el panel Guías de.

1. Seleccionar **Ver versiones** en el menú contextual.

   El historial de versiones del archivo se muestra en el cuadro de diálogo Versiones.

   ![Historial de versiones](images/version-history.png){width="550" align="left"}


### Visualización de los metadatos de un archivo {#id195GHN0H05C}

Siga estos pasos para ver los metadatos de un archivo:

1. AEM Haga clic con el botón derecho en un archivo en el panel Guías de.

1. Seleccionar **Ver metadatos** en el menú contextual.

   Los metadatos del archivo, como la clase DITA, el estado del documento, la fecha de modificación, el tamaño, el título y el UUID, se muestran en el cuadro de diálogo Metadatos.

   ![Ver metadatos](images/metadata.png){width="550" align="left"}


## AEM Buscar un tema en el repositorio de la {#id1826J20405Z}

AEM AEM Puede buscar temas en el repositorio de mediante la barra de búsqueda del panel Guías de. Puede buscar en toda la carpeta DAM o seleccionar una carpeta y, a continuación, buscar un tema en esa carpeta. El resultado de la búsqueda muestra los temas cuyo texto coincide con la consulta de búsqueda.

Siga estos pasos para buscar temas:

1. AEM Seleccione una carpeta en el repositorio de en la que desee buscar un tema.
1. Introduzca la consulta de búsqueda \(por ejemplo, `introduction`AEM \) en la barra de búsqueda del complemento de oxígeno para guías de la.
1. Haga clic en el botón de búsqueda o pulse Intro.

   El resultado se muestra en la ficha Resultados de la búsqueda como una lista con la ruta de acceso del archivo. Si no hay resultados que coincidan con la consulta de búsqueda, no se encontraron resultados en &lt;path of=&quot;&quot; the=&quot;&quot; selected=&quot;&quot; folder=&quot;&quot;> se muestra el mensaje.

   ![Resultados de la búsqueda](images/search.png){width="550" align="left"}

1. \(Opcional\) Haga doble clic en un archivo en el resultado de la búsqueda para abrirlo en Oxygen XML Author.
1. AEM Para volver a la vista Repositorio de, siga uno de estos procedimientos:
   - AEM Para ver la vista Repositorio de sin borrar los resultados de la búsqueda, haga clic en **Examinar** pestaña.
   - AEM Para borrar los resultados de la búsqueda y ver el repositorio de, haga clic en el icono Eliminar búsqueda.

## AEM Abrir el tema DITA en Oxygen XML Author desde la interfaz web de la interfaz de usuario de {#id182CE0I905Z}

AEM Puede abrir y editar el tema DITA en Oxygen XML Author desde la interfaz web de la interfaz de usuario de la aplicación de. AEM Para activar esta opción, debe instalar un paquete en el. Para obtener más información sobre la instalación de paquetes, consulte [AEM Instale el paquete para habilitar la función de edición de documentos desde la interfaz web de](#id182CE0Q0TY4).

>[!NOTE]
>
>El **Editar en oxígeno** AEM es accesible desde varios lugares de la zona de trabajo: cuando se selecciona un tema, cuando se obtiene una vista previa del mismo, o desde la ficha Temas e informes de la consola de mapas de DITA. Si selecciona varios temas, la opción no estará visible en la barra de herramientas.

**Abrir un tema DITA**

Realice los siguientes pasos para abrir un tema DITA en Oxygen XML Author:

1. Seleccione un tema en los recursos y haga clic en **Editar en oxígeno** en la barra de herramientas.

   >[!NOTE]
   >
   >Si el tema no está extraído, primero se extrae y, a continuación, se abre en Oxígeno en el modo de edición.

1. Seleccione Oxygen XML Author *&lt;version>* en el **Iniciar aplicación** cuadro de mensaje. Puede seleccionar **AEM Recordar mi elección para los vínculos de la** para guardar su preferencia.

**Edición de un tema DITA**

Realice los siguientes pasos para editar un tema DITA en Oxygen XML Author:

1. Seleccione y desproteja un tema de los recursos.
1. Clic **Editar en oxígeno** en la barra de herramientas.

   >[!NOTE]
   >
   >Si el tema no está extraído, primero se extrae y, a continuación, se abre en Oxígeno en el modo de edición.

1. Seleccione Oxygen XML Author *&lt;version>* en el **Iniciar aplicación** cuadro de mensaje. Puede seleccionar **AEM Recordar mi elección para los vínculos de la** para guardar su preferencia.
1. Edite el tema en Oxygen XML Author.
1. AEM Consulte el tema en el Complemento de oxígeno para guías de la.

   AEM Para obtener más información sobre cómo registrar un tema con el complemento Oxygen para guías de la, consulte [Proteger un archivo](#id182CF0J0FHS).

   >[!NOTE]
   >
   >AEM AEM Asegúrese de proteger el tema con el complemento Oxygen para guías de. Si lo hace desde la interfaz web de la interfaz de usuario, los cambios que realice en Oxygen XML Author no se guardarán en la versión protegida del tema.

**Inserte una referencia a un tema desde el repositorio de guías del Experience Manager**

También se puede arrastrar y soltar un tema para insertar la referencia en un tema o en un mapa DITA.
>[!NOTE]
>
> Es necesario desproteger un archivo antes de agregar cualquier referencia a él.

Se añaden los siguientes elementos en función del tipo de referencias:

Si suelta en el editor con un tema abierto:
- Se añade una referencia con `<image>` para las imágenes.
- Se agrega un elemento de objeto para un vídeo o audio.
- El `<xref>`  se añade para todas las demás referencias como tema, mapa, DITAVAL, PDF, ZIP y XML.

Si se coloca en el Editor o en el Administrador de mapas DITA con un mapa abierto:
- El `<mapref>` se añade para referencias de mapa, que incluyen un mapa DITA, un mapa de libro o un esquema de asunto.
- El `<topicref>` se añade para todas las demás referencias como tema, mapa, DITAVAL, PDF, ZIP y XML.


## Trabajo con perfiles de atributos {#id1827JA002YK}

AEM Guías de la permite crear y asociar fácilmente atributos condicionales utilizando los atributos DITA relevantes. Puede definir atributos condicionales en el nivel global o de carpeta. Las condiciones definidas globalmente son visibles en todos los proyectos y las condiciones a nivel de carpeta solo son visibles en proyectos creados dentro de la carpeta especificada. Los autores de contenido pueden utilizar estos atributos condicionales para condicionar el contenido de sus temas o mapas DITA que crean o utilizan. AEM AEM Para obtener más información acerca de cómo crear atributos condicionales en la aplicación de las guías de uso de la, consulte la sección sobre la configuración de atributos condicionales de la variable *Configurar atributos condicionales para perfiles globales o de nivel de carpeta* de la sección Instalación y configuración de las guías de Adobe Experience Manager.

>[!NOTE]
>
>AEM Asegúrese de haber añadido los atributos condicionales en la configuración de y de haber configurado el atributo de forma que se pueda usar el parámetro de configuración de la variable. [Preferencia para la personalización de atributos de perfil](#id1827K0D0OHT) antes de agregar atributos condicionales al contenido.

Realice los siguientes pasos para agregar atributos condicionales al contenido en Oxygen XML Author:

1. Cierre la compra y abra un tema en *AEM Complemento de oxígeno para guías de la*.
1. Seleccione la parte del contenido donde desea aplicar los atributos condicionales.
1. Haga doble clic en el atributo condicional en el panel Atributos del Autor XML de Oxygen.

   ![panel atributos](images/attribute-panel.png){width="300" align="left"}

1. En el **Disponible** en el cuadro de diálogo Editar atributo, seleccione el atributo y haga clic en **Añadir**.

   La siguiente pantalla muestra `audience` atributos.

   ![Cuadro de diálogo Editar atributos](images/edit-attributes.png){width="550" align="left"}

1. Haga clic en **Aceptar**.

   Los atributos se añaden al contenido.


## Solución de problemas comunes {#id188ABC00RY4}

Este tema cubre algunos de los problemas más comunes que podría tener al trabajar con el complemento, junto con sus soluciones.

### AEM Falta el panel Guías de {#id192BH200ZAX}

**Problema** AEM - Si no ve el panel Guías de la en Oxygen XML Author, pruebe las siguientes soluciones:

Solución 1:

1. En Oxygen XML Author, habilite el complemento.

   Clic **Opciones** \> **Preferencias** \> **Complementos** y seleccione **Complemento de oxígeno para Adobe Experience Manager Guides.**

1. Reinicie Oxygen XML Author.


Solución 2:

1. AEM AEM Si sigue sin poder ver el panel Guías de, habilite la ventana Guías de.

   En Oxygen XML Author, haga clic en **Ventana** \> **Mostrar vista** \> **AEM Guías de**.

Solución 3:

1. Desinstale y vuelva a instalar el complemento Oxygen para Adobe Experience Manager Guides.

   - En Windows, desinstale el complemento de **Agregar o quitar programas** lista. A continuación, vuelva a instalar el complemento.

   - En Mac, acceda a la carpeta aem-connector-x.x en la carpeta de complementos de Oxygen XML Author y muévala a **Papelera**. A continuación, vacíe el **Papelera** carpeta.


### Configurar el puerto para la transformación DITA-OT

**Problema** : Cuando se ejecuta cualquier transformación DITA-OT en archivos procesados por el complemento, la transformación falla con el siguiente error:

![Error de error de transformación DITA-OT](images/proxy-server-path-error-new.png){width="800" align="left"}

**Solución** - Este problema se ha solucionado añadiendo un servidor proxy entre DITA-OT y el complemento. Este servidor proxy procesa y comparte todos los archivos solicitados por DITA-OT para las transformaciones. El puerto predeterminado en el que se ha configurado este servidor es: `5972`. Si utiliza este puerto para algún otro servidor, puede especificar un puerto diferente para el servidor proxy.

Realice los siguientes pasos para cambiar el puerto predeterminado del servidor proxy:

1. Vaya al directorio de inicio de \(user\).
1. Cree un archivo llamado aem\_connector\_proxy.
1. Abra el archivo en cualquier editor de texto y agregue un número de puerto disponible en la primera línea del archivo.
1. Guarde y cierre el archivo.
1. Reinicie Oxygen XML Author y ejecute la transformación DITA-OT.


### AEM El panel Guías no busca la ubicación del archivo abierto

AEM Problema: Cuando elige abrir un archivo para editarlo en Oxygen XML Author desde el servidor de, el archivo se abre para editarlo en Oxygen XML Author. AEM Sin embargo, el panel Guías de la aplicación no muestra la ubicación del archivo en el árbol de navegación.

Solución: este problema se ha observado en escenarios en los que la ruta de archivo contiene /content/dam dos veces. AEM De forma predeterminada, todos los recursos de los recursos de se almacenan en la carpeta /content/dam. Si carga o crea una estructura de carpetas que también contiene /content/dam, se observa este problema. Puede realizar todas las operaciones normales con estos archivos, pero su ubicación en el árbol de navegación no se muestra de forma predeterminada. Para acceder a dicho archivo en el árbol de navegación, debe examinar manualmente la ubicación del archivo. Tenga en cuenta que en el árbol de navegación, la ruta duplicada /content/dam se reemplaza por /content/assets.

### Configurar el registro

AEM Problema: De forma predeterminada, el complemento de oxígeno para guías de no genera ningún registro, lo que dificulta la depuración de cualquier escenario de error.

Solución: realice los siguientes pasos para configurar los registradores de Xygen y JxBrowser:

1. Cerrar Oxygen XML Author

1. Cree un archivo llamado `logback.xml` con el siguiente contenido:

   ```xml
   <configuration>
       <appender name="R2" class="ch.qos.logback.core.rolling.RollingFileAppender">
           <file>${user.home}/Desktop/oxygenLog/oxygen.log</file>
           <rollingPolicy class="ch.qos.logback.core.rolling.FixedWindowRollingPolicy">
               <fileNamePattern>${user.home}/Desktop/oxygenLog/oxygen%i.log.gz</fileNamePattern>
               <minIndex>1</minIndex>
               <maxIndex>20</maxIndex>
           </rollingPolicy>
           <triggeringPolicy class="ch.qos.logback.core.rolling.SizeBasedTriggeringPolicy">
               <maxFileSize>100MB</maxFileSize>
           </triggeringPolicy>
           <encoder>
               <pattern>%r %marker %p [ %t ] %c - %m%n</pattern>
           </encoder>
       </appender> 
   
       <root level="debug">
           <appender-ref ref="R2" />
       </root>
   </configuration>   
   ```

1. Guarde el archivo en. `Oxygen Author 25` directorio. (Por ejemplo, la ruta sería: `C:\Program Files\Oxygen XML Author 25\logback.xml`)

1. Cierre el archivo. Esto habilitará los registros de oxígeno, que estarán disponibles en la ruta: `${user.home}/Desktop/oxygenLog/oxygen.log`
1. Abra el `oxygenAuthor.bat` en un editor de texto.
1. Configure los registros relacionados con JxBrowser añadiendo el parámetro
   `-Denable.aem.jx.log=true`. Esto habilita los registros relacionados con JxBrowser, que puede ver en la ruta: `${user.home}\AppData\Local\Temp\Oxygen_Plugin_Javax_Log.log`:




   ```java
   SET OXYGEN_JAVA=java.exe
   if exist "%JAVA_HOME%\bin\java.exe" set OXYGEN_JAVA="%JAVA_HOME%\bin\java.exe"
   if exist "%~dp0\jre\bin\java.exe" SET OXYGEN_JAVA="%~dp0\jre\bin\java.exe"
   rem Set environment variables
   call "%~dp0\env.bat"
   %OXYGEN_JAVA% -XX:-OmitStackTraceInFastThrow -XX:SoftRefLRUPolicyMSPerMB=10 -Djdk.module.illegalAccess=permit -Djava.ipc.external=true 
   -Denable.aem.jx.log=true -Dsun.java2d.noddraw=true -Dsun.awt.nopixfmt=true -Dsun.java2d.dpiaware=true -Dsun.io.useCanonCaches=true -Dsun.io.useCanonPrefixCache=true 
   -Dsun.awt.keepWorkingSetOnMinimize=true -Dcom.oxygenxml.app.descriptor=ro.sync.exml.AuthorFrameDescriptor
    -Dcom.oxygenxml.ApplicationDataFolder="%APPDATA%" -cp %CP% ro.sync.exml.Oxygen %*
   ```


Con los pasos anteriores, los registros se habilitarán y puede utilizarlos para depurar los problemas.
