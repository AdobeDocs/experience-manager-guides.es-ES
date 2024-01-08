---
title: Agregar nuevo botón procesable personalizado en la barra de herramientas del editor web
description: Aprenda a añadir un nuevo botón personalizado en la barra de herramientas del editor web y a llamar a JavaScript para utilizarlo de forma personalizada.
exl-id: 34999db6-027a-4d93-944f-b285b4a44288
source-git-commit: eb3fe92d36bc58a11e47f786a10d5938e2ed0184
workflow-type: tm+mt
source-wordcount: '528'
ht-degree: 0%

---

# Agregar nuevo botón procesable personalizado en la barra de herramientas del editor web

En este artículo aprenderemos a añadir un nuevo botón personalizado en la barra de herramientas del editor web y a llamar a javascript para realizar la operación personalizada que desee.

Añadir un botón procesable al editor web implica los siguientes pasos:
- Añadir el botón en la *ui_config.json* en la posición donde sea necesario
- Registrar el evento de botón al hacer clic en el editor web para que el usuario realice una acción cuando haga clic en él


## Implementación de mediante un ejemplo

Comprendamos esto con un ejemplo en el que un autor desea añadir una referencia jira a una sección de prólogo de tema. La sección de prólogo con el identificador de referencia jira incrustado puede tener el siguiente aspecto:

![Sección de prólogo con referencia de ID de JIRA](../../../assets/authoring/webeditor-add-customtoolbarbutton-prolog-sample.png)

El elemento &quot;change-request-id&quot; que contiene el ID de JIRA debe recuperarse de la API (por ejemplo, en función de una consulta JIRA específica que se representa mediante la aplicación). Cuando el usuario está creando la sección de prólogo, debe poder hacer clic en un botón e insertar un ID de referencia de jira desde la barra de herramientas del editor web, algo así como:

![Sección de prólogo: añadir referencia JIRA](../../../assets/authoring/webeditor-add-customtoolbarbutton-prolog-insertjirareference.png)

Y cuando el usuario hace clic en el botón, debe mostrar un cuadro de diálogo que debe extraer las posibles opciones y permitir al usuario seleccionar el ID de JIRA deseado, algo así como:

![Cuadro de diálogo Agregar ID de JIRA de la sección Prólogo](../../../assets/authoring/webeditor-add-customtoolbarbutton-prolog-insertjirareference-dialog.png)

que debería añadir &quot;change-request-id&quot; al prólogo:

![Sección de prólogo con referencia de ID de JIRA](../../../assets/authoring/webeditor-add-customtoolbarbutton-prolog-sample.png)



## Implementación de esto


### Añada el botón en el editor web configurándolo en *ui_config.json*

Utilice los perfiles de carpeta para comprobar la *ui_config.json* en la pestaña &quot;Configuración del editor XML&quot; y añada el botón de configuración JSON a la sección deseada del grupo &quot;barra de herramientas&quot;

```
{
    "on-click":"insertJIRARef",
    "icon":"linkCheck",
    "variant":"quiet",
    "type":"button",
    "title":"Insert JIRA Reference"
}
```

[utilice este vínculo para obtener más información sobre el perfil de carpeta y la configuración de ui_config.json](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/videos/advanced-user-guide/editor-configuration.html?lang=en)


### Controlar el evento en el que se hace clic para el botón nuevo

    NOTA: Los pasos que se mencionan a continuación están disponibles como paquete adjunto en esta publicación


- Después de guardar el perfil de carpeta, cree una &quot;cq:ClientLibraryFolder&quot; en un directorio de proyecto (puede estar en */apps*) y agregue propiedades como se muestra en la captura de pantalla siguiente:
  ![Configuración de la biblioteca de cliente para el editor web](../../../assets/authoring/webeditor-add-customtoolbarbutton-clientlibrarysettings.png)

```
This example uses "coralui3" library to show a dialog as it is used in the Javascript sample we presented.
You may use different library of your choice.
```

- En esta carpeta de biblioteca de cliente, cree dos archivos como se menciona a continuación:
   - *overrides.js*: que tendrá el código javascript para gestionar el evento en el que se hace clic para &quot;insertJIRARef&quot; (utilice el paquete adjunto para obtener el contenido de este javascript)
   - *js.txt*: que incluirá &quot;overrides.js&quot; para habilitar este javascript

- Guarde los cambios y estará listo para probarlos.


### Pruebas

- Abrir editor web
- En las preferencias de usuario, elija el perfil de carpeta en el que agregó el personalizado *ui_config.json*. Si lo ha agregado al perfil Global, probablemente ya esté utilizando.
- Al abrir un tema, notará que la barra de herramientas tiene un nuevo botón &quot;Insertar referencia Jira&quot;
- A continuación, puede añadir la sección de prólogo como se indica a continuación al tema y probar haciendo clic en el botón &quot;Insertar referencia Jira&quot; dentro del elemento de prólogo &quot;change-request-reference&quot;

```
<prolog>
    <change-historylist>
        <change-item>
            <change-request-reference>
            </change-request-reference>
            <change-completed></change-completed>
            <change-summary></change-summary>
        </change-item>
    </change-historylist>
</prolog>
```

Consulte la siguiente captura de pantalla para saber cómo se verá:

![Probar botón nuevo](../../../assets/authoring/webeditor-add-customtoolbarbutton-testing.png)


### Archivos adjuntos

- Paquete clientlibs de muestra que instalará la biblioteca de cliente del editor web con código javascript para la acción del botón de la barra de herramientas: [descargar mediante este vínculo](../../../assets/authoring/webeditor-addbuttonontoolbar-insertjira-clientlib.zip)
- Muestra *ui_config.json* que puede cargar en un perfil de carpeta: [descargar ejemplo de ui_config.json](../../../assets/authoring/sample_ui_config_Guides4.2-InsertJiraReference.json)

```
Please note this is compatible to AEM 6.5 and AEM Guides version 4.2.
If you are using a different version please add the toolbar button to the ui_config.json manually.
```
