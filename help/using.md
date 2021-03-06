---
title: Uso [!DNL Experience Manager] aplicación de escritorio
description: Uso [!DNL Adobe Experience Manager] aplicación de escritorio, para trabajar con [!DNL Adobe Experience Manager] Recursos DAM directamente desde el escritorio Win o Mac y utilizarlos en otras aplicaciones.
mini-toc-levels: 1
feature: Desktop App,Asset Management
exl-id: fa19d819-231a-4a01-bfd2-6bba6fec2f18
source-git-commit: ca04b64e1ebfee4b677fcc5ef84b0e8fd9950d17
workflow-type: tm+mt
source-wordcount: '4054'
ht-degree: 0%

---

# Uso [!DNL Adobe Experience Manager] aplicación de escritorio {#use-aem-desktop-app-v2}

Utilice la variable [!DNL Adobe Experience Manager] aplicación de escritorio, para acceder fácilmente a los recursos digitales almacenados en [!DNL Adobe Experience Manager] Repositorio DAM en el escritorio local y utilice estos recursos en cualquier aplicación de escritorio. Puede abrir los recursos en las aplicaciones de escritorio y editar los recursos localmente; vuelva a cargar los cambios en [!DNL Experience Manager] con control de versiones, para compartir las actualizaciones con otros usuarios. También puede cargar nuevos archivos y jerarquías de carpetas a [!DNL Experience Manager], crear carpetas y eliminar recursos o carpetas de [!DNL Experience Manager] DAM.

La integración permite que diversas funciones de la organización administren los recursos de forma centralizada en [!DNL Experience Manager Assets] y para acceder a los recursos en el escritorio local en las aplicaciones nativas en el sistema operativo Windows o Mac.

Cuando abra la aplicación después de cerrar sesión o por primera vez, proporcione la URL de su [!DNL Experience Manager] servidor en formato `https://[aem-server-url]:[port]/`. A continuación, seleccione la [!UICONTROL Connect] . Proporcione credenciales para conectar la aplicación con el servidor.

Las tareas clave que realiza mediante el [!DNL Adobe Experience Manager] las aplicaciones de escritorio son:

![Flujos de trabajo y tareas que puede realizar mediante [!DNL Experience Manager] aplicación de escritorio](assets/aem_desktop_app_usecases_v2.png "Flujos de trabajo y tareas que puede realizar mediante [!DNL Adobe Experience Manager] aplicación de escritorio")
Descargar [this](assets/aem_desktop_app_usecases_print.pdf) archivo PDF listo para imprimir.

## Cómo funciona la aplicación de escritorio {#how-app-works2}

Antes de empezar a usar la aplicación, es necesario que entienda [Funcionamiento de la aplicación](release-notes.md#how-app-works). Además, familiarícese con los siguientes términos:

* **[!UICONTROL Desktop Actions]**: Desde la interfaz web de Assets, desde un navegador, puede explorar las ubicaciones de los recursos o retirarse y abrir el recurso para editarlo en su aplicación de escritorio nativa. Estas acciones están disponibles en la interfaz web y utilizan la funcionalidad de la aplicación de escritorio. Consulte [cómo habilitar acciones de escritorio](using.md#desktopactions-v2).

* El estado del archivo es **[!UICONTROL Cloud Only]**: Estos recursos no se descargan en el equipo local y están disponibles en [!DNL Experience Manager] solo servidor.

* El estado del archivo es **[!UICONTROL Available locally]**: Los recursos se descargan y están disponibles en el equipo local tal cual. Los recursos no se cambian.

* El estado del archivo es **[!UICONTROL Edited locally]**: Estos recursos se modifican localmente y los cambios se mantienen en el archivo cargado en [!DNL Experience Manager] servidor. Después de cargar, el estado cambia a [!UICONTROL Available locally]. Consulte [editar recursos](using.md#edit-assets-upload-updated-assets).

* El estado del archivo es **[!UICONTROL Editing conflict]**: Si usted y otros usuarios modifican un recurso simultáneamente, la aplicación indica que se ha producido un conflicto de edición. La aplicación también proporciona opciones para conservar o descartar los cambios. Consulte [cómo evitar conflictos de edición](using.md#adv-workflow-collaborate-avoid-conflicts).

* El estado del archivo es **[!UICONTROL Modified remotely]**: La aplicación indica si un recurso que ha descargado se ha modificado en la variable [!DNL Experience Manager] servidor. La aplicación también ofrece la opción de descargar la última versión y actualizar la copia local. Consulte [cómo evitar conflictos de edición](using.md#adv-workflow-collaborate-avoid-conflicts).

* **[!UICONTROL Check-out]**: Si está editando un archivo o quiere editarlo, puede alternar el estado para extraerlo. Añade un icono de bloqueo al recurso en la aplicación y [!DNL Experience Manager] interfaz web. El icono de bloqueo indica a otros usuarios que eviten editar simultáneamente el mismo recurso, ya que conduce a un conflicto de edición.

* **[!UICONTROL Check-in]**: Marque el recurso como seguro para que otros usuarios lo editen sin causar ningún conflicto de edición. Al cargar los cambios, el icono de bloqueo se elimina automáticamente. Al alternar el estado de protección también se elimina el icono de bloqueo, aunque se recomienda no registrarlo manualmente sin cargar los cambios. Si descarta los cambios, active manualmente el registro de entrada.

* **[!UICONTROL Open]** acción: Simplemente abra el recurso para previsualizarlo en la aplicación nativa. No se recomienda editar el recurso mediante esta acción, ya que no desprotege el recurso y otros usuarios pueden realizar ediciones que conduzcan a conflictos de edición.

* **[!UICONTROL Edit]** acción: Utilice la acción para modificar la imagen. Hacer clic [!UICONTROL Edit] la acción extrae automáticamente el recurso y añade un icono de bloqueo al recurso. Después de hacer clic en Editar, si no desea editar el recurso, haga clic en [!UICONTROL Toggle check-in]. Para eliminar, cambiar el nombre o mover recursos en [!DNL Experience Manager] Jerarquía de carpetas DAM, utilice la variable [!DNL Experience Manager] acciones de interfaz web y no la acción de edición.

* **[!UICONTROL Download]** acción: Descargue el recurso en el equipo local. Ahora puede descargar los recursos y editarlos más tarde; trabajar sin conexión y cargar los cambios más tarde. Los recursos se descargan en una carpeta de caché del sistema de archivos.

* **[!UICONTROL Reveal File]** o **[!UICONTROL Reveal Folder]** acción: Mientras los recursos se descargan en una carpeta de caché local, la aplicación imita una unidad de red local y proporciona una ruta local para cada recurso. Para saber esta ruta, utilice la opción de revelación adecuada en la aplicación. Se requiere una acción de revelación para colocar recursos en la aplicación de Creative Cloud. Consulte [colocar recursos](using.md#place-assets-in-native-documents).

* **[!UICONTROL Open In Web]** acción: Para ver el recurso en [!DNL Experience Manager] interfaz web, ábrala en web. Puede iniciar más flujos de trabajo desde [!DNL Experience Manager] como actualizar metadatos o detección de recursos.

* **[!UICONTROL Delete]** acción: Elimine el recurso del [!DNL Experience Manager] Repositorio DAM. La acción elimina la copia original del recurso en el servidor de Experience Manager. Si solo desea descartar modificaciones del recurso local, consulte [descartar cambios](using.md#edit-assets-upload-updated-assets).

* **[!UICONTROL Upload Changes]**: La aplicación de escritorio carga el recurso actualizado solo cuando se carga explícitamente en [!DNL Experience Manager] servidor. Al guardar las ediciones, los cambios se guardan únicamente en el equipo local. Al cargar, el recurso se registra automáticamente y se elimina el icono de bloqueo. Consulte [editar recursos](using.md#edit-assets-upload-updated-assets).

## Habilitar acciones de escritorio en [!DNL Experience Manager] interfaz web {#desktopactions-v2}

Desde dentro de la variable [!DNL Assets] en un navegador, puede explorar las ubicaciones de los recursos o desproteger y abrir el recurso para editarlo en la aplicación de escritorio. Estas opciones se denominan [!UICONTROL Desktop Actions] y no están activados de forma predeterminada. Para habilitarlo, siga estos pasos.

1. En el [!DNL Assets] de la consola, haga clic en **[!UICONTROL User]** de la barra de herramientas.
1. Haga clic en **[!UICONTROL My Preferences]** para mostrar el **[!UICONTROL Preferences]** diálogo.

1. En el [!UICONTROL User Preferences] cuadro de diálogo, seleccione **[!UICONTROL Show Desktop Actions For Assets]** y haga clic en **[!UICONTROL Accept]**.


   ![Seleccione Mostrar acciones de escritorio para recursos para habilitar las acciones de escritorio](assets/enable_desktop_actions.png)

   *Figura: Select [!UICONTROL Show Desktop Actions For Assets] para habilitar las acciones de escritorio.*

## Examinar, buscar y previsualizar recursos {#browse-search-preview-assets}

Puede buscar y previsualizar los recursos disponibles en la [!DNL Experience Manager] repositorio, todo desde la aplicación de escritorio. Pruebe lo siguiente en la aplicación:

1. Vaya a una carpeta y vea información básica de los recursos disponibles en la carpeta, así como miniaturas pequeñas de todos los recursos.

   ![Examinar los archivos y carpetas DAM](assets/browse_folder_da2.png "Examinar los archivos y carpetas DAM")

1. Para ver más información y una miniatura más grande de un recurso individual, haga clic en el nombre del archivo.

   ![Ver una vista previa más grande de un recurso y acciones](assets/large_preview_actions_da2.png "Ver una vista previa más grande de un recurso y acciones")

1. Haga clic en **[!UICONTROL Open]** o **[!UICONTROL Edit]** para descargar el archivo localmente y solo viéndolo o editarlo en la aplicación nativa, respectivamente.
1. Busque utilizando palabras clave para encontrar un recurso relacionado en la variable [!DNL Experience Manager] repositorio. Uso `?` y `*` como comodines. Estos comodines sustituyen a un solo carácter o a varios caracteres, respectivamente. Filtre y ordene los resultados según sea necesario.

   ![Búsqueda de muestra mediante el comodín asterisco](assets/search_wildcard_da2.png "Búsqueda de muestra mediante el comodín asterisco")

   ![Otra búsqueda de ejemplo utilizando el comodín asterisco](assets/search_wildcard2_da2.png "Otra búsqueda de muestra con una ubicación diferente del comodín asterisco")

>[!NOTE]
>
>La aplicación muestra los recursos cumpliendo los criterios de búsqueda en varios campos de metadatos y no solo el título del recurso o el nombre de archivo.

## Descarga de recursos {#download-assets}

Puede descargar los recursos en el sistema de archivos local. La aplicación recupera los recursos de [!DNL Experience Manager] y guarda la misma copia en el sistema de archivos local.

Haga clic en ![Icono Más opciones](assets/do-not-localize/more2_da2.png) para las opciones y haga clic en ![Icono de descarga](assets/do-not-localize/download_cloud_da2.png) para descargar.

![Opción de descarga de un recurso](assets/download_option_da2.png "Opción de descarga de un recurso")

>[!NOTE]
>
>Al descargar o cargar un archivo grande o varios archivos, la aplicación desactiva las acciones en los recursos y carpetas. Las acciones están disponibles cuando se completa la descarga o carga.

La descarga de varios recursos puede producir un rendimiento deficiente si el tamaño de la cola es grande o si tiene algún problema de red. Además, puede poner en cola inconscientemente muchos recursos para su descarga cuando descargue una carpeta. Para evitar largos tiempos de espera, la aplicación restringe el número de recursos descargados de una sola vez. Para saber cómo configurarlo, consulte [Definir preferencias](install-upgrade.md#set-preferences). Incluso por debajo de este límite, la aplicación puede a veces buscar una confirmación antes de descargar una carpeta aparentemente grande.

![La aplicación confirma la descarga de un número relativamente grande de recursos](assets/download_confirmation_da2.png "La aplicación confirma la descarga de un número relativamente grande de recursos")

Si se seleccionan y descargan carpetas, la aplicación solo descarga los recursos almacenados directamente en las carpetas de [!DNL Experience Manager]. No descarga recursos de subcarpetas automáticamente.

## Abra recursos en el escritorio {#openondesktop-v2}

Puede abrir los recursos remotos para verlos en la aplicación nativa. Los recursos se descargan en una carpeta local y se inician en la aplicación nativa asociada al formato de archivo. Puede cambiar la aplicación nativa para abrir tipos de archivo específicos (extensiones) en su Mac o Windows.

Haga clic en **[!UICONTROL Open]** en el menú de recursos. El recurso se descarga localmente y se abre en la aplicación nativa. Compruebe el progreso de la descarga y la velocidad de transferencia de recursos grandes en la barra de estado.

<!-- ![Download progress bar for large-sized assets](assets/download_status_bar_da2.png "Download progress bar for large-sized assets")
-->

>[!NOTE]
>
>Si los cambios esperados no se reflejan en la aplicación, haga clic en el icono actualizar . ![Actualizar icono](assets/do-not-localize/refresh.png) o haga clic con el botón derecho en la interfaz de la aplicación y haga clic en **[!UICONTROL Refresh]**. Las acciones no están disponibles mientras haya descargas o cargas más grandes en curso.

Para abrir la carpeta de descarga local de un recurso, haga clic en ![Más icono de acciones](assets/do-not-localize/more2_da2.png) y haga clic en ![Icono Revelar](assets/do-not-localize/reveal_action2_da2.png) **[!UICONTROL Reveal File]** acción.

## Usar o colocar recursos en documentos nativos {#place-assets-in-native-documents}

En algunos casos, por ejemplo, al colocar un recurso en un documento nativo, se accede a un archivo en el Explorador de Windows o en el Buscador de Mac. Para llegar a la ubicación del sistema de archivos del archivo descargado localmente, utilice la variable ![Icono Revelar](assets/do-not-localize/reveal_action2_da2.png) **[!UICONTROL Reveal File]** .

![Mostrar acción de archivo para un recurso](assets/revealfile_action_da2.png "Mostrar acción de archivo para un recurso")

Haga clic en **[!UICONTROL Reveal File]** o **[!UICONTROL Reveal Folder]** en una carpeta, para abrir el Explorador de Windows o el Buscador de Mac con el archivo o la carpeta preseleccionados en el equipo local. La opción es útil para, por ejemplo, colocar la variable [!DNL Experience Manager] en las aplicaciones nativas que admiten la colocación o vinculación de archivos locales. Para ver cómo colocar archivos en Adobe InDesign, consulte [Colocación de gráficos](https://helpx.adobe.com/indesign/using/placing-graphics.html).

La variable **[!UICONTROL Reveal File]** acción abre un recurso compartido de red local que muestra solo los recursos disponibles localmente, es decir, muestra los recursos que se mostraron, descargaron o abrieron/editaron mediante la aplicación. El recurso compartido de red local no carga ningún cambio en [!DNL Experience Manager]. Para cargar los cambios, utilice explícitamente **[!UICONTROL Upload Changes]** o **[!UICONTROL Upload]** acciones en la aplicación.

>[!NOTE]
>
>Para la compatibilidad con versiones anteriores con [!DNL Experience Manager] aplicación de escritorio v1.x, los archivos mostrados se proporcionan desde un recurso compartido de red local, lo que expone solo los archivos disponibles localmente. Las rutas de escritorio de los archivos revelados son las mismas que las rutas creadas por la aplicación v1.x.

>[!CAUTION]
>
>No use **[!UICONTROL Reveal File]** para editar recursos en aplicaciones nativas. En su lugar, utilice el **[!UICONTROL Edit]** acciones. Para obtener más información, consulte [Flujo de trabajo avanzado: colaborar en los mismos archivos y evitar conflictos de edición](#adv-workflow-collaborate-avoid-conflicts).

## Editar recursos y cargar recursos actualizados a [!DNL Experience Manager] {#edit-assets-upload-updated-assets}

Abra los recursos para editarlos cuando desee realizar cambios y cargue los recursos actualizados en el servidor de AEM de Experience Manager. Para evitar conflictos con las ediciones de otros usuarios, utilice la aplicación para iniciar una sesión de edición. Antes de comenzar la edición, asegúrese de que el recurso no tenga un icono de bloqueo, es decir, que otro usuario no esté editando el recurso.

Para editar un recurso, busque el recurso o navegue hasta su ubicación. Haga clic en ![Más icono](assets/do-not-localize/more2_da2.png) y haga clic en **[!UICONTROL Edit]**.

Uso **[!UICONTROL Toggle Check-out]** para bloquear el recurso y evitar conflictos con ediciones de otros usuarios en las dos situaciones siguientes:

* Ha empezado a editar un recurso sin desprotegerlo primero (por ejemplo, abriéndolo).
* Tiene previsto empezar a editar un recurso en breve y no desea que otros lo hagan.

Una vez que haya terminado de realizar las ediciones, la aplicación muestra la variable **[!UICONTROL Edited Locally]** estado de los recursos modificados. Todos los cambios guardados en los recursos son solo locales hasta que cargue los cambios en [!DNL Experience Manager]. Para cargar uno o varios recursos uno a uno, haga clic en **[!UICONTROL Upload Changes]** en las opciones de un recurso. Crea una versión del recurso en [!DNL Experience Manager]. Uso de la interfaz web de [!DNL Assets], puede ver el historial de recursos en la [Vista Cronología](https://experienceleague.adobe.com/docs/experience-manager-65/assets/using/activity-stream.html).

![Opción Cargar cambios en la aplicación](assets/upload_changes_single1_da2.png "Opción Cargar cambios en la aplicación")

![Opción Cargar cambios al ver una vista previa grande de un recurso](assets/upload_changes_single2_da2.png "Opción Cargar cambios al ver una vista previa grande de un recurso")

Para conocer las prácticas recomendadas relacionadas con la edición colaborativa, consulte [Flujo de trabajo avanzado: colaborar en los mismos archivos y evitar conflictos de edición](#adv-workflow-collaborate-avoid-conflicts).

En los siguientes casos, es posible que desee descartar los cambios y ediciones realizados en el recurso local. Haga clic **[!UICONTROL Discard Changes]**.

* Si no desea guardar los cambios locales en [!DNL Experience Manager].
* Comience a realizar cambios en el recurso original después de guardar algunos cambios.
* Deje de editar el recurso porque ya no es necesario.

Si es necesario, active la desprotección. El recurso actualizado se elimina de la carpeta de caché local y se descarga de nuevo al editarlo o abrirlo.

## Cargar y agregar nuevos recursos a [!DNL Experience Manager] {#upload-and-add-new-assets-to-aem}

Los usuarios pueden agregar nuevos recursos al repositorio de DAM. Por ejemplo, puede ser un fotógrafo o contratista de una agencia que quiera agregar un gran número de fotos de una sesión fotográfica al [!DNL Experience Manager] repositorio. Para agregar contenido nuevo a [!DNL Experience Manager], seleccione ![opción cargar en nube](assets/do-not-localize/upload_to_cloud_da2.png) en la barra superior de la aplicación. Vaya a los archivos de recursos en el sistema de archivos local y haga clic en **[!UICONTROL Select]**. Como alternativa, para cargar recursos, arrastre los archivos o carpetas en la interfaz de la aplicación. En Windows, si arrastra recursos en una carpeta dentro de la aplicación, los recursos se cargan en la carpeta . Si la carga tarda más, la aplicación muestra una barra de progreso.

<!-- ![Download progress bar for large-sized assets](assets/upload_status_da2.png "Download progress bar for large-sized assets")
-->

Puede cargar carpetas o archivos individuales desde el sistema de archivos local. La jerarquía de una carpeta se conserva cuando se carga. Antes de cargar los recursos de forma masiva, consulte [Cargas masivas](#bulk-upload-assets).

Para ver la lista de recursos transferidos en una sesión determinada, haga clic en **[!UICONTROL View]** > **[!UICONTROL Assets transfers]**. La lista le permite ver y verificar rápidamente las transferencias de archivos de la sesión actual.

![Lista de los activos transferidos en una sesión determinada](assets/assets_transfered_da2.png "Lista de los activos transferidos en una sesión determinada")

Puede controlar la concurrencia de carga (aceleración) en **[!UICONTROL Preferences]** > **[!UICONTROL Upload acceleration]** configuración. Una mayor concurrencia suele proporcionar cargas más rápidas, pero puede requerir muchos recursos, lo que consume más potencia de procesamiento del equipo local. Si experimenta un sistema lento, vuelva a intentar cargar las cargas utilizando un valor de concurrencia inferior.

>[!NOTE]
>
>La lista de transferencia no es persistente y no está disponible si sale de la aplicación y la vuelve a abrir.

### Administrar caracteres especiales en los nombres de recursos {#special-characters-in-filename}

En la aplicación heredada, los nombres de nodo creados en el repositorio conservaban los espacios y las mayúsculas y minúsculas de los nombres de carpeta proporcionados por el usuario. Para que la aplicación actual emule las reglas de nomenclatura de nodos de la aplicación v1.10, habilite [!UICONTROL Use legacy conventions when creating nodes for assets and folders] en el [!UICONTROL Preferences]. Consulte [preferencias de la aplicación](/help/install-upgrade.md#set-preferences). Esta preferencia heredada está desactivada de forma predeterminada.

>[!NOTE]
>
>La aplicación solo cambia los nombres de nodo en el repositorio mediante las siguientes convenciones de nomenclatura. La aplicación conserva la variable `Title` del recurso tal cual.

<!-- TBD: Do NOT use this table.

| Where do characters occur | Characters | Legacy preference | Renaming convention | Example |
|---|---|---|---|---|
| In file name extension | `.` | Enabled or disabled | Retained as is | NA |
| File or folder name | `. / : [ ] | *` | Enabled or disabled | Replaced with a `-` (hyphen) | `myimage.jpg` remains as is and `my.image.jpg` changes to `my-image.jpg`. |
| Folder name | `% ; # , + ? ^ { } "` | Disabled | Replaced with a `-` (hyphen) | tbd |
| File name | `% # ? { } &` | Disabled | Replaced with a `-` (hyphen) | tbd |
| File name | Whitespaces | Enabled or disabled | Retained as is | NA |
| Folder name | Whitespaces | Disabled | Replaced with a `-` (hyphen) | tbd |
| File name | Uppercase characters | Disabled | Retained as is | tbd |
| Folder name | Uppercase characters | Disabled | Replaced with a `-` (hyphen) | tbd |
-->

| Caracteres ‡ | Preferencias heredadas en la aplicación | Cuando se producen en nombres de archivo | Cuando ocurre en nombres de carpeta | Ejemplo |
|---|---|---|---|---|
| `. / : [ ] | *` | Habilitado o deshabilitado | Se sustituye por `-` (guion). A `.` (punto) en la extensión de nombre de archivo se conserva tal cual. | Se sustituye por `-` (guion). | `myimage.jpg` permanece tal cual y `my.image.jpg` cambia a `my-image.jpg`. |
| `% ; # , + ? ^ { } "` y espacios en blanco | ![anular selección de icono](assets/do-not-localize/deselect-icon.png) Desactivado | Los espacios en blanco se conservan | Se sustituye por `-` (guion). | `My Folder.` cambia a `my-folder-`. |
| `# % { } ? & .` | ![anular selección de icono](assets/do-not-localize/deselect-icon.png) Desactivado | Se sustituye por `-` (guion). | ND. | `#My New File.` cambia a `-My New File-`. |
| Caracteres en mayúsculas | ![anular selección de icono](assets/do-not-localize/deselect-icon.png) Desactivado | El cajón se conserva tal cual. | Se ha cambiado a caracteres en minúsculas. | `My New Folder` cambia a `my-new-folder`. |
| Caracteres en mayúsculas | ![icono seleccionado](assets/do-not-localize/selection-checked-icon.png) Habilitado | El cajón se conserva tal cual. | El cajón se conserva tal cual. | ND. |

✓ La lista de caracteres es una lista separada por espacios en blanco.

<!-- TBD: Check if the following is to be included in the footnote.

Do not use &#92;&#92; in the names of files and &#92;&#116; &#38; in the names of folders. 
-->


<!-- TBD: Securing the below presentation of the same content in a comment.

**File names**

| Characters | Replaced by |
|---|---|
| &#35; &#37; &#123; &#63; &#125; &#38; &#46; &#47; &#58; &#91; &#124; &#93; &#42; | hyphen (-) |
| whitespaces | whitespaces are retained |
| capital case | casing is retained |

>[!CAUTION]
>
>Avoid using &#92;&#92; in file names.

**Folder names**

| Characters | Replaced by |
|---|---|
| Characters | Replaced by |
| &#37; &#59; &#35; &#44; &#43; &#63; &#94; &#123; &#123; &#34; &#46; &#47; &#59; &#91; &#93; &#124; &#42; | hyphen (-) |
| whitespaces | hyphen (-) |
| capital case | lower case |

>[!CAUTION]
>
>Avoid using &#92;&#92; &#92;&#116; &#38; in folder names.

>[!NOTE]
>
>If you enable [!UICONTROL Use legacy conventions when creating nodes for assets and folders] in app [!UICONTROL Preferences], then the app emulates v1.10 app behavior when uploading folders. In v1.10, the node names created in the repository respect spaces and casing of the folder names provided by the user. For more information, see [app Preferences](/help/install-upgrade.md#set-preferences).

-->

## Trabajar con varios recursos {#work-with-multiple-assets}

Los usuarios pueden trabajar fácilmente con y administrar varios recursos mediante acciones como cargar todas las ediciones de una sola vez o cargar carpetas anidadas en pocos clics.

### Examinar carpetas grandes {#browse-large-folders}

Cuando trabaje con carpetas que contienen muchos recursos, desplácese para ver más recursos. Para desplazarse con el teclado, pulse la pestaña varias veces para seleccionar el recurso en la parte superior. Observe el recurso resaltado para saber cuándo está seleccionado. Ahora utilice la tecla de flecha abajo para desplazarse por la lista de recursos.

### Acciones rápidas para los recursos seleccionados {#quick-actions-for-selected-assets}

Haga clic en la miniatura de algunos recursos para seleccionar los recursos. Para seleccionar todos los recursos, haga clic en la casilla de verificación de la barra superior de la aplicación. El conjunto de acciones que se aplican a todos los recursos seleccionados de forma colectiva se muestra en una barra de herramientas situada en la parte inferior de la aplicación.

![La barra de herramientas de la parte inferior muestra las acciones relevantes para los recursos seleccionados](assets/actions_bottom_toolbar1_da2.png "La barra de herramientas de la parte inferior muestra acciones comunes para los recursos seleccionados")

![No hay acciones en la barra de herramientas cuando no hay acciones comunes para la selección](assets/actions_bottom_toolbar2_da2.png "No hay acciones en la barra de herramientas cuando no hay acciones comunes para la selección")

Las acciones disponibles en la barra de herramientas de la parte inferior dependen del estado de los archivos seleccionados. Por ejemplo, si solo selecciona **[!UICONTROL Edited Locally]** archivos, verá **[!UICONTROL Upload Changes]** icono. Si selecciona una combinación de **[!UICONTROL Edited locally]** y **[!UICONTROL Cloud only]**, el **[!UICONTROL Upload Changes]** la acción no está disponible.

### Buscar todas las imágenes editadas {#find-all-edited-images}

La aplicación proporciona una vista denominada **[!UICONTROL Edited locally]**, para permitirle acceder rápidamente a todos los archivos que descargó localmente (mediante [!UICONTROL Open] o [!UICONTROL Edit] acciones) y luego se modificó. La aplicación le permite seleccionar todos los recursos editados localmente y cargar los cambios en unos pocos clics. Esta vista también muestra los recursos editados localmente que tienen un conflicto de edición.

![Filtrar para ver todos los recursos editados localmente](assets/edited_locally_filter_da2.png "Filtre para ver todos los recursos editados localmente, por ejemplo, para la carga masiva de ediciones")

### Carga masiva de recursos {#bulk-upload-assets}

Los usuarios u organizaciones, como fotógrafos o agencias creativas, pueden crear numerosos recursos locales en escenarios, como fotografías, retoques o selecciones de un conjunto más grande realizado fuera [!DNL Experience Manager]. Pueden cargar estas carpetas locales grandes a [!DNL Assets] directamente desde la aplicación de escritorio. Las jerarquías de carpetas se conservan y se cargan todas las subcarpetas anidadas y los recursos incluidos. Los recursos cargados también están disponibles inmediatamente para el consumo de otros usuarios del mismo servidor. Los recursos se cargan en segundo plano, por lo que la operación no está vinculada a una sesión del explorador web.

![Cargue varias carpetas locales de forma masiva desde el escritorio a [!DNL Experience Manager]](assets/upload_local_folders_da2.png "Carga masiva de varias carpetas locales desde el escritorio en el Experience Manager")

Después de cargar, si los cambios esperados no se reflejan en la aplicación, haga clic en el icono de actualización ![Actualizar icono](assets/do-not-localize/refresh.png).

>[!NOTE]
>
>No utilice la funcionalidad de carga para migrar recursos entre dos [!DNL Experience Manager] implementaciones. En su lugar, consulte la [guía de migración](https://experienceleague.adobe.com/docs/experience-manager-65/assets/administer/assets-migration-guide.html).

### Lista de activos transferidos {#list-of-transferred-assets}

Para ver la lista de activos transferidos en una sesión determinada, consulte [Cargar recursos a [!DNL Experience Manager]](#upload-and-add-new-assets-to-aem).

## Flujo de trabajo avanzado: comience desde el [!DNL Assets] interfaz web {#adv-workflow-start-from-aem-ui}

Si es necesario, inicie el flujo de trabajo desde la interfaz web de Assets. La aplicación de escritorio se integra con el [!DNL Experience Manager] para tomar el cargo cuando se solicite mediante acciones de escritorio.

Un caso especial de inicio de un flujo de trabajo desde la interfaz web es la detección de recursos. La barra Omnisearch de la interfaz de usuario de Assets ofrece una experiencia de búsqueda avanzada y enriquecida. En primer lugar, es posible que desee localizar un recurso deseado en la web y, a continuación, iniciar el flujo de trabajo en la aplicación utilizando [!UICONTROL Desktop Actions]. Algunos casos de ejemplo incluyen el filtrado de resultados de búsqueda mediante facetas, la localización de un recurso específico con licencia de Adobe Stock o una personalización implementada por su organización que le permita realizar una mejor detección desde la interfaz web.

La funcionalidad de la aplicación de escritorio se utiliza cuando intenta realizar las siguientes acciones en la interfaz web de Assets:

* La variable [!UICONTROL Desktop Actions] que permite [!UICONTROL Open], [!UICONTROL Edit]y [!UICONTROL Reveal]
* [!UICONTROL Upload folder]
* [!UICONTROL Check-out] o [!UICONTROL check-in]

Por ejemplo, las acciones en la interfaz web que están disponibles para un recurso desprotegido en la aplicación son [!UICONTROL Open], [!UICONTROL Reveal]y [!UICONTROL Check-in].

![Acciones de escritorio en la variable [!DNL Experience Manager] interfaz web](assets/assets_web_actions_da2.png "Acciones de escritorio en la interfaz web del Experience Manager")

>[!NOTE]
>
>Es posible que el explorador le pida que permita el inicio de [!DNL Adobe Experience Manager] Escritorio. Para disfrutar de una transferencia ininterrumpida del explorador a la aplicación, active la casilla de verificación correspondiente para permitir siempre que la aplicación tome el control.

No se puede encontrar la siguiente información o flujo de trabajo mediante la interfaz web. Utilice la aplicación de escritorio, ya que la interfaz web no realiza un seguimiento de los cambios locales y no tiene en cuenta lo siguiente:

* Archivos editados localmente.
* Archivos que tienen un conflicto de edición y la forma de resolverlo.
* Cargar cambios locales a [!DNL Experience Manager].
* Varios estados de los archivos disponibles localmente.

Por el contrario, puede abrir el recurso en la interfaz web a partir de la aplicación de escritorio utilizando la función **[!UICONTROL Open In Web]** acción.

## Flujo de trabajo avanzado: colaborar en los mismos archivos y evitar conflictos de edición {#adv-workflow-collaborate-avoid-conflicts}

En entornos de colaboración, es posible que varios usuarios trabajen en el mismo conjunto de recursos que pueden provocar conflictos de versiones. Para evitar conflictos, siga estas prácticas recomendadas:

* No edite ningún recurso haciendo clic en [!UICONTROL Open]. No edite los recursos descargados localmente abriéndolos desde la carpeta del sistema de archivos. Otros usuarios no saben que el recurso se está editando.
* Para editar un recurso, haga clic siempre en [!UICONTROL Edit]. Abre el recurso en la aplicación nativa y añade un icono de bloqueo al recurso, de modo que los demás usuarios saben que el recurso se está editando.
* Haga clic en [!UICONTROL Toggle Check-in] si accidentalmente inicia la edición sin hacer clic en [!UICONTROL Edit]. Esto añade un icono de bloqueo al recurso. Incluso si planea editar un recurso más adelante pero desea evitar que otros lo editen, haga clic en [!UICONTROL Toggle Check-in] para bloquear el recurso.
* Antes de editar un recurso, asegúrese de que otros usuarios no lo estén editando. Busque el icono de candado en el recurso.
* Después de completar las ediciones, cargue todos los cambios y, a continuación, registre el recurso.

![Estados de la edición de conflictos](assets/edits_conflicts_status_da2.png "Estados de la edición de conflictos")

Si un recurso descargado localmente se actualiza en la variable [!DNL Experience Manager] servidor, la aplicación muestra un **[!UICONTROL Modified remotely]** estado. Puede quitar la copia local o actualizar la copia local haciendo clic en [!UICONTROL Remove] o [!UICONTROL Update] respectivamente. Los vínculos del cuadro de diálogo permiten ver ambas versiones del recurso.

![Opciones para resolver el conflicto cuando el recurso se modifica de forma remota](assets/modified_remotely_dialog_da2.png "Opciones para resolver el conflicto cuando el recurso se modifica de forma remota")

Si un recurso que está editando localmente también se actualiza en el servidor sin su conocimiento, la aplicación muestra un **[!UICONTROL Editing Conflict]** estado. Puede conservar un conjunto de cambios, ya sea conservar las actualizaciones (haga clic en **[!UICONTROL Keep Mine]**) y eliminar la edición del otro usuario, o respetar las actualizaciones del otro usuario y eliminar la suya (**[!UICONTROL Overwrite Mine]**).

![Opciones para resolver un conflicto de edición](assets/editing_conflict_dialog_da2.png "Opciones para resolver un conflicto de edición")

## Flujo de trabajo avanzado: colocar y vincular recursos en el archivo de InDesign {#adv-workflow-place-assets-indesign}

Cuando utilice [!DNL Experience Manager] aplicación de escritorio para abrir archivos con recursos vinculados, los recursos se descargan previamente y aparecen colocados en las aplicaciones nativas. Para que este flujo de trabajo funcione, la aplicación nativa debe admitir la colocación de vínculos a recursos locales y [!DNL Experience Manager] debe admitir la resolución de estos vínculos en los archivos binarios a referencias del lado del servidor.

[!DNL Experience Manager] la aplicación de escritorio es compatible con este flujo de trabajo con algunas aplicaciones de escritorio y formatos de archivo de Adobe Creative Cloud seleccionadas: Adobe InDesign, Adobe Illustrator y Adobe Photoshop. El flujo de trabajo le permite trabajar de forma eficaz con los archivos Creative Cloud admitidos. Por lo tanto, si el usuario A coloca algunos recursos en un archivo de InDesign y lo comprueba en [!DNL Experience Manager], el usuario B ve los recursos en el archivo de InDesign aunque no formen parte del archivo. Los recursos se descargan localmente en el equipo del usuario B.

>[!NOTE]
>
>La aplicación de escritorio puede asignarse a cualquier unidad de Windows. Sin embargo, para operaciones suaves, no cambie la letra de unidad predeterminada. Si los usuarios de la misma organización utilizan letras de unidad diferentes, no pueden ver los recursos colocados por otros. Los recursos colocados no se recuperan a medida que cambia la ruta. Los recursos colocados siguen colocados en el archivo binario (por ejemplo, INDD) y no se eliminan.

Para conocer las limitaciones de este flujo de trabajo, consulte la [requisitos del sistema y versiones compatibles](release-notes.md).

Para probar este flujo de trabajo con un recurso de imagen y un InDesign, siga estos pasos:

1. Mantener a mano un archivo INDD con activos colocados en [!DNL Experience Manager]. Para saber cómo crear un archivo INDD de este tipo, consulte [Colocación de gráficos](https://helpx.adobe.com/indesign/using/placing-graphics.html).
1. Desde la aplicación de escritorio, **[!UICONTROL Edit]** el archivo INDD con activos colocados en [!DNL Experience Manager].
1. La aplicación descarga tanto el archivo de InDesign como los recursos vinculados. Cuando el InDesign abre el documento, los vínculos se resuelven, los recursos se descargan y los recursos se muestran en el documento de InDesign.
1. Para colocar un nuevo gráfico en el archivo de InDesign, utilice **[!UICONTROL Reveal File]** en el recurso. La acción descarga el recurso localmente y abre la ubicación del recurso compartido de red local en el Explorador de Windows o en el Buscador de Mac.
1. Coloque el recurso mostrado en el documento de InDesign. Esto crea un vínculo en el documento.
1. Una vez completadas las ediciones en el documento de InDesign, guárdelo y cárguelo en [!DNL Experience Manager] mediante la aplicación de escritorio.

## Flujo de trabajo avanzado: descargar los recursos localmente {#adv-workflow-download-assets-locally}

La aplicación descarga los recursos de [!DNL Experience Manager] servidor localmente en su sistema de archivos en muchos casos. Las descargas consumen ancho de banda y espacio en disco. Conocer los escenarios le ayuda a optimizar el tiempo de espera para que se completen las descargas.

Los recursos se descargan desde la aplicación bajo demanda. Consulte [Descargar recursos](#download-assets).

Al usar la variable [!UICONTROL Open] para abrir un recurso en una aplicación de escritorio nativa, el recurso se descarga localmente si no está disponible localmente. Consulte [Abrir recursos](#openondesktop-v2).

Cuando se muestra la ubicación de un recurso o una carpeta dentro de la aplicación, el recurso o la carpeta se descarga primero localmente y, a continuación, se abre en el equipo en el recurso compartido de red local. Consulte [Abrir recursos](#openondesktop-v2).

Al usar la variable [!UICONTROL Edit] para editar un recurso en una aplicación de escritorio nativa, el recurso se descarga localmente si no está disponible localmente. Consulte [Editar recursos y cargar recursos actualizados a [!DNL Experience Manager]](#edit-assets-upload-updated-assets).

Si la aplicación está instalada y se le permite hacerlo, completa las acciones cuando utiliza [!UICONTROL Desktop Actions] from [!DNL Experience Manager] interfaz web. La aplicación descarga primero el recurso y, a continuación, completa la acción.
