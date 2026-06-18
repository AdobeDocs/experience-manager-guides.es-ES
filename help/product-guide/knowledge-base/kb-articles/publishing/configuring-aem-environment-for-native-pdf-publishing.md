---
title: Configuración del entorno de AEM para la publicación nativa de PDF
description: Configuración del entorno de AEM para la publicación nativa de PDF
exl-id: 40266ca0-0b0b-4418-b606-f70270addbaa
feature: Native PDF Output
role: User, Admin
TQID: https://experienceleague.adobe.com/SLuPn9YigAcHvcSEdrbbQOz29Y6DeWGYnWktWY9L9nQ
product_v2:
  - id: fae5e35a-80c9-4b94-9352-1a060a6aab1d
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: a3bd6397-2eb2-4908-a61c-226e26855dca
  - id: cb8c6a2a-3c38-4e40-867c-756f8c36bb0e
subfeature_v2:
  - id: b1ef4d86-3917-4b76-a0bc-4a4771f9b3b0
  - id: d6596f3f-92a7-43ec-b444-237db6adad05
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
source-git-commit: cc73b81787a3c3dbe8390d93e558064327e59965
workflow-type: tm+mt
source-wordcount: 911
ht-degree: 1%

---

# Configuración del entorno de AEM para la publicación nativa de PDF

AEM Guides incluye un motor de publicación nativo de PDF que permite a los usuarios diseñar, desarrollar y publicar el contenido en formato PDF.

Proporciona la capacidad de crear diferentes diseños de página, plantillas CSS y diseñar las plantillas PDF junto con los diseños de página y CSS.

Los pasos para configurar este PDF nativo en AEM Guides difieren según el sistema operativo. Siga los pasos de configuración siguientes en función del sistema operativo en el que esté instalado AEM.

## Requisitos previos

Requisitos mínimos para configurar PDF nativo:

- Se ha instalado Java Platform, Standard Edition 8 o 11 JDK (kit de desarrollo de Java SE) y JRE (entorno de tiempo de ejecución de Java SE)
- AEM 6.5 SP13, SP12, SP11 o SP10
- Guías 4.1 y versiones posteriores (no UUID o UUID)

El motor de publicación nativo de PDF necesita el JDK de Oracle para generar los módulos de nodo en la carpeta crx-quickstart de AEM. Admite los siguientes sistemas operativos de forma predeterminada:

- Windows 10, windows 2019 server y superior.
- Linux: (RHEL 8 y versiones posteriores, CentOS 7 y versiones posteriores, Ubuntu 18 y versiones posteriores)
- Sistema operativo Mac (basado en Intel)

## Pasos de configuración para Windows Server (JAVA 11/8)

1. Asegúrese de que el servidor de AEM esté inactivo.
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
12. Inicie el servidor de AEM.
13. Genere PDF nativo a partir de ajustes preestablecidos en el editor.

## Pasos de configuración para el servidor Linux (RHEL7/centOS 7)

1. Asegúrese de que el servidor de AEM esté inactivo.
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

5. Reinicie AEM Server y vaya al paso 12 si utiliza la versión 4.2 de las guías o una posterior.
6. Copie el &quot;_node_ modules.zip_&quot; adjunto en la parte inferior de este artículo al directorio crx-quickstart/profiles/nodejs-b1aad0a7-9079-e56c-1ed8-6fcababe8166/.
7. Abra el terminal en crx-quickstart/profiles/nodejs—b1aad0a7-9079-e56c-1ed8-6fcababe8166/ location.
8. Elimine el directorio node_modules con el comando siguiente

   **rm -rf node_modules**

9. Descomprima node_modules.zip con el comando siguiente

   **descomprimir node_modules.zip**

10. Si el comando unzip no está instalado/reconocido, se puede instalar mediante el siguiente comando

    **yum install unzip**

11. Instale el paquete fontconfig.
Comando: yum install fontconfig
12. Genere PDF nativo a partir de ajustes preestablecidos en el editor.

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

7. Ejecute los tres comandos siguientes desde la ruta de instalación de AEM

   C:/{aem-installation-folder}/crx-quickstart/profiles/nodejs—b1aad0a7-9079-e56c-1ed8-6fcababe8166

   i) encontrar . -type d -exec chmod 0755 {} \;
ii) encontrar . -type f -exec chmod 0755 {} \;
iii) ./node-darwin/bin/node node-darwin/lib/node_modules/npm/bin/npm-cli.js —prefix . install —unsafe-perm —scripts-prepend-node-path

8. Compruebe si Java está instalado con el comando siguiente

   i) Ejecute el comando **./node-darwin/bin/node** desde la carpeta /crx-quickstart/profiles/nodejs—b1aad0a7-9079-e56c-1ed8-6fcababe8166

   ![mac](../assets/publishing/mac.png)

   ii) a = require(&#39;java&#39;)

9. Instale el paquete fontconfig.
Comando: apt install fontconfig

10. Genere PDF nativo a partir de ajustes preestablecidos en el editor.

## Resolución de problemas

A continuación se muestran los errores comunes que pueden producirse durante la generación de PDF cuando las variables de entorno no se configuran correctamente.

### Excepción de puntero nulo en el sistema operativo Windows/Mac

![excepción de puntero nulo](../assets/publishing/null-pointer-exception.png)

Si el problema persiste incluso después de corregir la configuración del entorno Java, vuelva a validar lo siguiente:

1. Compruebe si el ajuste preestablecido de salida está definido correctamente o cree uno nuevo sin espacios.

2. Compruebe el directorio de recursos del nodo en /libs/fmdta/node_resources para asegurarse de que todas las bibliotecas necesarias se instalan durante la instalación.

### Faltan bibliotecas en el sistema operativo RHEL 7 Linux

![bibliotecas faltantes](../assets/publishing/missing-libraries.png)

### Tiempo de espera del proceso de publicación. El proceso no se completó en un tiempo determinado de 0 ms

![tiempo de espera del proceso de publicación](../assets/publishing/publish-process-timeout.png)

Valide el valor de la propiedad timeout para el nodo nodejs en /var/dxml/profiles/b1aad0a7-9079-e56c-1ed8-6fcababe8166/nodejs en el repositorio de CRX. El valor predeterminado es 300.



Si encuentra algún problema al realizar cualquiera de los pasos anteriores, publique su pregunta en el [foro](https://experienceleaguecommunities.adobe.com/t5/experience-manager-guides/ct-p/aem-xml-documentation?profile.language=es) de la comunidad de AEM Guides para obtener asistencia.
