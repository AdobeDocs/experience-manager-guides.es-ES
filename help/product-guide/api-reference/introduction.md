---
title: Introducción
description: Introducción a la Guía de referencia de API para AEM Guides
exl-id: d8ee9cf7-1d67-4b4a-aa80-64e893a99463
feature: API Introduction
role: Developer
level: Experienced
source-git-commit: bf7838690d7632cd74fef0db3aaf7bdc48a50a2c
workflow-type: tm+mt
source-wordcount: '622'
ht-degree: 0%

---

# Introducción {#id1761C0007W7}

Adobe Experience Manager Guides \(más adelante denominado *AEM Guides*\) es una solución empresarial integral que permite a Adobe Experience Manager \(AEM\) disponer de funcionalidades de la solución de administración de contenido de componentes \(CCMS\) para la creación y entrega de contenido basado en DITA. Los clientes pueden acceder a los flujos de trabajo de AEM Guides mediante programación utilizando las API de AEM Guides para integrarlos con otras aplicaciones empresariales. Los socios de Adobe también pueden utilizar estas API para mejorar la propuesta de valor de AEM Guides ampliando su funcionalidad o integrándola con otras aplicaciones o servicios.

## API de AEM Guides

Las API de AEM Guides están disponibles en dos formatos:

- [API basadas en Java](#java-based-apis)
- [API basadas en REST](#rest-based-apis)

Estas API exponen funciones clave de AEM Guides a los desarrolladores de aplicaciones. Con estas funciones, los desarrolladores pueden crear sus propios complementos para ampliar los flujos de trabajo predeterminados. Las API están disponibles para administrar salidas para contenido DITA, trabajar con mapas DITA, añadir atributos condicionales a perfiles de nivel de carpeta y convertir documentos de HTML y Words a formato DITA.


### API basadas en Java

Puede utilizar las API basadas en Java disponibles en Experience Manager Guides para crear complementos personalizados y ampliar los flujos de trabajo predeterminados.

**Configurar SDK desde el repositorio central de Maven para AEM Guides as a Cloud Service**

>[!INFO]
>
>Consulta [![javadoc](./images/javadoc-cs-icon.svg)](https://javadoc.io/doc/com.adobe.aem/aem-dox-sdk-api/latest/index.html) para obtener la documentación más reciente y detallada sobre el uso de la API basada en Java para Experience Manager Guides as a Cloud Service.

Para configurar y utilizar los JAR de la API de servicio del repositorio de Maven en sus proyectos, agregue la API de SDK como dependencia de proyecto en el archivo `pom.xml` de su proyecto, como se muestra a continuación.

    &quot;XML
    &lt;dependencia>
    &lt;groupId>com.adobe.aem&lt;/groupId>
    &lt;artifactId>aem-dox-sdk-api&lt;/artifactId>
    &lt;versión>${RELEASE}&lt;/versión>
    &lt;/dependencia>
    
    &quot;

>[!NOTE]
>
> Asegúrese de utilizar la misma versión del JAR de API que el paquete de AEM Guides instalado en el servidor.

**Configurar y utilizar el JAR de API del repositorio central de Maven (On-Premise)**

>[!INFO]
>
>Consulte [![javadoc](https://javadoc.io/badge2/com.adobe.aem/aem-guides-sdk-api/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api/latest/index.html) para obtener la documentación más reciente y detallada sobre el uso de la API basada en Java para la configuración On-Premise de Experience Manager Guides.

Para configurar y utilizar los JAR de la API de servicio para implementaciones locales, agregue el JAR de la API de servicio como una dependencia de proyecto en el archivo `pom.xml` de su proyecto, como se muestra a continuación:

    &quot;XML
    &lt;dependencia>
    &lt;groupId>com.adobe.aem&lt;/groupId>
    &lt;artifactId>aem-guides-sdk-api&lt;/artifactId>
    &lt;versión>${RELEASE}&lt;/versión>
    &lt;/dependencia>
    
    &quot;

>[!NOTE]
>
> Asegúrese de utilizar la misma versión del JAR de API que el paquete de AEM Guides instalado en el servidor.


**Configurar y utilizar el JAR de API del repositorio Maven público de AEM Guides (On-Premise)**

>[!NOTE]
>
> El repositorio público de AEM Guides Maven quedará obsoleto después de la versión 5.3.0 de Experience Manager Guides. El JAR de API solo estará disponible en el repositorio central de Maven a partir de entonces.

Siga estos pasos para utilizar los JAR de API de servicio del repositorio público de Maven:

1. Configure el repositorio Maven público de AEM Guides en su archivo `pom.xml` o `settings.xml` como se muestra a continuación:

   ```XML
   <repository>
       <id>fmdita-public</id>
       <name>fmdita-public</name>
       <url>https://repo.aem-guides.com/repository/fmdita-public</url>
    </repository>
   ```

1. Una vez configurado el repositorio, agregue el JAR de la API de servicio como una dependencia de proyecto en el archivo `pom.xml` del proyecto.

   ```XML
   <dependency>
       <groupId>com.adobe.fmdita</groupId>
       <artifactId>api</artifactId>
       <version>${RELEASE}</version>
   </dependency>
   ```

   >[!NOTE]
   >
   > Utilice la misma versión del JAR de API que el paquete de AEM Guides que ha instalado en el servidor.

Una vez agregado el JAR de la API de servicio como dependencia de proyecto en el archivo `pom.xml` del proyecto, puede generar y utilizar las API de Java de AEM Guides en su proyecto.


### API basadas en REST

Experience Manager Guides proporciona un conjunto completo de API basadas en REST que permiten a los desarrolladores acceder e interactuar con las funcionalidades principales a través de HTTP.

Estas API son perfectas para:

- Integración de Experience Manager Guides con otros sistemas empresariales
- Automatización de flujos de trabajo de publicación y revisión
- Creación de aplicaciones y extensiones personalizadas

Para obtener información detallada sobre el uso de la API, los parámetros y las solicitudes de ejemplo, consulte los temas relevantes en la sección **Referencia de la API** de la documentación de Experience Manager Guides.

## Recursos adicionales

A continuación se muestra una lista de otros recursos útiles de AEM Guides, que están disponibles en la página [Aprendizaje y asistencia](https://helpx.adobe.com/es/support/xml-documentation-for-experience-manager.html):

- Guía del usuario
- Guía de instalación y configuración
- Guía de inicio rápido
- [Página de archivo de ayuda](https://helpx.adobe.com/es/xml-documentation-for-experience-manager/archive.html) \(acceder a la documentación de la versión anterior\)
