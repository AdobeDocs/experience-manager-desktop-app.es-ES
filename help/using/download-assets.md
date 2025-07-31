---
title: Descargar recursos mediante la aplicación de escritorio  [!DNL Experience Manager] iOS
description: Descargar recursos mediante la aplicación de escritorio  [!DNL Adobe Experience Manager] iOS.
feature: Desktop App,Asset Management
source-git-commit: 2947fbd3bfeb15b37a8f1b0118e969b5d70499d0
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 1%

---


# Descargar recursos localmente {#download-assets-locally}

La aplicación descarga con frecuencia recursos del servidor [!DNL Experience Manager] a su sistema de archivos local. Las descargas consumen ancho de banda y espacio en disco. Conocer los escenarios puede ayudarle a optimizar el tiempo de espera para que se completen las descargas. Puede descargar los recursos en su sistema de archivos local. La aplicación recupera los recursos del servidor [!DNL Experience Manager] y guarda la misma copia en el sistema de archivos local.

Haga clic en **[!UICONTROL More actions]** ![icono de más opciones](assets/do-not-localize/more2_da2.png) para ver las opciones y haga clic en ![Icono de descarga](assets/do-not-localize/download_cloud_da2.png) para descargar.

![Opción de descarga para un recurso](assets/download_option_da2.png "Opción de descarga para un recurso")

>[!NOTE]
>
>Al descargar o cargar un archivo grande o varios archivos, la aplicación desactiva las acciones en recursos y carpetas. Las acciones están disponibles cuando se completa la descarga o la carga.

Cuando utiliza la acción [!UICONTROL Open] para abrir un recurso en una aplicación de escritorio nativa, el recurso se descarga localmente si no está disponible localmente. Consulte [Abrir recursos](#openondesktop-v2).

Al revelar la ubicación de un recurso o una carpeta desde la aplicación, el recurso o la carpeta primero se descargan localmente y, a continuación, se abren en el equipo en el recurso compartido de red local. Consulte [Abrir recursos](#openondesktop-v2).

Cuando se usa la acción [!UICONTROL Edit] para editar un recurso en una aplicación de escritorio nativa, el recurso se descarga localmente si no está disponible localmente. Consulte [Editar recursos y cargar recursos actualizados a [!DNL Experience Manager]](#edit-assets-upload-updated-assets).

Si la aplicación está instalada y se le permite, completa las acciones cuando usa [!UICONTROL Desktop Actions] desde la interfaz web [!DNL Experience Manager]. La aplicación descarga primero el recurso y, a continuación, completa la acción.

## Descargar varios recursos {#download-multiple-assets}

La descarga de varios recursos puede provocar un rendimiento deficiente si el tamaño de la cola es grande o si se enfrenta a algún problema de red. Además, puede poner en cola, sin saberlo, muchos recursos para su descarga al descargar una carpeta. Para evitar tiempos de espera prolongados, la aplicación restringe el número de recursos descargados de una sola vez. Para saber cómo configurarlo, consulte [Establecer preferencias](install-upgrade.md#set-preferences). Incluso por debajo de este límite, la aplicación a veces puede solicitar una confirmación antes de descargar una carpeta aparentemente grande.

![La aplicación confirma la descarga de un número relativamente grande de recursos](assets/download_confirmation_da2.png "La aplicación confirma la descarga de un número relativamente grande de recursos")

Si se seleccionan y descargan carpetas, la aplicación solo descarga los recursos almacenados directamente en las carpetas de [!DNL Experience Manager]. No descarga automáticamente recursos de subcarpetas.

## Próximos pasos {#next-steps}

* [Vea un vídeo para empezar a usar la aplicación de escritorio de Adobe Experience Manager](https://experienceleague.adobe.com/en/docs/experience-manager-learn/assets/creative-workflows/aem-desktop-app)

* Proporcione comentarios sobre la documentación usando [!UICONTROL Edit this page] ![editar la página](assets/do-not-localize/edit-page.png) o [!UICONTROL Log an issue] ![crear un problema de GitHub](assets/do-not-localize/github-issue.png), disponibles en la barra lateral derecha

* Contacto con el [Servicio de atención al cliente](https://experienceleague.adobe.com/es?support-solution=General#support)

>[!MORELIKETHIS]
>
>* [Cargar recursos](/help/using/upload-assets.md)
>* [Comprenda la interfaz de usuario](/help/using/user-interface.md)
>* [Buscar](/help/using/search.md)

