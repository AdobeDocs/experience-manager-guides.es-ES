---
title: Icono de configuración para tipos de datos personalizados
description: AEM Obtenga información sobre cómo definir iconos para tipos de datos personalizados para mostrar su icono en diferentes interfaces de usuario en
source-git-commit: ce2f5e4ab6b05fbce7b8384ff59091ebf9bab7be
workflow-type: tm+mt
source-wordcount: '484'
ht-degree: 0%

---

# Configuración del icono para tipos de datos personalizados (tema o mapa)


## Declaración de problema

AEM Con el esquema personalizado utilizado en las guías de recursos, puede crear temas o tipos de asignación personalizados y, con él, puede observar que los temas o los mapas personalizados no se muestran en la interfaz de usuario del editor web o de Assets. Vea la captura de pantalla como referencia  (../assets/authoring/custom-ditatype-icon-notshown.png)

Por lo tanto, para asignar un icono a los tipos de tema/mapa personalizados, debe hacer lo siguiente:
- Buscar el tipo de tema o asignación personalizado
- Escriba estilos para añadir el icono deseado para el tipo personalizado


Podemos implementar los pasos anteriores para mostrar el icono en el editor web (vista de repositorio) así como en la interfaz de usuario de Assets. A continuación se muestran los pasos para ambas


## Icono para mostrar un tema o un mapa personalizado en la vista del editor web

Paso 1: Determine el tipo de dato para el tema/mapa de datos personalizado: Abra la vista del repositorio en web-editor > abrir la consola del desarrollador en el explorador, Inspect el espacio de icono junto al tema/mapa enumerado, compruebe la clase asignada al tema personalizado. Vea la captura de pantalla  (../assets/authoring/custom-ditatype-icon-knowditatype.png) para obtener más información: utilizaremos esta clase para asignar un icono y escribir css para esto

Paso 2: Crear css y asignar un icono a este tipo de datos: Cree una biblioteca de cliente en /apps, le permite crear una cq:ClientLibraryFolder en la ruta deseada, agregarle categorías &quot;apps.fmdita.xml_editor.page&quot;, crear una carpeta &quot;assets&quot; en este directorio y agregar todos los iconos que desee utilizar para tipos de datos personalizados, agregar un archivo css en la carpeta de biblioteca de cliente, decir &quot;tree-Icon.css&quot;, agregarle el siguiente código

```
            .tree-item-icon {
                &.custommaptype {
                    background-image: url('assets/custommap.svg')
                }
                &.customtopictype {
                    background-image: url('assets/customtopic.svg')
                }
            }
```

    - agregue css.txt en la carpeta de la biblioteca de cliente y agregue referencia a &quot;tree-icon.css&quot; que acaba de crear.
    - guardar/implementar estos cambios
Captura de pantalla de referencia  (../assets/authoring/custom-ditatype-icon-define-webeditor-styles.png) para obtener más información.

Y el resultado final se muestra en la captura de pantalla  (../assets/authoring/custom-ditatype-icon-webeditor-showstyles.png)


## Mostrando icono para el tema o el mapa personalizado en la IU de Assets

Paso 1: determinación del tipo de dita del tema/mapa de dita personalizado: esto se explica en el Paso 1 de los métodos anteriores

Paso 2: Crear JavaScript para definir qué iconos cargar para el tipo de datos personalizado para tipos de temas/mapas personalizados - Crear una biblioteca de cliente en /apps, permite crear una cq:ClientLibraryFolder en la ruta deseada - agregarle las siguientes propiedades: - &quot;categories&quot;(multivalue string) value como &quot;dam.gui.admin.coral&quot; - &quot;dependencies&quot;(multivalue string) value como &quot;libs.fmdita.versioncontrol&quot; - Crear una copia del archivo &quot;/libs/fmdita/clientlibs/clientlibs/xmleditor/clientlib-dam/topic_type.js&quot; en este directorio /apps - editar el &quot;topic_type.js&quot; copiado y cambiar/agregar personalizado ictype en la variable &quot;typeImageNameMap&quot;: también puede cambiar la ruta de la carpeta de imágenes cambiando el valor de la variable &quot;parentImagePath&quot; a donde se almacenan los iconos personalizados. Cree un archivo llamado js.txt en la carpeta de biblioteca del cliente y agregue referencia a &quot;topic_type.js&quot;. Guarde o implemente estos cambios.  (../assets/authoring/custom-ditatype-icon-define-assetsui-styles.png) para obtener más información.

Y el resultado final aparecerá como se muestra en la captura de pantalla  (../assets/authoring/custom-ditatype-icon-assetsui-showstyles.png)