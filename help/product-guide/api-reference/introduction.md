---
title: Introducción
description: AEM Introducción a la Guía de referencia de la API para guías de
exl-id: d8ee9cf7-1d67-4b4a-aa80-64e893a99463
source-git-commit: eb3fe92d36bc58a11e47f786a10d5938e2ed0184
workflow-type: tm+mt
source-wordcount: '725'
ht-degree: 0%

---

# Introducción {#id1761C0007W7}

Guías de Adobe Experience Manager \(más adelante denominadas *AEM Guías de*\) es una solución empresarial integral que permite a Adobe Experience Manager AEM \(\) disponer de funciones de la solución de gestión de contenido de componentes \(CCMS\) para la creación y entrega de contenido basado en DITA. AEM AEM Los clientes pueden acceder a los flujos de trabajo de las Guías de usuario de forma programática mediante las API de Guías de usuario para integrarlos con otras aplicaciones empresariales. Estas API también las pueden utilizar los socios de Adobe AEM para mejorar la propuesta de valor de las guías de la mediante la ampliación de su funcionalidad o la integración con otras aplicaciones o servicios.

## AEM API de guías de

AEM Las API de Guías de están disponibles en dos formatos: HTTP y Java. AEM Estas API exponen las funciones clave de las guías de la aplicación a los desarrolladores de aplicaciones. Con estas funciones, los desarrolladores pueden crear sus propios complementos para ampliar los flujos de trabajo predeterminados. Las API están disponibles para administrar salidas para contenido DITA, trabajar con mapas DITA, añadir atributos condicionales a perfiles de nivel de carpeta y convertir documentos de HTML y de Word a formato DITA.

## Instalación de los JAR en el repositorio local de Apache Maven {#install-jar-local}

AEM Para poder utilizar los archivos JAR expuestos por las Guías de, debe instalarlos en su repositorio local de Apache Maven. Siga estos pasos para instalar los JAR en su ubicación del repositorio de Maven:

1. AEM Extraiga el contenido del archivo \(.zip\) del paquete de guías de la aplicación en el sistema local.

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

4. \(*Opcional*\) Instale la dependencia en el repositorio local del proyecto Maven. Puede conseguirlo creando una carpeta en su proyecto de Maven y ejecutando a continuación el `mvn install` comando proporcionado en el paso anterior con el siguiente parámetro adicional:

   ```
   -DlocalRepositoryPath=<path_to_project_repository>
   ```

   A continuación, para exponer la carpeta de repositorio local del proyecto al proceso de generación de Maven, agregue una `repository` en el archivo pom.xml principal como se muestra a continuación:

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
   > En el siguiente fragmento de código, X.x debe reemplazarse por el número de versión real y el nombre de archivo del JAR de la API. Esta información es la misma que se proporciona en el paso 3 del [proceso de instalación](#install-jar-local).

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

1. AEM Para utilizar el JAR de la API de servicio en un proyecto, configure el repositorio Maven público de las Guías de en el archivo pom.xml.
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
   > AEM Utilice la misma versión del JAR de API que el paquete de Guías de que ha instalado en el servidor.

4. Configure la dependencia de Maven como se muestra a continuación:

   ```XML
   <dependency>
      <groupId>com.adobe.fmdita</groupId>
      <artifactId>api</artifactId>
      <version>4.0</version>
   </dependency>
   ```


AEM Una vez que el JAR de la API de servicio se agrega como dependencia de proyecto en el archivo pom.xml del proyecto, puede crear y utilizar las API de Java de Guías en el proyecto.

## AEM Uso del JAR de API del repositorio de Maven Central para guías de as a Cloud Service

AEM Para las guías de la as a Cloud Service, el JAR de la API se ha implementado en Maven Central. Puede utilizar el JAR de la API sin ninguna configuración.

>[!NOTE]
>
> La convención de nombres del JAR de la API se ha actualizado según la convención de nombres de los complementos de la nube.

Para utilizar el JAR de API, debe añadir la dependencia al pom.xml de su proyecto como se muestra a continuación:

```XML
<dependency>
   <groupId>com.adobe.aem</groupId>
   <artifactId>aem-guides-sdk-api</artifactId>
   <version>2022.5</version>
</dependency>
```

>[!NOTE]
>
> Dado que los paquetes dentro del JAR de API siguen siendo los mismos, no se requiere ningún cambio de código para utilizar este JAR de API en los proyectos de nube existentes.

## Recursos adicionales

AEM A continuación se muestra una lista de otros recursos útiles de las guías de la, que están disponibles en la [Aprendizaje y asistencia](https://helpx.adobe.com/support/xml-documentation-for-experience-manager.html) página:

- Guía del usuario
- Guía de instalación y configuración
- Guía de inicio rápido
- [Página de archivado de ayuda](https://helpx.adobe.com/xml-documentation-for-experience-manager/archive.html) \(acceder a la documentación de la versión anterior\)
