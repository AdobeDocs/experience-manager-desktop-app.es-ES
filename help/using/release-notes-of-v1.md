---
title: Notas de la versión 1.10 de la aplicación de escritorio
description: AEM Detalles de la versión, mejoras, nuevas funciones, compatibilidad y vínculos de descarga para la versión 1.10 de la aplicación de escritorio de.
exl-id: 886864e0-016a-4a17-b3ba-4b18a514214a
source-git-commit: 23719d2f5d92f6031687df18036acdbc04722402
workflow-type: tm+mt
source-wordcount: '3989'
ht-degree: 1%

---

# [!DNL Adobe Experience Manager] notas de la versión v1.10 de la aplicación de escritorio {#aem-desktop-app-release-notes}

AEM Para la versión v1.x de la aplicación de escritorio, los siguientes son los vínculos de descarga y la información de compatibilidad de la aplicación de escritorio de la versión 1.x.

| Productos | Aplicación de escritorio de [!DNL Adobe Experience Manager] |
|--- |--- |
| Versión | 1.10 (1.10.0.6 en Mac y 1.10.0.3 en Windows) |
| Tipo | Versión menor |
| Fecha | 1.10.0.6 (Mac): 15 de abril de 2020; 1.10.0.3 (Win): 31 de agosto de 2018 |
| Direcciones URL de descarga | [macOS X de 64 bits](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-osx-1.10.0.6.dmg); [Windows de 32 bits](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-win32-1.10.0.3.exe); [Windows de 64 bits](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-win64-1.10.0.3.exe) |
| Compatibilidad | AEM AEM AEM AEM AEM.5.x; 6.4.x; 6.3 SP2; 6.2 SP1 CFP2+; 6.2 SP2 CFP2+; 6.1 SP2 CFP7+; 6.3 SP2; 6.4.x; 600000000000000000000000000000000000000000000000000010000000000000000000000000000000000000000000000000000000000000000000 |

>[!NOTE]
>
>No se aplica el límite de tamaño de caché. Cuando se inicia la aplicación de escritorio, el tamaño de la caché se calcula una vez y se muestra una notificación si el tamaño se aproxima al límite predefinido.

## Requisitos y requisitos previos del sistema {#system-requirements-and-prerequisites}

La aplicación de escritorio [!DNL Adobe Experience Manager] es compatible con los siguientes sistemas operativos:

* macOS X 10.10 o posterior, con las últimas correcciones de errores.

* Windows 10 con los últimos paquetes de servicio y correcciones de errores.

El Adobe AEM recomienda utilizar la última versión de la aplicación de escritorio de para asegurarse de que está utilizando la funcionalidad más reciente, las correcciones de errores más recientes y el mejor rendimiento posible.

AEM AEM La versión de la aplicación de escritorio de que planea instalar en su equipo local requiere un servidor específico de
versión / componentes adicionales del lado del servidor (paquetes de servicio, correcciones rápidas o paquetes de funciones). AEM Asegúrese de que el servidor de esté configurado correctamente antes de conectarse a él por primera vez. AEM Si necesita ayuda, póngase en contacto con su administrador de.

Consulte la [matriz de compatibilidad detallada](#compatibilitymatrix) al final de este documento para evaluar los requisitos previos de la configuración.

## Novedades de la aplicación de escritorio v1.10 {#what-s-new-in-aem-desktop-app}

AEM La aplicación de escritorio 1.10 de se centra en mejorar la experiencia del usuario con cargas grandes, información sobre las operaciones en segundo plano y experiencia optimizada al abrir recursos con archivos vinculados (como el InDesign).

>[!NOTE]
>
>Si utiliza macOS 10.15.4 o posterior, utilice al menos la versión 1.10.0.6 de la aplicación. Esta versión del parche cumple con [los requisitos de certificación de Apple](https://developer.apple.com/news/?id=04102019a).

**Edición/desprotección local**: las cargas automáticas de los cambios guardados en los recursos se pueden deshabilitar en la ventana de estado. De este modo, el usuario puede seguir trabajando en los archivos y guardando los cambios y, después, cuando estén listos, decidir cargar todos los cambios.

**Ventana de estado de recursos simplificada**. La ventana de estado se ha simplificado. La ficha [!UICONTROL Uploads] ahora muestra recursos individuales y cargas de carpetas o masivas. Se ha eliminado la pestaña de cargas masivas anterior.

**Icono de aplicación para indicar cargas masivas**. El icono de la aplicación indica que se está realizando una carga masiva mediante la superposición &quot;transferir&quot;.

**Notificaciones de conflictos de actualización**. Cuando la aplicación detecta un conflicto durante una actualización de recursos, muestra una notificación que permite al usuario revisarlo sin monitorizar la ventana de estado. Durante el inicio, la aplicación comprueba todos los conflictos, lo que permite al usuario resolverlos.

**Mejor manejo de las pérdidas de conexión**. Las cargas masivas se pausan si se pierde la conexión y el usuario puede reanudarlas más tarde. Hay disponible una opción [!UICONTROL Retry] para reintentar una carga fallida de un archivo individual.

## Instrucciones de instalación {#installation-instructions}

AEM Para obtener instrucciones detalladas, consulte [Instalar y configurar la aplicación de escritorio de la aplicación de escritorio de la](install-configure-app-v1.md).

## Mejoras en las versiones anteriores {#enhancements-in-the-previous-versions}

Esta versión amplía y reemplaza las versiones anteriores de la aplicación de escritorio [!DNL Experience Manager], que proporcionaron las siguientes mejoras clave:

* **Versión 1.9 / 1.9.1**: cargas reanudables, ventana de estado mejorada, iconos de aplicación que indican el estado de la aplicación/conexión, recuperación previa de recursos vinculados para archivos de InDesign.

* **Versión 1.8**: mejor control del tamaño de la caché para el usuario, experiencia de inicio de sesión mejorada para SAML/SSO en Windows, compatibilidad con proxy de red `.pac` en Mac y problemas notificados por el cliente.

* **Versión 1.7**: mejoras en la estabilidad y la lógica de almacenamiento en caché, mejor compatibilidad con el proxy de red y capacidad para limpiar archivos internos después de la desinstalación.

* AEM **Versión 1.6**: mejoras en el proceso de inicio de sesión para varias configuraciones de seguridad de la aplicación y para la estabilidad y el rendimiento de la aplicación.

* **Versión 1.5**: estabilidad y resistencia de la aplicación frente a diversos problemas de red, mejor compatibilidad.

* **Versión 1.4**: la capacidad de cargar carpetas jerárquicas en segundo plano con la supervisión de progreso.

* AEM **Versión 1.3**: mejoras de rendimiento y estabilidad para tener acceso a archivos y guardar cambios en los archivos, especialmente desde aplicaciones de escritorio de Creative Cloud, como InDesign, Illustrator o Photoshop. Su objetivo era proporcionar a los usuarios una experiencia más local similar a un escritorio cuando se trabaja con archivos, mientras se controlan simultáneamente las operaciones de transferencia de datos de red en segundo plano.

### AEM Mejoras disponibles desde la aplicación de escritorio 1.9 de {#Enhancements-Available-Since-AEM-Desktop-App-19x}

[!DNL Adobe Experience Manager] versión 1.9.1 de aplicación de escritorio fue una versión de parche. Se diseñó para abordar los problemas clave de los clientes con el cierre de compra de recursos. Y, dirigir la copia de archivos de un recurso compartido de red a un directorio local.

* Assets desprotegido por un usuario no debe estar disponible para la modificación por otros usuarios (CQ-4246009)

* Compatibilidad con la copia de una carpeta asignada a una carpeta local cuando la carpeta del usuario está en una partición de disco independiente (CQ-4243978)

AEM La aplicación de escritorio 1.9 de se centró en la mejora de la experiencia del usuario en cargas grandes, información sobre las operaciones en segundo plano y experiencia optimizada al abrir recursos con archivos vinculados (como el InDesign).

**Cargas reanudables**
En el caso de las cargas, especialmente en archivos grandes, existe la opción de pausarlas o reanudarlas en la nueva ventana Estado de los recursos.

**Ventana de estado de recursos mejorada**
Una ventana de Estado de recursos mejorada proporciona la siguiente información sobre los recursos.

[!UICONTROL Changes]

* Muestra los cambios actualmente en cola.

* Muestra las cargas en curso con una barra de progreso, la velocidad de transferencia, el tamaño total del archivo y la cantidad transferida hasta el momento.

* Cargas completadas que se muestran con la tarifa total transferida y final.

* Las cargas con errores se muestran junto con un mensaje de error y la información de transferencia, si está disponible.

* Las cargas que han fallado tres veces muestran un mensaje de error.

* Los archivos en conflicto se muestran con un icono en el que el usuario puede hacer clic. Al hacer clic en el icono, se muestra un cuadro de diálogo con una explicación y dos opciones:

   * [!UICONTROL Keep Mine] carga inmediatamente el archivo en el servidor.

   * [!UICONTROL Overwrite Mine] elimina inmediatamente el archivo local y descarga una copia nueva del servidor.

[!UICONTROL Downloads]

* Muestra las descargas en curso, incluida la tasa de transferencia y el tamaño transferidos hasta el momento.

* Las descargas completadas se muestran con el total transferido, la tasa final y un icono que abre el archivo cuando se hace clic (solo disponible para archivos únicos).

* Las descargas fallidas se muestran con un mensaje de error y transfieren información, si está disponible.

* El pie de página muestra el número total de archivos descargados y la velocidad de transferencia promedio.

* Si un usuario elige abrir o editar varios archivos de la interfaz web [!DNL Experience Manager Assets], se agrupan. Por ejemplo, myasset.jpeg y 4 archivos más.

* Al descargar documentos de InDesign con recursos vinculados desde AEM Assets, la aplicación de escritorio descarga primero todos los recursos vinculados antes de abrir el documento e indicar el estado de descarga. Por ejemplo, 5 de 24.

[!UICONTROL Bulk Uploads]

AEM La carga de jerarquías de carpetas grandes a través de [!UICONTROL Create] > [!UICONTROL Upload Folder] en la interfaz de usuario de la web de la déclencheur este cuadro de diálogo. Lo mismo ocurre cuando copia y selecciona &quot;Pegar Assets&quot; en Finder o Explorer en el menú contextual de la aplicación de escritorio.

* Muestra las cargas en curso, incluida una barra de progreso y el nombre del archivo que se está transfiriendo en ese momento.

* Las cargas en curso incluyen un icono que cancela la carga cuando se hace clic en él. La transferencia se detiene una vez finalizado el archivo que se está transfiriendo.

* Los procesos de transferencia fallidos se muestran con un mensaje de error (solo si falla toda la transferencia).

* Si un archivo individual no se transfiere, se muestra en la pestaña como un error. De lo contrario, los archivos individuales no se muestran en la pestaña * solo una entrada para toda la carga.

**Iconos que indican el estado de las operaciones en segundo plano**

El icono de la aplicación indica el estado de las operaciones en segundo plano para proporcionar una mejor pista visual a los usuarios. AEM Por ejemplo, cuando la aplicación no está conectada a la aplicación, el icono aparece atenuado. Cuando hay una carga activa, se muestra una superposición de &quot;sincronización&quot;, etc.

**Recuperación previa de Assets enlazado**

Para mejorar la experiencia del usuario con los documentos de InDesign AEM que contienen recursos vinculados almacenados en la memoria caché, la aplicación de escritorio recupera previamente estos archivos vinculados en la memoria caché local. Este flujo se produce antes de que descargue y abra el documento de InDesign. De este modo, el usuario tiene los archivos vinculados disponibles localmente y no necesita esperar más cuando accede a los recursos en InDesign (en el panel Vínculos).
AEM La recuperación previa solo funciona si reconoce los vínculos en el lado del servidor. Un recurso con vínculos reconocidos tiene una lista de &quot;Referencias&quot; en la vista Propiedades del recurso de InDesign.

### AEM Mejoras disponibles desde la aplicación de escritorio 1.8.x de {#enhancements-available-since-aem-desktop-app-18x}

AEM AEM La versión de seguimiento rápido 1.8.1 de la aplicación de escritorio de añadió mejoras al abrir varios archivos a la vez desde la interfaz de usuario de hasta la versión 1.8 (CQ-4237747, CQ-4238780). AEM Las mejoras de la aplicación de escritorio 1.8 de son:

* AEM Almacenamiento en caché: nueva interfaz de usuario para administrar la caché de la aplicación de escritorio de la aplicación (CQ-4208690), que incluye:

   * ver tamaño de caché actual

   * definir el tamaño máximo de la caché antes de enviar una notificación

   * El tamaño de la caché solo se comprueba al iniciar la aplicación de escritorio y se muestra una notificación si alcanza el límite configurado

   * El botón Borrar caché ya está disponible en la nueva interfaz de usuario

* AEM Inicio de sesión: (Win) inicio de sesión fijo en la instancia de configurada para utilizar SAML y SSL (CQ-4216353)

* Red:

   * AEM cuando caduca una sesión de, ahora se notifica al usuario y puede hacer clic en la notificación para volver a iniciar sesión (CQ-4202028).

   * (Mac AEM) Agregue compatibilidad para conectarse a la mediante la configuración del proxy `.pac` (CQ-4233430).

   * (Win) Solucione problemas con el cuadro de diálogo Avanzado: URL de inicio de sesión (CQ-4236061).

* Correcciones de errores:

   * Cuadro de diálogo Más información del recurso: a veces la barra de acciones no estaba visible (CQ-4208540).

   * (Win) El archivo ahora se puede sincronizar después de volver a una versión anterior desde la interfaz de usuario de AEM Assets (CQ-4216411).

### AEM Mejoras disponibles desde la aplicación de escritorio 1.7 de {#Enhancements-Available-Since-AEM-Desktop-App-17}

* Estabilidad:

   * AEM AEM Se ha mejorado la estabilidad al conectar la aplicación de escritorio de a un servidor de sobrecargado (CQ-4224803).

   * Se ha mejorado la estabilidad cuando se solicitan muchos archivos (CQ-4224212).

   * Se ha mejorado la actualización de recursos con comprobaciones adicionales (CQ-4228291).

* Almacenamiento en caché:

   * Solucionar errores de disco y problemas de apertura al abrir archivos en Photoshop, InDesign, Finder (CQ-4223993, CQ-4217603, CQ-4223717).

   * Se ha mejorado el almacenamiento en caché para evitar binarios de tamaño cero (CQ-4216599).

* Inicio de sesión: permitir la conexión con el SSL estricto deshabilitado para configuraciones especiales (como certificados emitidos localmente) (CQ-4223949).

* Redes: compatibilidad mejorada para conectarse a través de un proxy de red (CQ-4223477, CQ-4221280, CQ-4206854).

* Instalación y desinstalación:

   * (Win) Desinstalación del limpiador (CQ-4220906).

   * El instalador de [Windows de 32 bits] no puede instalar Microsoft .NET Framework versión 4.5 (CQ-4218084).

   * (Mac) Script manual para eliminar por completo los archivos de la aplicación de escritorio (CQ-4216489).

>[!NOTE]
>
>AEM Los problemas encontrados en las cargas beta de la aplicación de escritorio 1.7 de que estaban ausentes en la versión 1.6 se omiten de las notas de la versión.

### AEM Mejoras disponibles desde la aplicación de escritorio de la aplicación de escritorio 100600000000000000100000000000000000000000000000000000000000000000000 00000000000000000000000000000000000000000000000000000000000000000000000000 {#Enhancements-Available-Since-AEM-Desktop-App-16}

* Documentación: nuevas [prácticas recomendadas para la aplicación v1.x](/help/using/best-practices-for-v1.md) documentación.

* AEM Se ha mejorado el proceso de inicio de sesión para:

   * Mejora de la gestión de SAML * reglas de relajación (CQ-4202781).

   * Añada la capacidad de configurar una URL de inicio de sesión independiente en Preferencias (CQ-4214052, CQ-4214051).

* Uso: notificar al usuario cuando un recurso aún se está descargando para recursos más grandes (CQ-4216284).

* Redes:

   * Almacenamiento en caché de DNS (CQ-4210176).

   * Compatibilidad con la conexión mediante proxy en Windows (CQ-4206854).

* Almacenamiento en caché y acceso al recurso compartido de red en Finder/Explorer:

   * El icono de candado ahora está visible para los recursos desprotegidos en Windows 10 (CQ-90957).

   * El contenido de la carpeta puede desaparecer o volver a aparecer en el recurso compartido de red (CQ-4209160, CQ-4210180).

   * Error al cargar el archivo debido a un conflicto notificado en el estado de la cola de carga (CQ-4215727).

   * Al abrir varios archivos desde la carpeta de la aplicación de escritorio en PS, es posible que se muestren mensajes truncados o incompletos (CQ-4216276).

* Correcciones en estabilidad y rendimiento:

   * Se ha mejorado el rendimiento al examinar las carpetas con muchos recursos (CQ-4214933).

   * La aplicación de escritorio 1.5 puede ralentizar un equipo de escritorio con el tiempo (CQ-4209159).

   * La función Mostrar estado de cola solo funciona para el usuario que instaló la aplicación (CQ-4212199).

   * (Windows) Asegúrese de que el instalador de 32 bits no contenga código de 64 bits (CQ-4217406).

* Problemas seleccionados encontrados y corregidos en la beta 1.6:

   * Uso elevado de CPU (CQ-4218070).

   * AEM Error al arrastrar y soltar archivos que generan un error al cargar en el servidor de correo electrónico (CQ-4217006).

### AEM Mejoras disponibles desde la aplicación de escritorio 1.5 de {#Enhancements-Available-Since-AEM-Desktop-App-15}

**Versión 1.5.1.5 para macOS X:** La versión 1.5.1.5 ofrece las siguientes ventajas:

* AEM Nuevas funciones y mejoras: Añada la funcionalidad Copiar/Pegar a la integración de Finder para permitir la transferencia directa de Escritorio a (CQ-4208158).

* Correcciones de errores:

   * Se ha corregido el error 43 que se producía a veces durante el cambio de nombre de recursos (CQ-4207900).

   * AEM La reversión a una versión anterior de la cronología en la que se encuentra el recurso no se actualiza en el Buscador (CQ-4205194).

   * La aplicación de escritorio se bloquea al examinar directorios anidados grandes (CQ-4208539).

   * El punto de montaje de la aplicación de escritorio ahora es /Volumes/DAM, por lo que es coherente para todos los usuarios (CQ-4208159).

   * Al colocar un archivo en el InDesign por primera vez se inicia una advertencia de actualización (CQ-4207454).

Nota sobre las advertencias de vínculos: las aplicaciones de Creative Cloud (como InDesigns) toman una &quot;instantánea&quot; de la última modificación del artículo en el momento en que se coloca. Si esa fecha cambia en un momento posterior, la aplicación de Adobe Creative Cloud informa de que los vínculos no están actualizados. Se informa de esta información de un par de maneras:

* Cuando se inicia la aplicación de Adobe Creative Cloud, muestra un cuadro de diálogo que informa al usuario de que los recursos vinculados no están actualizados y le solicita que realice una acción.

* Si la aplicación de Adobe Creative Cloud ya se está ejecutando, muestra un icono de advertencia de triángulo amarillo en el recurso vinculado.

AEM Este comportamiento es el mismo para los recursos del disco local y los recursos de un directorio montado en el escritorio de la aplicación, con las siguientes excepciones:

* Si otro usuario edita un recurso colocado, el icono de advertencia se mostrará la primera vez que otros usuarios abran un documento que lo contenga. Esta advertencia solo se produce si el recurso colocado ya se ha almacenado en caché localmente.

* AEM Si un usuario modifica un recurso colocado a través del directorio montado del escritorio del y luego borra su caché local, el recurso colocado se registra como obsoleto.

AEM Ambos casos son previsibles y son efectos secundarios de la arquitectura de &quot;sincronización retardada&quot; de los equipos de escritorio de la aplicación de escritorio.

**Versión 1.5.0.x para macOS AEM X y Windows:** Esta versión de la aplicación de escritorio de Adobe proporciona las siguientes ventajas:

* Mejor estabilidad y resiliencia frente a los problemas de red.

   * Asignación más estable de carpetas de AEM Assets (CQ-103276, CQ-4204669, CQ-4203957).

   * Mejor gestión de los archivos en caché (CQ-4204336, CQ-4206263).

   * Se ha mejorado la gestión de la descarga/carga de archivos de gran tamaño de más de 2 GB (CQ-4206438).

   * Se ha corregido el &quot;Error 36&quot; al mover o cambiar el nombre de un mayor número de archivos en Finder (CQ-4204640).

* AEM Optimizaciones en la comunicación de red con el servidor de (CQ-4204974, CQ-100903).

* AEM Se ha mejorado la fiabilidad de apertura, colocación y guardado de recursos desde las aplicaciones de Creative Cloud (CQ-4203968, CQ-4205511, CQ-103543, CQ-4207141, CQ-90980).

* Compatibilidad mejorada: opción para borrar la caché (CQ-4202541), fácil acceso a los registros (CQ-4202340, CQ-4204673).

* Otras correcciones:
   * Mejor compatibilidad con recursos y carpetas que tienen caracteres japoneses en la configuración de nombre/idioma no inglés (CQ-4195433, CQ-4205793, CQ-4199446).

   * Mejor gestión de inicio de sesión con SSL (CQ-4200217).

   * Montaje compartido más fiable (CQ-4200793).

   * Varias mejoras en la estabilidad (CQ-4207539, CQ-4200378).

   * Mejor gestión de la URL de AEM Assets en Preferencias (CQ-97388).

### AEM Mejoras disponibles desde la aplicación de escritorio 1.4 de {#Enhancements-Available-Since-AEM-Desktop-App-14}

* Carga simplificada de carpetas jerárquicas mediante la nueva acción Crear > Cargar carpeta en la IU táctil.
   * Esta acción inicia una operación de carga de carpetas realizada por la aplicación de escritorio.
   * La aplicación de escritorio atraviesa la jerarquía de carpetas determinada en el escritorio en segundo plano y carga los archivos en AEM Assets.
   * El usuario puede supervisar el progreso en la nueva ventana Cargar estado de cola para las operaciones en curso.
   * El estado de la cola de carga también proporciona mejor información de solución de problemas (por ejemplo, sin conexión al servidor).
* Nueva acción de edición en la IU táctil que combina las operaciones de cierre de compra y apertura en una.
* AEM Se ha optimizado la agrupación de acciones relacionadas con el escritorio en la IU táctil (6.3 de).
* Compatibilidad mejorada con las últimas versiones del sistema operativo.
* Correcciones notificadas por el cliente.

### AEM Mejoras disponibles desde la aplicación de escritorio 1.3 de {#Enhancements-Available-Since-AEM-Desktop-App-13}

* Mayor eficiencia. Los usuarios pasan menos tiempo esperando a que se completen las operaciones de red.
* Se ha mejorado la integración de Finder, que proporciona más estabilidad y acceso a funciones como las miniaturas.
* Mejoras de almacenamiento en caché y rendimiento.
* Mejor compatibilidad para guardar directamente desde aplicaciones de escritorio (PS, ID, AI, etc.).
* Se ha mejorado la integración con macOS (el protocolo de unidad de red local cambió de WebDAV a SMB1 más estable).
* AEM AEM La aplicación de escritorio se conecta con el servidor de mediante protocolo HTTP RESTful nativo.
* AEM Los archivos se guardan localmente primero y luego se cargan de nuevo en segundo plano, después de un tiempo predefinido (30 segundos), para volver a colocarlos en segundo plano. Este flujo de trabajo reduce el tiempo para guardar archivos.
* AEM Mejor gestión de las aplicaciones de escritorio que utilizan operaciones de archivo intermedias para guardar un archivo (guardados parciales y archivos temporales), lo que permite que la cronología de recursos de la muestre la versión correcta y la información de carga de recursos.
* Se proporciona un cuadro de diálogo para realizar un seguimiento del estado de las tareas de carga en segundo plano.

## Lista de cambios {#list-of-changes}

### Punto de montaje en Mac {#mount-point-on-mac}

Desde macOS 10.12 (Sierra), Apple ha cambiado los permisos de la carpeta /Volumes que se usan para montar unidades de red y dispositivos para que sean más restrictivos. La creación de un nuevo punto de montaje en esa ubicación requería derechos administrativos. Este problema se solucionó en macOS 10.12.5.

AEM El punto de montaje de la aplicación de escritorio de la aplicación de escritorio de la aplicación ha cambiado en las versiones 1.4 y 1.5. En macOS, se cambió a una subcarpeta DAM dentro de la carpeta local del usuario, que admite usuarios no administradores (CQ-104183).

Debido a que la carpeta `/Volumes` ya no requiere derechos administrativos, este cambio se revirtió en 1.5.1. Este cambio también permite compartir documentos de InDesign AEM que han colocado recursos de entre los usuarios de macOS a partir de una ubicación que los ha.

### Cambio de protocolo (desde la versión 1.3) {#protocol-change-since}

* macOS X:
   * El protocolo de unidad de red local para la integración de escritorio de OS X cambió de WebDAV a SMB1.
   * AEM El repositorio de montado con la aplicación de escritorio es visible como una unidad de red `smb` en el Finder, en lugar de como una unidad WebDAV.
* Windows:
   * AEM El protocolo de unidad de red local para las integraciones de escritorio de Windows permanece; se monta como un recurso compartido de WebDAV.
* Para ambas plataformas (Windows y Mac):
   * AEM AEM El protocolo para acceder/descargar recursos y cargar cambios en los recursos se ha cambiado a la versión nativa del protocolo de, que es un protocolo RESTful basado en HTTP. Proporciona un mayor control sobre las operaciones de red y es más compatible con la infraestructura de red.

>[!NOTE]
>
>En macOS X, el cambio del protocolo de la unidad de red local de WebDAV a SMB1 da como resultado una ruta local diferente al mismo recurso del repositorio. Este cambio podría afectar a los vínculos a archivos colocados en aplicaciones de Adobe Creative Cloud mediante el comando &quot;Colocar&quot;. AEM Consulte [Usar aplicación de escritorio](use-app-v1.md) para obtener más información.

### Administración de archivos (desde 1.3) {#file-handling-since}

* Las carpetas se actualizan automáticamente después de un retraso predefinido (actualmente de 30 años).
* Los archivos desprotegidos por otros usuarios se marcan como de sólo lectura.
* Los archivos se guardan en una ubicación de unidad de red montada mediante la aplicación de escritorio en dos fases.
* En la primera fase, se guarda un archivo localmente. AEM De este modo, el usuario que guarde el archivo no tendrá que esperar hasta que el archivo se transfiera completamente a la red de archivos y podrá reanudar el trabajo en cuanto se guarde el archivo.
* AEM En la segunda fase, la aplicación de escritorio carga un archivo actualizado en el servidor de después de un retraso predefinido (por ejemplo, treinta segundos). Esta operación se produce en segundo plano. Use la opción **Mostrar estado de sincronización de archivos en segundo plano** para ver el estado de la operación de carga.

## Avisos importantes {#important-notices}

**Carga de carpeta.El Adobe AEM** recomienda usar la nueva capacidad de carga de carpetas para cargar carpetas jerárquicas de mayor tamaño en las carpetas de la carpeta de destino de la. AEM Se recomienda este método en lugar de utilizar una copia/arrastrar y soltar en un repositorio de recursos montado desde el nivel de Finder/Explorador. AEM Al utilizar la función de carga de carpetas, la aplicación de escritorio se comunica directamente con los usuarios y, por lo tanto, tiene un control mucho mejor sobre el proceso general.

AEM **Mantener sesión disponible en el servicio de asistencia.AEM** La aplicación de escritorio de la aplicación de escritorio de la depende de una sesión abierta en el servidor de AEM Assets para garantizar el funcionamiento adecuado. Los usuarios diarios deben desmontar AEM Assets al final del día para cerrar la sesión y volver a montarla por la mañana para garantizar el inicio de sesión y la funcionalidad de uso compartido de red.

**Desactivar &quot;Vista previa de iconos&quot; en el Finder.** Para examinar con buen rendimiento carpetas grandes con Finder, especialmente con conectividad de red deficiente, asegúrese de que tanto &quot;Icon&quot; como &quot;Icon Preview&quot; estén desactivados. De lo contrario, Finder comienza a descargar cada recurso en una carpeta para generar una pequeña previsualización, lo que puede provocar un rendimiento deficiente y un uso elevado del ancho de banda (CQ-4219779)

* En Finder, vaya a AEM Assets shared network folder
* Haga clic con el botón derecho en el punto de montaje DAM
* Seleccione Mostrar opciones de vista
* Anular la selección de &quot;Mostrar icono de previsualización&quot;
* Haga clic en &quot;Usar como valores predeterminados&quot;

AEM **Limpie la caché al conectarse a un nuevo servidor de.AEM**: si la aplicación de escritorio se conecta a otro servidor de con la misma dirección URL, la caché no se borra automáticamente. Borre la caché manualmente para garantizar las operaciones adecuadas. AEM Tenga en cuenta que este proceso generalmente se produciría en pruebas, cuando las instalaciones de la se pueden reemplazar mientras se ejecutan en la misma dirección URL (CQ-4216982)

**Use certificados SSL firmados por la CA.AEM AEM**: la aplicación de escritorio de la aplicación de escritorio de la no admite certificados SSL autofirmados al conectarse a mediante una conexión segura HTTPS. Se requiere un certificado firmado por la CA en el servidor para estas conexiones. (CQ-87941)

## Problemas conocidos {#known-issues}

* General:
   * Las direcciones URL del servidor son necesarias para señalar al servidor sin una ruta de acceso (por ejemplo, `http://server`, `https://server`, `http://server:port` o `https://server:port`). No se admiten rutas de contexto ni subcarpetas que no sean /content/dam (CQ-89343, CQ-87272)
* Nombres de archivo / localización:
   * Los nombres de archivo y carpeta con caracteres reservados no se gestionan correctamente. AEM Asegúrese de utilizar nombres de archivo y carpeta que se ajusten a los requisitos de la. (CQ-93361, CQ-93308, CQ-89276, CQ-4217183)
   * Algunas aplicaciones, como Adobe Illustrator AEM, pueden crear archivos con nombres no admitidos en los archivos de datos de la aplicación de la aplicación de la aplicación de tipo de archivo. Por ejemplo, agregar `Converted` después de convertir un archivo, lo que impide que se cargue. (CQ-4216985)
   * Assets con nombres internacionales puede aparecer y desaparecer cada pocos segundos.
* Proteger y desproteger:
   * Un recurso desprotegido por un usuario no se puede abrir para otro usuario, ni mediante la acción Abrir de la interfaz de usuario táctil ni directamente en el escritorio. Algunas aplicaciones pueden informarlo como bloqueado, pero también dañado o incluso colgado al intentar abrir. (CQ-4199234)
   * Cambiar archivos simultáneamente por varios usuarios puede causar que se pierdan algunas modificaciones. La solución consiste en utilizar la funcionalidad de protección y desprotección para evitar que varios usuarios cambien el mismo archivo. (CQ-97035)
   * Algunas aplicaciones no admiten correctamente el indicador de solo lectura, lo que permite al usuario guardar un archivo que otro usuario ha desprotegido. El archivo modificado no se transferirá hasta que el otro usuario lo registre. AEM Ambas modificaciones están disponibles en los recursos en forma de versiones diferentes del recurso. (CQ-89551, CQ-87572, CQ-89615)
   * Los estados de cierre y solo lectura se informan de forma independiente en el Buscador. Este método genera dos iconos de bloqueo cuando un usuario desprotege un recurso. (CQ-89507)
* Integración de Finder:
   * Al arrastrar y soltar archivos grandes, el Finder podría agotar el tiempo de espera mientras los archivos se transfieren en segundo plano. Este retraso genera un `Error - 36`. La solución consiste en arrastrar y soltar o abrir el recurso de nuevo. (CQ-4219628)
   * La recarga manual de carpetas no siempre funciona. Solución alternativa: espere treinta segundos para que la carpeta se actualice automáticamente. (CQ-97389)
   * Más información del recurso... se limita a selecciones de un solo archivo. (CQ-89542, CQ-87656)
   * Abrir en AEM Assets... está limitado a selecciones de carpeta y un solo archivo. (CQ-83382)
   * Error al cambiar el nombre de recursos que no tienen extensión. (CQ-4218971)
* Funcionalidad Copiar/Pegar: La opción Pegar está disponible cuando no se ha copiado ningún recurso en el portapapeles.
* Windows:
   * Los archivos con secuencias de datos alternativas (ADS) sólo son totalmente compatibles con NTFS. Al copiar archivos en el recurso compartido WebDAV a través de la aplicación de escritorio, un cuadro de diálogo de precaución advierte que algunas propiedades de archivo no se pueden transferir a la nueva ubicación. Esta advertencia suele ser correcta porque las propiedades solo son relevantes para una aplicación concreta en el escritorio del usuario y no tienen nada que ver con el contenido real del archivo. (CQ-103770) (Win)
   * El usuario que utiliza la aplicación de escritorio en Windows debe ser el que la instale. (CQ-4216389) (Win)
   * La aplicación puede bloquearse al seleccionar la opción [!UICONTROL Retry] en una carga fallida. Este bloqueo puede producirse en determinadas circunstancias después de reanudar la carga por lotes cuando se desconecta. (CQ-4251884) (Win)

## Recursos útiles {#helpful-resources}

* AEM [Documentación de](https://experienceleague.adobe.com/es/docs)
* [AEM Uso de la aplicación de escritorio v1.x](use-app-v1.md)
* [AEM Prácticas recomendadas para la aplicación de escritorio v1.x](best-practices-for-v1.md)

## Matriz de compatibilidad y requisitos previos {#compatibilitymatrix}

AEM AEM La aplicación de escritorio de funciona con varias versiones de la aplicación de escritorio de. Consulte la matriz de compatibilidad para ver las versiones compatibles.

| Versión | Revisión | Fecha de lanzamiento | Compatibilidad |
|--- |--- |--- |--- |
| 1,10 | 1.10.0.3 (Mac y Win) | sábado, 31 de agosto de 2018 | AEM AEM AEM AEM AEM.5; 6.4 SP1; 6.3 SP2; 6.2 SP1 CFP2+; 6.1 SP2 CFP7+ |
| 1,9 | 1.9.1.1 (Mac y Win) | 21 de junio de 2018 | AEM AEM AEM AEM.4; 6.3 SP1; 6.2 SP1 CFP2+; 6.1 SP2 CFP7+ |
| 1.8 | 1.8.1.0 (Mac y Win) | jueves, 28 de marzo de 2018 | AEM AEM AEM AEM.4; 6.3 SP1; 6.2 SP1 CFP2+; 6.1 SP2 CFP7+ |
| 1,7 | 1.7.0.3 (Mac y Win) | jueves, 10 de enero de 2018 | AEM AEM AEM 6.3 SP1; 6.2 SP1 CFP2+; 6.1 SP2 CFP7+ |
