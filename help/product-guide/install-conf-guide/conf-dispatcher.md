---
title: Configuración de Dispatcher
description: Obtenga información sobre cómo configurar Dispatcher
feature: Installation
role: Admin
level: Experienced
source-git-commit: 834959a6a0e22cd5d2b2c5d0e57ceb6d45c0c666
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 7%

---

# Configuración de Dispatcher {#id213BCM0M05U}

Si planea utilizar una instancia de Dispatcher en AEM Author junto con AEM Guides, debe realizar las siguientes configuraciones adicionales para completar la configuración:

>[!NOTE]
>
> Dispatcher es la herramienta de almacenamiento en caché o de equilibrio de carga de Adobe Experience Manager. Para obtener más información acerca del uso de Dispatcher, consulte [Información general de Dispatcher](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/dispatcher.html?lang=es).

## Habilitar AllowEncodedSlashes en las direcciones URL

Las direcciones URL con barras codificadas no están habilitadas de forma predeterminada en la configuración de AEM Dispatcher, pero mientras trabaja en AEM Guides debe habilitarlas. Para ello, debe establecer el parámetro `AllowEncodedSlashes` en **On** en la configuración de Apache como se muestra en el siguiente fragmento de código:

```XML
<VirtualHost *:80>
                ServerName www.geometrixx-outdoors.com
                **AllowEncodedSlashes On**
                <Directory />
                <IfModule disp_apache2.c>
                SetHandler dispatcher-handler
                </IfModule>
                Options FollowSymLinks
                AllowOverride None
                </Directory>
                </VirtualHost>
            
```

## Configuración del archivo mime.types para DITA

Al utilizar una Dispatcher con AEM Guides, debe asegurarse de que el mapa DITA y los archivos de tema se representan como HTML para que los autores vean el contenido como esperan \(en lugar del formato de texto sin procesar\).

Siga estos pasos para actualizar el archivo `mime.types`:

1. Conéctese al servidor de Dispatcher mediante SSH y busque el archivo `httpd.conf`.

1. Compruebe la ruta de acceso del archivo `mime.types`.

1. Abra el archivo `mime.types` y busque &quot; text/html&quot;. La asignación predeterminada para &quot; text/html&quot; es:

   `text/html html htm`

1. Actualice la asignación añadiendo extensiones ditamap y dita como:

   `text/html html htm ditamap dita`

1. Guarde y cierre el archivo.


Esta actualización de configuración garantiza que los archivos de tema y mapa DITA representados por Dispatcher se muestren como HTML en la interfaz de usuario de Assets.

## Permitir URL de solicitud de preferencias de usuario

Cuando utilice una Dispatcher con AEM Guides, si la instancia de autor tiene una instancia de Dispatcher delante, realice los dos cambios siguientes:

- Incluya en la lista blanca la URL de petición POST. A continuación se muestra una regla `/filters` de muestra: Agregar esta regla al archivo de configuraciones de Dispatcher:

```json
/xxxx {/type "allow" /method "POST" /url "/home/users/*/preferences"}
```

- Asegúrese de que el patrón de URL `/libs/cq/security/userinfo.json` no se almacene en caché en el Dispatcher de autor; por lo tanto, agregue una regla `\(like below\)` en `author\_dispatcher.any`

```json
/xxxx {
                /glob "/libs/cq/security/userinfo.json"
                /type "deny"
                }
```

