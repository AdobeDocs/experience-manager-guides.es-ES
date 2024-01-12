---
title: Cargar contenido DITA existente
description: Obtenga información sobre cómo cargar contenido DITA existente
exl-id: 1dde8a29-301f-461e-b598-2a8cab61bf3d
feature: Migration
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '1201'
ht-degree: 0%

---

# Cargar contenido DITA existente {#id176FF000JUI}

AEM Lo más probable es que tenga un repositorio de contenido DITA existente que le gustaría utilizar con guías de. AEM Para dicho contenido existente, puede utilizar cualquiera de los siguientes métodos para cargar el contenido en lote en el repositorio de.

## Uso de una herramienta WebDAV

Si está creando los temas y mapas en cualquier otro editor DITA, puede utilizar cualquier herramienta WebDAV para cargar los archivos. El procedimiento que se describe en esta sección utiliza WinSCP como herramienta WebDAV para cargar contenido.

Siga estos pasos para usar WinSCP para cargar archivos:

1. Descargue e instale WinSCP en su equipo.

1. Inicie la aplicación WinSCP.

   Aparecerá el cuadro de diálogo Inicio de sesión.

1. En el cuadro de diálogo Inicio de sesión, especifique una configuración de Nuevo sitio eligiendo WebDAV como **Protocolo de archivo** y proporcionar otros detalles de conexión, como:

   - AEM la URL donde se aloja el servidor de la,

   - el número de puerto \(el valor predeterminado es 4502\), y

   - AEM Utilice el nombre de usuario y la contraseña para acceder a su servidor de.

1. Haga clic en **Login**.

   Si la conexión se realiza correctamente, verá el contenido de AEM Assets en la interfaz de usuario de WinSCP. Puede examinar, crear, actualizar o eliminar fácilmente el contenido mediante el explorador de archivos WinSCP.


## Usar FrameMaker

Adobe FrameMaker AEM incluye un potente conector de que permite cargar fácilmente los documentos DITA y de FrameMaker AEM \(.book y .fm\) existentes en la interfaz de usuario de. Puede utilizar varias funcionalidades de carga de archivos, como cargar un solo archivo o cargar una carpeta completa con o sin dependencias \(como referencias de contenido, referencias cruzadas y gráficos\).

Siga estos pasos para utilizar el conector de de FrameMaker AEM para cargar contenido:

1. Iniciar FrameMaker.

1. Abra el **Connection Manager** diálogo.

   ![](assets/fm-aem-connector.png){width="550" align="left"}

1. AEM Introduzca los siguientes detalles para conectarse al repositorio de la:

   - **Nombre** AEM : introduzca un nombre descriptivo para identificar la conexión con el servidor de la.
   - **Servidor** AEM : introduzca la dirección URL y el número de puerto del servidor de.

   - **Nombre de usuario**/**Contraseña** AEM : introduzca el nombre de usuario y la contraseña para acceder al servidor de la.

1. Clic **Connect**.

   AEM Una vez que la conexión se haya establecido correctamente, los recursos del repositorio de se mostrarán en la ventana Administrador de repositorios.

   ![](assets/fm-repo-manager.png){width="550" align="left"}

   Hacer clic con el botón derecho en cualquier archivo o carpeta le permite realizar operaciones relacionadas. Por ejemplo, si hace clic con el botón derecho en una carpeta, obtiene opciones para cargar un archivo, cargar archivo con dependencias, cargar una carpeta completa, etc.


## Configurar patrón de nombre de archivo UUID

Al importar contenido, no es necesario que los nombres de archivo estén basados en el UUID. En un sistema que utiliza nombres de archivo basados en UUID, es obligatorio que se haga referencia a todos los archivos utilizando sus UUID en lugar de sus nombres de archivo originales. Si un archivo importado no tiene nombres de archivo basados en UUID, puede configurar el sistema para agregar un UUID a su propiedad de archivo. A continuación, este UUID se utiliza para hacer referencia a estos archivos donde UUID no se utiliza para nombrar los archivos.

Realice los siguientes pasos para comprobar los nombres de archivo con un patrón UUID y asignar UUID a archivos que no tienen un UUID asignado:

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y haga clic en *com.adobe.fmdita.config.ConfigManager* paquete.

1. En el **Patrones de nombre de archivo UUID** , especifique un patrón para comprobar los nombres de los archivos importados.

   Si un archivo no sigue el patrón especificado, se agrega un UUID a la propiedad del archivo y todas las referencias al archivo se actualizan con el UUID asignado al archivo.

1. Haga clic en **Guardar**.


## Carga de contenido con UUID mediante una herramienta WebDav {#id201MI0I04Y4}

Puede utilizar cualquiera de los siguientes métodos para cargar el contenido con UUID:

- Arrastre y suelte contenido desde el sistema local.
- Utilice el **Crear** \> **Archivos** AEM flujo de trabajo desde la interfaz de usuario de Assets.
- Utilice una herramienta como WinSCP.

Si utiliza una herramienta como WinSCP, puede definir la acción que se va a realizar en un archivo duplicado estableciendo el valor **Mover el archivo antiguo con el mismo UUID a la nueva carpeta** en configMgr. AEM Esta opción define qué acción se realiza en un archivo que está disponible en alguna otra ubicación del repositorio de. Esta configuración está disponible en la variable *com.adobe.fmdita.config.ConfigManager* paquete en configMgr.

De forma predeterminada, la variable **Mover el archivo antiguo con el mismo UUID a la nueva carpeta** La opción está activada. Esto implica que cuando el archivo que se está cargando está presente en alguna otra carpeta del repositorio, el archivo existente se mueve a la ubicación actual y se sobrescribe con el archivo que se está cargando. Si no selecciona esta opción, el archivo se sobrescribe en su ubicación existente.

**Notas adicionales sobre cómo trabajar con archivos basados en UUID**:

AEM Se deben tener en cuenta los siguientes puntos al mover o copiar contenido dentro del repositorio de:

- Al copiar uno o más archivos de una ubicación a otra, se genera un nuevo UUID para los archivos que no tienen ningún UUID. Este UUID se agrega a los metadatos del archivo.

- Si un archivo tiene un conflicto o está duplicado, se generará un nombre de archivo único para el nuevo archivo que se está copiando o moviendo.

- Dos archivos no pueden tener el mismo UUID. Se asigna un UUID único a todos los archivos nuevos.


AEM Se deben tener en cuenta los siguientes puntos al mover o copiar contenido del sistema local al repositorio de:

- Si dos usuarios diferentes están cargando un archivo al mismo tiempo, el archivo que se procese más adelante sobrescribirá el archivo anterior. Sin embargo, esta práctica es poco frecuente y debe evitarse.

- AEM Cuando extraiga contenido del repositorio de y realice cambios en el sistema local, asegúrese de que el nombre del archivo no cambie en el momento de cargarlo.


## Usar comandos curl

También puede utilizar comandos curl para crear una carpeta en DAM, cargar archivos y agregar metadatos al contenido cargado.

**Crear una carpeta**

AEM Ejecute el siguiente comando para crear una carpeta en el repositorio de:

```curl
curl --user <username>:<password> --data jcr:primaryType=sling:Folder "<server folder path>"
```

Especifique los siguientes parámetros para crear una carpeta:

- `<username>:<passowrd>`AEM : especifique el nombre de usuario y la contraseña para acceder al repositorio de. Este usuario debe tener los privilegios de creación de carpetas.

- `jcr:primaryType=sling:Folder`: especifique este parámetro *como está* para crear un recurso de tipo folder.

- `<server folder path>`AEM : Ruta de la carpeta completa que incluye el nombre de la nueva carpeta que desea crear en el repositorio de. Por ejemplo, si especifica la ruta como `http://192.168.1.1:4502/content/dam/projects/AEM-Guides`, luego la carpeta `AEM-Guides` se crea dentro de `projects` en DAM.


**Cargar un archivo**

AEM Ejecute el siguiente comando para cargar un archivo en el repositorio de:

```curl
curl --user <username>:<password> -T "<local file path>" "<server folder path>"
```

Especifique los siguientes parámetros para cargar un archivo:

- `<username>:<passowrd>`AEM : especifique el nombre de usuario y la contraseña para acceder al repositorio de. Este usuario debe tener privilegios de escritura en `server folder path`.

- ``local file path``: Ruta de archivo completa en el sistema local que desea cargar.

- `<server folder path>`AEM : Ruta de carpeta completa en el servidor en el que desea cargar el archivo.


**Añadir metadatos**

Ejecute el siguiente comando para agregar metadatos a un archivo:

```curl
curl --user <username>:<password> -F<attribute name>=<value> <metadata node path>
```

Especifique los siguientes parámetros para agregar información de metadatos:

- `<username>:<passowrd>`AEM : especifique el nombre de usuario y la contraseña para acceder al repositorio de. Este usuario debe tener privilegios de escritura en ``metadata node path``.

- ``-F<attribute name>=<value>``: La `<attribute name>` es el nombre del atributo de metadatos, como `audience` y el `<value>` podría ser `internal`. Puede especificar varios pares de nombre-valor de atributo separados por espacio.

- `<metadata node path>`: Ruta de carpeta completa que incluye el nombre del archivo y su nodo de metadatos. Por ejemplo, si especifica la ruta como `http://192.168.1.1:4502/content/dam/projects/AEM-Guides/intro.xml/jcr:content/metadata`, la información de metadatos especificada se establece en `intro.xml` archivo.


**Tema principal:**[ Migrar contenido existente](migrate-content.md)
