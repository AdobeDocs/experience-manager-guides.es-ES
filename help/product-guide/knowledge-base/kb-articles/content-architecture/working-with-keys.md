---
title: Uso de claves
description: Cómo crear claves para utilizarlas en el contenido de la organización
role: Admin
exl-id: b8e3a6d2-ea82-4fdb-bd16-3f4b6594af52
feature: Use Keys in AEM Guides
source-git-commit: 47e6c57b8a61f02dc4f03594d91ee842bdccef90
workflow-type: tm+mt
source-wordcount: '179'
ht-degree: 0%

---

# Creación de claves

Las organizaciones deben utilizar claves en casos en los que tengan algún texto reutilizable y común, como el nombre o el tono del producto, que se utilice en muchos lugares, pero que sea propenso a cambiar. El uso de teclas para este tipo de texto reutilizable le permite insertar una actualización en varios lugares realizando el cambio en una sola ubicación, como en el valor de clave.

## Paso 1: Crear un mapa global para almacenar las claves

Cree un mapa y añada el [!UICONTROL keyref] elemento a él.

```
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE map PUBLIC "-//OASIS//DTD DITA Map//EN" "technicalContent/dtd/map.dtd">
<mapid="map.ditamap_ffbdbf06-8658-4311-ad84-1c631bba904f">
  <title>global-keys-map</title>
  <keydefkeys="adobe">
    <topicmeta>
      <linktext>Adobe Systems</linktext>
    </topicmeta>
  </keydef>
  <keydefkeys="AEM">
    <topicmeta>
      <linktext>Adobe Experience Manager</linktext>
    </topicmeta>
  </keydef>
</map>
```

Aquí ha definido dos definiciones, como se muestra arriba, siempre que [!UICONTROL keyref] as _AEM_ para el _Adobe Experience Manager_ texto.

## Paso 2: Agregar este mapa al mapa de publicación

```
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE map PUBLIC "-//OASIS//DTD DITA Map//EN" "technicalContent/dtd/map.dtd">
<mapid="map.ditamap_cbf4a96d-e382-4e8c-8830-bcc093fe6638">
  <title>sample-map</title>
  <topicrefhref="sample-topic-using-the-keys.dita"type="topic">
  </topicref>
  <maprefformat="ditamap"href="global-keys-map.ditamap"type="map">
  </mapref>
</map>
```

## Paso 3: Utilice las claves para hacer referencia a las variables definidas en el mapa de claves global

+ Edite el tema y añada el valor clave mediante la variable [!UICONTROL keyref].
+ Como se muestra en la captura de pantalla, aparecerá una pequeña ventana desde donde se pueden elegir las palabras clave. Esto se mostrará cuando añada el elemento &quot;keyword&quot;.
  ![Insertar elemento](assets/insert_element.png)
  ![Ref clave](assets/key_ref.png)

```
<?xml version="1.0" encoding="UTF-8"?>
<!DOCTYPE topic PUBLIC "-//OASIS//DTD DITA Topic//EN" "technicalContent/dtd/topic.dtd">
<topicid="topic.dita_31b00e61-04b5-4193-af7a-68503e88b087">
  <title>sample-topic-using-the-keys</title>
  <shortdesc></shortdesc>
  <body>
    <p>This is a sample topic using the keys defined in the global map</p>
    <p>here i am using the key definition for AEM :<keyword keyref="AEM"></keyword></p>
  </body>
</topic>
```
