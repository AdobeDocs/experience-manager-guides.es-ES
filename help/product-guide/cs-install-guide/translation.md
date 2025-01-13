---
title: Traducir contenido
description: Aprenda a traducir contenido
exl-id: 5af78233-343e-47ba-b60c-b7f4789e2406
feature: Translation
role: Admin
level: Experienced
source-git-commit: ea3083542e955a56c27cd833600370a7962c6b8d
workflow-type: tm+mt
source-wordcount: '773'
ht-degree: 9%

---

# Traducir contenido {#id181GB0400UI}

Automatice la traducción del contenido de la página, los activos y el contenido generado por el usuario para crear y mantener sitios web multilingües. Para automatizar los flujos de trabajo de traducción, se integran los proveedores de servicios de traducción con AEM y se crean proyectos para traducir contenido a varios idiomas. AEM admite flujos de trabajo de traducción automática y humana.

- Traducción humana: el contenido se envía a su proveedor de traducción y lo traducen traductores profesionales. Cuando se completa, el contenido traducido se devuelve e importa en AEM. AEM AEM Cuando el proveedor de traducción está integrado con la traducción, el contenido se intercambia automáticamente entre el proveedor de traducción y el proveedor de traducción, lo que hace que el contenido se intercambie de forma automática entre el proveedor de traducción y el proveedor de traducción

- Traducción automática: el servicio de traducción automática traduce inmediatamente su contenido


La traducción de contenido implica los siguientes pasos:

1. AEM Conéctese con su [proveedor de servicios de traducción](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/integration-framework.html?lang=en) y cree configuraciones del marco de trabajo de integración de traducciones.

1. Asocie las páginas del maestro de idioma con el servicio de traducción y las configuraciones del marco de trabajo.

1. Identifique el tipo de [contenido para traducir](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/rules.html?lang=en).

1. [Preparar el contenido para su traducción](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/preparation.html?lang=en) creando el maestro de idioma y las páginas raíz de las copias de idioma.

1. Cree [proyectos de traducción](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/managing-projects.html?lang=en) para recopilar el contenido que se va a traducir y para preparar el proceso de traducción.

1. Use los proyectos de traducción para [administrar el proceso de traducción de contenido](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/managing-projects.html?lang=en).


AEM AEM Cuando el proveedor de servicios de traducción no proporciona un conector para la integración con la traducción, a continuación, admite la exportación manual y la importación de contenido traducido en formato XML, de forma que se admita el uso de la.

>[!TIP]
>
> Consulte la sección *Traducción* en la guía de prácticas recomendadas para conocer las prácticas recomendadas sobre la traducción de contenido.

## Configuración de la ficha Traducción en el tablero de mandos de asignación DITA

Para ocultar la ficha Traducción en el tablero de mandos de asignación DITA, realice los siguientes pasos:

1. Siga las instrucciones indicadas en [Anulaciones de configuración](download-install-additional-config-override.md#) para crear el archivo de configuración.
1. En el archivo de configuración, proporcione los siguientes detalles \(property\) para configurar la pestaña de traducción en el panel de asignaciones:

   | PID | Clave de propiedad | Valor de propiedad |
   |---|------------|--------------|
   | `com.adobe.fmdita.config.ConfigManager` | `tabs.translation` | Booleano \( true/ false\).<br> **Valor predeterminado**: `true` |

   >[!NOTE]
   >
   > Esta configuración está habilitada de forma predeterminada y la pestaña Traducción no está disponible en el panel de asignaciones.


## Configurar flujo de trabajo de traducción basado en componentes

Si el conector del proveedor de traducción no admite contenido DITA, es necesario habilitar el flujo de trabajo de traducción basado en componentes. Una vez activado, el contenido traducible se envía como metadatos de recursos. Sin embargo, el conector debe admitir la traducción de metadatos de recursos para que este flujo de trabajo funcione.

En función del flujo de trabajo de traducción utilizado en la configuración, se debe configurar la opción del flujo de trabajo de traducción basado en componentes. Siga las instrucciones indicadas en [Anulaciones de configuración](download-install-additional-config-override.md#) para crear el archivo de configuración. En el archivo de configuración, proporcione los siguientes detalles \(property\) para configurar el flujo de trabajo de traducción basado en componentes:

| PID | Clave de propiedad | Valor de propiedad |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `component.translation` | Boolean: <br> -   Si usa traducción humana, *Deshabilitar* \( `false`\) la opción **Flujo de trabajo de traducción basado en componentes**. <br> -   Si está usando la traducción automática, *habilite \( `true`\)* la opción **Flujo de trabajo de traducción basado en componentes**. |



## Configuración del flujo de trabajo de traducción heredado

>[!IMPORTANT]
>
> Se recomienda utilizar el flujo de trabajo de traducción más reciente, disponible en AEM Guides 2024.06.0 y versiones posteriores, para un rendimiento mejorado. Sin embargo, si ha habilitado cualquier personalización en el proceso de traducción y este se ve afectado por el nuevo flujo de trabajo, considere la posibilidad de volver al flujo de trabajo de traducción heredado como solución alternativa.

Siga las instrucciones indicadas en [Anulaciones de configuración](download-install-additional-config-override.md#) para crear el archivo de configuración. En el archivo de configuración, proporcione los siguientes detalles (propiedad) para configurar el flujo de trabajo de traducción heredado:


| PID | Clave de propiedad | Valor de propiedad |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `translation.workflow.version.legacy` | Booleano: <br> - Si usa el flujo de trabajo de traducción más reciente, *Deshabilitar* \( `false`\) la opción **Ejecutar flujo de trabajo de traducción heredado**.  <br> -   Si usa la traducción heredada, *habilite \( `true`\)* la opción **Ejecutar flujo de trabajo de traducción heredada**. <br> **Valor predeterminado**: false |




>[!NOTE]
>
> Si está usando un conector de traducción, asegúrese de haber configurado el conector tal como se describe en el tema *[Configuración del marco de trabajo de integración de traducción](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/sites/administering/reusing-content/translation/integration-framework.html?lang=en)* de la documentación de Adobe Experience Manager.

>[!IMPORTANT]
>
> Después de configurar las configuraciones de traducción, asegúrese de configurar la configuración de nube adecuada en las carpetas de idioma.

## Configurar el posprocesamiento de las copias de idioma temporales

Al iniciar el flujo de trabajo de traducción, el sistema crea copias de idioma temporales del contenido de origen. Puede elegir habilitar o deshabilitar la operación de posprocesamiento en estos archivos temporales. En la operación posterior al procesamiento, se resuelven las referencias entrantes y salientes de los archivos, se establece el estado del documento y otras operaciones. Si habilita el posprocesamiento en estos archivos temporales, el proceso de traducción podría tardar más tiempo en completarse. Por lo tanto, se recomienda mantener desactivada la opción de posprocesamiento.

Siga las instrucciones indicadas en [Anulaciones de configuración](download-install-additional-config-override.md#) para crear el archivo de configuración. En el archivo de configuración, proporcione los siguientes detalles \(property\) para configurar el posprocesamiento de copias de idioma temporales:

| PID | Clave de propiedad | Valor de propiedad |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `postprocess.temporary.langcopies` | Boolean: <br> -   Si no desea ejecutar la operación de posprocesamiento en los archivos temporales, *Deshabilitar* \( false\) la opción **Copias de idioma de posprocesamiento**.<br> -   Si desea ejecutar la operación de posprocesamiento en los archivos temporales, *Habilite* \( true\) la opción **Copias de idioma de posprocesamiento**.<br> **Valor predeterminado**: false |

