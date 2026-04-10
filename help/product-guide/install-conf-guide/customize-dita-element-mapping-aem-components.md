---
title: Personalizar la asignación de elementos de datos con componentes de AEM
description: Obtenga información sobre cómo personalizar la asignación de elementos dita con componentes de AEM
feature: Output Generation
role: Admin
level: Experienced
source-git-commit: 834959a6a0e22cd5d2b2c5d0e57ceb6d45c0c666
workflow-type: tm+mt
source-wordcount: '1268'
ht-degree: 1%

---


# Personalización de la asignación de elementos DITA con componentes de AEM {#id1679J600HEL}

Los elementos DITA de AEM Guides se asignan a sus componentes AEM correspondientes. AEM Guides utiliza esta asignación en flujos de trabajo como la publicación y la revisión para convertir un elemento DITA en un componente de AEM correspondiente. La asignación se define en el archivo `elementmapping.xml`, al que se puede acceder mediante el administrador de paquetes para la configuración de Cloud Service y desde la dirección URL: `/libs/fmdita/config/elementmapping.xml` en el modo de CRXDE Lite para la configuración local.

>[!NOTE]
>
> No realice ninguna personalización en los archivos de configuración predeterminados disponibles en el nodo ``libs``. Debe crear una superposición del nodo ``libs`` en el nodo ``apps`` y actualizar los archivos necesarios solo en el nodo ``apps``.

Puede utilizar las asignaciones de elementos DITA predefinidas o asignar elementos DITA a los componentes personalizados de AEM. Para usar los componentes personalizados de AEM, debe comprender la estructura del archivo `elementmapping.xml`.

## estructura de elementmapping.xml

A continuación se explica una descripción general de alto nivel de la estructura de `elementmapping.xml`:

1. En cada elemento DITA se busca primero una asignación de componentes correspondiente basada en el nombre del elemento. Por ejemplo:

   ```XML
   <ditaelement>     
      <name>**substeps**</name>  
      <class>- topic/ol task/substeps</class>  
      <componentpath>dita/components/ditaolist</componentpath>  
      <type>COMPOSITE</type>  
      <target>para</target>
   </ditaelement>
   ```

   En el ejemplo anterior, todos los `substeps` elementos DITA se representan con el componente `dita/components/ditaolist`.

1. Si un elemento DITA no encuentra una coincidencia basada en el nombre, entonces se realiza una coincidencia basada en `class`. Por ejemplo:

   ```XML
   <ditaelement>  
      <name>topic</name>  
      <class>**- topic/topic**</class>  
      <componentpath>fmdita/components/dita/topic</componentpath>  
      <type>COMPOSITE</type>  
      <target>para</target>  
      <attributemap> 
         <attribute from="id" to="id" />  
      </attributemap>
   </ditaelement>
   ```

   En el ejemplo anterior, si no hay ninguna asignación definida para el elemento `task`, el elemento `task` se asigna al componente anterior porque `task` se hereda del componente `topic`.

1. Cuando un elemento tiene una asignación de componente correspondiente, el procesamiento posterior de sus elementos secundarios se determina por `type`. Por ejemplo:

   ```XML
   <ditaelement>  
      <name>title</name>  
      <class>- topic/title</class>  
      <componentpath>foundation/components/title</componentpath>  
      <type>**STANDALONE**</type>  
      <target>para</target>  
      <textprop>jcr:title</textprop>
   </ditaelement>
   ```

   `type` toma los siguientes valores:

   - COMPUESTO: la asignación del elemento al componente *también continúa para los elementos secundarios*.

   - INDEPENDIENTE: los elementos secundarios del elemento actual están *sin asignar más*.

   En el ejemplo anterior, si el elemento `<title>` tiene elementos secundarios, no se asignarán a ningún otro componente. El componente del elemento `<title>` es responsable de procesar todos los elementos secundarios dentro del elemento `<title>`.

1. Si hay varios componentes asignados a un único elemento DITA, se selecciona la mejor coincidencia para el elemento. Para seleccionar el componente que mejor se ajuste, se tiene en cuenta la especialización estructural y de dominio de los elementos DITA.

   Si hay elementos DITA con especialización de dominio y un componente está asignado para la especialización de dominio, se le asigna una prioridad alta a ese componente.

   Del mismo modo, si hay elementos DITA con especialización estructural y se asigna un componente para la especialización estructural, se le asigna una alta prioridad a dicho componente.

1. Puede usar `<attributemap>` en la asignación de elementos para asignar valores de atributo a las propiedades del nodo correspondiente.
1. `textprop` se puede usar para serializar el contenido de texto de un elemento DITA en una propiedad de nodo. Además, se puede utilizar varias veces en una etiqueta de elemento para serializar el contenido de texto en varias ubicaciones de la jerarquía publicada. También puede personalizar la ubicación y el nombre de la propiedad de destino. Por ejemplo:

   ```XML
   <ditaelement>
      <name>title</name>
      <componentpath>foundation/components/title</componentpath>
      <type>STANDALONE</type>
      <target>para</target>
       <textprop>**jcr:title**</textprop>
   </ditaelement>
   ```

   La asignación de elementos anterior especifica que el contenido de texto del elemento `<title>` se guardará como valor de una propiedad denominada `jcr:title` en el nodo de salida.

1. `xmlprop` se puede usar para serializar todo el XML de un elemento determinado en una propiedad de nodo. A continuación, el componente puede leer esta propiedad de nodo y realizar una representación personalizada. Por ejemplo:

   ```XML
   <ditaelement>
       <name>svg-container</name>
      <class>+ topic/foreign svg-d/svg-container</class>
       <componentpath>fmdita/components/dita/svg</componentpath>
       <type>STANDALONE</type>
       <target>para</target>
      <xmlprop>**data**</xmlprop>
   </ditaelement>
   ```

   La asignación de elementos anterior especifica que todo el marcado XML para el elemento `<svg-container>` se guardará como valor de una propiedad denominada `data` en el nodo de salida.

1. Hay una asignación de atributo especial para controlar la resolución de la ruta en el proceso de generación de resultados. Por ejemplo:

   ```XML
   <attributemap>
      <attribute from="href" to="fileReference" ispath="true" rel="source" />
      <attribute from="height" to="height" />
       <attribute from="width" to="width" />
   </attributemap>
   ```

   Para el elemento `attributemap` anterior, el atributo `href` del elemento DITA se asignará a una propiedad de nodo denominada `fileReference`. Ahora, dado que `ispath` está establecido en `true`, el proceso de generación de resultados resuelve esta ruta de acceso y la establece en la propiedad del nodo `fileReference`.

   El modo en que se produce esta resolución se determina en función del valor del atributo `rel` en la asignación de atributos.

   - Si es `rel=source`, el valor de `href` se resuelve con respecto al archivo de origen DITA que se está procesando actualmente. El valor de `href` se resuelve y se coloca en el valor de la propiedad `fileReference`.

   - Si es `rel=target`, el valor de `href` se resuelve con respecto a la ubicación de publicación raíz. El valor de `href` se resuelve y se coloca en el valor de la propiedad `fileReference`.

   Si no desea que se produzca ningún procesamiento previo o resolución en los atributos de ruta de acceso, no necesita especificar el atributo `ispath`. El valor se copia tal cual y el componente puede realizar la resolución necesaria.


## Esquema de elemento DITA

A continuación se muestra un ejemplo del esquema de elementos DITA en el archivo `elementmapping.xml`:

```XML
<ditaelement>        
    <name>element_name</name>    
    <class>element_class</class>    
    <componentpath>fmdita/components/dita/component_name</componentpath>    
    <type>COMPOSITE|STANDALONE</type>     
    <attributeprop>propname_a</attributeprop>      
    <textprop>propname_t</textprop>    
    <xmlprop>propname_x</xmlprop>     
    <xpath>xpath expression string</xpath>     
    <target>head|para</target>     
    <wrapelement>div</wrapelement>     
    <wrapclass>class_name</wrapclass>     
    <attributemap>         
        <attribute from="attrname"         to="propname"         ispath="true|false"         rel="source|target" />    
    </attributemap>    
    <skip>true|false</skip> 
</ditaelement>
```

En la tabla siguiente se describen los elementos del esquema de elementos DITA:

| Elemento | Descripción |
|-------|-----------|
| `<ditaelement>` | Nodo de nivel superior para cada elemento de asignación. |
| `<class>` | Atributo de clase del elemento DITA de destino para el que se está escribiendo el componente.<br> Por ejemplo, el atributo de clase para el tema DITA es: <br> `- topic/topic` |
| `<componentpath>` | Ruta CRXDE del componente de AEM asignado. |
| `<type>` | Valores posibles: <br> -   **COMPUESTO**: procesar también elementos secundarios <br> -   **STANDALONE**: omite el procesamiento de elementos secundarios |
| `<attributeprop>` | Se utiliza para asignar atributos y valores DITA serializados a nodos AEM como propiedad. Por ejemplo, si tiene el elemento `<note type="Caution">` y el componente asignado para este elemento tiene `<attributeprop>attr_t</ attributeprop>`, el atributo y valor del nodo se serializa a la propiedad `attr_t` del nodo \( `attr_t->type="caution"`\) de AEM correspondiente. |
| `<textprop>propname_t</textprop>` | Guardar la salida `getTextContent()` en la propiedad definida por `propname_t.` <br> **Nota:** Esta es una propiedad optimizada. |
| `<xmlprop>propname_x </xmlprop>` | Guardar el XML serializado de este nodo en la propiedad definida por `propname_x.<br> `**Nota:** Esta es una propiedad optimizada. |
| `<xpath>` | Si se proporciona un elemento XPath en la asignación de elementos, junto con el nombre del elemento y la clase, la condición XPath también debe cumplirse para que se utilice la asignación de componentes. |
| `<target>` | Coloque el elemento DITA en el repositorio CRX en la ubicación especificada.<br> valores posibles: <br> - **head**: bajo el nodo de encabezado <br> - **text**: bajo el nodo de párrafo |
| `<wrapelement>` | El elemento HTML en el que ajustar el contenido. |
| `<wrapclass>` | El valor del elemento para la propiedad `wrapclass.` |
| `<attributemap>` | Nodo contenedor que contiene uno o más `<attribute>` nodos. |
| `<attribute from="attrname" to="propname" ispath="true\|false" rel="source\|target" />` | Asigna los atributos DITA a las propiedades de AEM: <br> -   **`from`**: nombre de atributo DITA <br> -   **`to`**: nombre de propiedad de componente de AEM <br> -   **`ispath`**: si el atributo es un valor de ruta \(por ejemplo: *image*\) <br> -   **`rel`**: si la ruta de acceso es el origen o el destino <br> **Nota:** Si `attrname` empieza por `%`, asigne `attrname minus '%'` a la prop &#39; `propname`&#39;. |

**Notas adicionales**

- Si planea anular la asignación de elementos predeterminada, se recomienda no realizar los cambios en el archivo `elementmapping.xml` predeterminado. Debe crear un nuevo archivo XML de asignación y colocar el archivo en otra ubicación, preferiblemente dentro de la carpeta de aplicaciones personalizadas que cree.

- En el archivo `elementmapping.xml`, hay muchas entradas de asignación que hacen referencia al componente fmdita/components/dita/wrapper. Wrapper es un componente genérico que procesa construcciones DITA relativamente sencillas utilizando propiedades en su nodo de sitio para generar HTML relevantes. Utiliza la propiedad `wrapelement` para generar etiquetas envolventes y delega el procesamiento secundario a los componentes correspondientes. Esto resulta útil en casos en los que solo desea un componente contenedor. En lugar de crear un nuevo componente que procese una etiqueta contenedora específica como `div` o `p`, puede utilizar el componente Envolvente con las propiedades `wrapelement` y `wrapclass` para lograr el mismo efecto.

- No se recomienda guardar grandes cantidades de texto en las propiedades JCR de la cadena. El cálculo del tipo de propiedad optimizada en la generación de salida garantiza que el contenido de texto grande no se guarde como tipo de cadena. En su lugar, cuando es necesario guardar contenido que supera un determinado umbral, el tipo de la propiedad se cambia a binario. De manera predeterminada, este umbral está configurado a 512 bytes, pero se puede cambiar en el Administrador de configuración \(*com.adobe.fmdita.config.ConfigManager*\) cambiando la opción **Guardar como umbral binario**.

- Si planea anular algunas \(y no todas\) de las asignaciones de elementos, no tiene que replicar todo el archivo `elementmapping.xml`. Debe crear un nuevo archivo de asignación XML y definir sólo los elementos que va a anular.

- Después de crear el archivo XML en la ubicación personalizada, actualice la configuración `Override Element Mapping` en el paquete `com.adobe.fmdita.config.ConfigManager`.


