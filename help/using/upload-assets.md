---
title: Cargar recursos mediante  [!DNL Experience Manager] aplicación de escritorio
description: Cargar recursos mediante  [!DNL Adobe Experience Manager] aplicación de escritorio.
feature: Desktop App,Asset Management
source-git-commit: 2947fbd3bfeb15b37a8f1b0118e969b5d70499d0
workflow-type: tm+mt
source-wordcount: '778'
ht-degree: 1%

---


# Carga de activos {#upload-assets}

## Editar recursos y cargar recursos actualizados a [!DNL Experience Manager] {#edit-assets-upload-updated-assets}

Abra los recursos para editarlos cuando desee realizar cambios y cargar los recursos actualizados en el servidor [!DNL Experience Manager]. Para evitar conflictos con ediciones de otros usuarios, utilice la aplicación para iniciar una sesión de edición. Antes de empezar a editar, asegúrese de que el recurso no tenga un icono de bloqueo que indique que otro usuario está editando el recurso.

Para editar un recurso, búsquelo o vaya a la ubicación del recurso. Haga clic en ![icono Más](assets/do-not-localize/more2_da2.png) y luego en **[!UICONTROL Edit]**.

Use **[!UICONTROL Toggle Check-out]** para bloquear el recurso y evitar conflictos con ediciones de otros usuarios en las dos situaciones siguientes:

* Ha empezado a editar un recurso sin desprotegerlo primero (por ejemplo, abriéndolo).
* Tiene intención de empezar a editar un recurso pronto y no desea que otros lo editen.

Una vez que haya terminado de realizar las ediciones, la aplicación mostrará el estado **[!UICONTROL Edited Locally]** de los recursos modificados. Todos los cambios guardados en los recursos son de tipo local solamente hasta que cargue los cambios en [!DNL Experience Manager]. Para cargar un individuo o algunos recursos uno por uno, haga clic en **[!UICONTROL Upload Changes]** desde las opciones de un recurso. Crea una versión del recurso en [!DNL Experience Manager]. Mediante la interfaz web de [!DNL Assets], puede ver el historial de recursos en la [vista Escala de tiempo](https://experienceleague.adobe.com/es/docs/experience-manager-65/content/assets/using/activity-stream).

![Cargar cambios en la opción de la aplicación](assets/upload_changes_single1_da2.png "Cargar cambios en la aplicación")

![Opción Cargar cambios al ver una vista previa grande de un recurso](assets/upload_changes_single2_da2.png "Cargar cambios al ver una vista previa grande de un recurso")

Para conocer las prácticas recomendadas sobre la edición colaborativa, consulte [Flujo de trabajo avanzado: colabore en los mismos archivos y evite conflictos de edición](#adv-workflow-collaborate-avoid-conflicts).

En los casos siguientes, es posible que desee descartar los cambios y ediciones realizados en el recurso local. Haga clic en **[!UICONTROL Discard Changes]**.

* Si no desea guardar los cambios localmente en [!DNL Experience Manager].
* Empiece a realizar cambios en el recurso original después de guardar algunos cambios.
* Deje de editar el recurso, ya que ya no es necesario.

Si es necesario, cambie la desprotección. El recurso actualizado se eliminará de la carpeta de caché local y se descargará de nuevo cuando lo edite o abra.

## Cargar y agregar nuevos recursos a [!DNL Experience Manager] {#upload-and-add-new-assets-to-aem}

Los usuarios pueden agregar nuevos recursos al repositorio de DAM. Por ejemplo, puede ser un fotógrafo o contratista de una agencia que desee agregar un gran número de fotos de una sesión de fotos al repositorio [!DNL Experience Manager]. Para agregar contenido nuevo a [!DNL Experience Manager], seleccione ![cargar a la nube](assets/do-not-localize/upload_to_cloud_da2.png) en la barra superior de la aplicación. Busque los archivos de recursos en el sistema de archivos local y haga clic en **[!UICONTROL Select]**. Como alternativa, para cargar recursos, arrastre los archivos o carpetas a la interfaz de la aplicación. En Windows, si arrastra recursos a una carpeta dentro de la aplicación, estos se cargarán en la carpeta. Si tarda más en cargarse, la aplicación muestra una barra de progreso.

<!-- ![Download progress bar for large-sized assets](assets/upload_status_da2.png "Download progress bar for large-sized assets")
-->

Puede cargar carpetas o archivos individuales desde el sistema de archivos local. La jerarquía de una carpeta se conserva cuando se carga. Antes de cargar recursos en lotes, consulte [Cargas en lotes](#bulk-upload-assets).

Para ver la lista de recursos transferidos en una sesión determinada, haga clic en **[!UICONTROL View]** > **[!UICONTROL Assets transfers]**. La lista le permite ver y comprobar rápidamente las transferencias de archivos de la sesión actual.

![Lista de recursos transferidos en una sesión en particular](assets/assets_transfered_da2.png "Lista de recursos transferidos en una sesión en particular")

Puede controlar la concurrencia de carga (aceleración) en la configuración **[!UICONTROL Preferences]** > **[!UICONTROL Upload acceleration]**. Una mayor concurrencia suele proporcionar cargas más rápidas, pero puede consumir muchos recursos y consumir más potencia de procesamiento del equipo local. Si experimenta un sistema lento, vuelva a intentar la carga con un valor inferior de concurrencia.

>[!NOTE]
>
>La lista de transferencias no es persistente y no está disponible si sale de la aplicación y la vuelve a abrir.

## Carga masiva de recursos {#bulk-upload-assets}

Los usuarios u organizaciones, como los fotógrafos o las agencias creativas, pueden crear numerosos recursos locales durante actividades como sesiones de fotos, retoques o selecciones entre un conjunto más amplio. Estas tareas se realizan a menudo fuera de [!DNL Experience Manager]. Pueden cargar estas carpetas locales grandes en [!DNL Assets] directamente desde la aplicación de escritorio. Las jerarquías de carpetas se conservan y se cargan todas las subcarpetas anidadas y los recursos incluidos. Los recursos cargados también están disponibles inmediatamente para otros usuarios del mismo servidor para su consumo. Assets se carga en segundo plano, por lo que la operación no está vinculada a una sesión del explorador web.

![Carga en lotes de varias carpetas locales desde tu escritorio a [!DNL Experience Manager]](assets/upload_local_folders_da2.png "Carga en lotes de varias carpetas locales desde tu escritorio a Experience Manager")

Después de la carga, si los cambios esperados no se reflejan en la aplicación, haga clic en el icono de actualización ![Actualizar icono](assets/do-not-localize/refresh.png).

>[!NOTE]
>
>No use la funcionalidad de carga para migrar recursos en dos implementaciones de [!DNL Experience Manager]. En su lugar, consulte la [guía de migración](https://experienceleague.adobe.com/es/docs/experience-manager-65/content/assets/administer/assets-migration-guide).

## Próximos pasos {#next-steps}

* [Vea un vídeo para empezar a usar la aplicación de escritorio de Adobe Experience Manager](https://experienceleague.adobe.com/es/docs/experience-manager-learn/assets/creative-workflows/aem-desktop-app)

* Proporcione comentarios sobre la documentación usando [!UICONTROL Edit this page] ![editar la página](assets/do-not-localize/edit-page.png) o [!UICONTROL Log an issue] ![crear un problema de GitHub](assets/do-not-localize/github-issue.png), disponibles en la barra lateral derecha

* Contacto con el [Servicio de atención al cliente](https://experienceleague.adobe.com/es?support-solution=General#support)

>[!MORELIKETHIS]
>
>* [Descarga de recursos](/help/using/download-assets.md)
>* [Comprenda la interfaz de usuario](/help/using/user-interface.md)
>* [Buscar](/help/using/search.md)
