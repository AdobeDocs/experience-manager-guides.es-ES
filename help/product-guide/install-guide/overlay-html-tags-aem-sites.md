---
title: Superponga las etiquetas de HTML en la salida de AEM Sites no heredada
description: Configure el vídeo y la configuración de imagen para la salida de aem sites en función de la asignación de componentes principales
feature: Installation
role: Admin
level: Experienced
source-git-commit: 8310ae8d2e2eeda0fcfba9ec50650c806263cd49
workflow-type: tm+mt
source-wordcount: '156'
ht-degree: 0%

---


# Superponer etiquetas de HTML en la salida de AEM Sites

Puede añadir y personalizar etiquetas de HTML en la salida de AEM Sites generada mediante el ajuste preestablecido de AEM Sites basado en la asignación de componentes principales desde el editor web. Para personalizar las etiquetas de HTML, puede superponer el archivo `config.xml`. Por ejemplo, puede configurar los mapas de vídeo e imagen en la salida de AEM Sites.

Realice los siguientes pasos para superponer y actualizar el archivo `config.xml`:

1. AEM Inicie sesión en la aplicación y abra el modo CRXDE Lite.

1. Vaya al archivo de configuración disponible en la siguiente ubicación:

   `/libs/fmdita/cq/xssprotection/config.xml`

1. Cree un nodo de superposición de la carpeta `xssprotection` dentro del nodo de aplicaciones.

1. Vaya al archivo de configuración disponible en el nodo `apps`:

   `/apps/fmdita/config/config.xml`

1. Actualice las siguientes etiquetas para los vídeos e imágenes. A continuación, guarde el archivo.

Vídeos:

```XML
    <tag name="video" action="validate">
   	<attribute name="src">
      <regexp-list>
        <regexp name="anything"/>
      </regexp-list>
    </attribute>
    <attribute name="width">
       <regexp-list>
           <regexp name="anything"/>
       </regexp-list>
    </attribute>
    <attribute name="height">
       <regexp-list>
          <regexp name="anything"/>
       </regexp-list>
     </attribute>
     <attribute name="data">
       <regexp-list>
         <regexp name="anything"/>
       </regexp-list>
    </attribute>
    <attribute name="class">
       <regexp-list>
           <regexp name="anything"/>
       </regexp-list>
    </attribute>
    <attribute name="poster">
      <regexp-list>
        <regexp name="anything"/>
        </regexp-list>
    </attribute>
    <attribute name="controls">
        <regexp-list>
            <regexp name="anything"/>
        </regexp-list>
    </attribute>
    </tag>
    <tag name="source" action="validate">
      <attribute name="src">
        <regexp-list>
           <regexp name="anything"/>
        </regexp-list>
      </attribute>
    </tag>
```

Mapas de imagen:

```XML
    	<tag name="map" action="validate">
	<attribute    name="name">
		<regexp-list>
			<regexp name="anything"/>
		</regexp-list>
	</attribute>
    </tag>
    <!-- Image & image related tags -->
    <tag name="img" action="validate">
	<attribute name="src" onInvalid="removeTag">
		<regexp-list>
			<regexp name="onsiteURL"/>
			<regexp name="offsiteURL"/>
		</regexp-list>
	</attribute>
	<attribute name="name"/>
	<attribute name="alt"/>
	<attribute name="height"/>
	<attribute name="width"/>
	<attribute name="border"/>
	<attribute name="align"/>
	<attribute name="usemap">
		<regexp-list>
			<regexp name="anything"/>
		</regexp-list>
	</attribute>
	<attribute name="hspace">
		<regexp-list>
			<regexp name="number"/>
		</regexp-list>
	</attribute>
	<attribute name="vspace">
		<regexp-list>
			<regexp name="number"/>
		</regexp-list>
	</attribute>
    </tag>
    <tag name="area" action="validate">
	<attribute name="shape">
		<regexp-list>
			<regexp name="anything"/>
		</regexp-list>
	</attribute>
	<attribute name="coords">
		<regexp-list>
			<regexp name="anything"/>
		</regexp-list>
	</attribute>
	<attribute name="href">
		<regexp-list>
			<regexp name="anything"/>
		</regexp-list>
	</attribute>
   </tag>
```




Más información sobre las prácticas recomendadas de [Seguridad](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/developing/introduction/security).