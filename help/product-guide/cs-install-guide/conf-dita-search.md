---
title: Configuración de la búsqueda para la IU de AEM Assets
description: Obtenga información sobre cómo configurar la IU de búsqueda para AEM Assets
exl-id: 125d247f-1017-4450-9e3f-9ecc7188ca8f
feature: Search Configuration
role: Admin
level: Experienced
source-git-commit: 8ee4863470f69bca52a9b36cde52703e4d6643bc
workflow-type: tm+mt
source-wordcount: '1578'
ht-degree: 1%

---

# Configuración de la búsqueda para la IU de AEM Assets {#id192SC800MY4}

De forma predeterminada, AEM no reconoce el contenido DITA, por lo que no proporciona ningún mecanismo para buscar contenido DITA dentro de su repositorio. Además, no hay capacidad de OOTB para buscar contenido en función de su UUID. AEM Guides permite añadir las funciones de búsqueda de contenido DITA y búsqueda basada en UUID en el repositorio de AEM.

La configuración de la búsqueda de contenido DITA implica las siguientes tareas:

1. [Añadir el componente de búsqueda Elemento DITA en la IU de Assets](#id192SF0F50HS)
1. [Añadir un componente de búsqueda basado en UUID en la interfaz de usuario de Assets](#id2034F04K05Z)
1. [Proporcionar permisos a los usuarios](#id192SF0G0RUI)
1. [Agregar elementos o atributos personalizados en la búsqueda](#id192SF0G10YK)
1. [Extracción de metadatos de contenido existente](#id192SF0GA0HT)

Además de agregar la capacidad de búsqueda, también puede configurar las carpetas que no deben incluirse en la búsqueda. Para obtener más información, consulte [Excluir archivos temporales de los resultados de búsqueda](#id197AHI0035Z).

## Añadir el componente de búsqueda Elemento DITA en la IU de Assets {#id192SF0F50HS}

Realice lo siguiente para añadir el componente de búsqueda de contenido DITA en la interfaz de usuario de AEM Assets:

1. Inicie sesión en Adobe Experience Manager como administrador.

1. Haz clic en el vínculo **Adobe Experience Manager** de la parte superior y elige **Herramientas**.

1. Seleccione **General** de la lista de herramientas y haga clic en el icono **Buscar Forms**.

1. En la lista **Buscar en Forms**, seleccione **Carril de búsqueda de administración de Assets**.

1. Haga clic en **Editar**.
1. En la ficha **Seleccionar predicado**, desplácese hasta el final de la lista.

1. Arrastre y suelte **Predicado de elemento DITA** en la ubicación requerida en el formulario de búsqueda.

   ![](assets/drag-search-predicate.png)

1. Haga clic en **Listo** para guardar los cambios.

   Al acceder a la opción Filtros en la interfaz de usuario de Assets, se obtiene la opción de filtrado de búsqueda de elementos DITA.

   ![](assets/search-filter-asset-console.png)


## Añadir un componente de búsqueda basado en UUID en la interfaz de usuario de Assets {#id2034F04K05Z}

Realice lo siguiente para agregar un componente de búsqueda basado en UUID en la interfaz de usuario de AEM Assets:

1. Inicie sesión en Adobe Experience Manager como administrador.

1. Haz clic en el vínculo **Adobe Experience Manager** de la parte superior y elige **Herramientas**.

1. Seleccione **General** de la lista de herramientas y haga clic en el icono **Buscar Forms**.

1. En la lista **Buscar en Forms**, seleccione **Carril de búsqueda de administración de Assets**.

1. Haga clic en **Editar**.
1. En la ficha **Seleccionar predicado**, elija **Predicado de propiedad** y arrástrelo y suéltelo en la ubicación requerida en el formulario de búsqueda.

1. En la ficha **Configuración**, proporcione los siguientes detalles para el componente **Predicado de propiedad** recién agregado:

   - **Etiqueta de campo**: UUID
   - **Nombre de propiedad**: jcr:content/fmUuid
1. Haga clic en **Listo** para guardar los cambios.

   Al acceder a la opción Filtros en la interfaz de usuario de Assets, obtendrá la opción de filtrado de búsqueda basada en UUIS.


## Proporcionar permisos a los usuarios {#id192SF0G0RUI}

Los autores y editores necesitarían recibir permisos explícitos para poder acceder a las funcionalidades de búsqueda desde la interfaz de usuario de Assets. Si no concede estos permisos, los usuarios no podrán buscar contenido DITA según sus valores de elemento/atributo o UUID.

Siga estos pasos para proporcionar acceso a la función de búsqueda DITA:

1. Acceda a la página de permisos de usuarios y grupos.

1. Busque el grupo de usuarios o un usuario individual al que desee dar acceso. Por ejemplo, para dar acceso a todos los usuarios del grupo de autores, escriba autores en el campo **Filtrar consulta** y presione **Entrar**.

   ![](assets/authors-group-permission.png)

1. Seleccione el grupo **authors**.

1. En el panel derecho, seleccione la ficha **Permisos**.

1. Vaya a la siguiente ubicación de carpeta:

   /conf/global/settings/dam/search

1. Conceda permiso para **leer** en la carpeta de búsqueda.

   ![](assets/read-permission-authors.png)

1. Haga clic en **Guardar**.


El usuario o grupo de usuarios seleccionado ahora tendrá acceso a la función de contenido DITA de búsqueda en la interfaz de usuario de Assets.

## Agregar elementos o atributos personalizados en la búsqueda {#id192SF0G10YK}

Para que funcione la búsqueda DITA, es necesario realizar un cierto preprocesamiento del contenido DITA. Este paso de preprocesamiento extrae contenido selectivo de temas y mapas DITA individuales, de modo que se pueda indexar para realizar búsquedas más rápidas. Internamente, este proceso se denomina *Serialización*. La serialización de archivos DITA tiene lugar durante la carga de contenido o también se puede ejecutar bajo demanda. Utiliza un fichero de configuración para determinar la cantidad de contenido de cada fichero DITA que debe indexarse. La ubicación predeterminada del archivo de serialización es:

/libs/fmdita/config/serializationconfig.xml

La configuración de búsqueda predeterminada permite buscar todos los elementos y atributos dentro del elemento DITA `prolog`. Si desea buscar basándose en otros elementos o atributos, debe configurar el archivo de serialización de búsqueda.

>[!NOTE]
>
> Si desea ir con la configuración de búsqueda predeterminada dentro del elemento `prolog`, puede omitir este proceso.

Este archivo contiene dos secciones principales: conjunto de atributos y conjunto de reglas. A continuación se muestra un fragmento de la sección del conjunto de reglas:

```
<ruleset filetypes="xml dita"><!-- Element rules --><rule xpath="//[contains(@class, 'topic/topic')]/[contains(@class, 'topic/prolog')]//*[not(*)]" text="yes" attributeset="all-attrs" /><!-- Attribute rules --><rule xpath="//[contains(@class, 'topic/topic')]/[contains(@class, 'topic/prolog')]///@[local-name() != 'class']" /></ruleset>
```

En la sección del conjunto de reglas, puede especificar:

- Reglas para extraer los elementos

- Reglas para extraer atributos


Una regla consta de lo siguiente:

**xpath**: consulta XPath que recupera los elementos o atributos de archivos DITA. La configuración predeterminada para la regla de elemento recupera todos los elementos `prolog`. Además, la configuración predeterminada de la regla de atributos recupera todos los atributos de `prolog` elementos. Puede especificar una consulta XPath para serializar los elementos o atributos que desea buscar.

La consulta XPath contiene el nombre de clase del tipo de documento. La clase `topic/topic` se utiliza para documentos DITA de tipo de tema. Si desea crear una regla para otros documentos DITA, debe utilizar los siguientes nombres de clase:

| Tipo de documento | Nombre de clase |
|-------------|----------|
| Tema | - tema/tema |
| Tarea | - tema/tema tarea/tarea |
| Concepto | - tema/concepto del tema/concepto |
| Referencia | - tema/referencia/referencia del tema |
| Mapa | - mapa/mapa |

**texto**: si desea buscar el texto dentro del elemento especificado, especifique el valor yes. Si especifica no como valor, solo se serializan los atributos dentro del elemento. Los atributos que desea buscar deben especificarse en la sección de conjuntos de atributos.

**attributeset**: especifique el identificador del conjunto de atributos que desea asociar con esta regla. El valor all-attrs es un caso especial para indicar que todos los atributos de esta regla deben serializarse.

Un conjunto de atributos contiene una lista de atributos que desea buscar en el contenido DITA. El conjunto de atributos contiene lo siguiente:

**id**: un identificador único para el conjunto de atributos. Este ID se especifica en el parámetro attributeSet de un conjunto de reglas.

**atributo** - Una lista de atributos que desea buscar. Para cada atributo, debe crear una entrada individual en el elemento `attribute`.

Realice los siguientes pasos para agregar elementos o atributos DITA personalizados en el archivo de serialización de búsqueda:

1. Utilice el Administrador de paquetes para descargar el archivo /libs/fmdita/config/serializationconfig.xml.

1. Cree un nodo de superposición de la carpeta `config` dentro del nodo `apps`.

1. Vaya al archivo de configuración disponible en el nodo `apps`:

   `/apps/fmdita/config/serializationconfig.xml`

1. Añada los conjuntos de reglas de elementos o atributos necesarios.

1. Confirme los cambios y ejecute la canalización \(CI/CD\) de Cloud Manager para implementar los cambios de configuración.


La nueva información de serialización se almacena y activa para la búsqueda. Sin embargo, es necesario extraer los metadatos del contenido DITA existente para que estén disponibles para la búsqueda.

## Extracción de metadatos de contenido existente {#id192SF0GA0HT}

Una vez que haya realizado algún cambio en el archivo de serialización de búsqueda predeterminado, debe habilitar la opción Extracción de metadatos DITA en el paquete *com.adobe.fmdita.config.ConfigManager* y luego ejecutar el flujo de trabajo para extraer metadatos. De este modo se extraen los metadatos requeridos de los ficheros DITA existentes y éstos quedan disponibles para la búsqueda.

Si crea nuevos archivos o edita cualquier archivo después de actualizar el archivo de serialización, los metadatos se extraen automáticamente de esos archivos. El proceso de extracción de metadatos solo es necesario para los archivos que ya existen en el repositorio de AEM.

La extracción de metadatos de ficheros DITA existentes implica dos tareas:

1. Habilitar la opción de extracción de metadatos en configMgr
1. Ejecución del flujo de trabajo de extracción de metadatos

Siga las instrucciones indicadas en [Anulaciones de configuración](download-install-additional-config-override.md#) para crear el archivo de configuración. En el archivo de configuración, proporcione los siguientes detalles \(property\) para configurar la opción de extracción de metadatos:

| PID | Clave de propiedad | Valor de propiedad |
|---|------------|--------------|
| `com.adobe.fmdita.config.ConfigManager` | `dita.serialization` | Booleano \(true/false\).<br> **Valor predeterminado**: `false` |

Siga estos pasos para ejecutar el flujo de trabajo de extracción de metadatos:

1. Inicie sesión en Adobe Experience Manager como administrador.

1. Haz clic en el vínculo **Adobe Experience Manager** de la parte superior y elige **Herramientas**.

1. Seleccione **Guías** de la lista de herramientas y haga clic en el mosaico **Extracción de metadatos DITA**.

1. Si desea extraer metadatos de un solo archivo y sus dependencias, haga clic en el vínculo **Seleccionar un archivo** y busque un archivo.

1. Si desea extraer metadatos de varios archivos dentro de una carpeta, haga clic en el vínculo **Seleccionar carpeta\(s\)**, busque y seleccione la carpeta requerida. Haga clic en el botón **Agregar** para agregar la carpeta a la lista de tareas de serialización.

   >[!NOTE]
   >
   > Puede seleccionar y agregar varias carpetas a una tarea de serialización.

1. Haga clic en **Iniciar**.

1. En el diálogo Confirmar extracción de metadatos, haga clic en **Aceptar**.


## Excluir archivos temporales de los resultados de búsqueda {#id197AHI0035Z}

De forma predeterminada, la búsqueda se realiza en todo el repositorio de AEM. Podría haber algunas ubicaciones que le gustaría excluir de la búsqueda. Por ejemplo, cuando se inicia el flujo de trabajo de traducción de contenido, los archivos no aprobados permanecen en una ubicación de carpeta temporal. Al realizar la búsqueda, los archivos de esta ubicación temporal también se devuelven en los resultados de la búsqueda.

Para evitar que AEM Guides busque en la ubicación de la carpeta de traducción temporal, debe agregar la ubicación de la carpeta temporal en la lista de exclusión.

Realice los siguientes pasos para excluir la carpeta de traducción temporal de la búsqueda:

>[!NOTE]
>
> Puede agregar cualquier otra ubicación de carpeta a la lista de exclusión mediante este procedimiento. Para obtener más información acerca de cómo trabajar con índices, vea [Búsqueda e indexación de contenido](https://experienceleague.adobe.com/docs/experience-manager-cloud-service/operations/indexing.html?lang=es).

1. Agregue la siguiente propiedad en el índice damAssetLucene personalizado:

   | Nombre de la propiedad | Tipo | Valor  |
   |-------------|----|-----|
   | excludedPaths | Cadena\[\] | Agregue el siguiente valor a esta propiedad:<br> `/content/dam/projects/translation\_output` |

1. Vaya al nodo lucene disponible en la siguiente ubicación:

   /oak:index/lucene

1. Agregue la siguiente propiedad en el nodo lucene:

   | Nombre de la propiedad | Tipo | Valor  |
   |-------------|----|-----|
   | excludedPaths | Cadena\[\] | Agregue los siguientes valores a esta propiedad:<br> `/content/dam/projects/translation\_output` |
