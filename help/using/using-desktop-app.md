---
title: Usando  [!DNL Experience Manager] aplicación de escritorio
description: Usando  [!DNL Adobe Experience Manager] aplicación de escritorio.
feature: Desktop App,Asset Management
source-git-commit: 2947fbd3bfeb15b37a8f1b0118e969b5d70499d0
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 1%

---


# Abrir recursos en el escritorio {#openondesktop-v2}

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

## Próximos pasos {#next-steps}

* [Vea un vídeo para empezar a usar la aplicación de escritorio de Adobe Experience Manager](https://experienceleague.adobe.com/es/docs/experience-manager-learn/assets/creative-workflows/aem-desktop-app)

* Proporcione comentarios sobre la documentación usando [!UICONTROL Edit this page] ![editar la página](assets/do-not-localize/edit-page.png) o [!UICONTROL Log an issue] ![crear un problema de GitHub](assets/do-not-localize/github-issue.png), disponibles en la barra lateral derecha

* Contacto con el [Servicio de atención al cliente](https://experienceleague.adobe.com/es?support-solution=General#support)

>[!MORELIKETHIS]
>
>* [Comprenda la interfaz de usuario](/help/using/user-interface.md)
>* [Administrar Assets en la aplicación de escritorio](/help/using/assets-management-tasks.md)
>* [Buscar](/help/using/search.md)
