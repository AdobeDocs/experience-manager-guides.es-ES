---
title: Publicación con FrameMaker Publishing Server (FMPS) en AEM Guides
description: Publicación con FMPS mediante AEM Guides
exl-id: 05d4d876-f83b-473c-bf31-14d6565e80e2
feature: AEM Guides FrameMaker Publishing Server
author: Pulkit Nagpal(punagpal)
role: User, Admin
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '623'
ht-degree: 0%

---

# Publicación con FrameMaker Publishing Server (FMPS) en AEM Guides

La integración de AEM Guides con FrameMaker Publishing Server podría ser su solución si busca una publicación automatizada de alta calidad.\
Este artículo le ayuda a configurar y ejecutar FMPS con AEM Guides.

## Compatibilidad de FMPS con AEM Guides

- Compatibilidad con AEM Guides 4.1: [Matriz de compatibilidad 4.1](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/release-info/release-notes/on-prem-release-notes/release-notes-4.1.html?lang=en/#compatibility-matrix)
- Compatibilidad con AEM Guides 4.0: [Matriz de compatibilidad 4.0](https://helpx.adobe.com/xml-documentation-for-experience-manager/release-note/release-notes-xml-documentation-solution-4-0.html/#Compatibility%20matrix)
- Última versión: [Información de la versión más reciente](https://experienceleague.adobe.com/docs/experience-manager-guides-learn/tutorials/release-info/latest-release-info.html?lang=en)

## Instalación

Consulte a continuación la instalación y configuración de AEM Guides y FMPS

### Guías de AEM

Referencia de instalación y configuración: [4.1 instalación y configuraciones](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-1-2/Adobe-Experience-Manager-Guides_Installation-Configuration-Guide_EN.pdf)

### FMPS

Para la instalación de FMPS, puede consultar [vínculo de YouTube](https://www.youtube.com/watch?v=2deelyM5VA8&t) o [instalación y configuración de FMPS](https://help.adobe.com/en_US/framemaker/server/index.html#t=fmps-user-guide%2Finstall_config_fmps.html%23install_config_fmps&rhtocid=_2)

## Configuraciones requeridas

FrameMaker Publishing Server (FMPS) puede utilizarse para generar contenido DITA. FMPS admite una amplia gama de formatos de salida. Modifique las siguientes propiedades del &quot;paquete com.adobe.fmdita.config.ConfigManager&quot; en la consola web para configurar AEM Guides y utilizar FMPS.

Para abrir la consola web, vaya a la URL Access http://\&lt;server name\>:\&lt;port\>/system/console/configMgr.

**Propiedades de configuración y su descripción** [Instalación y configuración de 4.1](https://helpx.adobe.com/content/dam/help/en/xml-documentation-solution/4-1-2/Adobe-Experience-Manager-Guides_Installation-Configuration-Guide_EN.pdf#page=89)

## Ejecución de la prueba:

Con FMPS, puedes publicar automáticamente **PDF, HTML5** adaptable y **Epub** para tu Assets DITA y FM.

En el menú &quot;Generar PDF con&quot;, seleccione FrameMaker Publishing Server.

El usuario puede proporcionar &quot;settings File(.sts)&quot; y &quot;ditaval&quot;. El filtrado se realiza mediante ditaval en función de las condiciones que proporcione.

- **Archivo de configuración**: Un archivo de configuración de publicación /FMPS de FrameMaker que contiene toda la configuración que FMPS debe respetar al publicar. Por ejemplo, crear resultados con una plantilla personalizada, crear Marcas y sangrados (PDF) y crear PDF con TDC.
- **Ajuste preestablecido de FMPS:** Es una combinación predefinida de ditaval y archivo de configuración. En lugar de proporcionar archivos de ditaval y de configuración independientes, el usuario puede crear previamente un ajuste preestablecido de FMPS que se puede reutilizar para satisfacer las necesidades de publicación.

**Nota:** FMPS usará la configuración predeterminada del sistema para publicar si no elige ninguna de las opciones o el ajuste preestablecido de FMPS.

Si ha elegido el ajuste preestablecido FMPS y también ha proporcionado una configuración personalizada o un archivo ditaval de AEM, se producirá un conflicto. En este caso, el ajuste preestablecido de FMPS tiene prioridad sobre la configuración personalizada o el archivo ditaval.

### Publicación de línea base con FMPS:

Puede publicar las líneas de base ya creadas con FMPS2020.0.2 o una versión superior.

**Archivo de configuración de FMPS de muestra (archivo .sts) para empezar:** [Archivo de configuración de FMPS de muestra](https://acrobat.adobe.com/link/track?uri=urn:aaid:scds:US:ef750752-7a7e-4e51-923e-6b7d9861ed54) (descomprima este archivo)

## Preguntas frecuentes y resolución de problemas:

- ### La publicación de FMPS falla con &quot;Timeout Exception&quot;

>Compruebe y aumente el valor de &quot;FMPS timeout&quot; (segundos) en /system/console/configMgr/com.adobe.fmdita.config.ConfigManager&quot;

- ### No se puede obtener el ajuste preestablecido de FMPS en el menú desplegable

>Asegúrese de que ha creado un ajuste preestablecido de FMPS en el servidor y de que la configuración de conexión es correcta.

- ### Obtengo PDF en blanco al publicar

>Si utiliza UUID, asegúrese de haber marcado &quot;Usar referencia basada en UUID&quot; en las Preferencias de edición de FrameMaker y, a la inversa, en las guías de AEM que no sean UUID.

- ### Mi configuración/ditaval no se aplica en la salida final publicada

>Compruebe que no está eligiendo simultáneamente el ajuste preestablecido FMPS y el archivo de configuración/diaval. Utilice FrameMaker para comprobar manualmente la salida.

- ### La línea de base no se publica desde FMPS

>FMPS2020.0.2 o versiones posteriores son compatibles con la publicación de línea de base.
>Asegúrese de que la línea de base se ha creado correctamente; para comprobarlo, vaya al Panel de mapas— Temas— Descargar  Asigne y elija &quot;Usar línea de base&quot;.

- ### Las tareas de publicación de FMPS tardan más tiempo que otros motores

>Al publicar desde FMPS, el tiempo de encabezado fijo ideal es de aproximadamente 3-4 minutos; si cree que es más largo, consulte con su administrador de FMPS o póngase en contacto con el Soporte técnico de Adobe.

## Otros recursos:

[Formación y soporte de FMPS](https://helpx.adobe.com/support/framemaker-publishing-server.html)

[Aprendizaje y asistencia de AEM Guides](https://helpx.adobe.com/in/support/xml-documentation-for-experience-manager.html)

[Comunidad de FrameMaker y FMPS](https://community.adobe.com/t5/framemaker/ct-p/ct-framemaker?page=1&sort=latest_replies&lang=all&tabid=all)

[Comunidad de AEM Guides](https://experienceleaguecommunities.adobe.com/t5/experience-manager-guides/ct-p/aem-xml-documentation)
