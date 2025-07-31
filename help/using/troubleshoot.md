---
title: Prácticas recomendadas y solución de problemas de la aplicación de escritorio  [!DNL Adobe Experience Manager] iOS
description: Siga las prácticas recomendadas y solucione problemas para resolver los problemas ocasionales relacionados con la instalación, actualización, configuración, etc.
exl-id: f388e4ac-907d-4093-ba6f-86ecdafeb015
source-git-commit: a8cb0aaab08f24c83a9b5640a96a5ae8895685d2
workflow-type: tm+mt
source-wordcount: '2275'
ht-degree: 0%

---

# Solucionar problemas de la aplicación de escritorio [!DNL Adobe Experience Manager] {#troubleshoot-v2}

La aplicación de escritorio [!DNL Adobe Experience Manager] se conecta al repositorio de administración de activos digitales (DAM) de una implementación [!DNL Experience Manager]. La aplicación obtiene información del repositorio y resultados de búsqueda en el equipo, descarga y carga archivos y carpetas, e incluye funciones para administrar conflictos con la interfaz de usuario de Assets.

Siga leyendo para solucionar los problemas de la aplicación, conocer las prácticas recomendadas y averiguar las limitaciones.

## Prácticas recomendadas {#best-practices-to-prevent-troubles}

Siga las siguientes prácticas recomendadas para evitar algunos problemas comunes y solucionar problemas.

* **Comprenda cómo funciona la aplicación de escritorio**: Antes de empezar a utilizarla, dedique unos minutos a conocer cómo funciona la aplicación. Obtenga información sobre la vinculación entre la interfaz web [!DNL Experience Manager] y el escritorio, la asignación de repositorios, el almacenamiento en caché de recursos, el almacenamiento local y la carga en segundo plano. Ver [cómo funciona](release-notes.md#how-app-works).

* **Evite los caracteres no admitidos en los nombres de carpeta**: no utilice espacios en blanco ni caracteres no válidos al crear o cargar carpetas. Ver una lista de caracteres en [Crear carpetas en [!DNL Adobe Experience Manager Assets]](https://experienceleague.adobe.com/es/docs/experience-manager-65/content/assets/managing/manage-assets#creating-folders). Los caracteres no admitidos en el nombre de la carpeta pueden afectar algunos casos de uso de [!DNL Experience Manager].

* **Prácticas recomendadas para evitar conflictos**: Para evitar posibles conflictos al colaborar en varios recursos, ve a [evitar conflictos de edición](assets-management-tasks.md#adv-workflow-collaborate-avoid-conflicts).

* **Usar la carga de carpetas para carpetas jerárquicas grandes**: en lugar de usar la interfaz web de Assets u otros métodos, usa la aplicación de escritorio [!DNL Experience Manager] para cargar carpetas grandes. La aplicación carga los recursos en segundo plano mediante el registro y la supervisión. Consulte [cargar recursos en lotes](using-desktop-app.md#bulk-upload-assets).

* **Usar la última versión**: usar la última versión de la aplicación. Compruebe siempre la compatibilidad antes de instalar una nueva versión de la aplicación o antes de actualizar a una versión más reciente de [!DNL Experience Manager]. Ver [notas de la versión](release-notes.md).

* **Use la misma letra de unidad**: use la misma letra de unidad en toda la organización para asignar al DAM [!DNL Experience Manager]. Para ver los recursos colocados por otros usuarios, las rutas deben ser las mismas. El uso de la misma letra de unidad garantiza una ruta constante a los recursos DAM. Los recursos permanecen colocados y no se eliminan aunque distintos usuarios utilicen letras de unidad distintas.

* **Cuidado con la red**: El rendimiento de la red es crítico para el rendimiento de la aplicación de escritorio [!DNL Experience Manager]. Si se enfrenta a una respuesta lenta a las transferencias de archivos o a las operaciones masivas, desactive las funciones o aplicaciones que puedan causar mucho tráfico de red.

* **Casos de uso no admitidos para la aplicación de escritorio**: evite utilizar la aplicación para la migración de recursos, ya que requiere planificación y herramientas adicionales. Tampoco es adecuado para operaciones DAM de gran capacidad, como mover carpetas grandes, cargas grandes o búsquedas avanzadas de metadatos. Además, no lo utilice como cliente de sincronización, ya que sus principios de diseño y patrones de uso difieren de los clientes de sincronización como Microsoft OneDrive o Adobe Creative Cloud Desktop Sync.

* **Tiempo de espera agotado**: actualmente, la aplicación de escritorio no tiene un valor de tiempo de espera configurable que desconecte la conexión entre el servidor [!DNL Experience Manager] y la aplicación de escritorio después de un intervalo de tiempo fijo. Al cargar recursos de gran tamaño, si la conexión supera el tiempo de espera después de un tiempo, la aplicación vuelve a intentar cargar el recurso varias veces aumentando el tiempo de espera de carga. No se recomienda ninguna forma de cambiar la configuración de tiempo de espera predeterminada.

## Cómo solucionar problemas {#troubleshooting-prep}

Para solucionar problemas de la aplicación de escritorio, tenga en cuenta la siguiente información. Además, le prepara para transmitir mejor los problemas al Servicio de atención al cliente de Adobe si elige buscar asistencia.

### Ubicación de los archivos de registro {#check-log-files-v2}

La aplicación de escritorio [!DNL Experience Manager] almacena sus archivos de registro en las siguientes ubicaciones, según el sistema operativo:

En Windows: `%LocalAppData%\Adobe\AssetsCompanion\Logs`

En Mac: `~/Library/Logs/Adobe\ Experience\ Manager\ Desktop`

Al cargar muchos recursos, si algunos archivos no se pueden cargar, consulte el archivo `backend.log` para identificar las cargas fallidas.

>[!NOTE]
>
>Cuando trabaje con Asistencia al cliente de Adobe en una solicitud de asistencia o un ticket, se le puede pedir que comparta los archivos de registro para ayudar al equipo de Asistencia al cliente a comprender el problema. Archiva toda la carpeta `Logs` y compártela con el contacto de Atención al cliente.

### Cambiar el nivel de detalles en los archivos de registro {#level-of-details-in-log}

Para cambiar el nivel de detalles en los archivos de registro:

1. Asegúrese de que la aplicación no se esté ejecutando.

1. En el sistema Windows:

   1. Abra una ventana de comandos.

   1. Inicie la aplicación de escritorio [!DNL Adobe Experience Manager] ejecutando el comando:

   ```shell
   set AEM_DESKTOP_LOG_LEVEL=DEBUG&"C:\Program Files\Adobe\Adobe Experience Manager Desktop.exe
   ```

   En el sistema Mac:

   1. Abra una ventana de terminal.

   1. Inicie la aplicación de escritorio [!DNL Adobe Experience Manager] ejecutando el comando:

   ```shell
   AEM_DESKTOP_LOG_LEVEL=DEBUG open /Applications/Adobe\ Experience\ Manager\ Desktop.app
   ```

Los niveles de registro válidos son DEBUG, INFO, WARN o ERROR. El nivel de detalle de los registros es mayor en DEPURACIÓN y menor en ERROR.

### Habilitar modo de depuración {#enable-debug-mode}

Para solucionar problemas, puede habilitar el modo de depuración y obtener más información en los registros.

>[!NOTE]
>
>Los niveles de registro válidos son DEBUG, INFO, WARN o ERROR. El nivel de detalle de los registros es mayor en DEPURACIÓN y menor en ERROR.

Para usar la aplicación en modo de depuración en Mac:

1. Abra una ventana de terminal o un símbolo del sistema.

1. Inicie la aplicación de escritorio [!DNL Experience Manager] ejecutando el siguiente comando:

   `AEM_DESKTOP_LOG_LEVEL=DEBUG open /Applications/Adobe\ Experience\ Manager\ Desktop.app`.

Para habilitar el modo de depuración en Windows:

1. Abra una ventana de comandos.

1. Inicie la aplicación de escritorio [!DNL Experience Manager] ejecutando el siguiente comando:

`AEM_DESKTOP_LOG_LEVEL=DEBUG&"C:\Program Files\Adobe\Adobe Experience Manager Desktop.exe`.

### Conocer la versión de la aplicación de escritorio [!DNL Adobe Experience Manager] {#know-app-version-v2}

Para ver el número de versión:

1. Inicie la aplicación.

1. Haga clic en los puntos suspensivos de la esquina superior derecha, pase el ratón sobre [!UICONTROL Help] y, a continuación, haga clic en [!UICONTROL About].

   El número de versión aparece en esta pantalla.

### Borrar caché {#clear-cache-v2}

Siga estos pasos:

1. Inicie la aplicación y conecte a una instancia de [!DNL Experience Manager].

1. Abra las preferencias de la aplicación haciendo clic en los puntos suspensivos de la esquina superior derecha y seleccionando [!UICONTROL Preferences].

1. Busque la entrada que muestra [!UICONTROL Current Cache Size]. Haga clic en el icono de papelera situado junto a este elemento.

Para borrar la caché manualmente, haga lo siguiente:

>[!CAUTION]
>
>Estos pasos son una operación potencialmente destructiva. Si hay cambios en el archivo local que no se han cargado en [!DNL Adobe Experience Manager], se perderán dichos cambios.

La caché se borra eliminando el directorio de caché de la aplicación, que se encuentra en las preferencias de la aplicación.

1. Inicie la aplicación.

1. Abra las preferencias de la aplicación seleccionando los puntos suspensivos en la esquina superior derecha y [!UICONTROL Preferences].

1. Observe el valor [!UICONTROL Cache Directory].

   En este directorio, hay subdirectorios con nombre después de los extremos codificados [!DNL Adobe Experience Manager]. Los nombres son una versión codificada de la dirección URL [!DNL Adobe Experience Manager] de destino. Por ejemplo, si la aplicación tiene como destino `localhost:4502`, el nombre del directorio es `localhost_4502`.

Para borrar la caché, elimine el directorio de extremo codificado [!DNL Adobe Experience Manager] deseado. Como alternativa, al eliminar todo el directorio especificado en las preferencias, se borra la caché de todas las instancias que haya utilizado la aplicación.

Borrar la caché de la aplicación de escritorio [!DNL Adobe Experience Manager] es una tarea preliminar de solución de problemas que puede resolver varios problemas. Borre la caché de las preferencias de la aplicación. Ver [establecer preferencias](install-upgrade.md#set-preferences). La ubicación predeterminada de la carpeta de caché es:

## No se pueden ver los recursos colocados {#placed-assets-missing}

Si no puede ver los recursos que usted u otros profesionales creativos han colocado en los archivos de soporte (por ejemplo, archivos INDD), compruebe lo siguiente:

* Conexión al servidor. La conectividad de red débil puede detener las descargas de recursos.

* Tamaño de archivo. Los recursos grandes tardan más en descargarse y mostrarse.

* Impulse la coherencia de letras. Si usted u otro colaborador colocaron los recursos al asignar el DAM [!DNL Experience Manager] a una letra de unidad diferente, los recursos colocados no se mostrarán.

* Permisos. Para comprobar si tiene permisos para recuperar los recursos colocados, póngase en contacto con el administrador de [!DNL Experience Manager].

### Las ediciones hechas en archivos en la interfaz de usuario de la aplicación de escritorio no se reflejan en [!DNL Adobe Experience Manager] inmediatamente {#changes-on-da-not-visible-on-aem}

[!DNL Adobe Experience Manager] aplicación de escritorio deja en manos del usuario decidir cuándo se completan todas las ediciones de un archivo. Según el tamaño y la complejidad de un archivo, se tarda una cantidad de tiempo considerable en volver a transferir la nueva versión de un archivo a [!DNL Adobe Experience Manager]. La aplicación está diseñada para minimizar el número de transferencias de archivos, en lugar de cargar automáticamente archivos en función de la finalización prevista de las ediciones. Se recomienda que el usuario inicie la transferencia del archivo de nuevo a [!DNL Adobe Experience Manager] eligiendo cargar los cambios de un archivo.

### Problemas al actualizar en macOS {#issues-when-upgrading-on-macos}

En ocasiones, pueden producirse problemas al actualizar la aplicación de escritorio [!DNL Experience Manager] en macOS. Las carpetas heredadas del sistema para la aplicación de escritorio [!DNL Experience Manager] causan estos problemas. Las carpetas impiden que las nuevas versiones de la aplicación de escritorio [!DNL Experience Manager] se carguen correctamente. Para solucionar este problema, se pueden eliminar manualmente las siguientes carpetas y archivos.

Antes de ejecutar los siguientes pasos, arrastre la aplicación `Adobe Experience Manager Desktop` desde la carpeta Aplicaciones macOS a la papelera. A continuación, abra el terminal, ejecute el siguiente comando y proporcione la contraseña cuando se le solicite.

```shell
sudo rm -rf ~/Library/Application\ Support/com.adobe.aem.desktop
sudo rm -rf ~/Library/Preferences/com.adobe.aem.desktop.plist
sudo rm -rf ~/Library/Logs/Adobe\ Experience\ Manager\ Desktop

sudo find /var/folders -type d -name "com.adobe.aem.desktop" | xargs rm -rf
sudo find /var/folders -type d -name "com.adobe.aem.desktop.finderintegration-plugin" | xargs rm -rf
```

## No se pueden cargar archivos {#upload-fails}

Si utiliza la aplicación de escritorio con [!DNL Experience Manager] 6.5.1 o posterior, actualice S3 o el conector de Azure a la versión 1.10.4 o posterior. Resuelve el problema de error de carga de archivo relacionado con [OAK-8599](https://issues.apache.org/jira/browse/OAK-8599). Ver [instrucciones de instalación](install-upgrade.md#install-v2).

## [!DNL Experience Manager] problemas de conexión de aplicación de escritorio {#connection-issues}

Si experimenta problemas generales de conectividad, hay algunas formas de obtener más información sobre lo que está haciendo la aplicación de escritorio de [!DNL Experience Manager].

**Compruebe el registro de solicitudes**

La aplicación de escritorio [!DNL Experience Manager] registra todas las solicitudes que envía, junto con el código de respuesta de cada solicitud, en un archivo de registro dedicado.

1. Abra `request.log` en el directorio de registro de la aplicación para ver estas solicitudes.

1. Cada línea del registro representa una solicitud o una respuesta. Las solicitudes tienen un carácter `>` seguido de la dirección URL solicitada. Las respuestas tienen un carácter `<` seguido del código de respuesta y la dirección URL solicitada. Las solicitudes y las respuestas pueden coincidir utilizando el GUID de cada línea.

**Compruebe las solicitudes cargadas por el explorador incrustado de la aplicación**

La mayoría de las solicitudes de la aplicación se encuentran en el registro de solicitudes. Sin embargo, si no hay información útil allí, puede resultar útil examinar las solicitudes enviadas por el explorador incrustado de la aplicación.
Consulte la [sección SAML](#da-connection-issue-with-saml-aem) para obtener instrucciones sobre cómo ver esas solicitudes.

### La autenticación de inicio de sesión SAML no funciona {#da-connection-issue-with-saml-aem}

Es posible que la aplicación de escritorio [!DNL Experience Manager] no se conecte a su implementación [!DNL Adobe Experience Manager] con SSO habilitado (SAML). El diseño de la aplicación intenta adaptarse a las variaciones y complejidades de las conexiones y procesos de SSO. Sin embargo, una configuración puede requerir una solución de problemas adicional.

A veces, el proceso de SAML no redirige de nuevo a la ruta solicitada originalmente. O bien, el redireccionamiento final es a un host distinto de lo configurado en la aplicación de escritorio [!DNL Adobe Experience Manager]. Para comprobar que este problema no es el caso, haga lo siguiente:

1. Abra un explorador Web. URL de acceso `https://[aem_server]:[port]/content/dam.json`.

1. Inicie sesión en la implementación de [!DNL Adobe Experience Manager].

1. Cuando finalice el inicio de sesión, observe la dirección actual del explorador en la barra de direcciones. Debe coincidir exactamente con la dirección URL introducida inicialmente.

1. Compruebe también que todo lo anterior a `/content/dam.json` coincide con el valor de destino [!DNL Adobe Experience Manager] configurado en la configuración de la aplicación de escritorio [!DNL Adobe Experience Manager].

**El proceso de inicio de sesión de SAML funciona correctamente de acuerdo con los pasos anteriores, pero los usuarios aún no pueden iniciar sesión**

La ventana de la aplicación de escritorio [!DNL Adobe Experience Manager] que muestra el proceso de inicio de sesión es simplemente un explorador web que muestra la interfaz de usuario web de la instancia de destino [!DNL Adobe Experience Manager]:

* La versión de Mac usa [WebView](https://developer.apple.com/documentation/webkit/webview).

* La versión de Windows usa [CefSharp](https://cefsharp.github.io/) basado en Chromium.

Asegúrese de que el proceso de SAML sea compatible con esos exploradores.

Para solucionar más problemas, es posible ver las direcciones URL exactas que el explorador está intentando cargar. Para ver esta información:

1. Siga las instrucciones para iniciar la aplicación en [modo de depuración](#enable-debug-mode).

1. Reproduzca el intento de inicio de sesión.

1. Vaya al [directorio de registro](#check-log-files-v2) de la aplicación.

1. Para Windows:

   1. Abra &quot;aemcompanionlog.txt&quot;.

   1. Busque mensajes que comiencen por &quot;La dirección del explorador de inicio de sesión cambió a&quot;. Estas entradas también contienen la dirección URL que cargó la aplicación.

   Para Mac:

   1. En `com.adobe.aem.desktop-nnnnnnnn-nnnnnn.log`, los números que estén en el nombre de archivo más reciente reemplazan a **n**.

   1. Busque mensajes que comiencen por &quot;marco cargado&quot;. Estas entradas también contienen la dirección URL que cargó la aplicación.

Mirar la secuencia de URL que se está cargando puede ayudar a solucionar el problema al final de SAML para determinar qué está mal.

### Problema de configuración SSL {#ssl-config-v2}

Las bibliotecas que utiliza la aplicación de escritorio [!DNL Experience Manager] para la comunicación HTTP utilizan una estricta aplicación SSL. A veces, es posible que una conexión se realice correctamente con un explorador, pero se produce un error al usar la aplicación de escritorio [!DNL Experience Manager]. Para configurar SSL correctamente, instale el certificado intermedio que falta en Apache. Ver [Cómo instalar un certificado de CA intermedia en Apache](https://access.redhat.com/solutions/43575).

Las bibliotecas que usa la aplicación de escritorio [!DNL Experience Manager] para la comunicación HTTP usan la estricta aplicación SSL. Por lo tanto, puede haber casos en los que las conexiones SSL que se realizan correctamente a través de un explorador fallen con la aplicación de escritorio [!DNL Adobe Experience Manager]. Este resultado es bueno porque fomenta la configuración correcta de SSL y aumenta la seguridad, pero puede ser frustrante cuando la aplicación no se puede conectar.

El método recomendado en este caso es utilizar una herramienta para analizar el certificado SSL de un servidor e identificar problemas para que se puedan corregir. Hay sitios Web que inspeccionan el certificado de un servidor proporcionando su dirección URL.

Como medida temporal, es posible deshabilitar la aplicación SSL estricta en la aplicación de escritorio [!DNL Adobe Experience Manager]. Este enfoque no es una solución recomendada a largo plazo, ya que reduce la seguridad al ocultar la causa raíz de SSL configurado incorrectamente. Para deshabilitar la aplicación estricta:

1. Utilice el editor que desee para editar el archivo de configuración de JavaScript de la aplicación, que se encuentra (de forma predeterminada) en las siguientes ubicaciones (según el sistema operativo):

   En Mac: `/Applications/Adobe Experience Manager Desktop.app/Contents/Resources/javascript/lib-smb/config.json`

   En Windows: `C:\Program Files (x86)\Adobe\Adobe Experience Manager Desktop\javascript\config.json`

1. Busque la siguiente sección en el archivo:

   ```shell
   ...
   "assetRepository": {
       "options": {
   ...
   ```

1. Modifique la sección agregando `"strictSSL": false` de la siguiente manera:

   ```shell
   ...
   "assetRepository": {
       "options": {
           "strictSSL": false,
   ...
   ```

1. Guarde el archivo y reinicie la aplicación de escritorio [!DNL Adobe Experience Manager].

### Problemas de inicio de sesión al cambiar a un servidor diferente {#cannot-login-cookies-issue}

Después de usar un servidor [!DNL Experience Manager], cuando intente cambiar la conexión a un servidor diferente, puede encontrar problemas de inicio de sesión. Se debe a que las cookies antiguas interfieren con la nueva autenticación. Ayuda una opción del menú principal de [!UICONTROL Clear Cookies]. Cierre la sesión actual en la aplicación y seleccione [!UICONTROL Clear Cookies] antes de continuar con la conexión.

![Borrar cookies al cambiar de servidor](assets/main_menu_logout_da2.png)

## La aplicación no responde {#unresponsive}

En raras ocasiones, la aplicación puede dejar de responder, mostrar solo una pantalla en blanco o mostrar un error en la parte inferior de la interfaz sin ninguna opción en la interfaz. Pruebe lo siguiente en el orden:

* Haga clic con el botón derecho en la interfaz de la aplicación y seleccione **[!UICONTROL Refresh]**.
* Salga de la aplicación y ábrala de nuevo.

En ambos métodos, la aplicación se inicia en la carpeta raíz DAM.

## Ocultar recursos caducados {#hide-expired-assets}

Al examinar los recursos desde la interfaz de usuario de [!DNL Experience Manager], no se muestran los recursos caducados. Los administradores pueden configurar opciones para evitar la visualización, la búsqueda y la captura de recursos caducados al navegar desde la aplicación de escritorio y Asset Link. Al hacerlo, se garantiza que los recursos caducados no sean accesibles durante estas operaciones. La configuración funciona para todos los usuarios, independientemente del privilegio de administrador.

* [Configuración en Experience Manager 6.5 para ocultar recursos caducados](https://experienceleague.adobe.com/es/docs/experience-manager-65/content/assets/managing/manage-assets#hide-expired-assets-via-acp-api).
* [Configuración en Experience Manager as a Cloud Service para ocultar recursos caducados](https://experienceleague.adobe.com/es/docs/experience-manager-cloud-service/content/assets/manage/manage-digital-assets#hide-expired-assets-via-acp-api).

<!--
### Need additional help with [!DNL Experience Manager] desktop app {#additional-help}

Create Jira ticket with the following information:

* Use `DAM - Companion App` as the [!UICONTROL Component].

* Detailed steps to reproduce the issue in [!UICONTROL Description].

* DEBUG level logs that were captured while reproducing the issue.

* Target Experience Manager version.

* Operating system version.

* [!DNL Adobe Experience Manager] desktop app version. To know your app version, see [finding the desktop app version](#know-app-version-v2).
-->

>[!MORELIKETHIS]
>
>* [Problemas conocidos](release-notes.md#known-issues-v2)
>* [Evitar conflictos de edición](assets-management-tasks.md#adv-workflow-collaborate-avoid-conflicts)
