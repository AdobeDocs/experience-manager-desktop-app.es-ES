---
title: Solucionar problemas de la versión 1.10 de la aplicación de escritorio.
description: Solucione  [!DNL Adobe Experience Manager] versión 1.10 de la aplicación de escritorio para resolver los problemas ocasionales relacionados con la instalación, actualización y configuración.
exl-id: 1e1409c2-bf5e-4e2d-a5aa-3dd74166862c
source-git-commit: 19e4b92016670de20474b251cda9f2f5274dbc26
workflow-type: tm+mt
source-wordcount: '3358'
ht-degree: 0%

---

# Solucionar problemas de la aplicación de escritorio [!DNL Adobe Experience Manager] v1.x {#troubleshoot-aem-desktop-app}

Solucione los problemas de la aplicación de escritorio de AEM para resolver los problemas ocasionales relacionados con la instalación, actualización, configuración, etc.

La aplicación de escritorio [!DNL Adobe Experience Manager] incluye utilidades que le ayudan a asignar el repositorio de AEM Assets como un recurso compartido de red en el escritorio (recurso compartido SMB en macOS). El recurso compartido de red es una tecnología de sistema operativo que permite que los orígenes remotos se traten como si formaran parte del sistema de archivos local de un equipo. Para la aplicación de escritorio, el origen de archivos remoto es la estructura del repositorio de administración de recursos digitales (DAM) de una instancia remota de AEM. En el diagrama siguiente se describe la topología de la aplicación de escritorio:

![diagrama de aplicación de escritorio](assets/aem-desktopapp-architecture.png)

Con esta arquitectura, la aplicación de escritorio intercepta las llamadas del sistema de archivos (abrir, cerrar, leer, escribir, etc.) al recurso compartido de red montado y las traduce en llamadas HTTP de AEM nativas al servidor de AEM. Los archivos se almacenan localmente en caché. Para obtener más información, consulte [Usar la aplicación de escritorio de AEM v1.x](use-app-v1.md).

## información general sobre el componente aplicación de escritorio AEM {#desktop-app-component-overview}

La aplicación de escritorio incluye los siguientes componentes:

* **La aplicación de escritorio**: La aplicación monta o desmonta DAM como sistema de archivos remoto. Traduce llamadas al sistema de archivos entre el recurso compartido de red montado localmente y la instancia remota de AEM a la que se conecta.
* **Cliente WebDAV/SMB del sistema operativo**: administra la comunicación entre el Explorador/Finder de Windows y la aplicación de escritorio. Si se recupera, crea, modifica, elimina, mueve o copia un archivo, el cliente WebDAV/SMB del sistema operativo (SO) comunica esta operación a la aplicación de escritorio. Después de recibir la comunicación, la aplicación de escritorio la traduce a llamadas API remotas nativas de AEM. Por ejemplo, si un usuario crea un archivo en el directorio montado, el cliente WebDAV/SMB inicia una solicitud, que la aplicación de escritorio traduce en una solicitud HTTP que crea el archivo en DAM. El cliente WebDAV/SMB es un componente integrado del sistema operativo. No está afiliado a la aplicación de escritorio, AEM o Adobe de ninguna manera.
* **Instancia de Adobe Experience Manager**: proporciona acceso a los recursos almacenados en el repositorio DAM de AEM Assets. Además, realiza las acciones solicitadas por la aplicación de escritorio en nombre de las aplicaciones de escritorio locales que interactúan con el recurso compartido de red montado. La instancia de AEM de destino debe ejecutar AEM versión 6.1 o superior. Las instancias de AEM que ejecutan versiones anteriores de AEM pueden requerir paquetes de funciones y correcciones rápidas adicionales instalados para funcionar por completo.

## Casos de uso previstos para la aplicación de escritorio de AEM {#intended-use-cases-for-aem-desktop-app}

La aplicación de escritorio de AEM utiliza la tecnología de uso compartido de red para asignar un repositorio remoto de AEM a un escritorio local. Sin embargo, no pretende reemplazar a un recurso compartido de red que contiene recursos, donde los usuarios realizan operaciones de administración de recursos digitales directamente desde su equipo de escritorio local. Estos incluyen mover o copiar varios archivos, o arrastrar estructuras de carpetas grandes al recurso compartido de red de los AEM Assets directamente en Finder/Explorer.

La aplicación de escritorio de AEM proporciona una forma cómoda de acceder (abrir) y editar (guardar) los recursos DAM entre la IU táctil de los AEM Assets y el escritorio local. Vincula los recursos del servidor de AEM Assets con los flujos de trabajo basados en el escritorio.

El siguiente ejemplo de caso de uso ilustra cómo se debe utilizar AEM Desktop:

* Un usuario inicia sesión en AEM y utiliza la interfaz de usuario web para localizar un recurso.
* Con las funciones de acción del escritorio de la interfaz de usuario web de AEM, el usuario abre, muestra o edita el recurso en el escritorio según sea necesario.
* AEM Desktop abre el recurso en el editor predeterminado para el tipo de archivo del recurso.
* El usuario realiza los cambios deseados en el recurso.
* Una vez modificado un archivo, el usuario puede ver el estado de sincronización del archivo mediante la ventana de estado de sincronización en segundo plano de AEM Desktop.
* Con el menú contextual de AEM Desktop, el usuario protege/desactiva el recurso o vuelve a la interfaz de usuario de DAM.
* Después de completar los cambios en el archivo, el usuario vuelve a la IU web de AEM

Este escenario no es el único caso de uso. Sin embargo, ilustra cómo AEM Desktop es un mecanismo cómodo para acceder y editar recursos localmente. Se le recomienda utilizar la interfaz de usuario web de DAM en la medida de lo posible porque ofrece una mejor experiencia. Proporciona a Adobe más flexibilidad para satisfacer los requisitos de los clientes.

## Limitaciones {#limitations}

El recurso compartido de red WebDAV/SMB1 proporciona la comodidad de trabajar con archivos en una ventana de Explorer/Finder. Sin embargo, Explorer/Finder y AEM se comunican a través de una conexión de red que tiene ciertas limitaciones. Por ejemplo, el tiempo empleado para copiar un archivo de 1 GB en el directorio WebDAV/SMB montado es aproximadamente el mismo que el tiempo necesario para cargar un archivo de 1 GB en un sitio web mediante un explorador web. De hecho, en el primer caso, la duración puede ser mayor debido a ineficiencias del protocolo WebDAV/SMB y de los clientes WebDAV/SMB del sistema operativo (especialmente macOS X).

Existen limitaciones a los tipos de tareas que se pueden realizar desde un directorio montado. En general, trabajar con archivos grandes, especialmente a través de una conexión de red de baja o baja latencia o baja anchura de banda, puede ser difícil, especialmente cuando se editan archivos grandes.

Adobe recomienda realizar algunas pruebas de casos de uso antes de confirmar con un cliente que ciertos tipos de archivos se pueden editar de forma eficaz in situ desde el directorio montado.

AEM Desktop no es adecuado para realizar una manipulación intensiva del sistema de archivos, incluyendo, entre otros:

* Mover o copiar archivos y directorios
* Adición de muchos recursos a AEM
* Buscar y abrir archivos a través del sistema de archivos, excepto para explorar carpetas
* Comprimir o descomprimir archivos de almacenamiento

Debido a limitaciones en el sistema operativo, Windows tiene una limitación de tamaño de archivo de 4.294.967.295 bytes (aproximadamente 4,29 GB). Se debe a una configuración del Registro que define el tamaño que puede tener un archivo en un recurso compartido de red. El valor de la configuración del Registro es un valor DWORD con un tamaño máximo igual al número al que se hace referencia.

La aplicación de escritorio [!DNL Experience Manager] no tiene un valor de tiempo de espera configurable que desconecte la conexión entre el servidor [!DNL Experience Manager] y la aplicación de escritorio después de un intervalo de tiempo fijo. Al cargar recursos de gran tamaño, si la conexión supera el tiempo de espera después de un tiempo, la aplicación vuelve a intentar cargar el recurso varias veces aumentando el tiempo de espera de carga. No se recomienda ninguna forma de cambiar la configuración de tiempo de espera predeterminada.

## Almacenamiento en caché y comunicación con AEM {#caching-and-communication-with-aem}

La aplicación de escritorio de AEM proporciona funciones internas de almacenamiento en caché y carga en segundo plano para mejorar la experiencia del usuario final. Al guardar un archivo grande, primero se guarda localmente para permitirle continuar trabajando. Después de un tiempo (actualmente 30 segundos), el archivo se envía al servidor de AEM en segundo plano.

A diferencia de Creative Cloud Desktop u otras soluciones de sincronización de archivos, como Microsoft One Drive, la aplicación de escritorio de AEM no es un cliente de sincronización de escritorio completo. El motivo es que proporciona acceso a todo el repositorio de AEM Assets, que puede ser extremadamente grande (cientos de gigabytes o terabytes) para una sincronización completa.

El almacenamiento en caché permite limitar la sobrecarga de red/almacenamiento a solo un subconjunto de recursos que son relevantes para el usuario.

>[!CAUTION]
>
>Adobe recomienda desactivar la generación de miniaturas para que la exploración sea más rápida. Si activa las vistas previas de iconos, la aplicación almacenará en caché los recursos digitales al navegar por la carpeta montada. La aplicación también descarga recursos que pueden no interesar al usuario. Como tal, agrega carga al servidor, consume el ancho de banda del usuario y utiliza más espacio en disco del usuario.

Así es como la aplicación de escritorio de AEM realiza el almacenamiento en caché:

* Cuando abre una carpeta en el Finder y muestra miniaturas o vistas previas de archivos, la aplicación de escritorio almacena en caché el binario del archivo. Del mismo modo, cuando se abre un archivo en una aplicación, la aplicación también almacena en caché el binario del archivo.
* Cuando se almacenan archivos mediante Finder u otras aplicaciones de escritorio, el archivo se almacena primero localmente (en caché) y se notifica al sistema operativo. A continuación, el archivo se pone en cola para su carga en el servidor en segundo plano y, finalmente, se carga en la red. Si hay un error de red, la aplicación de escritorio reintenta cargar todo el archivo durante un máximo de tres veces. Si el archivo no se carga después de tres reintentos, se marca como un archivo en conflicto y el estado se muestra en la ventana Estado de la cola de carga en segundo plano. la aplicación de escritorio ya no intenta actualizar el archivo. El usuario debe actualizar el archivo y volver a cargarlo una vez restaurada la conectividad

Cada operación no se almacena en caché localmente. Lo siguiente se transmite al servidor de AEM inmediatamente sin almacenamiento en caché local:

* Cualquier operación en las carpetas, por ejemplo crear, eliminar, etc
* La funcionalidad Carga de carpetas introducida en la versión 1.4 carga una jerarquía de carpetas local sin almacenar en caché los archivos localmente

## Operaciones individuales {#individual-operations}

Cuando solucione problemas de rendimiento suboptimizado para usuarios individuales, primero revise [las limitaciones de la aplicación](#limitations). Las secciones siguientes incluyen sugerencias para mejorar el rendimiento de los usuarios individuales.

## Recomendaciones de ancho de banda {#bandwidth-recommendations}

El ancho de banda disponible para un usuario individual desempeña un papel fundamental en el rendimiento del cliente WebDAV/SMB.

Adobe recomienda que la velocidad de carga de un usuario individual esté cerca de 10 Mbps. En las conexiones inalámbricas, el ancho de banda suele compartirse entre varios usuarios. Si varios usuarios realizan simultáneamente tareas que consumen ancho de banda de la red, el rendimiento puede degradarse aún más. Para evitar estos problemas, utilice una conexión con cable.

<!-- 
AG, 8/18: The Windows KB article is removed by MS now. Giving 404. Also, Win 7 support is gone and the desktop app is also not supported on Win 7. Hiding this content for now.

## Windows-specific configurations {#windows-specific-configurations}

If you use Experience Manager on Windows, you can configure Windows to enhance the performance of the WebDAV client. For more information, go to [https://support.microsoft.com/en-us/kb/2445570](https://support.microsoft.com/en-us/kb/2445570).

On Windows 7, modifying IE settings can improve the performance of WebDAV. For details, see how to [fix slow WebDAV performance in Windows 7](https://oddballupdate.com/2009/12/fix-slow-webdav-performance-in-windows-7/).
-->

## Operaciones simultáneas {#concurrent-operations}

Cuando interactúa con un archivo localmente, AEM Desktop comprueba si hay una versión más reciente del archivo disponible en AEM. Si hay una nueva versión disponible, la aplicación descarga una copia nueva del archivo en la caché local. Sin embargo, AEM Desktop no sobrescribe un archivo almacenado en caché local si se ha modificado. Esta función evita que su trabajo se sobrescriba de forma involuntaria.

Cuando se modifica el mismo archivo tanto localmente como en AEM, la versión modificada localmente sobrescribe la versión en AEM. En este caso, la versión anterior está disponible en la cronología del recurso. Puede verificar ambas versiones y resolver cualquier conflicto.

Si un archivo local no es coherente con la versión disponible en el servidor, el cuadro de diálogo de estado de carga en segundo plano le notificará el conflicto. Para resolver el problema, abra el archivo en conflicto y guárdelo. Guardar el archivo obliga a AEM Desktop a sincronizar los cambios locales más recientes con AEM. Puede ver las versiones anteriores del recurso en la cronología y resolver cualquier conflicto.

Tenga en cuenta factores adicionales cuando varios usuarios intenten trabajar en directorios montados independientes dirigidos a la misma instancia de AEM. En particular, los siguientes factores son importantes:

* La cantidad de ancho de banda disponible en la red de origen de los usuarios
* Configuración de red, como servidores de seguridad o proxies, de la red de origen
* Cantidad de ancho de banda disponible en la red de la instancia de AEM de destino
* Si hay un Dispatcher presente antes de la instancia de AEM de destino
* Carga actual en la instancia de AEM de destino

## Configuraciones adicionales de AEM {#additional-aem-configurations}

Si el rendimiento de WebDAV/SMB se degrada drásticamente cuando varios usuarios trabajan simultáneamente, puede configurar algunos elementos en AEM, lo que puede ayudar a mejorar el rendimiento.

## Actualizar flujos de trabajo transitorios de recursos {#update-asset-transient-workflows}

Puede mejorar el rendimiento de AEM si habilita flujos de trabajo transitorios para el flujo de trabajo de recursos de actualización de DAM. La activación de flujos de trabajo transitorios reduce la potencia de procesamiento necesaria para actualizar los recursos cuando se crean o modifican en AEM.

1. Vaya a `/miscadmin` en la instancia de Experience Manager (`https://[aem_server]:[port]/miscadmin`).
1. En el árbol de navegación, expanda **Herramientas** > **Flujo de trabajo** > **Modelos** > **Dam**.
1. Haga doble clic en **Recurso de actualización DAM**.
1. En el panel de herramientas flotante, cambie a la ficha **Página** y, a continuación, haga clic en **Propiedades de página**.
1. Seleccione la casilla **Flujo de trabajo transitorio** y haga clic en **Aceptar**.

### Ajustar cola de flujo de trabajo transitorio de Granite {#adjust-granite-transient-workflow-queue}

Otro método para mejorar el rendimiento de AEM es configurar el valor del máximo de trabajos paralelos para el trabajo de cola de flujo de trabajo transitorio de Granite. El valor recomendado es aproximadamente la mitad del número de CPU disponibles con el servidor. Para ajustar el valor, realice estos pasos:

1. Vaya a `/system/console/configMgr` en la instancia de AEM que desea configurar (por ejemplo, `https://[aem_server]:[port]/system/console/configMgr`).
1. Busque `QueueConfiguration` y haga clic para abrir cada trabajo hasta que encuentre el trabajo **Cola de flujo de trabajo transitorio de Granite** y haga clic en **Editar**.
1. Cambie el valor `Maximum Parallel Jobs` y haga clic en **Guardar**.

## Configuración de AWS {#aws-configuration}

Debido a las limitaciones de ancho de banda de la red, el rendimiento de WebDAV/SMB puede degradarse cuando varios usuarios trabajan simultáneamente. Adobe recomienda aumentar el tamaño de la instancia de AWS para una instancia de AEM de destino que se ejecute en AWS para mejorar el rendimiento de WebDAV/SMB.

Esta medida aumenta específicamente la cantidad de ancho de banda de red disponible para el servidor. A continuación se muestran algunos detalles:

* La cantidad de ancho de banda de red dedicado a una instancia de AWS aumenta a medida que aumenta el tamaño de la instancia. Para obtener información sobre cuánto ancho de banda hay disponible para cada tamaño de instancia, consulte la [documentación de AWS](https://aws.amazon.com/ec2/instance-types/).
* Al solucionar problemas de un cliente grande, Adobe configuró el tamaño de su instancia de AEM en c4.8xlarge, principalmente para los 4000 Mbps de ancho de banda dedicado que proporciona.
* Si hay una Dispatcher antes de la instancia de AEM, asegúrese de que tenga el tamaño adecuado. Si la instancia de AEM proporciona 4000 Mbps pero la Dispatcher solo proporciona 500 Mbps, el ancho de banda efectivo es solo 500 Mbps. Esto se debe a que Dispatcher crea un cuello de botella en la red.

## Limitaciones de archivos desprotegidos {#checked-out-file-limitations}

Existen algunas limitaciones conocidas en la forma en que puede interactuar con archivos desprotegidos mediante el Explorador/Finder. Si un archivo está desprotegido, debe ser de sólo lectura para cualquier usuario, excepto para el usuario que lo tiene desprotegido. La implementación del protocolo WebDAV/SMB1 en AEM aplica esta regla. Sin embargo, los clientes de SO WebDAV/SMB no suelen interactuar correctamente con los archivos desprotegidos. A continuación se describen algunas rarezas.

### General {#general}

Al escribir en un archivo desprotegido, el bloqueo solo se aplica dentro de la implementación WebDAV de AEM. En consecuencia, los clientes que utilizan WebDAV, como la aplicación de escritorio, solo aplican el bloqueo. El bloqueo no se aplica a través de la interfaz web de AEM. La interfaz de AEM solo muestra un icono de candado en la vista de tarjeta de los recursos desprotegidos. El icono es cosmético y no afecta al comportamiento de AEM.

En general, los clientes de WebDAV no siempre se comportan como se espera. Puede haber problemas adicionales. Sin embargo, actualizar o comprobar el recurso en AEM es una forma correcta de comprobar que no se está modificando. Este comportamiento es típico de los clientes WebDAV del sistema operativo, que no están bajo el control de Adobe.

### Windows {#windows}

La eliminación de un archivo parece ser correcta porque el archivo desaparece del explorador de archivos de Windows. Sin embargo, si se actualiza el directorio y se registran los AEM Assets, se muestra que el archivo sigue presente. Además, la edición de archivos parece ser correcta (no se muestran cuadros de diálogo de advertencia ni mensajes de error). Sin embargo, si se vuelve a abrir el archivo o se registran los AEM Assets, el archivo no cambia.

#### MACOS X {#mac-os-x}

Reemplazar un archivo no muestra una advertencia ni un error, pero al comprobar el recurso en AEM se muestra que permanece sin cambios. Actualice o compruebe el recurso en AEM para comprobar que no se está modificando.

## Resolución de problemas de iconos de aplicaciones de escritorio (macOS X) {#troubleshooting-desktop-app-icon-issues-mac-os-x}

Después de instalar la aplicación de escritorio, el icono de menú de la aplicación de escritorio aparece en la barra de menús. Si el icono no aparece, realice estos pasos para resolver el problema:

1. Abra la ventana de terminal del sistema operativo.
1. Escriba el siguiente comando en el símbolo del sistema y, a continuación, presione Entrar:

   ```shell
    cd ../Library/Caches.
   ```

1. Escriba el siguiente comando y presione Entrar:

   ```shell
   rm -r com.adobe.aem.assetscompanion
   ```

1. Escriba el siguiente comando y presione Entrar:

   ```shell
   cd ~/Library/Preferences
   ```

1. Escriba el siguiente comando y presione Entrar:

   ```shell
   rm com.adobe.aem.assetscompanion.plist
   ```

1. Escriba el siguiente comando y presione Entrar:

   ```shell
   rm ~/Library/Group\ Containers/group.com.adobe.aem.desktop/*
   ```

1. Reinicie el sistema.

AEM Desktop intenta sincronizar un archivo determinado tres veces. Si el archivo no se sincroniza después del tercer intento, AEM Desktop considera que el archivo está en conflicto y le notifica mediante la ventana de estado de carga en segundo plano. Un estado de conflicto indica que los cambios más recientes aún están disponibles localmente, pero no se sincronizan con AEM. La aplicación de escritorio de AEM ya no intenta sincronizarse.

La forma más sencilla de solucionar esta situación es abrir el archivo en conflicto y guardarlo de nuevo. Fuerza a AEM Desktop a intentar la sincronización en otras tres ocasiones. Si el archivo sigue sin sincronizarse, consulte las secciones siguientes para obtener más ayuda.

## Borrando caché de AEM Desktop {#clearing-aem-desktop-cache}

Borrar la caché de AEM Desktop es una tarea preliminar de resolución de problemas que puede resolver varios problemas de AEM Desktop.

Puede borrar la caché eliminando el directorio de caché de la aplicación en las ubicaciones siguientes.
En Windows, `%LocalAppData%\Adobe\AssetsCompanion\Cache\`

En Mac, `~/Library/Group/Containers/group.com.adobe.aem.desktop/cache/`

Sin embargo, la ubicación puede cambiar según el punto de conexión de AEM configurado en AEM Desktop. El valor es una versión codificada de la dirección URL de destino. Por ejemplo, si la aplicación tiene como destino `http://localhost:4502`, el nombre del directorio es `http%3A%2F%2Flocalhost%3A4502%2F`.

Para borrar la caché, elimine el directorio &lt;Encoded AEM Endpoint>.

>[!NOTE]
>
>Si borra la caché de AEM Desktop, los cambios del archivo local se perderán si no se sincronizan con AEM.

>[!NOTE]
>
>A partir de la versión 1.5 de la aplicación de escritorio de AEM, hay una opción en la interfaz de usuario para borrar la caché.

## Búsqueda de la versión de AEM Desktop {#finding-the-aem-desktop-version}

El procedimiento para comprobar la versión de AEM Desktop es el mismo para Windows y para macOS.

Haga clic en el icono de AEM Desktop y, a continuación, seleccione **Acerca de**. El número de versión se muestra en la pantalla.

## Actualización de la aplicación de escritorio de AEM en macOS {#upgrading-aem-desktop-app-on-macos}

En ocasiones, pueden producirse problemas al actualizar la aplicación de escritorio de AEM en macOS. Las carpetas de sistema heredadas para la aplicación de escritorio de AEM causan estos problemas. Evita que las nuevas versiones de AEM Desktop se carguen correctamente. Para solucionar este problema, se pueden eliminar manualmente las siguientes carpetas y archivos.

Antes de ejecutar los pasos siguientes, arrastre la aplicación &quot;Adobe Experience Manager Desktop&quot; de la carpeta Aplicaciones macOS a la papelera. A continuación, abra el terminal y ejecute el siguiente comando, proporcionando la contraseña cuando se le solicite.

```shell
sudo rm -rf ~/Library/Application\ Support/com.adobe.aem.desktop
sudo rm -rf ~/Library/Preferences/com.adobe.aem.desktop.plist
sudo rm -rf ~/Library/Logs/Adobe\ Experience\ Manager\ Desktop

sudo find /var/folders -type d -name "com.adobe.aem.desktop" | xargs rm -rf
sudo find /var/folders -type d -name "com.adobe.aem.desktop.finderintegration-plugin" | xargs rm -rf
```

## Guardar un archivo desprotegido por otros usuarios {#saving-a-file-checked-out-by-others}

Las limitaciones técnicas del sistema operativo impiden que los usuarios tengan una experiencia coherente al intentar sobrescribir un archivo que otros usuarios han desprotegido. La experiencia varía en función de la aplicación utilizada para editar el archivo desprotegido. A veces, la aplicación muestra un mensaje de error que indica un error de escritura en disco o un error genérico o aparentemente no relacionado. En otras ocasiones, no se muestra ningún mensaje de error y la operación parece ser correcta.

En este caso, cerrar y volver a abrir el archivo puede revelar que el contenido no ha cambiado. Sin embargo, algunas aplicaciones pueden almacenar una copia de seguridad del archivo para que se puedan aplicar los cambios.

Independientemente del comportamiento, el archivo permanece sin cambios cuando se protege. Aunque se muestre una versión diferente del archivo, los cambios no se sincronizan con AEM.

## Solución de problemas relacionados con el movimiento de archivos {#troubleshooting-problems-around-moving-files}

La API de servidor requiere que se pasen encabezados adicionales, X-Destination, X-Depth y X-Overwrite, para que funcionen las operaciones de mover y copiar. Dispatcher no pasa estos encabezados de forma predeterminada, lo que provoca que estas operaciones fallen. Para obtener más información, consulte [Conectarse a AEM Behind a Dispatcher](install-configure-app-v1.md#connect-to-an-aem-instance-behind-a-dispatcher).

## Solución de problemas de conexión a AEM Desktop {#troubleshooting-aem-desktop-connection-issues}

### Problema de redirección de SAML {#saml-redirect-issue}

El motivo más común de los problemas con AEM Desktop que se conecta a la instancia de AEM con SSO habilitado (SAML) es que el proceso de SAML no redirige de nuevo a la ruta solicitada originalmente. Como alternativa, la conexión se puede redirigir a un host que no esté configurado en la aplicación de escritorio de AEM. Siga estos pasos para verificar el proceso de inicio de sesión:

1. Abra un explorador Web.
1. En la barra de direcciones, especifique la dirección URL `/content/dam.json`.
1. Reemplace la dirección URL por la instancia de AEM de destino, por ejemplo `https://localhost:4502/content/dam.json`.
1. Inicie sesión en AEM.
1. Después de iniciar sesión, compruebe la dirección actual del explorador en la barra de direcciones. Debe coincidir con la dirección URL que introdujo inicialmente.
1. Compruebe que todo lo anterior a `/content/dam.json` coincide con el valor de AEM de destino configurado en AEM Desktop.

### Problema de configuración SSL {#ssl-configuration-issue}

Las bibliotecas que utiliza la aplicación de escritorio de AEM para la comunicación HTTP utilizan una estricta aplicación SSL. A veces, una conexión puede realizarse correctamente mediante un explorador, pero no puede utilizar la aplicación de escritorio de AEM. Para configurar SSL correctamente, instale el certificado intermedio que falta en Apache. Ver [Cómo instalar un certificado de CA intermedia en Apache](https://access.redhat.com/solutions/43575).

## Uso de AEM Desktop con Dispatcher {#using-aem-desktop-with-dispatcher}

AEM Desktop funciona con implementaciones de AEM detrás de un Dispatcher, que es una configuración predeterminada y recomendada para los servidores de AEM. Los distribuidores de AEM situados delante de los entornos de creación de AEM suelen configurarse para omitir el almacenamiento en caché de los recursos DAM. Por lo tanto, los distribuidores no proporcionan almacenamiento en caché adicional desde el punto de vista de AEM Desktop. Asegúrese de que la configuración de Dispatcher esté ajustada para funcionar con AEM Desktop. Para obtener más información, consulte [Conexión a AEM con un Dispatcher](install-configure-app-v1.md#connect-to-an-aem-instance-behind-a-dispatcher).

## Comprobación de archivos de registro {#checking-for-log-files}

Según el sistema operativo, puede encontrar los archivos de registro para AEM Desktop en las siguientes ubicaciones:

* Windows: `%LocalAppData%\Adobe\AssetsCompanion\Logs`
* Mac: `~/Library/Logs/Adobe\ Experience\ Manager\ Desktop`
