---
title: Prácticas recomendadas para la aplicación de escritorio v1.10
description: Funcionalidades clave y uso recomendado de  [!DNL Adobe Experience Manager] aplicación de escritorio versión 1.10.
exl-id: 5de06b33-c05c-47eb-b884-408b6f9afc94
TQID: https://experienceleague.adobe.com/5r3NDLi2KQXMNH1s4hxfLlBzqmEisKTynSUFTVANwkU
product_v2: id: d09181b5-a36a-43de-ba01-36641440bc43id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2: id: da0dfbce-df02-4f8b-b32d-a4e3b1d05085
subfeature_v2: id: d18d21f5-ea10-400d-a1f0-a2071ad38419
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: a004cc84-67b9-4a33-a3a7-8ec7273ef4dcid: d095671a-1355-40aa-8b5f-06c33c68080bid: da3860b0-d637-47df-bef0-273751180266
source-git-commit: 6427cf5cb782d62b7335cfb7e3fa6b4189ac72d2
workflow-type: tm+mt
source-wordcount: 1721
ht-degree: 0%

---

# Prácticas recomendadas para la aplicación de escritorio de AEM v1.10 {#aem-desktop-app-best-practices}

## Información general {#overview}

La aplicación de escritorio [!DNL Adobe Experience Manager] vincula su solución de administración de activos digitales (DAM) con su escritorio para que pueda abrir los archivos disponibles en la interfaz de usuario web de AEM directamente en el escritorio. Si ha guardado un recurso desde el escritorio, se cargará en AEM en la ubicación adecuada.

La aplicación de escritorio de AEM elimina las posibilidades de actualizar copias locales incorrectas o de actualizar un recurso incorrecto en AEM. El flujo de trabajo fácil de usar de la aplicación de escritorio se habilita mediante la tecnología de uso compartido de red que proporcionan los sistemas operativos de escritorio.

La aplicación de escritorio monta el repositorio de AEM Assets como un recurso compartido de red en el escritorio. Por lo tanto, las carpetas y archivos aparecen como si fueran locales. Sin embargo, no se recomienda realizar operaciones de administración de recursos digitales directamente desde el escritorio en el recurso compartido de red montado en Finder o Explorer. En su lugar, Adobe recomienda utilizar la interfaz de usuario web de AEM Assets para realizar operaciones como copiar o mover un gran número de recursos.

>[!NOTE]
>
>Antes de leer este documento, puede revisar las [prácticas recomendadas generales de integración de AEM y Creative Cloud](https://experienceleague.adobe.com/es/docs/experience-manager-65/content/assets/administer/aem-cc-integration-best-practices) para obtener una descripción general de nivel superior del tema.

## Arquitectura de aplicación de escritorio de AEM {#aem-desktop-app-architecture}

La aplicación de escritorio de AEM utiliza recursos compartidos de red WebDAV (Windows) o SMB (Mac) para montar recursos compartidos de red. El recurso compartido de red montado es solo local. La aplicación de escritorio de AEM intercepta las llamadas (abre, lee y escribe) y proporciona almacenamiento en caché local adicional. Traduce llamadas remotas al servidor de AEM Assets para solicitudes HTTP de AEM optimizadas. El diagrama siguiente muestra la arquitectura de la aplicación de escritorio de AEM.

![Arquitectura de la aplicación de escritorio de AEM](assets/arch_v1.png)

*Figura: arquitectura de la aplicación de escritorio*

Cuando se guarda un archivo, el almacenamiento en caché adicional durante la escritura garantiza que se almacene localmente primero, lo que permite al usuario evitar esperar a la transferencia de red. A continuación, después de un retraso predefinido (30 segundos), el archivo se carga en AEM en segundo plano y, después, el recurso se carga en AEM. La aplicación de escritorio de AEM proporciona una interfaz de usuario para monitorizar el estado de las cargas de archivos en segundo plano.

## Uso recomendado de la aplicación de escritorio de AEM {#recommended-use-of-aem-desktop-app}

Las funciones clave de la aplicación de escritorio de AEM incluyen:

* **Abrir archivos desde la interfaz de usuario web de AEM Assets en el escritorio**. Desde la interfaz de usuario web, puede mostrar recursos en el escritorio (en Finder, Explorer) o abrir un recurso mediante una aplicación de escritorio.

* **Desproteger y proteger**. Assets se puede desproteger para editarlo y se marcan como bloqueados para el usuario en los AEM Assets. Después de la edición, el recurso se puede registrar para desbloquearlo.

* **Guardar cambios en los archivos**. Cualquier cambio que guarde en el archivo en el recurso compartido de red se cargará automáticamente en AEM y se creará una nueva versión.

* **Colocar recursos vinculados en otros documentos**. En aplicaciones como Creative Cloud ([!DNL Adobe Photoshop], [!DNL Adobe InDesign] y [!DNL Adobe Illustrator]), puede colocar un archivo externo como vínculo. Por ejemplo, puede colocar una imagen en un documento de InDesign. En este caso, el montaje del recurso compartido de red le permite examinar y seleccionar recursos de AEM para su colocación. La colocación de archivos vinculados también funciona en algunas aplicaciones que no son de Adobe, como MS® Office.

* **Resolución de referencia en AEM**. Si tanto los archivos colocados como los archivos principales con vínculo se almacenan en AEM, puede proporcionar automáticamente información del lado del servidor acerca de las referencias de recursos.

* **Acceda al recurso desde el escritorio**. En el recurso compartido de red montado, un menú contextual proporciona un cuadro de diálogo [!UICONTROL More Info] (vista previa más grande, metadatos clave) y la capacidad de abrir un recurso en la interfaz de usuario de AEM.

* **Cargando carpetas jerárquicas de gran tamaño en lotes**. Si usa la opción **Crear** > **Carga de carpetas** en la interfaz de usuario de AEM para cargar recursos, la aplicación de escritorio de AEM carga la jerarquía de carpetas seleccionada en AEM en segundo plano. El progreso de carga se monitoriza con una interfaz de usuario dedicada en la aplicación de escritorio.

## Uso inapropiado de la aplicación de escritorio de AEM {#inappropriate-use-of-aem-desktop-app}

* No utilice la aplicación de escritorio de AEM para administrar recursos desde el escritorio. La aplicación de escritorio de AEM no se creó como reemplazo de las unidades de red. En su lugar, utilice las siguientes funciones:

   * IU web de AEM Assets para la administración de recursos digitales (buscar o compartir recursos, metadatos y copiar o mover).

   * Aplicación de escritorio de AEM [!UICONTROL Folder Upload] para cargar carpetas jerárquicas y de gran tamaño.

* No considere la aplicación de escritorio de AEM como un cliente de &quot;sincronización de escritorio&quot; para AEM Assets. La principal ventaja de la aplicación de escritorio de AEM aquí es que proporciona acceso &quot;virtual&quot; a todo el repositorio y las aplicaciones de sincronización de escritorio generalmente solo sincronizan recursos que pertenecen a un usuario. La aplicación de escritorio de AEM proporciona cierto nivel de almacenamiento en caché y carga en segundo plano; aun así, funciona de forma muy diferente a las aplicaciones de &quot;sincronización&quot; típicas, como la aplicación de escritorio de Adobe Creative Cloud o Microsoft OneDrive.

* No utilice las unidades de red de la aplicación de escritorio de AEM para guardar recursos con frecuencia. Todas las operaciones de guardado se transmiten a los AEM Assets. Por lo tanto, no es práctico realizar operaciones de edición intensivas directamente en el repositorio de AEM Assets montado. La edición de un recurso directamente en el repositorio montado saturará la cronología del recurso con versiones irrelevantes e impondrá costes generales adicionales al servidor.

* No utilice la aplicación de escritorio de AEM para migrar grandes cantidades de datos de una instancia de AEM a otra. Consulte la [Guía de migración](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/assets/administer/assets-migration-guide) para planificar y ejecutar migraciones de recursos. Por el contrario, la aplicación de escritorio [admite la carga masiva](use-app-v1.md#bulkupload) de un gran número de recursos por primera vez en [!DNL Adobe Experience Manager].

## Recomendaciones para casos de uso seleccionados {#recommendations-for-selected-use-cases}

### Acceso a los recursos para usuarios creativos {#access-to-assets-for-creative-users}

La aplicación de escritorio de AEM proporciona acceso virtual a todo el repositorio de DAM, y puede resultar complicado para los usuarios creativos encontrar y acceder a los recursos adecuados en su escritorio. Siga estos procedimientos recomendados para simplificarlos.

* Utilice las funciones de colaboración de la interfaz de usuario web de AEM Assets para proporcionar un acceso más directo a los recursos adecuados para el usuario creativo. Algunas de ellas son compartir carpetas o colecciones, proporcionar colecciones inteligentes (búsquedas guardadas) o enviar notificaciones con punteros a los recursos adecuados. A continuación, el usuario de Creative puede utilizar las acciones del escritorio en la interfaz de usuario web para acceder rápidamente a estos recursos en su escritorio.

* Considere los permisos adecuados para los recursos (control de acceso) para simplificar la vista en el repositorio de DAM para los usuarios creativos, limitando básicamente su acceso a solo los recursos que necesitan o en los que están interesados:

   * Es posible que se denieguen ciertas áreas no relevantes para los usuarios creativos a sus grupos de usuarios para quitarlas de su vista, también en el escritorio.

   * La mayoría de los recursos de DAM son finales y no están pensados para cambiarlos: estos recursos deben ser de solo lectura para los usuarios creativos.

   * Solo los recursos que requieran cambios o retoques deben estar habilitados para escritura para los usuarios creativos. Algunas organizaciones utilizan los proyectos de AEM y las carpetas que crean para alojar recursos que aún están sujetos a cambios.

### Buscando recursos {#searching-assets}

Para buscar un archivo que desee abrir en el escritorio:

* Utilice la interfaz de usuario web de AEM Assets para localizar el recurso. La búsqueda en AEM Assets no solo es potente (facetas de búsqueda, búsquedas guardadas), sino que también proporciona funciones adicionales para encontrar el recurso adecuado. Estos incluyen filtros adicionales, como la capacidad de buscar recursos en función del estado (aprobación, caducidad), colecciones, tareas, notificaciones y el uso compartido de carpetas/colecciones con otros usuarios/grupos.

* Una vez localizado el recurso, utilice las acciones del escritorio en la interfaz de usuario de AEM para acceder al recurso en el escritorio.

### Actualizar recursos abiertos mediante la aplicación de escritorio de AEM {#updating-assets-opened-using-aem-desktop-app}

Si edita un recurso directamente en la ubicación asignada desde los AEM Assets a un recurso compartido de red local, el recurso se cargará en AEM cada vez que lo guarde en el equipo de escritorio. Además, AEM crea una versión y genera representaciones.

Si un recurso almacenado en AEM necesita una actualización:

* Para **actualizaciones menores**, como solicitudes de retoque menores en el proceso de aprobación:

   * Desproteja el archivo y ábralo en el escritorio.

   * Actualice el archivo.

   * Guarde la versión actualizada. El recurso se actualiza y la cronología muestra la versión original para la comparación.

* Para **actualizaciones importantes**, como una solicitud de cambio que requiere un pequeño ciclo de trabajo en curso creativo:

   * Utilice la opción Mostrar para abrir la carpeta correspondiente en el escritorio.

   * Copie el archivo en una carpeta de trabajo en curso fuera del recurso compartido de AEM Assets asignado (por ejemplo, copie el archivo en una carpeta sincronizada con la aplicación de escritorio de Adobe Creative Cloud).

   * Trabaje en el archivo y guárdelo intermitentemente. Los cambios no se guardan en los AEM Assets.

   * Una vez completadas las ediciones, mueva, copie o guarde el archivo asignado desde AEM para cargarlo como una nueva versión.

## Rendimiento de red {#network-performance}

Una buena experiencia de usuario con la aplicación de escritorio de AEM depende de una conectividad de red estable y de un servidor bien ajustado, especialmente para cargar y actualizar recursos. Estas recomendaciones son para los equipos de red/TI de las organizaciones.

### Consideraciones de red {#network-considerations}

Para comprender las prácticas recomendadas sobre la configuración de la red de los AEM Assets, vaya al documento [Cómo migrar recursos en lote](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/assets/administer/assets-migration-guide). Algunos de los aspectos importantes que ayudan a optimizar la experiencia de la aplicación de escritorio de AEM para los usuarios son:

* **Use un Dispatcher correctamente configurado**. Use AEM Dispatcher para obtener seguridad adicional y asegúrese de que esté configurado para la conexión de la aplicación de escritorio de [AEM a AEM detrás de un Dispatcher](install-configure-app-v1.md#connect-to-an-aem-instance-behind-a-dispatcher)

* **Ahorre ancho de banda**. Considere la posibilidad de desactivar la previsualización de iconos en Finder en Mac al explorar el repositorio montado mediante Finder. El Finder solicita a cada archivo que genere una vista previa y hace que la aplicación de escritorio descargue y almacene en caché el recurso localmente. Al ahorrar ancho de banda, también disminuye la experiencia del usuario para los usuarios en el escritorio, por lo que debe hacerse cuando se trabaja en repositorios con recursos grandes o ancho de banda limitado.

>[!NOTE]
>
>Para desactivar las vistas previas de iconos, en el Finder ve a [!UICONTROL View], selecciona [!UICONTROL View Options] y, a continuación, desmarca la opción [!UICONTROL Show icon preview]. Esto solo funciona para la carpeta actual: para convertirla en predeterminada, haga clic en la opción [!UICONTROL Use as default] en el mismo cuadro de diálogo.

### Optimización del rendimiento del servidor {#optimizing-server-performance}

Para comprender cómo se debe optimizar el rendimiento del servidor de AEM Assets, vaya a [Guía de optimización del rendimiento de los AEM Assets](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/assets/administer/performance-tuning-guidelines). Algunos de los aspectos importantes del rendimiento del servidor para la aplicación de escritorio de AEM son la optimización de la configuración del flujo de trabajo para que funcione bien en las cargas de recursos:

* **Carga de recursos con mayor rendimiento**. Configure el modelo de flujo de trabajo [AEM Asset Update para que sea transitorio](https://experienceleague.adobe.com/en/docs/experience-manager-65/content/assets/administer/performance-tuning-guidelines).

* **Limitar CPU de servidor para las cargas**. Asegúrese de que el parámetro de trabajos de flujo de trabajo en paralelo máximo esté configurado correctamente para que las cargas no agoten toda la CPU.
