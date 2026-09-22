---
title: Notas de versión | Se han corregido problemas en la versión 2026.09.0 de Adobe Experience Manager Guides
description: Obtenga información acerca de las correcciones de errores en la versión 2026.09.0 de Adobe Experience Manager Guides as a Cloud Service.
source-git-commit: 71ddd55d2a6848449d5810701b60e9f69a29112b
workflow-type: tm+mt
source-wordcount: '1241'
ht-degree: 0%

---

# Se han corregido problemas en la versión 2026.09.0

Este artículo cubre los errores corregidos en varias áreas de la versión 2026.09.0 de Adobe Experience Manager Guides as a Cloud Service.

Para obtener más información sobre las nuevas características y mejoras, vea [Novedades de la versión 2026.09.0](./whats-new-2026-09-0.md).

Obtenga información acerca de [instrucciones de actualización para la versión 2026.09.0](./upgrade-instructions-2026-09-0.md).

## Editor 2.0

- Al copiar una tabla del modo Autor y pegarla en el modo Autor, se eliminan atributos como `colwidth` y cualquier otro atributo definido en `colspec`, lo que provoca que se pierda la configuración de ancho de columna. (GUIDES-52916)
- Espacio en blanco introducido inmediatamente antes de que se elimine una etiqueta en línea dentro de una celda de tabla `<entry>`. (GUIDES-49144)

## Creación

Esta sección trata sobre los errores corregidos en la creación que son comunes para Editor 1.0 y Editor 2.0.

- En pantallas de baja resolución, el cuadro de diálogo Insertar palabra clave no aparece al insertar una palabra clave desde la barra de herramientas, mientras que se abre como se espera al usar la opción **Más**. (GUIDES-48304)
- Al guardar un tema cuando la validación de Schematron está configurada con un archivo de reglas vacío, se muestra un mensaje de error genérico impreciso. (GUIDES-48106)
- Las reglas de Schematron que utilizan un contexto de nodo de texto no almacenan en déclencheur la validación. (GUIDES-14500)
- Al insertar una referencia cruzada usando la opción **vínculo web**, se agrega un vínculo `scope=local` y se modifica el valor `href`, en lugar de insertar un `scope=external` como se esperaba. (GUIDES-48457)
- Guardar un mapa de referencia genera una referencia rota en lugar de resolverse en el mapa correcto cuando un autor mueve el mapa al que se hace referencia mientras otro autor le agrega simultáneamente una referencia en un mapa no guardado. (GUIDES-47467)

## Administración de recursos

- La API de estado del recurso no devuelve el estado correcto para los recursos cuya ruta contiene una coma. (GUIDES-49065)
- El filtro de elementos DITA del carril de búsqueda de administración de Assets no aplica el valor introducido, por lo que los resultados de búsqueda no se filtran. (GUIDES-48450)
- La utilidad de depuración de versiones no se completa en varios casos, incluidos algunos tipos de archivo, recursos a los que les faltan metadatos e informes grandes, en lugar de completar la depuración y generar un informe preciso. (GUIDES-43453)
- Al cambiar el nombre de un recurso con un nombre de archivo basado en GUID a un GUID diferente mediante la operación Mover en la interfaz de usuario de Assets, se sustituye el GUID único original del recurso por el nuevo GUID. (GUIDES-43006)

## Publicación

- Cuando se genera una salida de AEM Sites (con asignación de componentes compuestos) con una línea de base dirigida a una versión anterior, el contenido de la página muestra correctamente esa versión anterior, pero los metadatos de la página muestran la versión actual en su lugar. (GUIDES-49325)
- Cuando las páginas se replican mediante activación masiva, las propiedades de seguimiento de replicación se establecen únicamente en la página raíz y no en las secundarias, lo que dificulta determinar qué contenido ha cambiado desde la última replicación. (GUIDES-37871)
- Cuando el campo **Etiqueta** del cuadro de diálogo Crear/Editar línea de base recibe el enfoque por primera vez, pegar o escribir el primer carácter no filtra correctamente las sugerencias de autocompletar y el campo muestra todas las sugerencias en lugar de los resultados filtrados. (GUIDES-50143)
- El filtrado de ramas genera páginas adicionales para los temas no deseados utilizados como `keydef` (que están marcados como `resource-only ="true"` por DITA-OT). (GUIDES-19701)
- La colección de mapas habilita la opción **Publish** para los ajustes preestablecidos que aún no se han generado. (GUIDES-50510)
- La sección Historial de publicaciones no muestra texto de marcador de posición cuando una colección de mapas recién creada no tiene registros de publicación. (GUIDES-50366)
- La aplicación de un perfil de color ICC a un ajuste preestablecido de PDF nativo provoca que la generación de salida falle y que los colores CMYK no se representen correctamente incluso cuando se utiliza una ruta de acceso de perfil directa. (GUIDES-47137)
- El ajuste de sangrado configurado en un ajuste preestablecido de PDF nativo no se refleja en la salida generada. (GUIDES-47034)
- El campo **Texto antes del salto** para la continuación de la tabla solo representa la cadena localizada y no reemplaza el marcador de posición del número de página. (GUIDES-32872)
- El explorador de perfiles ICC muestra incorrectamente los archivos DITA en lugar de mostrar únicamente los archivos ICC. (GUIDES-25017)
- Los comentarios del borrador no se representan en la salida nativa de PDF. (GUIDES-47044)
- Un comentario de borrador colocado dentro de un elemento `title` aparece inesperadamente en la salida publicada. (GUIDES-10686)
- En el tablero de mapas, al seleccionar un ajuste preestablecido diferente, se déclencheur una llamada para recuperar vínculos de igual a igual, lo que da como resultado un procesamiento adicional. (GUIDES-53703)

## Traducción

- Al iniciar una traducción con un proyecto XLIFF, se crea un proyecto vacío que nunca pasa a un estado en curso. (GUIDES-51759)
- Mover contenido de una carpeta de idioma a otra mediante la operación de movimiento de recursos impide que los autores seleccionen ese contenido para su traducción en el panel Traducción. (GUIDES-49386)
- Enviar recursos para su traducción mediante la opción **Agregar a proyecto de traducción existente** mientras otra solicitud de traducción (ya sea una creación de nuevo proyecto o una solicitud *Agregar a proyecto existente*) para el mismo proyecto sigue procesando los resultados en un conflicto. (GUIDES-49354)

## Línea de base

- La selección de línea de base guardada de un ajuste preestablecido se muestra incorrectamente como *Sin línea de base* después de eliminarse la línea de base o mientras se sigue creando una línea de base dinámica. (GUIDES-52690)

## Revisión

- Abrir el panel Revisar o aplicar un filtro de proyecto tarda un poco en cargar la lista de tareas. (GUIDES-48893)

## Informes

- La generación del informe Vínculos rotos para un mapa con un gran número de temas hace que la interfaz del informe permanezca atascada en el mensaje **Recuperando detalles de vínculos rotos** indefinidamente, lo que hace que el explorador no responda y, finalmente, haga que se bloquee. (GUIDES-37845)

## Contenido de aprendizaje

- Cuando se crea un nuevo tema de aprendizaje con un HTML o una plantilla de aprendizaje con un encabezado personalizado, el título del tema no aparece en el encabezado personalizado. (GUIDES-52343)
- El porcentaje de precisión calculado para una prueba de curso difiere ligeramente del valor esperado. (GUIDES-52346)
- En un curso, al intentar realizar una prueba, las puntuaciones difieren ligeramente de la puntuación calculada esperada. (GUIDES-52345)

## Problemas conocidos

Adobe ha identificado los siguientes problemas conocidos para la versión 2026.09.0:

- Al cambiar el estado del documento de un tema ya bloqueado, se actualiza todo el documento. (GUIDES-53905)
- Al utilizar la característica Vista previa mediante línea de base, se agota el tiempo de espera de las solicitudes de vista previa para asignaciones grandes (más de 10 000 temas) o asignaciones con un número elevado de `keydefs` (por ejemplo, 100 `keydefs` y 3500 temas). (GUIDES-54147)
- En los servidores de base de datos, cuando se obtiene una vista previa de un mapa que contiene un(a) `keydef` sin un(a) `href` con la opción Vista previa mediante línea de base habilitada, el(la) `keydef` no se resuelve. (GUIDES-53878)
- Las regiones de puntos interactivos configuradas en un recurso de mapa de imagen no son interactivas en el modo de vista previa, lo que impide a los autores validar los vínculos de puntos interactivos antes de publicar. (GUIDES-53398)<br>**Solución alternativa**: inserte la imagen que desea convertir en un mapa de imagen, seleccione **Editar mapa de imagen** del menú contextual y configure los vínculos de puntos interactivos.
- Cuando mueve un mapa con una línea de base existente a una carpeta diferente mientras el mapa está abierto, la opción **Vista previa mediante línea de base** permanece seleccionada en el modo Vista previa, pero la línea de base ya no aparece en la lista desplegable. (GUIDES-54284)<br>**Solución alternativa**: puede cerrar y volver a abrir el mapa para resolver el problema.
- En un entorno de AEM Cloud Service recién configurado (AEM as a Cloud Service SDK), al intentar crear un mapa o un archivo de tema se produce un error de *No se pudo crear el archivo* o *Error al recuperar la regla DTD*. (GUIDES-53904)<br>**Solución alternativa**: Puede reiniciar el entorno de AEM Cloud Service.
- Cuando dos autores trabajan en el mismo tema simultáneamente, bloquear un tema que un autor haya abierto durante algún tiempo no actualiza las propiedades de los metadatos, como el número de versión, las etiquetas, el estado del documento, las etiquetas y otros, incluso después de que el otro autor los haya cambiado, lo que provoca que se sigan mostrando valores obsoletos. (GUIDES-54810)<br>**Solución alternativa**: cierre y vuelva a abrir el tema para actualizar los metadatos y mostrar los valores más recientes.