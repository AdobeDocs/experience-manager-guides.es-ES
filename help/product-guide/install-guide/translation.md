---
title: AEM Traducción de contenido en guías de
description: Aprenda a traducir contenido
exl-id: 0d3a909c-3499-4ef4-b033-02e412dae959
feature: Translation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '707'
ht-degree: 9%

---

# Traducir contenido {#id181GB0400UI}

Automatice la traducción del contenido de la página, los activos y el contenido generado por el usuario para crear y mantener sitios web multilingües. Para automatizar los flujos de trabajo de traducción, se integran los proveedores de servicios de traducción con AEM y se crean proyectos para traducir contenido a varios idiomas. AEM admite flujos de trabajo de traducción automática y humana.

- Traducción humana: el contenido se envía a su proveedor de traducción y lo traducen traductores profesionales. Cuando se completa, el contenido traducido se devuelve e importa en AEM. AEM AEM Cuando el proveedor de traducción está integrado con la traducción, el contenido se intercambia automáticamente entre el proveedor de traducción y el proveedor de traducción, lo que hace que el contenido se intercambie de forma automática entre el proveedor de traducción y el proveedor de traducción

- Traducción automática: el servicio de traducción automática traduce inmediatamente su contenido


La traducción de contenido implica los siguientes pasos:

1. AEM Conéctese con su [proveedor de servicios de traducción](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-tic.html#ConnectingtoaTranslationServiceProvider) y crear [configuraciones del marco de integración de traducciones](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-tic.html#CreatingaTranslationIntegrationConfiguration).

1. Asocie las páginas del maestro de idioma con el [configuraciones del servicio de traducción y del marco de trabajo](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-tic.html#ConfiguringPagesforTranslation).

1. Identificar el tipo de [contenido para traducir](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-rules.html).

1. [Preparar el contenido para su traducción](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-prep.html) creando el maestro de idioma y las páginas raíz de las copias de idioma.

1. Crear [proyectos de traducción](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-manage.html) para recopilar el contenido que se va a traducir y preparar el proceso de traducción.

1. Utilice los proyectos de traducción para lo siguiente [administrar la traducción de contenido](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-manage.html) proceso.


AEM AEM Cuando el proveedor de servicios de traducción no proporciona un conector para la integración con la traducción, a continuación, admite la exportación manual y la importación de contenido traducido en formato XML, de forma que se admita el uso de la.

>[!TIP]
>
> Consulte la *Traducción* s sección de la Guía de prácticas recomendadas para prácticas recomendadas de traducción de contenido.

## Configuración de la ficha Traducción en el tablero de mandos de asignación DITA

La opción Ocultar ficha de traducción no está activada de forma predeterminada y debe activarla desde configMgr. Para ocultar la ficha Traducción en el tablero de mandos de asignación DITA, realice los siguientes pasos:

1. Abra la página Configuración de la consola web de Adobe Experience Manager.

   La URL predeterminada para acceder a la página de configuración es:

   ```http
   http://<server name>:<port>/system/console/configMgr
   ```

1. Busque y haga clic en **com.adobe.fmdita.config.ConfigManager** paquete.

1. Seleccione el **Pestaña Ocultar traducción** , para ocultar la pestaña traducción en el panel de mapas.

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

1. Busque y haga clic en **com.adobe.fmdita.config.ConfigManager** paquete.

1. Configure las variables **Flujo de trabajo de traducción DITA basado en componentes** según su configuración:

   - Si utiliza la traducción humana, *Deshabilitar* el **Flujo de trabajo de traducción basado en componentes** opción.

   - Si utiliza la traducción automática, *Activar* el **Flujo de trabajo de traducción basado en componentes** opción.

   >[!NOTE]
   >
   > Si utiliza el conector de traducción, asegúrese de haber configurado el conector como se describe en la sección *[Configuración del marco de trabajo de integración de traducción](https://helpx.adobe.com/experience-manager/6-5/sites/administering/using/tc-tic.html)* AEM tema en la documentación de la.

1. Haga clic en **Guardar**.


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

1. Busque y haga clic en **com.adobe.fmdita.config.ConfigManager** paquete.

1. Configure las variables **Copias de idioma posteriores al procesamiento** según su configuración:

   - \(*Predeterminado*\) Si no desea ejecutar la operación de posprocesamiento en los archivos temporales, *Deshabilitar* el **Copias de idioma posteriores al procesamiento** opción.

   - Si desea ejecutar la operación de posprocesamiento en los archivos temporales, *Activar* el **Copias de idioma posteriores al procesamiento** opción.

1. Haga clic en **Guardar**.
