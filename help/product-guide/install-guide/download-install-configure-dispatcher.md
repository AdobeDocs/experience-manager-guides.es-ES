---
title: Configurar Dispatcher
description: Obtenga información sobre cómo configurar Dispatcher
exl-id: 525de1c3-5a79-4d65-89b4-ca05ae660c2c
feature: Installation
role: Admin
level: Experienced
source-git-commit: 0513ecac38840a4cc649758bd1180edff1f8aed1
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 6%

---

# Configurar Dispatcher {#id213BCM0M05U}

AEM AEM Si planea utilizar una instancia de Dispatcher en instancia de autor junto con las guías de la, debe realizar las siguientes configuraciones adicionales para completar la configuración:

>[!NOTE]
>
> Dispatcher es la herramienta de almacenamiento en caché o de equilibrio de carga de Adobe Experience Manager. Para obtener más información sobre el uso de Dispatcher, consulte [Información general de Dispatcher](https://experienceleague.adobe.com/docs/experience-manager-dispatcher/using/dispatcher.html?lang=en).

## Habilitar AllowEncodedSlashes en las direcciones URL

AEM AEM Las direcciones URL con barras oblicuas codificadas no están habilitadas de forma predeterminada en la configuración de Dispatcher, pero mientras trabaja en Guías de la aplicación, debe habilitarlas. Para ello, debe establecer el parámetro AllowEncodedSlashes en On en la configuración de Apache como se muestra en el siguiente fragmento:

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

AEM Al utilizar Dispatcher con guías de, debe asegurarse de que el mapa DITA y los archivos de tema se representen como HTML para que los autores vean el contenido como esperan \(en lugar del formato de texto sin procesar\).

Siga estos pasos para actualizar el archivo mime.types:

1. Conéctese al servidor de Dispatcher mediante SSH y busque el archivo httpd.conf.

1. Compruebe la ruta del archivo &quot; mime.types&quot;.

1. Abra el archivo mime.types y busque &quot; text/html&quot;. La asignación predeterminada para &quot; text/html&quot; es:

   `text/html html htm`

1. Actualice la asignación añadiendo extensiones ditamap y dita como:

   `text/html html htm ditamap dita`

1. Guarde y cierre el archivo.


Esta actualización de configuración garantiza que los archivos de tema y mapa DITA representados por Dispatcher se muestren como HTML en la interfaz de usuario de Assets.

## Permitir URL de solicitud de preferencias de usuario

AEM Al utilizar Dispatcher con guías de, si la instancia de autor tiene una instancia de Dispatcher delante, realice los dos cambios siguientes:

- Incluya en la lista blanca la URL de solicitud de POST. Una muestra de &quot; `/filters`La regla &quot; se indica a continuación: Añada esta regla al archivo de configuraciones de Dispatcher:

```json
/xxxx {/type "allow" /method "POST" /url "/home/users/*/preferences"}
```

- Asegúrese de que el patrón de URL &quot; /libs/cq/security/userinfo.json&quot; no se almacene en caché en el Dispatcher de autor, así que agregue una regla \(como la que se muestra a continuación\) en author\_dispatcher.any

```json
/xxxx {
                /glob "/libs/cq/security/userinfo.json"
                /type "deny"
                }
```

**Tema principal:**[ Descargar e instalar](download-install.md)
