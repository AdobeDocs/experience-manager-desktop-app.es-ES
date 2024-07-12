---
title: Instalación y configuración de la aplicación de escritorio v1.10
description: Instala y configura la  [!DNL Experience Manager] versión 1.10 de la aplicación de escritorio para que funcione con [!DNL Assets] servidores y asigne los recursos que se van a montar como una unidad en el escritorio.
exl-id: 7f3bdfb1-d345-4e48-b020-6e06531f46f2
source-git-commit: 1c7437786a50eeafa884ce92b745f3438b2d2b88
workflow-type: tm+mt
source-wordcount: '884'
ht-degree: 0%

---

# Instalar y configurar la aplicación de escritorio [!DNL Experience Manager] versión 1.10 {#install-and-configure-aem-desktop-app}

Con la aplicación de escritorio [!DNL Experience Manager], los recursos de [!DNL Experience Manager] son fácilmente accesibles desde el escritorio local y se pueden usar en cualquier aplicación de escritorio. Assets se puede mostrar en el Finder de Mac o en el Explorador de Windows, se puede editar en las aplicaciones de escritorio y los cambios se vuelven a guardar en [!DNL Experience Manager], lo que crea una nueva versión tras la carga.

Esta integración permite que diferentes funciones administren recursos de forma centralizada dentro de la organización en Assets, accedan a ellos en Creative Cloud y otras aplicaciones y cumplan fácilmente con varios estándares, incluida la marca.

Para usar la aplicación de escritorio [!DNL Experience Manager],

* Asegúrese de que la versión del servidor [!DNL Experience Manager] sea compatible con la aplicación de escritorio [!DNL Experience Manager]. Consulte la [matriz de compatibilidad](release-notes-of-v1.md#compatibilitymatrix).

* Descargue e instale la aplicación.

* Pruebe la conexión con algunos recursos. Ver [Acceder y abrir recursos en tu escritorio](use-app-v1.md#openondesktop).

## Requisitos del sistema, requisitos previos y vínculos de descarga {#system-requirements-prerequisites-and-download-links}

Para obtener información detallada, consulte las [[!DNL Experience Manager] notas de la versión de la aplicación de escritorio](release-notes-of-v1.md).

## Instalar y conectar la aplicación al servidor [!DNL Experience Manager] {#install-and-connect-aem-desktop-app-to-aem-server}

Para obtener más información, consulta [Instalar y conectar [!DNL Experience Manager] la aplicación de escritorio a [!DNL Experience Manager] servidor](use-app-v1.md#installandconnect).

>[!NOTE]
>
>Solo se puede instalar y activar una instancia de la aplicación de escritorio [!DNL Experience Manager] a la vez.

## Administración de archivos {#file-handling}

Al cambiar un archivo desde una ubicación de recurso compartido de red montada por la aplicación de escritorio, los archivos se guardan en esa ubicación en dos fases. En la primera fase, se guarda un archivo localmente. Un usuario puede guardar el archivo y continuar trabajando en él, sin esperar a que se complete la transferencia.

En la segunda fase, la aplicación de escritorio carga el archivo actualizado en el servidor [!DNL Experience Manager] después de un retraso predefinido (por ejemplo, 30 segundos). Esta operación se produce en segundo plano. Utilice la opción Ver estado del recurso para ver el estado de la operación de carga.

1. Cargue un recurso en Assets.

1. Haga clic en el icono de la aplicación de escritorio [!DNL Experience Manager] de la barra de herramientas.

1. En el menú, seleccione la opción Ver estado del recurso.

1. En el cuadro de diálogo, revise el estado de la operación de carga.

>[!NOTE]
>
>La aplicación de escritorio [!DNL Experience Manager] puede administrar recursos de hasta 40 GB de tamaño.

## Conectarse a una instancia de [!DNL Experience Manager] detrás de un Dispatcher {#connect-to-an-aem-instance-behind-a-dispatcher}

Los métodos copy y move de la API de Assets requieren que se pasen los siguientes encabezados adicionales a [!DNL Experience Manager]:

* Destino X
* Profundidad X
* Sobrescribir X

El escritorio [!DNL Experience Manager] se conecta a [!DNL Experience Manager] mediante una dirección URL que incluye el puerto predeterminado. Por lo tanto, la configuración de `virtualhosts` en la configuración de Dispatcher debe incluir el número de puerto predeterminado. Para obtener más información sobre la configuración de `virtualhosts`, consulte [identificar hosts virtuales](https://experienceleague.adobe.com/en/docs/experience-manager-dispatcher/using/configuring/dispatcher-configuration#identifying-virtual-hosts-virtualhosts).

Para obtener información adicional sobre cómo configurar Dispatcher para que pase estos encabezados adicionales, consulte [Especificación de los encabezados HTTP](https://experienceleague.adobe.com/en/docs/experience-manager-dispatcher/using/configuring/dispatcher-configuration#specifying-the-http-headers-to-pass-through-clientheaders).

### Compatibilidad con proxy {#proxy-support}

La aplicación de escritorio [!DNL Experience Manager] usa el proxy predefinido del sistema para conectarse a Internet a través de HTTPS. La aplicación solo se puede conectar con un proxy de red que no requiera autenticación adicional.

Si establece o modifica la configuración del servidor proxy para Windows (Opciones de Internet > Configuración de LAN), reinicie la aplicación de escritorio [!DNL Experience Manager] para que los cambios surtan efecto.

>[!NOTE]
>
>La configuración proxy solo se aplica al iniciar la aplicación de escritorio. Cierre y vuelva a iniciar la aplicación para que los cambios surtan efecto.

Si el proxy requiere autenticación, el equipo de TI puede permitir que la URL de Experience Manager Assets en la configuración del servidor proxy permita el paso del tráfico de la aplicación.

## Personalización del cuadro de diálogo Información del recurso {#customize-the-asset-info-dialog}

Puede personalizar el cuadro de diálogo Información del recurso superponiendo uno o ambos de estos componentes:

* La página de interfaz de usuario de Granite en `/libs/dam/gui/content/assets/moreinfo`.

* El componente HTL `/css/javascript` en `/libs/dam/gui/components/admin/moreinfo`.

El componente que se superponga depende de la naturaleza de la personalización. Para cambiar qué componentes se muestran como parte del cuadro de diálogo Información del recurso, superponga la página de interfaz de usuario de Granite. Para cambiar el contenido del HTML, CSS o JavaScript del cuadro de diálogo, superponga el componente HTL.

## Administrar caché {#manage-cache}

En Windows, la caché se encuentra en `%LOCALAPPDATA%\Adobe\AssetsCompanion\Cache\`, donde es una versión codificada del host [!DNL Experience Manager] configurado en la aplicación de escritorio. Por ejemplo, `http://localhost:4502` aparece como `http%3A%2F%2Flocalhost%3A4502%2F`.

En macOS X, hay un directorio similar en `~/Library/Group Containers/group.com.adobe.aem.desktop/cache`.

### Opción en la aplicación para administrar la caché {#in-app-option-to-manage-cache}

Puede controlar la cantidad de espacio en disco disponible para el almacenamiento en caché local. Los artefactos del servidor de Assets se almacenan en caché localmente para una experiencia más fluida. Puede cambiar los valores predeterminados para adaptarlos a sus necesidades. Además, puede borrar la caché para recuperar todos los recursos de nuevo. Para establecer las opciones deseadas, haga clic en el icono de la aplicación y luego en **[!UICONTROL Advanced]** > **[!UICONTROL Manage Cache]**. ****

>[!NOTE]
>
>Cuando borra la caché, conserva los cambios no guardados. Los recursos que no se hayan registrado en el servidor [!DNL Experience Manager] se conservarán y no se eliminarán.

### Cambiar la ubicación de la caché en Windows {#change-location-of-cache-on-windows}

La ubicación predeterminada de la caché para la aplicación de escritorio [!DNL Experience Manager] es la siguiente:

* En Windows, `%LocalAppData%\Adobe\AssetsCompanion\Cache\EncodedAEMEndpoint`.

* En Mac, `~/Library/Group/Containers/group.com.adobe.aem.desktop/cache/EncodedAEMEndpoint`.

`EncodedAEMEndpoint` es la URL de extremo [!DNL Experience Manager] configurada en la aplicación. El valor es una versión codificada de la dirección URL de destino del servidor [!DNL Experience Manager]. Por ejemplo, si la aplicación tiene como destino `http://localhost:4502`, el nombre del directorio es `http%3A%2F%2Flocalhost%3A4502`. La ruta de acceso de Windows al directorio de caché en este ejemplo es `%LocalAppData%\Adobe\AssetsCompanion\Cache\http%3A%2F%2Flocalhost%3A4502`.

Para dirigir la aplicación a una carpeta o unidad diferente, edite el archivo de configuración de la aplicación.

1. Vaya al directorio de instalación de la aplicación. La ubicación predeterminada en Windows es `C:\Program Files (x86)\Adobe\Adobe Experience Manager Desktop`.

1. Edite el archivo `Adobe Experience Manager Desktop.exe.config` con un editor de texto.

   Se requieren privilegios de administrador para guardar los cambios en este archivo.

1. Busque la cadena &quot;ProxyCacheRoot&quot;. Verá que su valor está establecido en la ubicación de caché `%LocalAppData%\Adobe\AssetsCompanion\Cache`. Simplemente cambie este valor a cualquier ruta válida.

   >[!NOTE]
   >
   >AEM La aplicación crea automáticamente un subdirectorio *&lt;Codificado Extremo>*. Este comportamiento no se puede configurar.

>[!MORELIKETHIS]
>
* Vea una [introducción a la [!DNL Experience Manager] aplicación de escritorio](https://experienceleague.adobe.com/en/docs/experience-manager-learn/assets/creative-workflows/aem-desktop-app) (5 minutos y 43 segundos).
* [Usar [!DNL Experience Manager] aplicación de escritorio](use-app-v1.md).
* [Solución de problemas [!DNL Experience Manager] aplicación de escritorio](troubleshoot-app-v1.md).
