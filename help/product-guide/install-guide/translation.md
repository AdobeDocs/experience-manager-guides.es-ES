---
title: Traducción de contenido en AEM Guides
description: Aprenda a traducir contenido
exl-id: 0d3a909c-3499-4ef4-b033-02e412dae959
feature: Translation
role: Admin
level: Experienced
source-git-commit: bc2348ae3342addf9ab05a3e3898fa485dba9bcf
workflow-type: tm+mt
source-wordcount: '707'
ht-degree: 9%

---

# Traducir contenido {#id181GB0400UI}

Automatice la traducción del contenido de la página, los activos y el contenido generado por el usuario para crear y mantener sitios web multilingües. Para automatizar los flujos de trabajo de traducción, se integran los proveedores de servicios de traducción con AEM y se crean proyectos para traducir contenido a varios idiomas. AEM admite flujos de trabajo de traducción automática y humana.

- Traducción humana: el contenido se envía a su proveedor de traducción y lo traducen traductores profesionales. Cuando se completa, el contenido traducido se devuelve e importa en AEM. AEM AEM Cuando el proveedor de traducción está integrado con la traducción, el contenido se intercambia automáticamente entre el proveedor de traducción y el proveedor de traducción, lo que hace que el contenido se intercambie de forma automática entre el proveedor de traducción y el proveedor de traducción

- Traducción automática: el servicio de traducción automática traduce inmediatamente su contenido


La traducción de contenido implica los siguientes pasos:

1. AEM Conéctese con su [proveedor de servicios de traducción](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-tic.html#ConnectingtoaTranslationServiceProvider) y cree [configuraciones del marco de trabajo de integración de traducción](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-tic.html#CreatingaTranslationIntegrationConfiguration).

1. Asocie las páginas del maestro de idioma con el [servicio de traducción y las configuraciones del marco de trabajo](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-tic.html#ConfiguringPagesforTranslation).

1. Identifique el tipo de [contenido para traducir](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-rules.html).

1. [Preparar el contenido para su traducción](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-prep.html) creando el maestro de idioma y las páginas raíz de las copias de idioma.

1. Cree [proyectos de traducción](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-manage.html) para recopilar el contenido que se va a traducir y para preparar el proceso de traducción.

1. Use los proyectos de traducción para [administrar el proceso de traducción de contenido](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-manage.html).


AEM AEM Cuando el proveedor de servicios de traducción no proporciona un conector para la integración con la traducción, a continuación, admite la exportación manual y la importación de contenido traducido en formato XML, de forma que se admita el uso de la.

>[!TIP]
>
> Consulte la sección *Traducción* s en la guía de prácticas recomendadas para conocer las prácticas recomendadas sobre la traducción de contenido.

## Configuración de la ficha Traducción en el tablero de mandos de asignación DITA

La opción Ocultar ficha de traducción no está activada de forma predeterminada y debe activarla desde configMgr. Para ocultar la ficha Traducción en el tablero de mandos de asignación DITA, realice los siguientes pasos:

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y haga clic en el paquete **com.adobe.fmdita.config.ConfigManager**.

1. Seleccione la opción **Ocultar ficha de traducción** para ocultar la ficha de traducción en el panel de asignaciones.

   >[!NOTE]
   >
   > Esta propiedad está desactivada de forma predeterminada y la pestaña Traducción está disponible en el panel de mapas.

1. Haga clic en **Guardar**.

## Configurar flujo de trabajo de traducción basado en componentes

Si el conector del proveedor de traducción no admite contenido DITA, es necesario habilitar el flujo de trabajo de traducción basado en componentes. Una vez activado, el contenido traducible se envía como metadatos de recursos. Sin embargo, el conector debe admitir la traducción de metadatos de recursos para que este flujo de trabajo funcione.

En función del flujo de trabajo de traducción utilizado en la configuración, la opción del flujo de trabajo de traducción basado en componentes debe configurarse de la siguiente manera:

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y haga clic en el paquete **com.adobe.fmdita.config.ConfigManager**.

1. Configure la opción **Flujo de trabajo de traducción DITA basado en componentes** según su configuración:

   - Si usa traducción humana, *deshabilite* la opción **Flujo de trabajo de traducción basado en componentes**.

   - Si está usando traducción automática, *Habilite* la opción **Flujo de trabajo de traducción basado en componentes**.

   >[!NOTE]
   >
   > AEM Si está usando un conector de traducción, asegúrese de que ha configurado el conector tal como se describe en el tema *[Configuración del marco de trabajo de integración de traducción](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-tic.html)* de la documentación de.

1. Haga clic en **Guardar**.

<!---

This was added for 2406 CS IG

## Configure the legacy translation workflow 

It is recommended that you use the latest translation workflow, which provides enhanced performance. However, you can configure the legacy translation workflow if necessary.

Based on the translation workflow used in your setup, provide the following (property) details to configure the legacy translation workflow: the component-based translation workflow option should be configured as follows:

1.  Open the Adobe Experience Manager Web Console Configuration page.

    The default URL to access the configuration page is:

    ! Add the syntax of http as given in previous config

    Note: Configure htttp code as given in previous sample
    

1.  Search for and click on the **com.adobe.fmdita.config.ConfigManager** bundle.



1.  Configure the **Run legacy translation workflow** option as per your setup:

    -   If you use the latest translation workflow, then *Disable* \( `false`\) the **Run legacy translation workflow** option. The latest translation workflow is enabled by default. <br> 

    -   If you use the legacy translation, then *Enable \( `true`\)* the **Run legacy translation workflow** option.

1.  Click **Save**.


--->
>[!IMPORTANT]
>
> Después de configurar las configuraciones de traducción, asegúrese de configurar la configuración de nube adecuada en las carpetas de idioma.

## Configurar el posprocesamiento de las copias de idioma temporales

Al iniciar el flujo de trabajo de traducción, el sistema crea copias de idioma temporales del contenido de origen. Puede elegir habilitar o deshabilitar la operación de posprocesamiento en estos archivos temporales. En la operación posterior al procesamiento, se resuelven las referencias entrantes y salientes de los archivos, se establece el estado del documento y otras operaciones. Si habilita el posprocesamiento en estos archivos temporales, el proceso de traducción podría tardar más tiempo en completarse. Por lo tanto, se recomienda mantener desactivada la opción de posprocesamiento.

De forma predeterminada, la opción posprocesar archivos temporales está desactivada. Puede configurar esta opción realizando los siguientes pasos:

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y haga clic en el paquete **com.adobe.fmdita.config.ConfigManager**.

1. Configure la opción **Post-process language copies** según su configuración:

   - \(*Predeterminado*\) Si no desea ejecutar la operación de posprocesamiento en los archivos temporales, *Deshabilitar* la opción **Post-process language copies**.

   - Si desea ejecutar la operación de posprocesamiento en los archivos temporales, *habilite* la opción **Copias de idioma de procesamiento de Post**.

1. Haga clic en **Guardar**.
