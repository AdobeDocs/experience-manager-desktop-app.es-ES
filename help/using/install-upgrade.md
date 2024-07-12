---
title: Instalación y configuración de la aplicación de escritorio
description: Instala y configura la aplicación de escritorio  [!DNL Adobe Experience Manager] para que funcione con  [!DNL Adobe Experience Manager Assets] servidores y descarga los recursos en tu sistema de archivos local.
feature: Desktop App,Release Information
exl-id: 422e51c1-c456-4151-bb43-4b3d29a58187
source-git-commit: 1c7437786a50eeafa884ce92b745f3438b2d2b88
workflow-type: tm+mt
source-wordcount: '1449'
ht-degree: 0%

---

# Instalar la aplicación de escritorio [!DNL Adobe Experience Manager] {#install-app-v2}

Con la aplicación de escritorio [!DNL Adobe Experience Manager], los recursos de [!DNL Experience Manager] están fácilmente disponibles en el escritorio local y se pueden usar en cualquier aplicación de escritorio nativa. Assets se puede previsualizar y abrir en aplicaciones de escritorio. Pueden mostrarse en Finder o Explorer para su uso en documentos y editarse localmente. Los cambios se vuelven a guardar en [!DNL Experience Manager] y se crea una nueva versión tras la carga.

Esta integración permite que varias funciones de la organización:

* Administrar los recursos de forma centralizada en [!DNL Experience Manager Assets].

* Acceda a los recursos en cualquier aplicación de escritorio nativa, incluidas las aplicaciones de terceros y en Adobe Creative Cloud. Al hacerlo, los usuarios pueden adherirse fácilmente a los distintos estándares, incluida la marca.

Para usar la aplicación de escritorio [!DNL Experience Manager]:

* Asegúrese de que su versión de [!DNL Experience Manager] sea compatible con la aplicación de escritorio [!DNL Experience Manager].

* Descargue e instale la aplicación. Consulte [instalar aplicación de escritorio](#install-v2) a continuación.

* Pruebe la conexión con algunos recursos. Ver [cómo examinar y buscar recursos](using.md#browse-search-preview-assets).

## Requisitos del sistema, requisitos previos y vínculos de descarga {#tech-specs-v2}

Para obtener información detallada, consulte las [[!DNL Experience Manager] notas de la versión de la aplicación de escritorio](release-notes.md).

## Actualización desde una versión anterior {#upgrade-from-previous-version}

Si es usuario de la versión 1.x de la aplicación de escritorio, comprenda las diferencias y similitudes entre la versión anterior y la más reciente de la aplicación. Ver [las novedades de la aplicación de escritorio](introduction.md#whats-new-v2) y [cómo funciona la aplicación](release-notes.md#how-app-works).

>[!NOTE]
>
>Dos versiones de una aplicación de escritorio no pueden coexistir en un equipo. Antes de instalar una versión, desinstale la otra versión.

Para actualizar desde una versión anterior de la aplicación, siga estas instrucciones:

1. Antes de actualizar, sincronice todos los recursos y cargue los cambios en [!DNL Experience Manager]. Al hacerlo, evitará perder las ediciones realizadas al desinstalar la aplicación.

1. Desinstale la versión anterior de la aplicación. Al desinstalar, seleccione la opción para borrar la caché.

1. Reinicie el equipo.

1. [Descargar](release-notes.md) e [instalar](#install-v2) la aplicación más reciente. Siga las instrucciones siguientes.

## Instalar {#install-v2}

Para instalar la aplicación de escritorio, siga estos pasos. Desinstale cualquier aplicación de escritorio de Adobe [!DNL Experience Manager] existente v1.x antes de instalar la aplicación más reciente. Para obtener más información, consulte lo anterior.

1. Descargue el instalador más reciente desde la página [notas de la versión](release-notes.md).

1. Mantenga a mano la dirección URL y las credenciales de su implementación de [!DNL Experience Manager].

1. Si está actualizando desde otra versión de la aplicación, consulte [Actualizar la aplicación de escritorio](#upgrade-from-previous-version).

1. Omita este paso si usa [!DNL Experience Manager] como [!DNL Cloud Service], [!DNL Experience Manager] 6.4.4 o posterior, o [!DNL Experience Manager] 6.5.0 o posterior. Asegúrese de que la configuración de [!DNL Experience Manager] cumpla los requisitos de compatibilidad mencionados en las [notas de la versión](release-notes.md). Si es necesario, descargue el [paquete de compatibilidad](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/cq640/featurepack/adobe-asset-link-support) aplicable e instálelo con el Administrador de paquetes [!DNL Experience Manager] como administrador de [!DNL Experience Manager]. Para instalar un paquete, vea [Cómo trabajar con paquetes](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/sites/administering/contentmanagement/package-manager).

1. Ejecute el binario del instalador y siga las instrucciones que aparecen en pantalla para instalar.

1. En Windows, el instalador puede pedir que se instale `Visual Studio C++ Redistributable 2015`. Siga las instrucciones que aparecen en pantalla para instalarlo. Si la instalación falla, instálela manualmente. Descargue el instalador desde [aquí](https://www.microsoft.com/en-us/download/details.aspx?id=52685) e instale `vc_redist.x64.exe` y `vc_redist.x86.exe` archivos. Vuelva a ejecutar el instalador de la aplicación de escritorio [!DNL Experience Manager].

1. Reinicie el equipo cuando se le solicite. Inicie y configure la aplicación de escritorio de.

1. Para conectar la aplicación con un repositorio de [!DNL Experience Manager], haga clic en el icono de la aplicación en la bandeja e inicie la aplicación. Proporcione la dirección del servidor [!DNL Experience Manager] con el formato `https://[aem_server]:[port]/`.

   Haga clic en **[!UICONTROL Connect]** y proporcione las credenciales.

   ![Pantalla de conexión de la aplicación de escritorio a la dirección del servidor de entrada](assets/connect_da2.png)

   *Figura: pantalla de conexión a la dirección del servidor de entrada.*

   Seleccione **[!UICONTROL Remember Connection]** para evitar ingresar los detalles de conexión cada vez que inicie sesión en la aplicación de escritorio.

   >[!CAUTION]
   >
   >Asegúrese de que no haya espacios iniciales o finales antes o después de la dirección del servidor [!DNL Experience Manager]. De lo contrario, la aplicación no podrá conectarse al servidor [!DNL Experience Manager].

1. [Opcional] Haga clic en **[!UICONTROL I want to connect a different way]** y haga clic en **[!UICONTROL Adobe login]** para iniciar sesión en el servidor de Experience Manager Assets mediante el servicio Identity Management de Adobe (IMS). El inicio de sesión de IMS permite que la aplicación de escritorio actualice el token de acceso automáticamente, lo que permite al usuario permanecer conectado durante un máximo de 14 días. Haga clic en **[!UICONTROL Direct login]** para realizar el inicio de sesión estándar en el servidor [!DNL Experience Manager] con las credenciales del usuario.

   ![Inicio de sesión en el Adobe](assets/adobe-login.png)

1. Una vez que la conexión se haya realizado correctamente, podrá ver la lista de carpetas y recursos disponibles en la carpeta raíz del DAM [!DNL Experience Manager]. Puede examinar las carpetas desde la aplicación.

   ![Al iniciar sesión, la aplicación muestra el contenido de DAM](assets/firstview_da2.png)

   *Imagen: la aplicación muestra el contenido de DAM después del inicio de sesión*

1. ([!DNL Experience Manager] 6.5.1 o posterior) Si utiliza la aplicación de escritorio con [!DNL Experience Manager] 6.5.1 o posterior, actualice S3 o el conector de Azure a la versión 1.10.4 o posterior. Ver [conector de Azure](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/deploying/deploying/data-store-config#azure-data-store) o [conector S3](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/implementing/deploying/deploying/data-store-config#amazon-s-data-store).

   Si es cliente de Adobe Managed Services (AMS), póngase en contacto con el servicio de atención al cliente de Adobe.

## Definir preferencias {#set-preferences}

Para cambiar las preferencias, haga clic en ![Icono de más opciones](assets/do-not-localize/more_options_da2.png) y **[!UICONTROL Preference]** ![Icono de preferencias](assets/do-not-localize/preferences_icon_da2.png). En la ventana **[!UICONTROL Preferences]**, ajuste los valores de lo siguiente:

* [!UICONTROL Launch the application on logon].

* [!UICONTROL Show a window when the application starts].

* **[!UICONTROL Cache Directory]**: ubicación de la caché local de la aplicación (contiene los recursos descargados localmente).

* **[!UICONTROL Network Drive Letter]**: letra de unidad utilizada para asignarse al DAM [!DNL Experience Manager]. No cambie esta letra de unidad de red si no está seguro. La aplicación puede asignarse a cualquier letra de unidad en Windows. Si dos usuarios colocan recursos de letras de unidad diferentes, no podrán ver los recursos que el otro ha colocado. La ruta de los recursos cambia. Los recursos permanecen colocados en el archivo binario (por ejemplo, INDD) y no se eliminan. La aplicación enumera todas las letras de unidad disponibles y, de forma predeterminada, utiliza la última letra disponible que suele ser `Z`.

* **[!UICONTROL Maximum Cache Size]**: caché permitida en el disco duro en GB que se usa para almacenar recursos descargados localmente.

* **[!UICONTROL Current cache size]**: tamaño de almacenamiento de los recursos descargados localmente. La información solo se muestra después de descargar los recursos mediante la aplicación.

* **[!UICONTROL Automatically download linked assets]**: al descargar el archivo original, los recursos colocados en las aplicaciones de Creative Cloud nativas admitidas se recuperan automáticamente.

* **[!UICONTROL Maximum number of downloads]**: ![icono de precaución](assets/do-not-localize/caution-icon.png) Cambiar con precaución. Al descargar recursos por primera vez (mediante las opciones Revelar, Abrir, Editar, Descargar o similares), los recursos solo se descargan si el lote contiene un número inferior a este. El valor predeterminado es 50. No cambie si no está seguro. Elevar el valor puede resultar en tiempos de espera más largos, mientras que reducirlo puede impedir que descargue todos los recursos o carpetas necesarios de un solo intento.

* **[!UICONTROL Use legacy conventions when creating nodes for assets and folders]**: ![icono de precaución](assets/do-not-localize/caution-icon.png) Cambiar con precaución. Esta configuración permite que la aplicación emule el comportamiento de la aplicación v1.10 al cargar carpetas. En la versión 1.10, los nombres de nodo creados en el repositorio respetan los espacios y mayúsculas de los nombres de carpeta proporcionados por el usuario. Sin embargo, en la versión 2.1 de la aplicación, los espacios adicionales de los nombres de carpeta se convierten en guiones. Por ejemplo, al cargar `New Folder` o `new   folder` se crea el mismo nodo en el repositorio si la opción no está seleccionada y se conserva el comportamiento predeterminado en v2.1. Si se selecciona esta opción, se crean diferentes nodos en el repositorio para las dos carpetas anteriores y coincide con el comportamiento de la aplicación v1.10.

  El comportamiento predeterminado de v2.1 permanece sin cambios: reemplaza varios espacios en los nombres de carpeta con guiones en el nombre del nodo del repositorio y convierte los nombres de nodo en minúsculas.

* **[!UICONTROL Upload Acceleration]**: ![icono de precaución](assets/do-not-localize/caution-icon.png) Cambiar con precaución. Al cargar recursos, la aplicación puede utilizar cargas simultáneas para mejorar la velocidad de carga. Puede aumentar la concurrencia de la carga moviendo el control deslizante a la derecha. El control deslizante del extremo izquierdo significa que no hay concurrencia (carga de un solo hilo), la posición central corresponde a diez hilos simultáneos y el límite máximo del extremo derecho corresponde a 20 hilos simultáneos. Un límite de concurrencia más alto consume más recursos.

Para actualizar las preferencias no disponibles, cierre la sesión del servidor [!DNL Experience Manager] y, a continuación, actualícela. Después de actualizar las preferencias, haga clic en ![Guardar preferencias](assets/do-not-localize/save_preferences_da2.png).

![Preferencias y configuración de la aplicación de escritorio](assets/preferences_da2.png)

*Imagen: preferencias de aplicación de escritorio.*

### Compatibilidad con proxy {#proxy-support}

La aplicación de escritorio [!DNL Experience Manager] usa el proxy predefinido del sistema para conectarse a Internet a través de HTTPS. La aplicación solo se puede conectar con un proxy de red que no requiera autenticación adicional.

Si establece o modifica la configuración del servidor proxy para Windows (Opciones de Internet > Configuración de LAN), reinicie la aplicación de escritorio [!DNL Experience Manager] para que los cambios surtan efecto. La configuración de proxy se aplica al iniciar la aplicación de escritorio. Cierre y vuelva a iniciar la aplicación para que los cambios surtan efecto.

Si el proxy requiere autenticación, el equipo de TI puede permitir que la dirección URL [!DNL Experience Manager Assets] de la configuración del servidor proxy permita el paso del tráfico de la aplicación.

## Desinstalar la aplicación {#uninstall-the-app}

Para desinstalar la aplicación en Windows, siga estos pasos:

1. Cargue todos los cambios en [!DNL Experience Manager] para evitar la pérdida de ediciones. Consulte [Editar recursos y cargar recursos actualizados a [!DNL Experience Manager]](using.md#edit-assets-upload-updated-assets). Cierre la sesión y [!UICONTROL Exit] la aplicación.

1. Elimine la aplicación del mismo modo que cualquier otra aplicación del sistema operativo. Desinstálelo de Agregar y quitar programas en Windows.

1. Para quitar la caché y los registros, active la casilla de verificación necesaria.

   ![Cuadro de diálogo de desinstalación para eliminar registros y caché](assets/uninstall_da2.png)

1. Siga las instrucciones que aparecen en pantalla. Una vez finalizado, reinicie el equipo.

Para desinstalar la aplicación en Mac, siga estos pasos:

1. Cargue todos los cambios en [!DNL Experience Manager] para evitar la pérdida de ediciones. Consulte [Editar recursos y cargar recursos actualizados a [!DNL Experience Manager]](using.md#edit-assets-upload-updated-assets). Cierre la sesión y [!UICONTROL Exit] la aplicación.

1. Quitar a `Adobe Experience Manager Desktop.app` de `/Applications`.

Como alternativa, para limpiar las cachés de aplicaciones internas en Mac y desinstalar la aplicación, puede ejecutar el siguiente comando en el terminal:

```shell
/Applications/Adobe Experience Manager Desktop/Contents/Resources/uninstall-osx/uninstall.sh
```
