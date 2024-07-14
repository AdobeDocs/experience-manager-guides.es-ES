---
title: Menús contextuales
description: Personalización de menús contextuales
role: User, Admin
exl-id: 25aa76dd-ef05-41ed-b980-14bbc1626059
source-git-commit: 4f00d6b7ad45636618bafe92e643b3e288ec2643
workflow-type: tm+mt
source-wordcount: '154'
ht-degree: 0%

---

# Personalización de menús contextuales

Los siguientes menús contextuales se pueden personalizar:

- `file_options`
controladores:
   - Vista de mapa: `ditamap_viewer_controller`
   - Panel de repositorio: `repository_panel_controller`
   - Panel Favoritos: `collection_tree_controller`
   - Vínculos de referencia de propiedades de archivo: `file_references_links_controller`
   - Panel de búsqueda del repositorio: `repository_search_controller`
   - Panel de esquema de asunto: `subject_scheme_tree_controller`

- `folder_options`
controladores:
   - Panel de repositorio: `repository_panel_controller`
   - Panel Favoritos: `collection_tree_controller`

- `collection_options`
controladores:
   - Panel Favoritos: `collection_tree_controller`

- `map_view_options`
controladores:
   - Vista de mapa: `ditamap_viewer_controller`

- `baseline_panel_menu`
controladores:
   - Panel de línea base: `baseline_panel`

- `preset_item_menu`
controladores:
   - Panel de ajustes preestablecidos: `preset_panel`

También puede crear su propio menú contextual definiendo un nuevo ID único.

Ahora cada menú contextual tiene un `controller id` asociado. Este controlador administra la funcionalidad `on-event` para las distintas opciones del menú contextual

Tomemos un ejemplo para entender

```js title=customise_context_menu.js"
const fileOptions = {
    id: "file_options",
    contextMenuWidget: "repository_panel",
    view: {
            items: [
                {
                    component: "div",
                    target: {
                        key:"displayName",value: "Delete",                    
                        viewState: VIEW_STATE.REPLACE
                    }
                },
                {
                    component: "div",
                    target: {
                        key:"displayName",value: "Edit",                    
                        viewState: VIEW_STATE.REPLACE
                    }
                },
                {
                    "displayName": "Download",
                    "data": {
                      "eventid": "downloadFile"
                    },
                    "icon": "downloadFromCloud",
                    "class": "menu-separator",         
                    target: {
                        key:"displayName",value: "Duplicate",                    
                        viewState: VIEW_STATE.REPLACE
                    }
                },
            ]

    },

    controller: {
        downloadFile(){
            const path  = this.getValue('selectedItems')[0].path
            this.loader.loadDitaFile(path).then((file) => {
              function download_file(name, contents) {
                const mime_type = "text/plain";
        
                const blob = new Blob([contents], {type: mime_type});
        
                const dlink = document.createElement('a');
                dlink.download = name;
                dlink.href = window.URL.createObjectURL(blob);
                dlink.onclick = function() {
                    // revokeObjectURL needs a delay to work properly
                    const that = this;
                    setTimeout(function() {
                        window.URL.revokeObjectURL(that.href);
                    }, 1500);
                };
        
                dlink.click();
                dlink.remove();
            }
            download_file(path,file.xml)
            });
          }
    }
}
```

Ahora vamos a entender lo que está haciendo este código.

1. `id` se usa para identificar el menú contextual que queremos personalizar.
2. `contextMenuWidget` se usa para definir `widget id` o `component` que llama al menú contextual y administra `events`.

El resto sigue siendo el mismo, por lo que `view` se utiliza para definir los elementos, `target` identifica dónde reemplazar, anexar o anteponer la opción y el controlador `contextMenuWidget` administra los eventos `on-click`.
