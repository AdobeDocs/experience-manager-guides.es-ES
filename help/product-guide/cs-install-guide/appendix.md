---
title: Apéndice
description: Obtenga información sobre cómo preparar documentos de InDesign para la migración
exl-id: 71b09039-b220-45f3-b334-c23f5b09dadc
feature: InDesign File Conversion, Troubleshooting
role: Admin
level: Experienced
source-git-commit: be06612d832785a91a3b2a89b84e0c2438ba30f2
workflow-type: tm+mt
source-wordcount: '2852'
ht-degree: 0%

---

# Apéndice {#id195AD0L60Y4}

## Solución de problemas de AEM Guides

Una vez que haya instalado y configurado AEM Guides, puede solucionar los problemas.

## Validar referencias

Puede ejecutar los scripts dados para validar las referencias. Estos scripts pueden ayudarle a identificar las referencias rotas y, a continuación, aplicarles parches o corregirlas.

- `/bin/fmdita/validatebtree?operation=validate`: informa de cualquier referencia de contenido interrumpido, pero no las corrige.

- `/bin/fmdita/validatebtree?operation=patch`: enumera las referencias de contenido interrumpido, las revisiones o las correcciones.


**Validar script**

Realice los siguientes pasos para comprobar las referencias mediante el script de validación disponible en el paquete del producto:

1. Ejecute el script de validación \[`/bin/fmdita/validatebtree?operation=validate`\] para comprobar si hay alguna referencia rota nueva.
1. Si la secuencia de comandos validate informa de algún error, puede aplicar parches con la secuencia de comandos patch.
1. Registre los detalles que se proporcionan a continuación y, si es necesario, compártalos con el equipo de éxito del cliente:
1. &#x200B;
   - Registros impresos por script de validación
- Paquete de &quot;`/content/fmdita/references`&quot;
- Cualquier otro detalle requerido según el escenario notificado

**Script de parche**

Realice los siguientes pasos para aplicar parches a cualquier referencia rota mediante la secuencia de comandos patch disponible en el paquete del producto:

1. Ejecute el script de parche `[/bin/fmdita/validatebtree?operation=patch]` para corregir las referencias rotas. La ejecución del script tarda unos minutos e imprime los registros a medida que progresa. Una vez finalizada la ejecución, se imprime &quot;`Done`&quot; al final.

>[!NOTE]
>
> Se recomienda copiar y guardar los registros como referencia.

1. Una vez que el script de parche se haya ejecutado correctamente, puede realizar las siguientes comprobaciones:
1. &#x200B;
   - Compruebe que se ha creado un nuevo nodo &quot;`references_backup_<timestamp>"`&quot; en `/content/fmdita`
- Compruebe que las referencias se hayan corregido

**Registrador**

También puede crear un registrador independiente para esta ejecución de script, según los detalles que se indican a continuación:

- Agregar un registrador en la clase &quot;`adobe.fmdita.common.BTreeReferenceValidator`&quot;
- Definirlo en `DEBUG`

El archivo de registro creado registrará toda la información relacionada con la ejecución de secuencias de comandos y resulta útil en caso de que se agote el tiempo de espera de la sesión del explorador, al tiempo que se activa la secuencia de comandos desde el explorador.

## Preparar archivos de InDesign para la conversión {#id195DBF0045Z}

InDesign proporciona a los autores un completo conjunto de funciones para crear documentos atractivos y complejos. A menudo, esto significa que las distintas partes de un documento se colocan visualmente en la página, pero sin intentar proporcionar ningún flujo entre esos marcos de texto. Cuando no se define el &#39;*orden de lectura*&#39; de los marcos de texto, el archivo IDML contendrá artículos que pueden no seguir ningún orden significativo. El resultado final será uno o más temas DITA con párrafos, tablas y gráficos en orden aleatorio.

Aunque es posible editar el contenido DITA en un orden razonable en un editor DITA, es mucho más fácil corregir el fichero de InDesign antes de crear el fichero IDML. Esto se puede hacer sin alterar el aspecto del documento de origen. También tiene la ventaja de hacer accesible el documento fuente definiendo correctamente el orden de lectura.

***Marcos de texto de subprocesamiento***

El InDesign utiliza el término *&#39;threading&#39;* para el proceso de vincular un fotograma a otro. Para obtener más información acerca de los marcos de texto de subprocesamiento, vea el tema *[Subprocesamiento de texto](https://helpx.adobe.com/in/indesign/using/threading-text.html)* en la documentación del InDesign.

***Marcos superpuestos***

Algunos documentos de InDesign utilizan marcos superpuestos sin subprocesos por motivos de diseño. Puede resultar muy difícil combinar este contenido en el hilo principal. La mejor opción puede ser editar el resultado en el entorno DITA.

***historias de InDesign***

Cada flujo de contenido enlazado en un documento de InDesign se denomina &#39;*story*&#39;. Para obtener los mejores resultados, se recomienda mantener limitada la cantidad de historias. Sin embargo, hay algunas partes del documento que pueden no ser necesarias en la salida DITA. Por ejemplo, los pies de página rara vez son necesarios, pero pueden aparecer en medio de un tema si no se gestionan con cuidado.

La manera más fácil de excluir texto que no se requiere en el documento es darle una *Etiqueta de párrafo* especial que solo se usa para el contenido no deseado. Por ejemplo, en lugar de reutilizar un *\[párrafo básico\]* para el pie de página, cree una etiqueta *Pie de página* dedicada. A continuación, en el archivo MapStyle, simplemente configure *Footer* párrafos para que se suelten de esta manera:

```
<paraRule style="Footer" local="0" refactor="drop">
   <attributeRules createID="false"/>
</paraRule>
```

***Asignación a tipos de documento DITA***

Es esencial que el documento de origen tenga al menos un estilo de párrafo o un elemento que pueda marcar el inicio de un tema. Es común que los documentos usen *Heading1* como nombre de los títulos de nivel superior del documento. A continuación, se puede crear una asignación a partir de ese estilo a un tipo de documento DITA específico. Si el documento está bien organizado y el uso de *Heading1* es constante en todo, obtendrá buenos resultados.

***Varios tipos de documentos DITA***

Si es necesario convertir algunos de los *párrafos Heading1* a diferentes tipos de documento DITA, duplique el estilo de párrafo en InDesign. Asigne a estos estilos un nombre fácil de reconocer, como *Heading1\_genTask* o *Heading1\_Troubleshooting*, según corresponda. A continuación, configure el archivo mapStyle como se muestra a continuación:

```
<doctypes>
   <doctypeParaRule style="Heading1" local="0" mapToDoctype="concept">
      <attributeRules createID="true"/>
   </doctypeParaRule>
   <doctypeParaRule style="Heading1_genTask" local="0" mapToDoctype=" generalTask">
      <attributeRules createID="true"/>
   </doctypeParaRule>
   <doctypeParaRule style="Heading1_troubleshooting" local="0"mapToDoctype=" troubleshooting">
      <attributeRules createID="true"/>
   </doctypeParaRule>
</doctypes>
```

***Documentos de InDesign estructurados***

El InDesign tiene una relación estrecha con XML. Aunque un documento puede incluir una DTD XML y el artículo principal puede ser válido para esa DTD, también es posible crear documentos híbridos en los que parte del contenido sea XML, pero no se incluya ninguna DTD. Estos son los casos no deseados para una conversión correcta a DITA. Si un documento contiene elementos XML, intente guardar el resultado en XML y ver si los resultados son aceptables. Si no es así, el contenido DITA también incluirá contenido no válido o puede fallar por completo.

***Formato de tabla***

La conversión de las reglas de formato de tabla de InDesign al formato de tabla equivalente en DITA es un proceso complejo. Esto se debe a las abundantes funciones de formato disponibles en los archivos de origen en comparación con las opciones básicas proporcionadas por el modelo de tabla Oasis \(CALS\) utilizado en DITA. Se proporciona alineación de texto vertical y horizontal y proporciona resultados similares, aunque el texto justificado siempre se justifica según la dirección del texto, mientras que el InDesign permite Justificado a la izquierda y Justificado a la derecha.

El manejo de los separadores de columnas y filas por parte de InDesign es de nuevo mucho más capaz que las opciones básicas del modelo de tablas Oasis. El InDesign proporciona cuatro bordes de celda: Tipo de borde \(sólido o motivo\), Grosor de borde, Color de borde, Tinta de borde, Color de espacio de borde y Tinta de espacio de borde. Todos estos elementos deben asignarse a los bordes situados a la derecha y en la parte inferior de cada celda \(elemento de entrada\), donde las únicas opciones son 0 o 1: ocultar el borde o mostrar el borde.

La regla de borde en InDesign puede aplicarse en los siguientes niveles:

- Estilos de tabla
- Estilos de celda
- Anulaciones locales en cada celda

El proceso de conversión de InDesign a DITA aplica la regla de borde de la siguiente manera:

- Los estilos de tabla se asignan al atributo `colspec/@colsep` para las reglas verticales. Las reglas horizontales se asignan al atributo `row/@rowsep`. En ambos casos, si el borde no está definido, el atributo no se crea.
- Los estilos de celda se han asignado a los atributos `entry/@colsep` y `entry/@rowsep`. Estos valores anularán cualquier regla de borde derivada del estilo de tabla.
- Las anulaciones locales aplican el formato directamente a la celda y anulan los estilos de tabla y los estilos de celda.

***Patrones alternativos***

Los estilos de tabla de InDesign permiten que las reglas de columna y celda sigan un patrón alterno. Aunque esta función es compatible con la conversión, los resultados solo serán obvios cuando un grupo de patrones se asigne para mostrar la regla \(1\) y el otro grupo de patrones se asigne para ocultar la regla \(0\).

## Preparar el archivo de asignación para la migración de InDesign a DITA {#id194AF0003HT}

La conversión DITA correcta requiere un fichero de asignación que coincida con el contenido del documento de origen. Para los documentos de InDesign no estructurados, esto significa que es necesario asignar todos los estilos de párrafo y de carácter disponibles. Para los documentos de InDesign estructurado XML, todos los elementos de su DTD asociado deben estar asignados.

Los archivos de asignación para documentos de InDesign no estructurados y estructurados son diferentes. Esto se debe a los requisitos de procesamiento más complejos para convertir contenido de origen no estructurado a DITA.

A continuación se muestra un ejemplo del archivo de asignación:

```
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE styleMap SYSTEM "mapStyle.dtd">
<styleMap xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xsi:noNamespaceSchemaLocation="mapStyle.xsd" >
   <doctypes>
      <mapDoctypeParaRule root="itpx:stories" mapToDoctype="map">
         <attributeRules createID="true">
            <addNew name="outputclass" value="map"/>
         </attributeRules>
      </mapDoctypeParaRule>
      <doctypeParaRule style="Heading 1" local="0" mapToDoctype="concept">
         <attributeRules createID="true"/>
      </doctypeParaRule>
      <doctypeParaRule style="Heading A" local="0" mapToDoctype="topic">
         <attributeRules createID="true"/>
      </doctypeParaRule>
   </doctypes>
   <wrappingRules>
      <wrap elements="li+" context="number" wrapper="ol">
         <attributeRules createID="true"/>
      </wrap>
      <wrap elements="li+" context="bullet" wrapper="ul">
         <attributeRules createID="true"/>
      </wrap>
   </wrappingRules>
   <paragraphStyleRules>
      <paraRule style="Heading 2" local="0"  mapTo="p">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="Heading 3" local="0"  mapTo="p">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="List Paragraph" local="p[-|-|-|-|-|b|-|-]" context="bullet" mapTo="li">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="List Paragraph" local="p[-|-|-|-|-|n|-|-]" context="number" mapTo="li">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="List Paragraph" local="0" context="bullet" mapTo="li">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="Normal" local="0"  mapTo="p">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="Normal" local="p[-|-|-|-|-|b|-|-]" context="bullet" mapTo="li">
         <attributeRules createID="true"/>
      </paraRule>
      <paraRule style="Title" local="0"  mapTo="p">
         <attributeRules createID="true"/>
      </paraRule>
   </paragraphStyleRules>
   <characterStyleRules>
      <charRule style="Bold" local="0" mapTo="b">
         <attributeRules createID="false"/>
      </charRule>
      <charRule style="Code" local="0" mapTo="codeph">
         <attributeRules createID="false"/>
      </charRule>
      <charRule style="[No character style]" local="c[Bold|-|-|-|-|-|-|-]" mapTo="b">
         <attributeRules createID="false"/>
      </charRule>
      <charRule style="[No character style]" local="c[Italic|-|-|-|-|-|-|-]" mapTo="i">
         <attributeRules createID="false"/>
      </charRule>
   </characterStyleRules>
</styleMap>
```

El archivo de asignación es un archivo XML con una estructura simple que enumera todos los estilos de párrafo de origen y códigos de estilo de carácter. A continuación se explica el contenido del archivo:

**Asignación de estilo**

En el elemento `styleMap`, puede especificar dos atributos opcionales: `@map_date` y `@map_version` para registrar la versión del archivo de asignación.

**Tipo de documento**

El elemento `doctypes` enumera las asignaciones de temas y mapas DITA compatibles.

**Asignar reglas de párrafo de tipo de documento**

El elemento `mapDoctypeParaRule` es obligatorio. Los atributos de este elemento no se deben editar porque el elemento raíz del XML de origen siempre está asignado al elemento raíz `map` de la asignación DITA.

**Regla de párrafo de tipo de documento**

El elemento `doctypeParaRule` es obligatorio. Esto proporciona al proceso de conversión una forma de identificar el inicio de un nuevo tema. Normalmente, el atributo `@style` se utiliza solo con el atributo `@local` establecido en 0. Sin embargo, si siempre hay anulaciones de formato local en el estilo elegido, deberá agregar una regla para cada estilo más sus anulaciones locales. Esto es fácil de reconocer en el archivo de asignación generado donde sería posible encontrar esto o algo similar:

```
<paraRule style="Heading 1" local="0" mapTo="p">
   <attributeRules createID="true"/>
</paraRule>
<paraRule style="Heading 1" local="p[Italic|-|-|-|-|-|-|-]" mapTo="p">
   <attributeRules createID="true"/>
</paraRule>
```

En el ejemplo anterior, hay dos elementos `paraRule` para `@style` = &quot;Heading1&quot;. Simplemente, cree elementos `doctypeParaRule` equivalentes con el atributo `@mapToDoctype` establecido como obligatorio.

Los atributos utilizados en `doctypeParaRule` se explican a continuación:

- `@style`: nombre de un estilo en el documento de InDesign de origen.
- `@local`: vea [\#id194CG0V005Z](#id194CG0V005Z).
- `@mapToDoctype`: nombre de un tipo de tema DITA de una lista enumerada de todos los `doctypes` válidos.

**Reglas de ajuste de elementos**

Las reglas de ajuste de elementos definen las formas de ajustar o mover elementos del documento entrante a un elemento predefinido de acuerdo con un conjunto de valores de atributo.

***`wrap`elemento***

Este es un elemento opcional. El elemento `wrap` enumera los elementos que se ajustarán o moverán. El ajuste se suele utilizar cuando una serie de elementos debe recibir un elemento principal común. Por ejemplo, se están envolviendo varios elementos `li` en un elemento `ol`. Además, `wrap` se puede usar para mover elementos como títulos para figuras y tablas.

Los atributos utilizados en `wrap` se explican a continuación:

- `@element`: un signo más después de un nombre de elemento muestra que todos los elementos adyacentes con el mismo nombre se ajustarán en el elemento denominado en el atributo `@wrapper`.
- `@wrapper`: nombre del elemento envolvente.
- `@context`: proporciona una forma de restringir aún más la forma en que se ajusta un elemento determinado. El ejemplo siguiente muestra una forma de asignar una serie de elementos `li` en una lista ordenada `ol` o en una lista sin ordenar `ul` según el valor `@context` \(el contexto está definido en el elemento `paraRule`\):

  ```
  <wrap elements="li+" context="number" wrapper="ol">
     <attributeRules createID="true"/>
  </wrap>
  <wrap elements="li+" context="bullet" wrapper="ul">
     <attributeRules createID="true"/>
  </wrap>
  ```


El ejemplo siguiente muestra cómo crear un elemento `fig` a partir de un elemento `title` y un elemento `image`:

- `@elements`: los elementos enumerados y separados por una coma se incluirán en el elemento denominado en el atributo `@wrapper`. Debido a la práctica común de incluir títulos de figuras debajo de la imagen, el título será el elemento `title` inmediatamente después de `image`.

  La siguiente regla de ajuste:

  ```
  <wrap elements="title, image" context="FigTitle" wrapper="fig">
     <attributeRules createID="true"/>
  </wrap>
  ```

  Convierte el siguiente XML intermedio:

  ```
  <image href="Links/myImage.png" scale="59">
     <title>IDML2DITA workflow</title>
  ```

  En la siguiente estructura de figura DITA válida:

  ```
  <fig id="id397504">
     <title>IDML2DITA workflow</title>
     <image href="Links/myImage.png" scale="59">
  </fig>
  ```

- `@wrapper`: nombre del elemento envolvente.
- `@context`: proporciona una forma de restringir aún más la forma en que se ajusta un elemento determinado \(el contexto se define en el elemento `paraRule`\).

El siguiente ejemplo muestra cómo mover un(a) `title` a un(a) `table`:

- `@elements`: el elemento `title` que se encuentra inmediatamente antes o inmediatamente después de `table` se incluirá en el elemento denominado en el atributo `@wrapper`. Un predicado de estilo XPath puede identificar la posición del elemento title como `[before]` o `[after]`.

  Ejemplo: La siguiente regla de ajuste:

  ```
  <wrap elements="title[before]" context="TableTitle" wrapper="table">
     <attributeRules createID="true"/>
  </wrap>
  ```

  Convierte el siguiente XML intermedio:

  ```
  <title>IDML2DITA workflow</title>
  <table id="id289742" outputclass="BasicTable">
     <tgroup cols="2">
        <colspec colname="0" colwidth="0.7*">
           <colspec colname="1" colwidth="0.3*">
  ```

  En esta estructura de figura DITA válida:

  ```
  <table id="id289742" outputclass="BasicTable">
     <title>IDML2DITA workflow</title>
     <tgroup cols="2">
        <colspec colname="0" colwidth="0.7*">
           <colspec colname="1" colwidth="0.3*">
  ```

- `@wrapper`: nombre del elemento envolvente.

- `@context`: proporciona una forma de restringir aún más la forma en que se ajusta un elemento determinado \(el contexto se define en el elemento `paraRule`\).


**Reglas de estilo de párrafo**

Los elementos `paragraphStyleRule` se describen a continuación:

**&#x200B; elemento `paraRule`**

El elemento `paraRule` es obligatorio. Esto especifica las reglas de asignación para todos los estilos de párrafo. En un documento de InDesign, todo el texto está contenido en una subestructura de Estilos de párrafo, incluso los párrafos sin ningún estilo se denominan `\[No paragraph style\]`. Los corchetes indican un nombre de estilo de InDesign integrado.

>[!NOTE]
>
> Los corchetes indican un nombre de estilo de InDesign integrado.

Los atributos utilizados en `paraRule` se explican a continuación:

- `@style`: nombre de un estilo en el documento de InDesign de origen.
- `@local`: vea [\#id194CG0V005Z](#id194CG0V005Z).
- `@mapTo`: nombre de un elemento de destino DITA.

- `@context`: este atributo se usa para vincularse a una regla **wrap** específica cuando hay más de una opción de envoltorio disponible. Ejemplo: el elemento `li` puede estar envuelto en un elemento `ol` o `ul`. Para identificar los diferentes tipos de lista, puede utilizar un nombre de estilo específico o el atributo `@local` que puede mostrar lo siguiente:
   - `local="p[-|-|-|-|-|b|-|-]"` Donde el &#39;`b`&#39; del campo 6 indica un elemento de lista con viñetas. En este caso, establezca `@context` en &#39;`bullet`&#39;.
   - `local="p[-|-|-|-|-|n|-|-]"` Donde el &#39;`n`&#39; del campo 6 indica un elemento de lista numerado. En este caso, establezca `@context` en &#39;`number`&#39;.

- `@commentOut`: este atributo habilita el ajuste del elemento de destino en los comentarios XML para que la información no se pierda, pero el usuario la pueda administrar manualmente. Esto resulta útil si no se puede forzar que el contenido de origen se ajuste a las reglas de estructura DITA.

- `@refactor`: este atributo opcional tiene una opción de dos valores:

- `unwrap`: el elemento coincidente se quita al conservar su contenido.

- `drop`: se quitan el elemento coincidente y todo su contenido.


**Reglas de estilo de carácter**

Los elementos `charRule` se describen a continuación:

>[!NOTE]
>
> No habrá asignación para el estilo de carácter integrado `[No character style]` cuando `local="0"`, ya que se quitan durante el preprocesamiento.

***`charRule`elemento***

Este es un elemento opcional.

Estas son las reglas de asignación para todos los estilos de carácter. En un documento de InDesign, todo el texto está contenido en elementos secundarios de Estilos de carácter.

Los atributos utilizados en `charRule` se explican a continuación:

- `@style`: nombre de un estilo en el documento de InDesign de origen.
- `@local`: vea [\#id194CG0V005Z](#id194CG0V005Z).
- `@mapTo`: nombre de un elemento de destino DITA.
- `@refactor`: este atributo opcional tiene una opción de dos valores:
   - `unwrap`: el elemento coincidente se quita al conservar su contenido.

   - `drop`: se quitan el elemento coincidente y todo su contenido.


**Reglas de atributo**

Este elemento puede ser un elemento secundario de los siguientes contextos de elemento:

- `mapDoctypeParaRule`
- `mapDoctypeElemRule`
- `doctypeParaRule`
- `doctypeElemRule`
- `paraRule`
- `charRule`
- `elementRule`

El propósito de las reglas de atributos es administrar los atributos de los elementos coincidentes.

Dependiendo del contexto, los atributos siguientes están disponibles en el elemento `attributeRules`:

- `@createID`: genera un identificador único para los elementos coincidentes. Valores permitidos `true` o `false`. Disponible en todos los contextos.
- `@copyAll`: copia todos los atributos del contenido XML de origen sólo para archivos de origen estructurados. Los valores permitidos son `true` o `false`. Disponible para los contextos `mapDoctypeParaRule`, `mapDoctypeElemRule`, `doctypeElemRule` y `elementRule`.


Los atributos utilizados en `attributeRules` se explican a continuación:

>[!NOTE]
>
> Este elemento puede contener varios elementos secundarios.

- `addNew`: agrega un nuevo atributo al elemento coincidente. Disponible para todos los contextos. Tiene dos atributos:
   - `@name`: debe ser un nombre XML válido, preferiblemente válido para el contexto DITA.
   - `@value`: puede ser texto literal o una expresión XPath simple.
- `copyAtt`: copia un solo atributo en el destino mientras lo cambia de nombre de manera opcional en el proceso. El valor no cambia. Disponible para los contextos `mapDoctypeParaRule`, `mapDoctypeElemRule`, `doctypeElemRule` y `elementRule`. Cuando este elemento está presente, se supone que el valor `@copyAllAtts` es `false`. Tiene dos atributos:
   - `@name`: debe ser el nombre de un atributo presente en el elemento XML de origen.
   - `@mapTo`: debe ser un nombre XML válido, preferiblemente válido para el contexto DITA.

**Códigos de formato locales**

En cualquier documento de InDesign, es posible que los estilos de párrafo y los estilos de carácter lleven cientos de invalidaciones de formato diferentes. La mayoría de estas propiedades no proporcionan ninguna función útil en el proceso de conversión. Sin embargo, hemos identificado un conjunto básico de funciones de formato que no afectan a la semántica del documento y necesitan influir en el proceso de conversión.

Los atributos `@local` se presentan como un formato delimitado especial en el que se proporcionan ocho campos junto con un prefijo para mostrar el tipo de invalidación de formato. A continuación se enumeran los campos de códigos de formato:

- Prefijo **p** para la invalidación local de estilo para o **c** para la invalidación local de estilo de carácter.
- **Estilo de fuente** que es el nombre de la familia y propiedades como &#39;***Negrita cursiva condensada***&#39;.
- **Tamaño de fuente** en puntos.
- **Posición del carácter** para superíndice o subíndice.
- **Menos de** para el guion bajo.
- **Tachar** para tachar.
- **Código de lista** para identificar el tipo de lista como con viñetas o numerada; no siempre se usa en el InDesign.
- **Código de viñeta** enumera todos los tipos de viñetas definidos en el documento.
- **Código de número** enumera todos los estilos de numeración definidos en el documento.

El uso cuidadoso de esta función permite perder el formato local, lo que puede ayudar a mejorar la calidad de una transferencia del contenido con estilo a DITA. Este ejemplo se puede resolver en cursiva, texto de 16 puntos en una lista con viñetas: `p[Italic|16|-|-|-|b|-|-]`.

**Asignación de estructura**

El archivo de asignación de estructura es similar al archivo de asignación de estilo con una estructura simple que enumera todos los elementos de origen y los tipos de atributos relevantes. Se proporcionan dos atributos, `@map_date` y `@map_version`, para registrar la versión del archivo de asignación que se va a utilizar.

**Tipo de documento**

El elemento `doctypes` enumera las asignaciones de temas y mapas DITA compatibles.

**Asignar reglas de elemento de tipo de documento**

El elemento `mapDoctypeElemRule` es obligatorio. Los atributos de este elemento no se deben editar porque el elemento raíz del XML de origen siempre está asignado al elemento raíz `map` de la asignación DITA.

**Reglas de ajuste de elementos**

Consulte [\#id194CG600NY4](#id194CG600NY4).

**`elementRules`elemento**

Esto enumera todos los [\#id194CGC00SHS](#id194CGC00SHS)elementos.

**`elementRule`elemento**

El elemento `elementRule` es obligatorio. Estas son las reglas de asignación para todos los elementos de origen. Aunque un documento de InDesign contiene elementos de estilo no estructurados, estos se omiten para el contenido estructurado a menos que el procesamiento de &#39;***modo híbrido***&#39; esté habilitado.

Los atributos utilizados en `elementRule` se explican a continuación:

- `@elementName`: nombre de un elemento del documento de InDesign de origen.

- `@local`: vea [\#id194CG0V005Z](#id194CG0V005Z). \(Solo es útil para documentos híbridos\).

- `@mapTo`: nombre de un elemento de destino DITA.

- `@refactor`: este atributo opcional tiene una opción de dos valores:

   - `unwrap`: el elemento coincidente se quita al conservar su contenido.

   - `drop`: se quitan el elemento coincidente y todo su contenido.

- `@context`: este atributo se usa para vincular a una regla de ajuste específica cuando hay más de una opción de contenedor disponible. Ejemplo: el elemento `li` puede estar envuelto en un elemento `ol` o `ul`.

- `@commentOut`: este atributo habilita el ajuste del elemento de destino en los comentarios XML para que la información no se pierda, pero el usuario la pueda administrar manualmente. Esto resulta útil si no se puede forzar que el contenido de origen se ajuste a las reglas de estructura DITA.
