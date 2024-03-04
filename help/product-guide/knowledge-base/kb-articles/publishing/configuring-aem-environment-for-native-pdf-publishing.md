---
title: AEM Configuración del entorno de trabajo para la publicación de PDF nativos
description: AEM Configuración del entorno de trabajo para la publicación de PDF nativos
exl-id: 40266ca0-0b0b-4418-b606-f70270addbaa
feature: Native PDF Output
role: User, Admin
source-git-commit: a41fed965ed9fe33994478d51030eefdad1037de
workflow-type: tm+mt
source-wordcount: '938'
ht-degree: 1%

---

# AEM Configuración del entorno de trabajo para la publicación de PDF nativos

AEM Guías de incluye un motor de publicación PDF nativo que permite a los usuarios diseñar, desarrollar y publicar el contenido en formato PDF.

Permite crear diferentes diseños de página, plantillas CSS y diseñar las plantillas de PDF junto con los diseños de página y CSS.

Los pasos para configurar este PDF AEM nativo en las Guías de difieren según el sistema operativo. AEM Siga los pasos de configuración que se indican a continuación en función del sistema operativo en el que se haya instalado la.

## Requisitos previos

Requisitos mínimos para configurar el PDF nativo:

- Se ha instalado Java Platform, Standard Edition 8 o 11 JDK (kit de desarrollo de Java SE) y JRE (entorno de tiempo de ejecución de Java SE)
- AEM,5 SP13, SP12, SP11 o SP10
- Guías 4.1 y versiones posteriores (no UUID o UUID)

El motor de publicación de PDF nativo necesita un JDK de Oracle AEM para generar los módulos de nodo en la carpeta de inicio rápido de crx de la. Admite los siguientes sistemas operativos de forma predeterminada:

- Windows 10, windows 2019 server y superior.
- Linux: (RHEL 8 y versiones posteriores, CentOS 7 y versiones posteriores, Ubuntu 18 y versiones posteriores)
- Sistema operativo Mac (basado en Intel)

## Pasos de configuración para Windows Server (JAVA 11/8)

1. AEM Asegúrese de que el servidor de esté inactivo.
2. En la barra de tareas de Windows, haga clic con el botón secundario en el icono de Windows y seleccione Sistema.
3. En la ventana Configuración, en Configuración relacionada, haga clic en Configuración avanzada del sistema.
4. En la pestaña Avanzadas, haga clic en Variables de entorno.
5. En la sección de variables del sistema, haga clic en &quot;_Nuevo_&quot; para crear una nueva variable de entorno.
6. Escriba el nombre de la variable como JAVA_HOME.
7. En el campo del valor, proporcione la ruta de instalación de Java y haga clic en Ok.

   Por ejemplo:

   JAVA 11:

   C:\Program Files\JAVA\jdk-11.0.15.1

   JAVA 8:

   C:\Program Files\JAVA\ jdk1.8.0_144

8. Añada, seleccione Path en las variables del sistema y haga clic en Edit.

9. Ahora, dentro de las variables Path, proporcione el valor de Server path y haga clic en Ok.

   Por ejemplo:

   JAVA 11:

   %JAVA_HOME%\bin\server\

   JAVA 8:

   %JAVA_HOME%\jre\bin\server\

10. Vuelva a hacer clic en Aceptar en el cuadro de diálogo Variables de entorno.
11. Vuelva a hacer clic en &quot;Aceptar&quot; en el cuadro de diálogo Propiedades del sistema.
12. AEM Ahora, inicie el servidor de la.
13. Genere un PDF nativo a partir de ajustes preestablecidos en el editor web.

## Pasos de configuración para el servidor Linux (RHEL7/centOS 7)

1. AEM Asegúrese de que el servidor de esté inactivo.
2. Compruebe la variable JAVA_HOME haciendo eco $JAVA_HOME
3. Si no se ha definido la variable JAVA_HOME, siga el paso 4. De lo contrario, vaya directamente al paso 5.
4. Establezca la variable JAVA_HOME utilizando los siguientes comandos según la versión de java instalada

   Por ejemplo:

   JAVA 11:

   1. export JAVA\_HOME=/usr/lib/jvm/java-11.0.15.1
   2. export PATH=$PATH: $JAVA\_HOME/bin
   3. export LD\_LIBRARY\_PATH=/usr/lib/jvm/jdk-11.0.15.1/lib/server:/usr/java/jdk-11.0.15.1/lib/server

   JAVA 8:

   1. export JAVA\_HOME=/usr/lib/jvm/java-11.0.15.1
   2. export PATH=$PATH: $JAVA\_HOME/bin

5. AEM Reinicie el servidor de y vaya al paso 12 si utiliza la versión 4.2 de las guías o una posterior.
6. Copie el &quot;_node_modules.zip_&quot; adjunto en la parte inferior de este artículo al directorio crx-quickstart/profiles/nodejs-b1aad0a7-9079-e56c-1ed8-6fcababe8166/.
7. Abra el terminal en crx-quickstart/profiles/nodejs—b1aad0a7-9079-e56c-1ed8-6fcababe8166/ location.
8. Elimine el directorio node_modules con el comando siguiente

   **rm -rf módulos_nodos**

9. Descomprima node_modules.zip con el comando siguiente

   **descomprimir node_modules.zip**

10. Si el comando unzip no está instalado/reconocido, se puede instalar mediante el siguiente comando

   **yum install unzip**

11. Instale el paquete fontconfig.
Comando: yum install fontconfig
12. Genere un PDF nativo a partir de ajustes preestablecidos en el editor web.

**NOTA** : el paquete node_modules.zip se puede descargar [aquí](https://acrobat.adobe.com/link/track?uri=urn:aaid:scds:US:295d8f03-41e1-429b-8465-2761ce3c2fb3).

La importación manual de los módulos de nodos descargados para el sistema operativo Linux es una solución alternativa para los usuarios que se encuentran en las Guías 4.1 o versiones anteriores (Paso 6-12)

## Pasos de configuración para el equipo Mac (JAVA 11/8)

1. Instale Oracle JAVA 11 o Oracle JAVA 8.
2. Establezca la variable de entorno JAVA_HOME en el directorio JAVA instalado.
3. Abra un shell de Unix.
(Bash se usa aquí para configurar la configuración)

   Comando: nano ~/.bashrc

4. Establezca la variable JAVA_HOME utilizando los siguientes comandos según la versión de java instalada

   Por ejemplo:

   JAVA 11:

   export JAVA\_HOME= /Library/Java/JavaVirtualMachines/jdk-11.0.15.1.jdk/Contents/Home

5. Volver a cargar bashrc

   Comando: source ~/.bashrc.

6. Verificar que JAVA_HOME esté establecido mediante el comando echo $JAVA_HOME

7. AEM Ejecute los tres comandos siguientes desde la ruta de instalación de la

   C:/{aem-installation-folder}/crx-quickstart/profiles/nodejs—b1aad0a7-9079-e56c-1ed8-6fcababe8166

   i) encontrar . -type d -exec chmod 0755 {} \; ii) buscar . -type f -exec chmod 0755 {} \; iii) ./node-darwin/bin/node node-darwin/lib/node_modules/npm/bin/npm-cli.js —prefix . install —unsafe-perm —scripts-prepend-node-path

8. Compruebe si Java está instalado con el comando siguiente

   i) Ejecutar **./node-darwin/bin/node** comando de la carpeta /crx-quickstart/profiles/nodejs—b1aad0a7-9079-e56c-1ed8-6fcababe8166

   ![mac](../assets/publishing/mac.png)

   ii) a = require(&#39;java&#39;)

9. Instale el paquete fontconfig.
Comando: apt install fontconfig

10. Genere un PDF nativo a partir de ajustes preestablecidos en el editor web.

## Solución de problemas

A continuación se muestran los errores comunes que pueden producirse durante la generación de PDF cuando las variables de entorno no se configuran correctamente.

### Excepción de puntero nulo en el sistema operativo Windows/Mac

![excepción de puntero nulo](../assets/publishing/null-pointer-exception.png)

Si el problema persiste incluso después de corregir la configuración del entorno Java, vuelva a validar lo siguiente:

1. Compruebe si el ajuste preestablecido de salida está definido correctamente o cree uno nuevo sin espacios.

2. Compruebe el directorio de recursos del nodo en /libs/fmdta/node_resources para asegurarse de que todas las bibliotecas necesarias se instalan durante la instalación.

### Faltan bibliotecas en el sistema operativo RHEL 7 Linux

![faltan bibliotecas](../assets/publishing/missing-libraries.png)

### Tiempo de espera del proceso de publicación. El proceso no se completó en un tiempo determinado de 0 ms

![tiempo de espera del proceso de publicación](../assets/publishing/publish-process-timeout.png)

Valide el valor de la propiedad timeout para el nodo nodejs en /var/dxml/profiles/b1aad0a7-9079-e56c-1ed8-6fcababe8166/nodejs en el repositorio CRX. El valor predeterminado es 300.

### Error al extraer la excepción de dependencia (cadena demasiado larga)
![Excepción de cadena demasiado larga](..//assets/publishing/string-too-long-error.png)

Para solucionar esta excepción:
1. Elimine algunos estilos que no sean necesarios para reducirlos.
2. Cree varias hojas de estilo en lugar de una sola css grande.


AEM Si encuentra algún problema al realizar cualquiera de los pasos anteriores, publique su pregunta en la Comunidad de guías de la comunidad de la comunidad de la [foro](https://experienceleaguecommunities.adobe.com/t5/experience-manager-guides/ct-p/aem-xml-documentation) para obtener asistencia.
