---
title: Cargar contenido DITA existente
description: Obtenga información sobre cómo cargar contenido DITA existente en Experience Manager Guides mediante la herramienta WebDAV y FrameMaker
feature: Migration
role: Admin
level: Experienced
source-git-commit: 834959a6a0e22cd5d2b2c5d0e57ceb6d45c0c666
workflow-type: tm+mt
source-wordcount: '759'
ht-degree: 0%

---

# Cargar contenido DITA existente mediante la herramienta WebDAV y FrameMaker para local

Lo más probable es que tenga un repositorio de contenido DITA existente que desee utilizar con AEM Guides. Para dicho contenido existente, puede utilizar cualquiera de los siguientes métodos para cargar el contenido de forma masiva en el repositorio de AEM.

- [Uso de una herramienta WebDAV](#use-a-webdav-tool)
- [Uso de FrameMaker](#use-framemaker)

## Uso de una herramienta WebDAV

Si está creando los temas y mapas en cualquier otro editor DITA, puede utilizar cualquier herramienta WebDAV para cargar los archivos. El procedimiento que se describe en esta sección utiliza WinSCP como herramienta WebDAV para cargar contenido.

Siga estos pasos para usar WinSCP para cargar archivos:

1. Descargue e instale WinSCP en su equipo.

1. Inicie la aplicación WinSCP.

   Aparecerá el cuadro de diálogo Inicio de sesión.

1. En el cuadro de diálogo Inicio de sesión, especifique una configuración de Nuevo sitio eligiendo WebDAV como **Protocolo de archivos** y proporcionando otros detalles de conexión como:

   - la URL donde está alojado el servidor de AEM,

   - el número de puerto `\(default is 4502\)`, y

   - Utilice el nombre de usuario y la contraseña para acceder a su servidor de AEM.

1. Seleccione **Iniciar sesión**.

   Si la conexión se realiza correctamente, verá el contenido de los AEM Assets en la interfaz de usuario de WinSCP. Puede examinar, crear, actualizar o eliminar fácilmente el contenido mediante el explorador de archivos WinSCP.

## Carga de contenido con UUID mediante una herramienta WebDav {#id201MI0I04Y4}

Puede utilizar cualquiera de los siguientes métodos para cargar el contenido con UUID:

- Arrastre y suelte contenido desde el sistema local.
- Use el flujo de trabajo **Crear** \> **Archivos** de la IU de Assets de AEM.
- Utilice una herramienta como WinSCP.

Si usa una herramienta como WinSCP, puede definir la acción que se realizará en un archivo duplicado estableciendo la opción **Mover archivo antiguo con el mismo UUID a una carpeta nueva** en configMgr. Esta opción define qué acción se realiza en un archivo que está disponible en alguna otra ubicación del repositorio de AEM. Esta opción está disponible en el paquete `*com.adobe.fmdita.config.ConfigManager*` de configMgr.

De manera predeterminada, la opción **Mover el archivo antiguo con el mismo UUID a la carpeta nueva** está activada. Esto implica que cuando el archivo que se está cargando está presente en alguna otra carpeta del repositorio, el archivo existente se mueve a la ubicación actual y se sobrescribe con el archivo que se está cargando. Si no selecciona esta opción, el archivo se sobrescribe en su ubicación existente.

**Notas adicionales sobre cómo trabajar con archivos basados en UUID**:

Los siguientes puntos deben tenerse en cuenta al mover o copiar contenido dentro del repositorio de AEM:

- Al copiar uno o más archivos de una ubicación a otra, se genera un nuevo UUID para los archivos que no tienen ningún UUID. Este UUID se agrega a los metadatos del archivo.

- Si un archivo tiene un conflicto o está duplicado, se generará un nombre de archivo único para el nuevo archivo que se está copiando o moviendo.

- Dos archivos no pueden tener el mismo UUID. Se asigna un UUID único a todos los archivos nuevos.


Los siguientes puntos deben tenerse en cuenta al mover o copiar contenido del sistema local al repositorio de AEM:

- Si dos usuarios diferentes están cargando un archivo al mismo tiempo, el archivo que se procese más adelante sobrescribirá el archivo anterior. Sin embargo, esta práctica es poco frecuente y debe evitarse.

- Cuando retire contenido del repositorio de AEM y realice cambios en el sistema local, asegúrese de que el nombre del archivo no cambie en el momento de cargar el archivo.

## Uso de FrameMaker

Adobe FrameMaker incluye un potente conector AEM que le permite cargar fácilmente su DITA existente y otros documentos de FrameMaker `\(.book and .fm\)`en AEM. Puede utilizar varias funcionalidades de carga de archivos, como cargar un solo archivo o cargar una carpeta completa con o sin dependencias \(como referencias de contenido, referencias cruzadas y gráficos\).

Siga estos pasos para utilizar el conector de AEM de FrameMaker para cargar contenido:

1. Inicie FrameMaker.

1. Abra el cuadro de diálogo **Connection Manager**.

   ![](assets/fm-aem-connector.png){width="550" align="left"}

1. Introduzca los siguientes detalles para conectarse al repositorio de AEM:

   - **Nombre**: escriba un nombre descriptivo para identificar la conexión con el servidor de AEM.
   - **Servidor**: Escriba la dirección URL y el número de puerto del servidor de AEM.

   - **Nombre de usuario**/**Contraseña**: Escriba el nombre de usuario y la contraseña para tener acceso al servidor de AEM.

1. Seleccione **Conectar**.

   Una vez establecida correctamente la conexión, Assets del repositorio de AEM se muestra en la ventana Administrador de repositorios.

   ![](assets/fm-repo-manager.png){width="550" align="left"}

   Hacer clic con el botón derecho en cualquier archivo o carpeta le permite realizar operaciones relacionadas. Por ejemplo, si hace clic con el botón derecho en una carpeta, obtiene opciones para cargar un archivo, cargar archivo con dependencias, cargar una carpeta completa, etc.






**Tema principal:**&#x200B;[&#x200B; Migrar contenido existente](migrate-content.md)
