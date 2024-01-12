---
title: Solución de problemas básica
description: AEM Resuelva los problemas con la solución de problemas básica en las Guías de. Aprenda a ver, copiar y comprobar el archivo de registro en un editor de texto y a resolver los errores de compilación de JSP.
exl-id: 57b88291-b5a3-4931-b3ed-f2b2ce7a463c
feature: Publishing, Troubleshooting
role: User
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '690'
ht-degree: 0%

---

# Solución de problemas básica {#id1821I0Y0G0A}

AEM Al trabajar con Guías de, puede encontrar errores al publicar o abrir el documento. AEM Estos errores pueden producirse en el propio proceso de DITA map, topic o en las guías de la aplicación de la aplicación. En esta sección se proporciona información sobre cómo tener acceso a la información del archivo de registro de generación de resultados y analizarla. Además, si el tema DITA es demasiado grande, es posible que vea el error de compilación de JSP. Esta sección también proporciona información sobre cómo resolver el error de compilación de JSP.

## Ver y comprobar el archivo de registro {#id1822G0P0CHS}

Realice los siguientes pasos para ver y comprobar el archivo de registro de generación de resultados:

1. Una vez iniciado el proceso de generación de resultados, haga clic en **Salidas** en la consola de mapas DITA.

   El **General** de la columna **Salidas generadas** muestra los iconos para proporcionar una pista visual sobre el éxito o el fracaso de la generación de resultados.

   ![](images/output-general-settings.png){width="300" align="left"}

   En la captura de pantalla anterior, el primer y el tercer iconos muestran la generación de resultados fallida. El segundo icono muestra una generación de salida correcta pero con mensajes. El último es una generación de salida correcta sin ningún mensaje.

1. Haga clic en el vínculo en la **Generado el** una vez completado el trabajo.

   El archivo de registro se abre en una nueva pestaña.

   ![](images/log-file.png){width="800" align="left"}

1. Aplique los siguientes filtros para resaltar el texto en el archivo de registro:
   - Grave: resalta los errores graves del archivo de registro con color rosa.
   - Error: resalta los errores del archivo de registro con color naranja.
   - Advertencia: resalta las advertencias del archivo de registro con color morado.
   - Información: resalta los mensajes de información del archivo de registro con color azul.
   - Excepción: Resalta las excepciones del archivo de registro con color amarillo.
1. Utilice los botones de navegación arriba y abajo para saltar al texto resaltado en el archivo de registro.

   También puede desplazarse por el archivo de registro y comprobar los mensajes.


## Copie y compruebe el archivo de registro en un editor de texto

Realice los siguientes pasos para copiar y comprobar el archivo de registro de generación de resultados en un editor de texto:

1. Una vez iniciado el proceso de generación de resultados, haga clic en **Salidas** en la consola de mapas DITA.

1. Haga clic en el vínculo en la **Generado el** una vez completado el trabajo.

   El archivo de registro se abre en una nueva pestaña.

1. Clic **Copiar registro** botón. El archivo de registro se copia en el portapapeles.
1. Abra un editor de texto y pegue el archivo de registro en el editor.

1. Desplácese por el archivo de registro y compruebe si hay mensajes.

   AEM La siguiente información le ayudará a determinar si hay algún error en el proceso de archivo o guías de la DITA o en el proceso de las guías de la:

   - *Error relacionado con el archivo de mapa DITA*: En caso de que se encuentre un error en el fichero de mapa DITA o en cualquier otro fichero contenido en el mapa DITA, el fichero de registro contendrá una cadena, &quot;ERROR DE COMPILACIÓN&quot;. Puede comprobar la información proporcionada en el archivo de registro para localizar el archivo erróneo y solucionar el problema.

   En el siguiente fragmento de archivo de registro de ejemplo, puede ver la variable `BUILD FAILED` junto con el motivo del error.

   ![](images/dita-error-in-log-file.png){width="650" align="left"}

   - *AEM Error relacionado con las guías de la* AEM : el otro tipo de error que se puede identificar en el archivo de registro está relacionado con el propio proceso de las Guías de la aplicación de la aplicación de la guía de usuario. AEM En este caso, el fichero de mapa DITA se analiza correctamente, pero el proceso de generación de salida falla debido a algún error interno en las Guías de la. Para este tipo de errores, debe buscar ayuda del equipo de asistencia técnica.

   En el siguiente fragmento de archivo de registro de ejemplo, puede ver la variable `BUILD SUCCESSFUL` Mensaje, seguido de otro error técnico.

   ![](images/process-error-in-log-file.png){width="650" align="left"}


## Resolver error de compilación de JSP

Si el tema DITA es demasiado grande, es posible que vea el error de compilación de JSP \(`org.apache.sling.api.request.TooManyCallsException`\) en el explorador. Este error puede aparecer al abrir un tema para editarlo, revisarlo o publicarlo.

Siga estos pasos para resolver este problema:

1. En Navegación global, seleccione Herramientas y elija Operaciones \> Consola web.

   Aparecerá la página Configuración de la consola web de Adobe Experience Manager.

1. Busque y haga clic en *Servlet principal de Apache Sling* componente.

   Se muestran las opciones configurables para el servlet principal de Apache Sling.

1. Aumente el valor del *Número de llamadas por solicitud* según sus necesidades.


**Tema principal:**[ Generación de salida](generate-output.md)
