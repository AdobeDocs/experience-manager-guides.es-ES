---
title: Notas de versión | Instrucciones de actualización y problemas corregidos en la versión 4.3.1 de Adobe Experience Manager Guides
description: Obtenga información acerca de las correcciones de errores y cómo actualizar a las versiones 4.3.1 de Adobe Experience Manager Guides
exl-id: 3fb6dc31-ec6e-40f5-ab3f-a6e591da315e
feature: Release Notes
role: Leader
source-git-commit: 6e23f52fc9124d0f07f8108da1b5fe574f553469
workflow-type: tm+mt
source-wordcount: '1307'
ht-degree: 1%

---

# Versión 4.3.1 de Adobe Experience Manager Guides (octubre de 2023)

Esta nota de la versión cubre las instrucciones de actualización, la matriz de compatibilidad y los problemas corregidos en la versión 4.3.1 de Adobe Experience Manager Guides (más adelante denominada *Experience Manager Guides*).

Para obtener más información sobre las nuevas características y mejoras, consulte [Novedades de la versión 4.3.1 de Adobe Experience Manager Guides](./whats-new-4-3-1-release.md).

## Actualización a la versión 4.3.1 de Experience Manager Guides


Puede actualizar fácilmente su versión actual de Experience Manager Guides a la versión 4.3.1. Antes de continuar actualizando a la versión 4.3.1 de Experience Manager Guides, debe tener en cuenta los siguientes puntos:
Puede actualizar su versión actual de Experience Manager Guides a la versión 4.3.1


- Si utiliza las versiones 4.3.0, 4.2 o 4.2.1, puede actualizar directamente a la versión 4.3.1.
- Si utiliza la versión 4.1 o 4.1.x, debe actualizar a las versiones 4.3.0, 4.2 o 4.2.x antes de actualizar a la versión 4.3.1.
- Si está utilizando la versión 4.0, debe actualizar a la versión 4.2 antes de actualizar a la versión 4.3.1.
- Si utiliza la versión 3.8.5, debe actualizar a la versión 4.0 antes de actualizar a la versión 4.2.
- Si su versión es anterior a la 3.8.5, consulte la sección Actualización de Experience Manager Guides en la guía de instalación específica del producto.


>[!NOTE]
>
>Debe instalar AEM Service Pack antes de actualizar la versión de Experience Manager Guides.

Para obtener más información, consulte [Instrucciones de actualización](../install-guide/upgrade-xml-documentation.md).

## Matriz de compatibilidad

Esta sección enumera la matriz de compatibilidad para las aplicaciones de software compatibles con la versión 4.3.1 de Experience Manager Guides.

### Adobe Experience Manager

**4.3.1 sin UUID**
Paquete de servicio 18, 17, 16, 15 o 14 de la versión 6.5

**4.3.1 UUID**
Paquete de servicio 18, 17, 16, 15 o 14 de la versión 6.5

Para obtener más información, consulte la sección *Requisitos técnicos* en la guía Instalar y configurar Adobe Experience Manager Guides.

### FRAMEMAKER y FRAMEMAKER PUBLISHING SERVER

| Versión | FMPS 2022 | FMPS 2020 | Fm 2022 | Fm 2020 |
| --- | --- | --- | --- | --- |
| 4.3.1 (no UUID) | 2022 o superior | 2020.2 o superior* | 2022 o superior | 2020.3 o superior |
| 4.3.1 (UUID) | 2022 o superior | 2020.2 o superior* | 2022 o superior | 2020.4 o superior |
| | | | | |

*Las condiciones y de línea de base creadas en AEM son compatibles con las versiones de FMPS a partir de 2020.2.

### Conector de oxígeno

| Versión | Ventanas de conector de oxígeno | Conector de oxígeno Mac | Editar en ventanas de oxígeno | Editar en Oxygen Mac |
| --- | --- | --- |--- |--- |
| 4.3.1 (no UUID) | 2.3-regular-5 | 2.3-regular-5 | 1,6 | 1,6 |
| 4.3.1 (UUID) | 3.2-uuid-5 | 3.2-uuid-5 | 2,3 | 2,3 |
|  |  |   | | |



### Versión de plantilla de base de conocimiento

| Nombre del paquete de componentes | Versión de componentes | Versión de plantilla |
|---|---|---|
| Paquete de contenido de componentes de Experience Manager Guides para Cloud Service | dxml-components.all-1.2.2 | aem-site-template-dxml.all-1.0.15 |

## Problemas solucionados

A continuación se enumeran los errores corregidos en varias áreas:

### Creación

- Las horas de la tarde no se establecen en **Date** para la creación de líneas de base. (12712)
- No se puede pegar el código JSON en el elemento `<codeblock>` del editor web. (12326)
- Los cambios de versión no guardados y los indicadores correspondientes no se muestran para los archivos grandes. (11784)
- Al editar en coreano, el primer carácter cambia al predeterminado. (10049)

- El prefijo se duplica en el modo de vista previa del editor web. (13133)
- `Choicetable` filas no se muestran o no se pueden seleccionar. (12616)
- El editor web genera errores de validación en escenarios específicos al crear un tema mediante un esquema personalizado. (12576)
- Las referencias a la plantilla de tema ditaval no crean una copia en la carpeta de contenido al crear un mapa a partir de la plantilla de mapa. (12150)

- El cuadro de búsqueda de los mapas DITA no tiene un botón de cierre. (11867)
- Al guardar archivos largos en el Editor Web, `DirtyChecker` genera una excepción con un seguimiento de pila largo y rellena los archivos de registro. (11860)
- La creación de temas DITA requiere permiso de eliminación en el nodo de carpeta correspondiente, aunque el mapa se puede crear con permiso de escritura. (11706)
- El editor web muestra un título incorrecto cuando hay una barra diagonal. (10949)

- Si el título de un tema contiene una barra &quot;/&quot;, la pestaña del editor solo muestra las cartas que vienen después. (13455)
- La previsualización de la imagen no desaparece después de mostrarla en el Editor. (13454)
- Algunas de las versiones existentes o sus etiquetas no se muestran en el Historial de versiones después de la actualización a la versión 4.x. (13247)
- El panel Historial de versiones en la IU de Assets muestra una marca de tiempo incorrecta para el campo **Actual**. (12624)
- El tema con título de conref no se resuelve en la vista de repositorio o en la vista de mapa.(13304)


### Publicación

- PDF nativo | El orden de los temas no se corrige cuando se genera la salida de PDF. (13157)
- PDF nativo| No hay ninguna etiqueta de estilo predeterminada disponible para el elemento `<p>`. (12559)
- PDF nativo | Los estilos en línea aplicados al área de contenido no se aplican a los temas de la materia principal y de la materia secundaria. (13510)
- El atributo `DeliveryTarget` no se propaga al generar la salida del sitio de AEM.  (13132)
- El flujo de trabajo **Publish** se atascó al generar la salida del sitio AEM para contenido con ciertos errores. (12000)

- PDF nativo | La inclusión de varias expresiones XFR extiende el texto más allá del ancho de columna. (13004)
- PDF nativo | Cuando el tema y el título tienen el mismo ID, se produce una generación incorrecta de la salida de PDF. (12644)
- PDF nativo | Al agregar una clase de salida a un elemento `<topicref>` principal en un mapa DITA y aplicar un estilo personalizado a la clase de salida, el estilo se aplica a los elementos dentro del cuerpo del tema, incluidos los títulos de sección. (12166)
- La publicación incremental no funciona si un mapa DITA tiene varios ditavalrefs. (12117)
- Sitio de AEM | Al crear un mapa con keydef apuntando a un tema como variable y agregar processing-role=resource-only, se crean algunas páginas inesperadas. (12099)
- Si se utiliza algún recurso de DAM de AEM en cualquier salida que no sea el sitio de AEM, los metadatos &quot;jcr:createdBy&quot; no reflejarán el nombre del editor o del usuario que modificó por última vez el tema o el mapa DITA. (12090)
- AEM Sites | El mapa DITA con el encabezado del tema en el título de navegación (con caracteres no compatibles) conduce a direcciones URL de página incorrectas. (11978)
- PDF nativo | Se producen problemas en la compatibilidad de topichead / topicmeta / navtitle en Frontmatter y Backmatter. (11969)
- PDF nativo | La generación de PDF para documentos grandes lleva mucho tiempo. (11955)
- PDF nativo | Al cambiar el nombre de un ajuste preestablecido, se produce una NullPointerException mientras se genera una salida de PDF. (11889)
- El contenido de `<conref>` no se muestra en la salida de PDF. (11131)
- Se agrega un espacio adicional dentro de los elementos `<div>` al alternar entre la vista Autor y Source en el editor de diseño de página. (10750)
- El contenido replicado en AEM Cloud Manager no es visible en la instancia de publicación. (9564)


### Administración

- El historial de versiones no se muestra aunque la propiedad `dc:format` no esté presente para un recurso. (10463)
- La referencia de contenido se interrumpe al copiar y pegar archivos DITA cuando el ID del tema no es el mismo que el GUID. (12614)
- En las líneas de base dinámicas, la lista de etiquetas no se extrae de las referencias directas de la copia de trabajo de un mapa DITA. (11917)
- La línea de base muestra un número incorrecto de archivos en el tablero de mapas al utilizar la funcionalidad Examinar todos los temas. (13265)
- En el Editor Web, la instantánea muestra el título de la versión anterior en lugar de la versión seleccionada del fichero DITA. (13444)

### Revisión

- La revisión de un tema muestra comentarios incorrectos. (13453)
- El botón Cerrar de la página Revisar de Experience Manager Guides lleva a los usuarios a la página principal de AEM. (13535)
- Los archivos adjuntos no se muestran en el panel derecho del editor para un tema de revisión. (13011)



### Traducción

- La línea de base exportada desde el panel **Translation** produce un error y no se abre en el idioma de destino. (13466)

- Se crean nuevos proyectos de traducción en lugar de agregar nuevos trabajos a los proyectos de traducción existentes seleccionados.  (10214)
- El título del archivo traducido se muestra en lugar del título del archivo de origen. (11630)
- La aprobación automática no funciona a veces y se producen excepciones si se establece un valor incorrecto en Estado de traducción. (13607)
- La línea de base exportada desde el panel de traducción produce un error y no se abre en el idioma de destino. (12993)
- Faltan algunos archivos al usar Líneas bases en la traducción. (13021)
