---
title: Examinar, buscar y obtener una vista previa de los recursos en la aplicación de escritorio [!DNL Experience Manager]
description: Examine, busque y obtenga una vista previa de los recursos en la aplicación de escritorio  [!DNL Adobe Experience Manager] .
feature: Desktop App
source-git-commit: 2947fbd3bfeb15b37a8f1b0118e969b5d70499d0
workflow-type: tm+mt
source-wordcount: '910'
ht-degree: 0%

---


# Examinar, buscar y previsualizar recursos {#browse-search-preview-assets}

Puede buscar, buscar y obtener una vista previa de los recursos disponibles en el repositorio [!DNL Experience Manager], todo desde la aplicación de escritorio. Pruebe lo siguiente en la aplicación:

1. Vaya a una carpeta y vea información básica de los recursos disponibles en ella, junto con miniaturas pequeñas de todos los recursos.

   ![Examinar los archivos y carpetas DAM](assets/browse_folder_da2.png "Examinar los archivos y carpetas DAM")

1. Para ver más información y una miniatura más grande de un recurso individual, haga clic en el nombre del archivo.

   ![Ver una vista previa más grande de un recurso y acciones](assets/large_preview_actions_da2.png "Ver una vista previa más grande de un recurso y acciones")

1. Haga clic en **[!UICONTROL Open]** o **[!UICONTROL Edit]** para descargar el archivo localmente y solo visualizarlo o editarlo en la aplicación nativa, respectivamente.
1. Busque mediante palabras clave para encontrar un recurso relacionado en el repositorio [!DNL Experience Manager]. Use `?` y `*` como caracteres comodín. Estos caracteres comodín sustituyen a un solo carácter o a varios, respectivamente. Filtre y ordene los resultados según sea necesario.

   ![Búsqueda de muestra con el comodín de asterisco](assets/search_wildcard_da2.png "Búsqueda de muestra con el comodín de asterisco")

   ![Otra búsqueda de muestra con el comodín asterisco](assets/search_wildcard2_da2.png "Otra búsqueda de muestra con una ubicación diferente del comodín asterisco")

>[!NOTE]
>
>La aplicación muestra los recursos haciendo coincidir los criterios de búsqueda en varios campos de metadatos, y no solo el título del recurso o el nombre del archivo.

## Abrir recursos en el escritorio {#openondesktop-v2}

Puede abrir los recursos remotos para verlos en la aplicación nativa. Los recursos se descargan en una carpeta local. A continuación, se inician en la aplicación nativa asociada al formato de archivo. Puede cambiar la aplicación nativa para abrir tipos de archivo específicos (extensiones) en Mac o Windows.

Haga clic en **[!UICONTROL Open]** en el menú de recursos. El recurso se descarga localmente y se abre en la aplicación nativa. Compruebe el progreso de descarga y la velocidad de transferencia de recursos grandes en la barra de estado.

<!-- ![Download progress bar for large-sized assets](assets/download_status_bar_da2.png "Download progress bar for large-sized assets")
-->

>[!NOTE]
>
>Si los cambios esperados no se reflejan en la aplicación, haga clic en el icono de actualización ![Actualizar icono](assets/do-not-localize/refresh.png) o haga clic con el botón secundario en la interfaz de la aplicación y seleccione **[!UICONTROL Refresh]**. Las acciones no están disponibles mientras haya descargas o cargas más grandes en curso.

Para abrir la carpeta de descarga local de un recurso, haga clic en ![Icono de más acciones](assets/do-not-localize/more2_da2.png) y luego en ![Icono de mostrar](assets/do-not-localize/reveal_action2_da2.png) **[!UICONTROL Reveal File]** acción.

## Uso o colocación de recursos en documentos nativos {#place-assets-in-native-documents}

En algunos casos, por ejemplo, al colocar un recurso en un documento nativo, se accede a un archivo en el Explorador de Windows o en el Buscador de Mac. Para llegar a la ubicación del sistema de archivos del archivo descargado localmente, use la opción ![Mostrar icono](assets/do-not-localize/reveal_action2_da2.png) **[!UICONTROL Reveal File]**.

![Mostrar acción de archivo para un recurso](assets/revealfile_action_da2.png "Mostrar acción de archivo para un recurso")

Haga clic en **[!UICONTROL Reveal File]** o en **[!UICONTROL Reveal Folder]** de una carpeta para abrir el Explorador de Windows o el Buscador de Mac con el archivo o la carpeta preseleccionados en el equipo local. Por ejemplo, la opción resulta útil para colocar los archivos de [!DNL Experience Manager] en las aplicaciones nativas que admiten la colocación o vinculación de archivos locales. Para ver cómo colocar archivos en Adobe InDesign, consulte [Colocación de gráficos](https://helpx.adobe.com/es/indesign/using/placing-graphics.html).

La acción **[!UICONTROL Reveal File]** abre un recurso compartido de red local. Muestra únicamente los recursos que están disponibles localmente. Es decir, muestra los recursos que se revelaron, descargaron o abrieron o editaron mediante la aplicación. El recurso compartido de red local no carga ningún cambio en [!DNL Experience Manager]. Para cargar los cambios, utilice explícitamente las acciones **[!UICONTROL Upload Changes]** o **[!UICONTROL Upload]** en la aplicación.

>[!NOTE]
>
>Para la compatibilidad con versiones anteriores de [!DNL Experience Manager] aplicación de escritorio v1.x, los archivos mostrados provienen de un recurso compartido de red local y sólo exponen los archivos disponibles localmente. Las rutas de escritorio de los archivos revelados son las mismas que las creadas por la aplicación v1.x.

>[!CAUTION]
>
>No use la opción **[!UICONTROL Reveal File]** para editar recursos en aplicaciones nativas. En su lugar, use las acciones **[!UICONTROL Edit]**. Para obtener más información, consulte [Flujo de trabajo avanzado: colabore en los mismos archivos y evite conflictos de edición](#adv-workflow-collaborate-avoid-conflicts).

### Administrar caracteres especiales en los nombres de recursos {#special-characters-in-filename}

En la aplicación heredada, los nombres de nodo creados en el repositorio conservaban los espacios y mayúsculas y minúsculas de los nombres de carpeta proporcionados por el usuario. Para que la aplicación actual emule las reglas de nomenclatura de nodos de la aplicación v1.10, habilite [!UICONTROL Use legacy conventions when creating nodes for assets and folders] en [!UICONTROL Preferences]. Ver [preferencias de aplicación](/help/using/install-upgrade.md#set-preferences). Esta preferencia heredada está desactivada de forma predeterminada.

>[!NOTE]
>
>La aplicación solo cambia los nombres de nodo en el repositorio mediante las siguientes convenciones de nomenclatura. La aplicación retiene el(la) `Title` del recurso tal cual.

| Caracteres ‡ | Preferencia heredada en la aplicación | Cuando se produce en nombres de archivo | Cuando se produce en nombres de carpeta | Ejemplos |
|---|---|---|---|---|
| `. / : [ ] \| *` | Habilitado o deshabilitado | Se reemplazó con `-` (guión). Un `.` (punto) en la extensión de nombre de archivo se conserva tal cual. | Se reemplazó con `-` (guión). | `myimage.jpg` permanece tal cual y `my.image.jpg` cambia a `my-image.jpg`. |
| `% ; # , + ? ^ { } "` y espacios en blanco | ![icono de anular selección](assets/do-not-localize/deselect-icon.png) deshabilitado | Se conservan los espacios en blanco | Se reemplazó con `-` (guión). | `My Folder.` cambia a `my-folder-`. |
| `# % { } ? & .` | ![icono de anular selección](assets/do-not-localize/deselect-icon.png) deshabilitado | Se reemplazó con `-` (guión). | NO. | `#My New File.` cambia a `-My New File-`. |
| Caracteres en mayúsculas | ![icono de anular selección](assets/do-not-localize/deselect-icon.png) deshabilitado | La carcasa se conserva tal cual. | Se ha cambiado a minúsculas. | `My New Folder` cambia a `my-new-folder`. |
| Caracteres en mayúsculas | ![icono de selección verificada](assets/do-not-localize/selection-checked-icon.png) habilitada | La carcasa se conserva tal cual. | La carcasa se conserva tal cual. | NO. |

‡ La lista de caracteres es una lista separada por espacios en blanco.

## Buscar todas las imágenes editadas {#find-all-edited-images}

La aplicación proporciona una vista, llamada **[!UICONTROL Edited locally]**, para proporcionarle acceso rápido a todos los archivos que descargó localmente (mediante [!UICONTROL Open] o [!UICONTROL Edit] acciones) y luego modificó. La aplicación le permite seleccionar todos los recursos editados localmente y cargar los cambios en unos pocos clics. Esta vista también muestra los recursos editados localmente que tienen un conflicto de edición.

![Filtre para ver todos los recursos editados localmente](assets/edited_locally_filter_da2.png "Por ejemplo, filtre para ver todos los recursos editados localmente para una carga masiva de ediciones")

## Próximos pasos {#next-steps}

* [Vea un vídeo para empezar a usar la aplicación de escritorio de Adobe Experience Manager](https://experienceleague.adobe.com/es/docs/experience-manager-learn/assets/creative-workflows/aem-desktop-app)

* Proporcione comentarios sobre la documentación usando [!UICONTROL Edit this page] ![editar la página](assets/do-not-localize/edit-page.png) o [!UICONTROL Log an issue] ![crear un problema de GitHub](assets/do-not-localize/github-issue.png), disponibles en la barra lateral derecha

* Contacto con el [Servicio de atención al cliente](https://experienceleague.adobe.com/es?support-solution=General#support)

>[!MORELIKETHIS]
>
>* [Comprenda la interfaz de usuario](/help/using/user-interface.md)
>* [Usando aplicación de escritorio](/help/using/using-desktop-app.md)
>* [Administrar Assets en la aplicación de escritorio](/help/using/assets-management-tasks.md)
