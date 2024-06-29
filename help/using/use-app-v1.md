---
title: Uso [!DNL Experience Manager] versión de aplicación de escritorio 1.10.
description: Aprenda a utilizar la versión 1.10 de la aplicación de escritorio de Adobe Experience Manager y a optimizar su trabajo con los recursos en el escritorio.
feature: Desktop App,Asset Management
exl-id: 2fdc1c8d-b822-4cca-ad06-bd875a00aa6d
source-git-commit: 5676e7ece8bb43f051dae72d17e15ab1c34caefc
workflow-type: tm+mt
source-wordcount: '2329'
ht-degree: 0%

---

# Uso [!DNL Experience Manager] aplicación de escritorio v1.10 {#use-aem-desktop-app-v1x}

Con la aplicación, los recursos de [!DNL Experience Manager] son fácilmente accesibles desde el escritorio local y se pueden utilizar en cualquier aplicación de escritorio. Assets se puede mostrar fácilmente en el Finder de Mac o en el Explorador de Windows, abrirse en aplicaciones de escritorio y cambiarse localmente: los cambios se guardan de nuevo en [!DNL Experience Manager] con una nueva versión creada en el repositorio.

Esta integración permite la administración centralizada de recursos y el acceso entre Creative Cloud y otras aplicaciones, lo que garantiza la conformidad con la marca y otros estándares.

Las tareas clave que realiza con la variable [!DNL Experience Manager] la aplicación de escritorio v1 incluye:

1. [Conexión con un [!DNL Experience Manager] server](#installandconnect)
1. [Abra los recursos directamente en la aplicación de escritorio](#openondesktop)
1. [Edición y extracción de recursos desde la aplicación de escritorio](#workonassets)
1. [Carga de recursos y carpetas por lotes](#bulkupload)

Para ver las distintas dosis y no opciones recomendadas, consulte la [prácticas recomendadas para utilizar la aplicación de escritorio](best-practices-for-v1.md). Si tiene problemas al utilizar la aplicación, consulte cómo [solucionar problemas [!DNL Experience Manager] aplicación de escritorio](troubleshoot-app-v1.md).

>[!NOTE]
>
>La aplicación de escritorio de se introdujo en [!DNL Experience Manager] Versión 6.1 y se ha llamado a [!DNL Experience Manager Assets Companion App].

## [!DNL Experience Manager] puntos de contacto de la aplicación de escritorio en el flujo de trabajo creativo {#aem-desktop-app-touch-points-in-the-creative-workflow}

[!DNL Experience Manager] aplicación de escritorio, junto con [!DNL Assets], se integra en su flujo de trabajo creativo y ofrece los siguientes puntos de contacto.

![[!DNL Experience Manager] aplicación de escritorio: puntos de contacto en el flujo de trabajo creativo](assets/aem_desktopapp_workflow.png)

[!DNL Experience Manager] aplicación de escritorio: puntos de contacto en el flujo de trabajo creativo

## Instale y conecte la aplicación al [!DNL Experience Manager] server {#installandconnect}

Antes de empezar a crear o editar los recursos creativos, conecte la aplicación de escritorio con el [!DNL Assets] para descargar y cargar recursos en el repositorio. Realice las siguientes tareas:

1. [Instalación de la aplicación](#installapp).
1. [Establezca sus preferencias](#inapppref) y detalles de conexión.
1. [Conexión a un [!DNL Experience Manager] server](#connect) y montar el repositorio de recursos como unidad local.
1. [Activar acciones de escritorio](#desktopactions) en el [!DNL Experience Manager] servidor.

El [!DNL Experience Manager] La aplicación de escritorio de utiliza una conexión HTTPS para conectarse a [!DNL Experience Manager] para transferir sus recursos de forma sólida y segura.

>[!NOTE]
>
>Para todos o parte de los pasos de instalación y configuración, es posible que necesite ayuda de su [!DNL Experience Manager] administrador o administrador del sistema.

### Instalación de la aplicación {#installapp}

Asegúrese de que la aplicación sea compatible con su versión del servidor de Experience Manager para utilizar la aplicación de escritorio de Experience Manager. Descargue el archivo de instalación adecuado (binario) para su sistema operativo (Mac o Windows) e instale la aplicación.

Puede ser necesaria una configuración detallada en función de las preferencias de la red y del sistema. Consulte [Instalación y configuración [!DNL Experience Manager] aplicación de escritorio](install-configure-app-v1.md) para obtener más información.

1. Vaya a la [[!DNL Experience Manager] página de descarga de la aplicación de escritorio v1.10](/help/using/release-notes-of-v1.md) y descargue el binario apropiado para su sistema operativo.
1. Inicie el archivo de instalación descargado y siga las instrucciones que aparecen en pantalla para instalar la aplicación.

   >[!NOTE]
   >
   >Solo una instancia de [!DNL Experience Manager] La aplicación de escritorio de se puede instalar y activar a la vez.

### Comprenda las opciones y preferencias en la aplicación {#inapppref}

La aplicación permite que la configuración se conecte y desconecte de [!DNL Experience Manager] servidores, ver el estado de las cargas, administrar la caché local, etc. La configuración predeterminada funciona para un usuario típico de la aplicación. Puede modificar la configuración para sacar más partido a la aplicación. Además, aproveche al máximo la integración con [!DNL Experience Manager] servidor. A continuación se indican las distintas configuraciones:

**Explorar Assets** Abra la unidad local en la que se encuentra el [!DNL Assets] el repositorio está montado. En otras palabras, explore los recursos que ahora están disponibles en su equipo local.

**Ver estado del recurso** Cuando se cargan recursos modificados o se añaden nuevos recursos a [!DNL Assets] repositorio, la aplicación carga los recursos en segundo plano. La carga en segundo plano permite realizar operaciones sin problemas, sin necesidad de esperar a que finalice la carga, especialmente para los recursos de gran tamaño. Puede guardar los cambios localmente y olvidarlos. La aplicación tarda algún tiempo en enviar estos recursos al servidor, según el ancho de banda disponible. Puede comprobar el estado de la carga junto con información más básica.

**Opciones** Haga clic en opciones en la bandeja de la aplicación de escritorio para configurar el inicio de la aplicación y conectarse al [!DNL Experience Manager] servidor en el inicio y cambie la letra de unidad local de [!DNL Assets] después del montaje.

**Avanzado > Administrar caché** Puede controlar la cantidad de espacio en disco disponible para el almacenamiento en caché local. Los artefactos del [!DNL Assets] Los servidores de se almacenan en caché localmente para una experiencia más fluida. Puede cambiar los valores predeterminados para adaptarlos a sus necesidades. Además, puede borrar la caché para recuperar todos los recursos de nuevo. Cuando borra la caché, conserva los cambios no guardados. Todos los recursos que no se hayan registrado en [!DNL Experience Manager] se conservan y no se eliminan.

### Conexión a un [!DNL Experience Manager] server {#connect}

La aplicación admite la configuración proxy en Mac y Windows. La configuración se lee cuando se inicia la aplicación. Si modifica la configuración del proxy, reinicie la aplicación para que los cambios surtan efecto.

>[!NOTE]
>
>Si modifica la configuración del proxy, reinicie la aplicación para que los cambios surtan efecto. De lo contrario, la aplicación seguirá utilizando el servidor proxy configurado anteriormente.

1. Inicie el [!DNL Experience Manager] aplicación de escritorio. Para asignar su [!DNL Experience Manager] con la aplicación, especifique su [!DNL Experience Manager] servidor con el formato `https://[aem-server-url]:[port]`.

   ![Autenticar en Mac y proporcionar [!DNL Experience Manager] URL del servidor](assets/aem_desktop_app_server_url.png)

1. En la pantalla de inicio de sesión, especifique el nombre de usuario y la contraseña de la instancia. Para especificar una alternativa [!DNL Experience Manager] instancia, seleccione la **[!UICONTROL Alternate Login URL]** opción.

   ![Proporcionar [!DNL Experience Manager] credenciales del servidor en la pantalla de inicio de sesión de [!DNL Experience Manager] aplicación de escritorio](assets/login_screen_v1.png)

### Habilitar acciones de escritorio en [!DNL Experience Manager] interfaz web {#desktopactions}

Desde la interfaz de usuario de Assets, puede explorar las ubicaciones de los recursos o retirarlos y abrirlos para editarlos en la aplicación de escritorio. Estas opciones se denominan acciones de escritorio y no están habilitadas de forma predeterminada. Siga estos pasos para habilitarlo.

1. En la interfaz de Assets, pulse o haga clic en el icono Usuario en la esquina superior derecha de la barra de herramientas.
1. Clic **[!UICONTROL My Preferences]** para mostrar el **[!UICONTROL Preferences]** diálogo.

   ![[!DNL Experience Manager] interfaz con preferencias de usuario](assets/aem_ui_user_preferences.png)

1. En el [!UICONTROL User Preferences] diálogo, seleccione **[!UICONTROL Show Desktop Actions For Assets]**, luego haga clic en **[!UICONTROL Accept]**.

   ![Marque [!UICONTROL Show Desktop Actions For Assets] para habilitar las acciones de escritorio](assets/enable_desktop_actions.png)

   *Imagen: comprobación [!UICONTROL Show Desktop Actions For Assets] para habilitar las acciones de escritorio.*

## Acceso y apertura de recursos en el escritorio {#openondesktop}

Al hacer clic en **Abrir** para abrir un recurso en el equipo local, la aplicación descarga el recurso en su caché interna. La aplicación inicia la aplicación de escritorio nativa asociada al tipo de archivo del recurso descargado.

En Mac, seleccione **Abrir** en el menú contextual para abrir un recurso a través de [!DNL Experience Manager] aplicación de escritorio. En Windows, seleccione Abrir en la web en el menú contextual para abrir el recurso. En la ventana Estado de los recursos, pulse o haga clic en ![Icono Abrir en el escritorio](assets/do-not-localize/aemassets_icon_openondesktop.png) para abrir el recurso.

Para archivos Adobe InDesign (INDD), seleccione **[!UICONTROL Open]** en el menú contextual. Al hacer clic en esta opción, la aplicación descarga los recursos vinculados al sistema de archivos local y, a continuación, abre el archivo INDD en Adobe InDesign. Este método garantiza que los recursos necesarios estén disponibles localmente al editar el archivo INDD.

![Opciones del menú contextual para acceder y abrir recursos mediante [!DNL Experience Manager] aplicación de escritorio](assets/aem_desktopapp_mac_context_menu.png)

*Imagen: opciones del menú contextual para acceder y abrir recursos con la variable [!DNL Experience Manager] aplicación de escritorio.*

>[!NOTE]
>
>El Adobe recomienda ir a Opciones de vista de Finder en Mac y desactivar las opciones **Mostrar información del elemento**, **Mostrar vista previa del elemento**, y **Mostrar columna de previsualización** para el montado [!DNL Assets] carpeta. Mejora el rendimiento.

### Opciones adicionales en [!DNL Experience Manager] interfaz {#additional-options-in-aem-assets}

Después de asignar el [!DNL Assets] en la unidad local, puede habilitar iconos adicionales y la función Carga de carpetas para que aparezcan en los recursos y carpetas asignados.

1. Abra el [!DNL Assets] y pase el puntero sobre una carpeta o un recurso para mostrar las acciones del escritorio como acciones rápidas en la vista de tarjeta.

   ![En la IU de Assets, abra el menú de acciones rápidas para ver las acciones del escritorio](assets/desktop_actions_in_card_view.png)

   *Imagen: en la interfaz de usuario de Assets, abra el menú de acciones rápidas para ver las acciones del escritorio.*

   Estas acciones de escritorio también están disponibles al hacer clic en el icono **Acciones de escritorio** en la barra de herramientas después de seleccionar el recurso o en la barra de herramientas de la página de recursos.

1. Para abrir el recurso en la aplicación de escritorio asociada a la extensión de archivo específica, haga clic en **Abrir en el escritorio** acción rápida ![Icono Abrir en el escritorio](assets/do-not-localize/aemassets_icon_openondesktop.png).

   También puede elegir **Abrir** desde el **Acciones de escritorio** en la barra de herramientas.

Para localizar el recurso concreto en el sistema de archivos local, haga clic en **Mostrar** acción rápida ![Icono Mostrar](assets/do-not-localize/aemassets_reveal_icon.png). También puede elegir **Mostrar** desde el **Acciones de escritorio** en la barra de herramientas.

## Comprender los estados de los recursos {#understand-the-asset-statuses}

| ![Icono de aplicación predeterminada de Windows](assets/do-not-localize/win_default.png) | La aplicación está conectada al servidor y todos los recursos están sincronizados. |
--- |--- |
| ![Icono de Windows deshabilitado](assets/do-not-localize/win_disabled.png) | La aplicación se inicia, pero no está conectada con el servidor. Es posible que algunos recursos estén pendientes de sincronización. |
| ![Icono de sincronización de archivos de Windows](assets/do-not-localize/win_sync.png) | Assets se está sincronizando. Los archivos se están cargando o descargando. Puede ver los estados exactos y pausar las transferencias desde la ventana Estado de los Activos. |
| ![Icono de reconexión de Windows](assets/do-not-localize/win_refresh.png) | La aplicación está intentando volver a conectarse. Es posible que los problemas de red estén provocando la desconexión. |

## Trabaje en sus recursos {#workonassets}

### Consulte los recursos en [!DNL Experience Manager] interfaz web {#check-out-assets-from-the-aem-web-interface}

[!DNL Experience Manager Assets] le permite extraer recursos para editarlos y volver a registrarlos después de completar los cambios. Después de desproteger un recurso, solo puede editarlo, anotarlo, publicarlo, moverlo o eliminarlo. La extracción de un recurso bloquea el recurso y evita que otros usuarios realicen cualquiera de estas operaciones. Para poder desproteger o proteger recursos, se requiere acceso de escritura en ellos.

Existen dos formas de extraer recursos de [!DNL Experience Manager] interfaz web. Para obtener información detallada sobre el primer método, consulte la [archivos de protección y desprotección de la interfaz de usuario de Assets](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/assets/managing/check-out-and-submit-assets). Siga estos pasos para los segundos métodos para desproteger y abrir el recurso cuando el [!DNL Experience Manager] La aplicación de escritorio de está instalada.

1. Abra el [!DNL Assets] y pase el puntero sobre una carpeta o un recurso para mostrar las acciones del escritorio como acciones rápidas en la vista de tarjeta.

   ![Opción Propiedades en la vista de tarjeta](assets/desktop_actions_in_card_view.png)

   Estas acciones de escritorio también están disponibles cuando pulsa o hace clic en el icono Acciones de escritorio de la barra de herramientas después de seleccionar el recurso o en la barra de herramientas de la página del recurso.

1. Para abrir el recurso, pulse o haga clic en la acción rápida Abrir en el escritorio ![Icono Abrir en el escritorio](assets/do-not-localize/aemassets_icon_openondesktop.png).

   También puede elegir Abrir en el menú Acciones de escritorio de la barra de herramientas.

   >[!NOTE]
   >
   >Cuando edita un archivo abierto pero no desprotegido, los demás usuarios no saben que está actualizando el recurso.

1. Para abrir un recurso y editarlo en una aplicación de Adobe Creative Cloud, haga clic en ![Icono Editar escritorio](assets/do-not-localize/aemassets_icon_editdesktop.png). Esta opción también extrae el recurso para editarlo. Una vez finalizada la edición, proteja el recurso para actualizar los cambios en [!DNL Assets].

   También puede elegir Editar en el menú Acciones de escritorio de la barra de herramientas.

1. Seleccione la opción Abrir menú. Los recursos seleccionados se abren en el modo de vista previa.
1. Para editar los recursos, seleccione la opción Editar. Los recursos se abren en modo de edición.

### Consulte los recursos de Finder en macOS {#check-out-assets-on-mac}

La aplicación permite retirar archivos de recursos para evitar que otros usuarios modifiquen los archivos en los que está trabajando.

1. En el menú contextual de Mac, seleccione la opción Abrir carpeta de AEM Assets para abrir el Buscador.

   ![Opciones del menú contextual para acceder y abrir recursos mediante [!DNL Experience Manager] aplicación de escritorio](assets/aem_desktopapp_mac_context_menu.png)

   *Imagen: opciones del menú contextual para acceder y abrir recursos con la variable [!DNL Experience Manager] aplicación de escritorio.*

1. Desplácese hasta el recurso que desee extraer.
1. Haga clic con el botón derecho en el recurso y seleccione Más información de Assets en el menú contextual.
1. En el cuadro de diálogo Información del recurso, pulse o haga clic en el icono Desproteger para desproteger el recurso. El icono Desproteger cambia al icono Proteger después de hacer clic en él o tocarlo.

   ![Examinar el recurso para pagar](assets/browse_assets_to_checkout.png)

1. Para proteger el recurso de modo que esté disponible para otros usuarios, pulse o haga clic en el icono Proteger del cuadro de diálogo Información del recurso.

### Desproteger recursos en Windows {#check-out-assets-on-windows}

La aplicación permite retirar archivos de recursos para evitar que otros usuarios modifiquen los archivos en los que está trabajando.

1. En el menú contextual, seleccione Explorar Assets para abrir el Explorador.
1. En el Explorador, vaya a la ubicación del recurso que desea desproteger.
1. Haga clic con el botón derecho en el recurso y seleccione Abrir en la web en el menú contextual.
1. En el cuadro de diálogo Información del recurso, haga clic en el icono Desproteger. El icono de cierre de compra cambia al icono de registro de entrada.

   ![Conmutadores del icono de cierre de compra](assets/checkout_icon_toggles.png)

1. Revise el recurso en Explorer. El icono de bloqueo del recurso ![Icono de bloqueo de recursos](assets/do-not-localize/aemassets_icon_lockcheckout.png) indica que ha retirado el recurso.

   >[!NOTE]
   >
   >El icono de bloqueo puede aparecer después de un cierto retraso. El [!DNL Experience Manager] la aplicación de escritorio almacena en caché los recursos para acceder rápidamente, por lo que puede tardar unos momentos en actualizar el estado bloqueado.

1. Para proteger el recurso de modo que esté disponible para otros usuarios, pulse o haga clic en el icono de protección en la **Información de recurso** diálogo.

### Registrar un recurso mediante Finder o Explorer y utilizar la interfaz web {#check-in-an-asset-using-finder-or-explorer-and-using-web-interface}

Cuando haya terminado de editar los recursos, guárdelos en la aplicación de escritorio. En el menú contextual, seleccione **Más información de Assets** y haga clic en protección.

Los recursos se cargan en [!DNL Experience Manager] servidor. De forma opcional, puede comprobar el estado de la carga seleccionando **Ver estado del recurso** desde el icono de la bandeja del sistema. También puede proteger un recurso desde el [!DNL Experience Manager] interfaz web. Haga clic en los recursos retirados o selecciónelos. En la barra de herramientas, haga clic en el icono de protección ![icono de registro](assets/do-not-localize/aemassets_icon_checkin.png).

Se carga un recurso en [!DNL Experience Manager] automáticamente después de guardar los cambios localmente. La protección hace que el recurso esté disponible para otros usuarios [!DNL Experience Manager] usuarios para editar.

### Carga masiva de recursos y carpetas a [!DNL Experience Manager] server {#bulkupload}

Uso del [!DNL Experience Manager] aplicación de escritorio, puede cargar una carpeta completa que contenga recursos del directorio de archivos local a [!DNL Assets]. De este modo, todos los recursos de la carpeta se cargan de forma masiva, en lugar de tener que cargarlos de uno en uno.

1. En la IU de Assets, pulse o haga clic en **Crear** en la barra de herramientas y en el menú, seleccione **Cargar carpeta**.
1. Busque la carpeta que desee cargar y selecciónela.
1. Pulse o haga clic en Aceptar. El cuadro de diálogo Estado de Assets muestra el estado de la carga.

   ![Consulte el estado de la carga en la ventana Estado de los activos](assets/aem_desktopapp_bulkupload_status.png)

   Consulte el estado de la carga en la ventana Estado de los recursos

   >[!NOTE]
   >
   >Puede pausar o cancelar manualmente la carga tocando o haciendo clic en el icono correspondiente.

1. Una vez cargada la carpeta, cierre el cuadro de diálogo y vaya a la interfaz de usuario de Assets. La carpeta cargada se muestra en la interfaz web.

El Adobe no recomienda copiar y pegar ni arrastrar un número mayor de archivos o carpetas anidadas, desde el sistema de archivos local, al área de recursos compartidos de red. La aplicación no puede controlar el proceso de carga debido a limitaciones técnicas y a que el rendimiento es deficiente.

También puede seleccionar archivos o carpetas en Finder o Explorer, copiarlos, navegar a la carpeta de destino en el área de recursos compartidos de red y elegir **Pegar Assets** desde el [!DNL Experience Manager] menú contextual de la aplicación de escritorio. Por aquí, el [!DNL Experience Manager] La aplicación de escritorio de comienza cargando los recursos pegados de forma similar a la **Cargar carpeta** opción disponible en el [!DNL Experience Manager] interfaz web.

>[!MORELIKETHIS]
>
>* [Solucionar problemas [!DNL Experience Manager] aplicación de escritorio](troubleshoot-app-v1.md)
