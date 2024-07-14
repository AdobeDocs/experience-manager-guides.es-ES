---
title: Reutilización de contenido DITA en AEM Guides
description: Este breve artículo explica cómo AEM Guides y DITA le ayudan a ahorrar tiempo y esfuerzo al utilizar la reutilización de contenido
role: User, Admin
exl-id: 1522ebf5-2aea-4d8f-ade7-367227b31dd9
source-git-commit: 4160c990bafe41611714ef66ee361aba0ef47c0a
workflow-type: tm+mt
source-wordcount: '553'
ht-degree: 0%

---

# Reutilización de contenido en AEM Guides

Adobe AEM Guides aprovecha los puntos fuertes de DITA para proporcionar una interfaz fácil de usar para la reutilización de contenido.

En este artículo hablaríamos de :

1. [Reutilización mediante referencia de tema (](#reusability-using-topic-referencestopicref)
2. [Reutilización mediante referencia de contenido (](#reusability-using-content-reference-conref--conkeyref)
3. [Sugerencia de bonificación para reutilizar contenido con arrastrar y soltar en AEM Guides](#reuse-content-with-a-single-click-in-aem-guides)

## Reutilización mediante referencias de temas (topicref)



Supongamos que es una empresa de fabricación y que tiene temas genéricos para precauciones de seguridad o técnicas de resolución de problemas.

Se pueden consultar y adaptar en manuales de usuario específicos para cada modelo de máquina, reduciendo la redundancia y asegurando que la información de seguridad central siga siendo coherente.

```
<map id="user_manual_model 100" title="ABC Model 100 User Manual ">


<topicref href="Safety_Information.dita" format="dita">
</topicref>
.
.
.
.
.
</map>
```


Del mismo modo para el modelo 200

```
<map id="user_manual_model 200" title="ABC Model 200 User Manual ">

<topicref href="Safety_Information.dita" format="dita">
</topicref>
.
.
.
.
.
  
</map>
```

## Reutilización mediante referencia de contenido (conref y conkeyref)

El atributo content reference (conref) permite vincular otras partes del contenido. Esto promueve la reutilización y reduce la redundancia.

Por ejemplo:

Supongamos que es una empresa financiera y tiene un tema genérico para KYC que contiene procedimientos KYC para individuos, empresas, etc.

Desea reutilizar el fragmento KYC individual para los temas &quot;Cuenta de almacenamiento&quot; y &quot;Cuenta de demostración&quot;.

```
<section id="kyc_requirements_saving_account">
  <title>Know Your Customer (KYC) Requirements</title>
  <p>To comply with regulations and ensure customer identification, all individual applicants for savings  accounts must fulfill the KYC requirements as outlined below</p>
  <p conref=kyc_procedures.dita#individual_kyc></p>
</section>
```

Aquí `conref=kyc_procedures.dita#indvidual_kyc` key_processes.dita es el identificador de archivo y #individual_kyc es el identificador de fragmento.

Kyc_procedure.dita sigue siendo la única fuente de información. Si hay cambios en el proceso de KYC según lo requerido por las regulaciones, simplemente necesita actualizar un tema, y esos cambios se reflejan automáticamente en todos los temas que se refieren a él.

Con AEM Guides, son dos clics

Paso 1: Haga clic en Insertar contenido reutilizable
![barra de herramientas](../../assets/publishing/content-reusability_image1.png)

<br>

Paso 2: Seleccione el archivo y el fragmento que debe reutilizarse.
![conref](../../assets/publishing/content-reusability_image2.png)

Al igual que &quot;conref&quot;, puede utilizar &quot;conkeyref&quot; donde, en lugar de proporcionar una ruta de contenido, puede hacer referencia al contenido mediante claves.

Ejemplo de código:

```
<section conkeyref="kyc_procedure/individual_kyc_procedure" id="individual_kyc_procedure"></section>
```

La definición de la clave tiene este aspecto:

```
<map id="ABC_manual">
  <title>ABC_Manual</title>
  <topicref href="kyc_procedure_2020.dita" keys="kyc_procedure" processing-role="resource-only" type="concept">
  </topicref>
  <topicref href="savings_account.dita" type="concept">
  </topicref>
</map>
```

Clave: &quot;Key_procedure&quot; seguirá siendo la única fuente de información. Si hay cambios en el proceso KYC según lo requerido por las regulaciones, simplemente necesita actualizar una ruta de tema con una nueva ruta de tema, y esos cambios se reflejarán automáticamente en todos los temas que se refieran a ella.

```
<map id="ABC_manual">
  <title>ABC_Manual</title>
  <topicref href="kyc_procedure_2024.dita" keys="kyc_procedure" processing-role="resource-only" type="concept">
  </topicref>
  <topicref href="savings_account.dita" type="concept">
  </topicref>
</map>
```

En este caso, la ruta del tema cambia de &quot;kyc_procedure_2020.dita&quot; a &quot;kyc_procedure_2024.dita&quot; debido a los cambios recientes en la regulación.

Con AEM Guides, son dos clics

Paso 1: Haga clic en Insertar contenido reutilizable
![barra de herramientas](../../assets/publishing/content-reusability_image1.png)

Paso 2: Seleccione el mapa raíz (opcional), la clave y el fragmento que debe reutilizarse.
![conkeyref](../../assets/publishing/content-reusability_image3.png)

El mapa raíz se seleccionó automáticamente porque ya estaba abierto en la vista del mapa


## Reutilización del contenido con un solo clic en AEM Guides

AEM Guides ofrece la capacidad &quot;Contenido reutilizable&quot; para agregar referencias de contenido con un solo clic.

Paso 1: Agregar un tema genérico a contenido reutilizable

![Agregar contenido reutilizable](../../assets/publishing/content-reusability_image4.png)

Paso 2: Una vez agregado, arrastre y suelte el fragmento que desee reutilizar en cualquiera de los temas de destino.

![Agregar gif de contenido reutilizable](../../assets/publishing/content-reusability_image5.gif)



## Preguntas más frecuentes

- ### No se muestra todo el contenido después de seleccionar el archivo o la clave en el cuadro de diálogo Reutilizar contenido

Debe asignar ID a fragmentos (elementos Dita ) que desee reutilizar en otros temas

- ## Las claves no se muestran en el cuadro de diálogo Reutilizar contenido

Asegúrese de haber abierto el mapa raíz/mapa principal en la vista de mapa que tiene una definición de clave o agregue la ruta del mapa raíz manualmente en el mismo cuadro de diálogo.


<br>


Post en la Comunidad de AEM Guides [forum](https://experienceleaguecommunities.adobe.com/t5/experience-manager-guides/ct-p/aem-xml-documentation) para cualquier consulta.
