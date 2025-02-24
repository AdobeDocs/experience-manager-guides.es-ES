---
title: Introducción
description: Introducción a la Guía de referencia de API para AEM Guides
exl-id: d8ee9cf7-1d67-4b4a-aa80-64e893a99463
feature: API Introduction
role: Developer
level: Experienced
source-git-commit: 00a926e82f7d848e0c8041de758f20e79758b01b
workflow-type: tm+mt
source-wordcount: '760'
ht-degree: 0%

---

# Introducción {#id1761C0007W7}

Adobe Experience Manager Guides \(más adelante denominado *AEM Guides*\) es una solución empresarial integral que permite a Adobe Experience Manager \(AEM\) disponer de funcionalidades de la solución de administración de contenido de componentes \(CCMS\) para la creación y entrega de contenido basado en DITA. Los clientes pueden acceder a los flujos de trabajo de AEM Guides mediante programación utilizando las API de AEM Guides para integrarlos con otras aplicaciones empresariales. Los socios de Adobe también pueden utilizar estas API para mejorar la propuesta de valor de AEM Guides ampliando su funcionalidad o integrándola con otras aplicaciones o servicios.

## API de AEM Guides

Las API de AEM Guides están disponibles en dos formatos: HTTP y Java. Estas API exponen funciones clave de AEM Guides a los desarrolladores de aplicaciones. Con estas funciones, los desarrolladores pueden crear sus propios complementos para ampliar los flujos de trabajo predeterminados. Las API están disponibles para administrar salidas para contenido DITA, trabajar con mapas DITA, añadir atributos condicionales a perfiles de nivel de carpeta y convertir documentos de HTML y Words a formato DITA.

## Instalación de los JAR en el repositorio local de Apache Maven {#install-jar-local}

Para poder utilizar los archivos JAR expuestos por AEM Guides, debe instalarlos en su repositorio local de Apache Maven. Siga estos pasos para instalar los JAR en su ubicación del repositorio de Maven:

1. Extraiga el contenido del archivo \(.zip\) del paquete de AEM Guides en el sistema local.

2. En el símbolo del sistema, vaya a la siguiente carpeta en la ruta de contenido extraída:

   ```
   \jcr_root\libs\fmdita\osgi-bundles\install
   ```

3. Ejecute el siguiente comando para instalar el paquete de API en el repositorio local de Maven:

   ```
   mvn install:install-file -Dfile=api-X.x.jar -DgroupId=com.adobe.fmdita -DartifactId=api -Dversion=X.x -Dpackaging=jar**
   ```

   >[!NOTE]
   >
   > En el comando anterior, X.x debe reemplazarse por el número de versión real en los parámetros Dfile y Dversion.

4. \(*Opcional*\) Instale la dependencia en el repositorio local del proyecto Maven. Puede conseguirlo creando una carpeta en su proyecto Maven y luego ejecutando el comando `mvn install` dado en el paso anterior con el siguiente parámetro adicional:

   ```
   -DlocalRepositoryPath=<path_to_project_repository>
   ```

   A continuación, para exponer la carpeta de repositorio local del proyecto al proceso de generación de Maven, agregue un elemento `repository` en el archivo pom.xml principal como se muestra a continuación:

   ```XML
   <repositories>
      <repository>
         <id>project-repository</id>
         <url>file://${project.basedir}/repository</url>
      </repository>
   </repositories>
   ```


Este proceso instala los JAR de API en el repositorio local de Maven.

## Uso del JAR de la API de servicio en un proyecto de Maven

Después de instalar los JAR de API en el repositorio local de Maven, realice los siguientes pasos para utilizar el JAR en sus proyectos:

1. Añada el JAR a la base de código y confírmelo en el repositorio de la base de código en una carpeta, como &quot;dependencias&quot;. Tenga en cuenta que el nombre de la carpeta depende de la jerarquía base de código.

2. Configure los archivos pom.xml del proyecto de la siguiente manera:

   Archivo pom.xml del proyecto principal:

   >[!IMPORTANT]
   >
   > En el siguiente fragmento de código, X.x debe reemplazarse por el número de versión real y el nombre de archivo del JAR de la API. Esta información será la misma que se proporciona en el paso 3 del [proceso de instalación](#install-jar-local).

   ```XML
   <plugin>
   
       <groupId>org.apache.maven.plugins</groupId>
   
      <artifactId>maven-install-plugin</artifactId>
   
       <version>2.5.2</version>
   
       <configuration>
   
               <groupId>com.adobe.fmdita</groupId>
   
               <artifactId>api</artifactId>
   
               <version>X.x</version>
   
               <file>${basedir}/dependencies/fmdita/api-X.x.jar</file>
   
               <packaging>jar</packaging>
   
               <generatePom>true</generatePom>
   
       </configuration>
   
       <executions>
   
           <execution>
   
               <id>inst_fmdita</id>
   
                   <goals>
   
                       <goal>install-file</goal>
   
                   </goals>
   
                   <phase>clean</phase>
   
           </execution>
   
       </executions>
   </plugin>
   ```

   Archivo pom.xml del módulo secundario:

   ```XML
   <plugin>
      <groupId>org.apache.maven.plugins</groupId>
   
      <artifactId>maven-install-plugin</artifactId>
   
      <configuration>
   
         <groupId>com.adobe.fmdita</groupId>
   
         <artifactId>api</artifactId>
   
         <version>3.6</version>
   
         <file>${basedir}/../dependencies/fmdita/api-3.6.jar</file>
   
         <packaging>jar</packaging>
   
         <generatePom>true</generatePom>
   
      </configuration>
   
      <executions>
   
         <execution>
   
            <id>inst_fmdita</id>
   
            <goals>
   
               <goal>install-file</goal>
   
            </goals>
   
            <phase>clean</phase>
   
         </execution>
   
      </executions>
   
   </plugin>
   ```


## Configure y utilice el JAR de la API de servicio del repositorio público de Maven

Realice los siguientes pasos para configurar y utilizar los JAR de la API de servicio del repositorio público de Maven en sus proyectos:

1. Para utilizar el JAR de la API de servicio en un proyecto, configure el repositorio Maven público de AEM Guides en el archivo pom.xml.
2. Configure el repositorio público de Maven en el archivo settings.xml de Maven de la siguiente manera:

   ```XML
   <repository>
      <id>fmdita-public</id>
      <name>fmdita-public</name>
      <url>https://repo.aem-guides.com/repository/fmdita-public</url>
   </repository>
   ```

3. Una vez configurado el repositorio, agregue el JAR de la API de servicio como una dependencia de proyecto en el archivo pom.xml del proyecto.

   >[!NOTE]
   >
   > Utilice la misma versión del JAR de API que el paquete de AEM Guides que ha instalado en el servidor.

4. Configure la dependencia de Maven como se muestra a continuación:

   ```XML
   <dependency>
      <groupId>com.adobe.fmdita</groupId>
      <artifactId>api</artifactId>
      <version>4.0</version>
   </dependency>
   ```


Una vez agregado el JAR de la API de servicio como dependencia del proyecto en el archivo pom.xml del proyecto, puede generar y utilizar las API de Java de AEM Guides en su proyecto.

## Uso del JAR de API del repositorio de Maven Central para AEM Guides as a Cloud Service

Para AEM Guides as a Cloud Service, el JAR de la API se ha implementado en Maven Central. Puede utilizar el JAR de la API sin ninguna configuración.

>[!NOTE]
>
> La convención de nombres del JAR de la API se ha actualizado según la convención de nombres de los complementos de la nube.

Para utilizar el JAR de API, debe añadir la dependencia al pom.xml de su proyecto como se muestra a continuación:

```XML
<dependency>
   <groupId>com.adobe.aem</groupId>
   <artifactId>aem-dox-sdk-api</artifactId>
   <version>${RELEASE}</version>
</dependency>
```

>[!NOTE]
>
> Dado que los paquetes dentro del JAR de API siguen siendo los mismos, no se requiere ningún cambio de código para utilizar este JAR de API en los proyectos de nube existentes.

### API basadas en Java

Puede utilizar las API basadas en Java disponibles en Experience Manager Guides para crear complementos personalizados y ampliar los flujos de trabajo predeterminados. Consulta [![javadoc](https://javadoc.io/badge2/com.adobe.aem/aem-guides-sdk-api/javadoc.svg)](https://javadoc.io/doc/com.adobe.aem/aem-guides-sdk-api) para obtener la documentación más reciente y detallada sobre el uso de la API basada en Java.



## Recursos adicionales

A continuación se muestra una lista de otros recursos útiles de AEM Guides, que están disponibles en la página [Aprendizaje y asistencia](https://helpx.adobe.com/support/xml-documentation-for-experience-manager.html):

- Guía del usuario
- Guía de instalación y configuración
- Guía de inicio rápido
- [Página de archivo de ayuda](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html) \(acceder a la documentación de la versión anterior\)
