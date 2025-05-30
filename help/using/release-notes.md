---
title: '[!DNL Adobe Experience Manager] notas de la versión de la aplicación de escritorio'
description: Detalles de la versión, mejoras, nuevas características, compatibilidad y vínculos de descarga para la aplicación de escritorio  [!DNL Adobe Experience Manager] iOS.
mini-toc-levels: 1
feature: Desktop App,Release Information
exl-id: e058e7a2-fcc8-4ad1-899e-20695db6bc72
source-git-commit: b5dace65444ca15d09ec8648deb4c262415f40cf
workflow-type: tm+mt
source-wordcount: '2195'
ht-degree: 10%

---

# [!DNL Adobe Experience Manager] notas de la versión de la aplicación de escritorio {#release-notes-v2}

A continuación, encontrará información de la última versión de la aplicación de escritorio, 2.3.3. La fecha de la versión es el 16 de mayo de 2025.

La versión más reciente de la aplicación de escritorio incluye las siguientes correcciones de errores y mejoras:

* Puede cargar los recursos recién creados desde el equipo local a AEM, donde se almacena el repositorio central, y verlos en la aplicación de escritorio.
* La función de actualización automática actualiza automáticamente el contenido en tiempo real, lo que garantiza que siempre vea la información más reciente sin volver a cargar manualmente la página y obtener la lista de recursos actualizados.
* La función de anclar o desanclar carpetas permite mantener carpetas importantes de fácil acceso anclándolas o desordenando la vista desanclándolas cuando ya no sean necesarias.
* La función Cambiar el nombre del título le permite actualizar o modificar fácilmente el título de un recurso, lo que le ayuda a mantener los nombres precisos y organizados a medida que evoluciona el contenido.
* Puede conservar el archivo original y realizar cambios en uno similar duplicando archivos en ubicaciones locales y de la nube mediante la operación de duplicación de archivos.
* La función de protección y desprotección permite administrar el acceso a archivos bloqueando un archivo para su edición (desprotección) y guardando los cambios al tiempo que lo hace disponible para otros (protección).
* Puede ver, descargar y examinar colecciones.
* Puede asignar metadatos al crear una carpeta nueva.

Las **versiones compatibles de [!DNL Experience Manager]** son:

* [!DNL Experience Manager] como [!DNL Cloud Service]. Ver [notas de la versión](https://experienceleague.adobe.com/es/docs/experience-manager-cloud-service/content/release-notes/home).
* [!DNL Experience Manager] 6.5.0 o posterior, en Adobe Managed Services (AMS) o local. Ver [notas de la versión del Service Pack](https://experienceleague.adobe.com/es/docs/experience-manager-65/content/release-notes/release-notes).

La aplicación de escritorio [!DNL Adobe Experience Manager] está disponible para los siguientes **sistemas operativos**:

* macOS X 10.14 o posterior, con las últimas correcciones de errores.
* Windows 10 con los últimos paquetes de servicio y correcciones de errores.

Hay dos versiones del programa de instalación de Windows disponibles para AEM Desktop App versión 2.3.1 y versiones posteriores. El instalador base instala AEM Desktop App en el directorio local de datos de la aplicación del usuario. Adobe recomienda este proceso de instalación para la mayoría de sus usuarios. También hay disponible un instalador de Enterprise Windows que instala AEM Desktop App en el directorio compartido Archivos de programa. Estos dos instaladores instalan la misma versión de la aplicación de escritorio de AEM, sin diferencias de funcionalidad.

Las **URL de descarga** para el sistema operativo admitido son:

| Sistema operativo | [!DNL Experience Manager] as a [!DNL Cloud Service] | [!DNL Experience Manager] 6.x |
|---|---|---|
| macOS (versión 2.3.3) | [Vínculo de descarga](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-desktop-app/aem-desktop-osx-x64-2.3.3.dmg) | [Vínculo de descarga](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-osx-x64-2.3.3.dmg) |
| macOS Apple Silicon (M1) (v2.3.3) | [Vínculo de descarga](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-desktop-app/aem-desktop-osx-arm64-2.3.3.dmg) | [Vínculo de descarga](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-osx-arm64-2.3.3.dmg) |
| Windows de 64 bits (v2.3.3) | [Vínculo de descarga](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-desktop-app/aem-desktop-win-x64-2.3.3.exe) | [Vínculo de descarga](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-win-x64-2.3.3.exe) |
| Windows Enterprise de 64 bits (v2.3.3) | [Vínculo de descarga](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-desktop-app/aem-desktop-win-x64-2.3.3.msi) | [Vínculo de descarga](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-win-x64-2.3.3.msi) |
| macOS (v2.3.1) | [Vínculo de descarga](https://nam04.safelinks.protection.outlook.com/?url=https%3A%2F%2Fexperience.adobe.com%2F%23%2Fdownloads%2Fcontent%2Fsoftware-distribution%2Fen%2Faemcloud.html%3Fpackage%3D%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faemcloud%2Fpublic%2Faem-desktop-app%2Faem-desktop-osx-x64-2.3.1.dmg&amp;data=05%7C02%7Canujm%40adobe.com%7Cfcf599743bd649c5cd7308dcab9ea5cd%7Cfa7b1b5a7b34438794aed2c178decee1%7C0%7C0%7C638573945081954149%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C0%7C%7C%7C&amp;sdata=mwSX5ilZL0he2raIx8t5ecQ%2FWuizky4MpcCXX3mEN38%3D&amp;reserved=0) | [Vínculo de descarga](https://nam04.safelinks.protection.outlook.com/?url=https%3A%2F%2Fexperience.adobe.com%2F%23%2Fdownloads%2Fcontent%2Fsoftware-distribution%2Fen%2Faem.html%3Fpackage%3D%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Fadobe%2Fpackages%2Fadobe%2Faem-desktop-app%2Faem-desktop-osx-x64-2.3.1.dmg&amp;data=05%7C02%7Canujm%40adobe.com%7Cfcf599743bd649c5cd7308dcab9ea5cd%7Cfa7b1b5a7b34438794aed2c178decee1%7C0%7C0%7C638573945081981239%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C0%7C%7C%7C&amp;sdata=LJH3OCFq7yRykN4wU8HN9%2FBXC%2BjfXLJH4QizeFZfRHE%3D&amp;reserved=0) |
| macOS Apple Silicon (M1) (v2.3.1) | [Vínculo de descarga](https://nam04.safelinks.protection.outlook.com/?url=https%3A%2F%2Fexperience.adobe.com%2F%23%2Fdownloads%2Fcontent%2Fsoftware-distribution%2Fen%2Faemcloud.html%3Fpackage%3D%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faemcloud%2Fpublic%2Faem-desktop-app%2Faem-desktop-osx-arm64-2.3.1.dmg&amp;data=05%7C02%7Canujm%40adobe.com%7Cfcf599743bd649c5cd7308dcab9ea5cd%7Cfa7b1b5a7b34438794aed2c178decee1%7C0%7C0%7C638573945081965822%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C0%7C%7C%7C&amp;sdata=2YENn0tDduiucogClt6aBZHDOE6dbzBdigq8VQawIO0%3D&amp;reserved=0) | [Vínculo de descarga](https://nam04.safelinks.protection.outlook.com/?url=https%3A%2F%2Fexperience.adobe.com%2F%23%2Fdownloads%2Fcontent%2Fsoftware-distribution%2Fen%2Faem.html%3Fpackage%3D%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Fadobe%2Fpackages%2Fadobe%2Faem-desktop-app%2Faem-desktop-osx-arm64-2.3.1.dmg&amp;data=05%7C02%7Canujm%40adobe.com%7Cfcf599743bd649c5cd7308dcab9ea5cd%7Cfa7b1b5a7b34438794aed2c178decee1%7C0%7C0%7C638573945081986151%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C0%7C%7C%7C&amp;sdata=jCepldg4dMej0%2BrK2mUonXwqsWL8ksE8%2BLMSgsH9qTA%3D&amp;reserved=0) |
| Windows de 64 bits (v2.3.1) | [Vínculo de descarga](https://nam04.safelinks.protection.outlook.com/?url=https%3A%2F%2Fexperience.adobe.com%2F%23%2Fdownloads%2Fcontent%2Fsoftware-distribution%2Fen%2Faemcloud.html%3Fpackage%3D%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faemcloud%2Fpublic%2Faem-desktop-app%2Faem-desktop-win-x64-2.3.1.exe&amp;data=05%7C02%7Canujm%40adobe.com%7Cfcf599743bd649c5cd7308dcab9ea5cd%7Cfa7b1b5a7b34438794aed2c178decee1%7C0%7C0%7C638573945081970892%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C0%7C%7C%7C&amp;sdata=sRn2UWW%2Bi7SMEvSO74ZGGvJ40vHh1KhLc7zAfKc37Es%3D&amp;reserved=0) | [Vínculo de descarga](https://nam04.safelinks.protection.outlook.com/?url=https%3A%2F%2Fexperience.adobe.com%2F%23%2Fdownloads%2Fcontent%2Fsoftware-distribution%2Fen%2Faem.html%3Fpackage%3D%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Fadobe%2Fpackages%2Fadobe%2Faem-desktop-app%2Faem-desktop-win-x64-2.3.1.exe&amp;data=05%7C02%7Canujm%40adobe.com%7Cfcf599743bd649c5cd7308dcab9ea5cd%7Cfa7b1b5a7b34438794aed2c178decee1%7C0%7C0%7C638573945081991004%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C0%7C%7C%7C&amp;sdata=aQWZtEK%2F3cWX8n8Au%2FwZ5Zd9xPVo5phvk%2FuF%2Be0HRrE%3D&amp;reserved=0) |
| Windows Enterprise de 64 bits (v2.3.1) | [Vínculo de descarga](https://nam04.safelinks.protection.outlook.com/?url=https%3A%2F%2Fexperience.adobe.com%2F%23%2Fdownloads%2Fcontent%2Fsoftware-distribution%2Fen%2Faemcloud.html%3Fpackage%3D%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faemcloud%2Fpublic%2Faem-desktop-app%2Faem-desktop-win-x64-2.3.1.msi&amp;data=05%7C02%7Canujm%40adobe.com%7Cfcf599743bd649c5cd7308dcab9ea5cd%7Cfa7b1b5a7b34438794aed2c178decee1%7C0%7C0%7C638573945081976350%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C0%7C%7C%7C&amp;sdata=v9C0sLDSkuL%2FMIyae2WkbitJPVgSlAw2BqcaH5Im0uw%3D&amp;reserved=0) | [Vínculo de descarga](https://nam04.safelinks.protection.outlook.com/?url=https%3A%2F%2Fexperience.adobe.com%2F%23%2Fdownloads%2Fcontent%2Fsoftware-distribution%2Fen%2Faem.html%3Fpackage%3D%2Fcontent%2Fsoftware-distribution%2Fen%2Fdetails.html%2Fcontent%2Fdam%2Faem%2Fpublic%2Fadobe%2Fpackages%2Fadobe%2Faem-desktop-app%2Faem-desktop-win-x64-2.3.1.msi&amp;data=05%7C02%7Canujm%40adobe.com%7Cfcf599743bd649c5cd7308dcab9ea5cd%7Cfa7b1b5a7b34438794aed2c178decee1%7C0%7C0%7C638573945081995827%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C0%7C%7C%7C&amp;sdata=2btCh0aIrUBiyeG37K9YorvzTeIJOggbq%2FRauUMn4LY%3D&amp;reserved=0) |
| macOS (v2.3.0) | [Vínculo de descarga](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-desktop-app/aem-desktop-osx-x64-2.3.0.dmg) | [Vínculo de descarga](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-osx-x64-2.3.0.dmg) |
| macOS Apple Silicon (M1) (v2.3.0) | [Vínculo de descarga](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-desktop-app/aem-desktop-osx-arm64-2.3.0.dmg) | [Vínculo de descarga](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-osx-arm64-2.3.0.dmg) |
| Windows de 64 bits (v2.3.0) | [Vínculo de descarga](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-desktop-app/aem-desktop-win-x64-2.3.0.exe) | [Vínculo de descarga](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-win-x64-2.3.0.exe) |
| macOS (v2.2.2) | [Vínculo de descarga](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-desktop-app/aem-desktop-osx-x64-2.2.2.dmg) | [Vínculo de descarga](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-osx-x64-2.2.2.dmg) |
| macOS Apple Silicon (M1) (v2.2.2) | [Vínculo de descarga](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-desktop-app/aem-desktop-osx-arm64-2.2.2.dmg) | [Vínculo de descarga](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-osx-arm64-2.2.2.dmg) |
| Windows de 64 bits (v2.2.2) | [Vínculo de descarga](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-desktop-app/aem-desktop-win-x64-2.2.2.exe) | [Vínculo de descarga](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-win-x64-2.2.2.exe) |
| macOS (v2.2.1) | [Vínculo de descarga](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-desktop-app/aem-desktop-osx-x64-2.2.1.dmg) | [Vínculo de descarga](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-osx-x64-2.2.1.dmg) |
| macOS Apple Silicon (M1) (v2.2.1) | [Vínculo de descarga](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-desktop-app/aem-desktop-osx-arm64-2.2.1.dmg) | [Vínculo de descarga](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-osx-arm64-2.2.1.dmg) |
| Windows de 64 bits (v2.2.1) | [Vínculo de descarga](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-desktop-app/aem-desktop-win-x64-2.2.1.exe) | [Vínculo de descarga](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-win-x64-2.2.1.exe) |
| macOS (v2.2.0) | [Vínculo de descarga](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-desktop-app/aem-desktop-osx-x64-2.2.0.dmg) | [Vínculo de descarga](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-osx-x64-2.2.0.dmg) |
| macOS Apple Silicon (M1) (v2.2.0) | [Vínculo de descarga](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-desktop-app/aem-desktop-osx-arm64-2.2.0.dmg) | [Vínculo de descarga](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-osx-arm64-2.2.0.dmg) |
| Windows de 64 bits (v2.2.0) | [Vínculo de descarga](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-desktop-app/aem-desktop-win-x64-2.2.0.exe) | [Vínculo de descarga](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-win-x64-2.2.0.exe) |
| macOS (v2.1.5.0) | [Vínculo de descarga](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-desktop-app/aem-desktop-osx-2.1.5.0.dmg) | [Vínculo de descarga](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-osx-2.1.5.0.dmg) |
| Windows de 64 bits (v2.1.5.0) | [Vínculo de descarga](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-desktop-app/aem-desktop-win64-2.1.5.0.exe) | [Vínculo de descarga](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-win64-2.1.5.0.exe) |
| Windows de 32 bits (v2.1.5.0) | [Vínculo de descarga](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-desktop-app/aem-desktop-win32-2.1.5.0.exe) | [Vínculo de descarga](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-win32-2.1.5.0.exe) |
| macOS (v2.1.4.0) | [Vínculo de descarga](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-desktop-app/aem-desktop-osx-2.1.4.0.dmg) | [Vínculo de descarga](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-osx-2.1.4.0.dmg) |
| Windows de 64 bits (v2.1.4.0) | [Vínculo de descarga](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-desktop-app/aem-desktop-win64-2.1.4.0.exe) | [Vínculo de descarga](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-win64-2.1.4.0.exe) |
| Windows de 32 bits (v2.1.4.0) | [Vínculo de descarga](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-desktop-app/aem-desktop-win32-2.1.4.0.exe) | [Vínculo de descarga](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-win32-2.1.4.0.exe) |
| macOS (v2.1.3.4) | [Vínculo de descarga](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-desktop-app/aem-desktop-osx-2.1.3.4.dmg) | [Vínculo de descarga](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-osx-2.1.3.4.dmg) |
| Windows de 64 bits (v2.1.3.4) | [Vínculo de descarga](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-desktop-app/aem-desktop-win64-2.1.3.4.exe) | [Vínculo de descarga](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-win64-2.1.3.4.exe) |
| Windows de 32 bits (v2.1.3.1) | [Vínculo de descarga](https://experience.adobe.com/#/downloads/content/software-distribution/en/aemcloud.html?package=/content/software-distribution/en/details.html/content/dam/aemcloud/public/aem-desktop-app/aem-desktop-win32-2.1.3.1.exe) | [Vínculo de descarga](https://experience.adobe.com/#/downloads/content/software-distribution/en/aem.html?package=/content/software-distribution/en/details.html/content/dam/aem/public/adobe/packages/adobe/aem-desktop-app/aem-desktop-win32-2.1.3.1.exe) |

## Compatibilidad con diferentes tipos de recursos y archivos {#support-for-file-types}

La aplicación admite recursos almacenados en [!DNL Experience Manager] que representan archivos binarios para sus operaciones básicas. La apertura de archivos en la aplicación de escritorio nativa depende de la asociación de sistema operativo de los tipos de archivo específicos, como PNG o JPG, a aplicaciones específicas, como Vista previa de Mac o Adobe Photoshop.

Algunos tipos de archivo admiten la colocación de recursos vinculados en el archivo binario. La aplicación descarga previamente los recursos vinculados si el recurso está presente en el repositorio [!DNL Experience Manager] cuando estos archivos binarios se abren con la aplicación de escritorio. Los tipos de archivo admitidos actualmente son:

* [!DNL Adobe InDesign] archivos (formato INDD)
* [!DNL Adobe Illustrator] archivos (formato AI)
* [!DNL Adobe Photoshop] archivos (formato PS)

La característica es compatible con [!DNL Adobe Creative Cloud] versiones de 2018 y [!DNL Adobe Creative Cloud] 2019 de la aplicación anterior. La aplicación utiliza un método heurístico que busca la mejor coincidencia para asignar las rutas de escritorio locales de los recursos vinculados a las direcciones URL en el servidor [!DNL Experience Manager]. Se basa en algunos supuestos:

* Las rutas para colocar archivos en la aplicación nativa usan una ruta de escritorio global (desde el recurso compartido de red local que se muestra con la opción [!UICONTROL Reveal]).

* La aplicación nativa almacena las rutas en el registro XMP del archivo.

* [!DNL Experience Manager] ha extraído el registro de XMP con las rutas al registro de metadatos del recurso.

* Las rutas de acceso pueden coincidir con los recursos de [!DNL Experience Manager], es decir, los archivos colocados también se encuentran en [!DNL Experience Manager] bajo una ruta de acceso coincidente.

## Nuevas funciones, mejoras y correcciones de errores {#what-is-new}

Para obtener más información, consulte [Novedades de la versión 2.0](introduction.md#whats-new-v2).

**Actualizaciones en la aplicación v2.3.1**

* El nuevo instalador de Enterprise Windows instala la aplicación en Archivos de programa.
* Compatibilidad con **Autenticación básica** durante los inicios de sesión de AEM y SSO.
* Número configurable de recursos permitidos durante la operación de carga

**Actualizaciones en la aplicación v2.3.0**

* Se ha añadido compatibilidad con el inicio de sesión IMS. La integración de IMS permite a la aplicación de escritorio realizar la actualización del token de acceso automáticamente, lo que permite al usuario permanecer conectado durante un máximo de 14 días.

* Se ha mejorado la compatibilidad con los proxies corporativos y el filtrado web.

**Actualizaciones en la aplicación v2.2.2**

* (Solo Windows) La aplicación de escritorio muestra una pantalla en blanco después de instalar las versiones 2.2.0 y 2.2.1.

**Actualizaciones en la aplicación v2.2.1**

* La aplicación de escritorio muestra un mensaje de error de tiempo de espera de sesión al hacer clic en **[!UICONTROL Sign In]**.

* Problemas al acceder a la aplicación de escritorio v2.2.0 en macOS.

* La aplicación de escritorio muestra un mensaje de error al ordenar los recursos al hacer clic en **[!UICONTROL Edited Locally]**.

**Actualizaciones en la aplicación v2.2.0**

* Soporte para Apple Silicon (M1).

* Capacidad para recordar la cadena de conexión al iniciar sesión en la aplicación de escritorio.

**Actualizaciones en la aplicación v2.1.5.0**

* La aplicación de escritorio deja de responder al cargar archivos en una carpeta que contiene caracteres chinos (ASSETS-9237).

* La aplicación de escritorio de reemplaza los puntos con guiones en los nombres de archivo (ASSETS-10955).

**Actualizaciones en la aplicación v2.1.4.0**

La nueva versión de la aplicación ofrece correcciones de errores.

**Actualizaciones en la aplicación v2.1.3.4**

La nueva versión de la aplicación ofrece una corrección de errores.

**Actualizaciones en la aplicación v2.1.3.3**

La nueva versión de la aplicación ofrece una corrección de errores.

**Actualizaciones en la aplicación v2.1.3.2**

Esta versión de la aplicación ofrece una corrección de errores.

**Actualizaciones en la aplicación v2.1.3.1**

El error corregido en esta versión es:

* Las velocidades de carga y descarga de recursos han mejorado, incluso con recursos grandes. Esta versión corrigió un problema en el cual las cargas de recursos con [!DNL desktop app] fallaban a veces cuando se cargaban archivos muy grandes.

**Actualización en la aplicación v2.1.2.0**

* Se agrega una nueva opción a [!UICONTROL Clear Cookies] al menú principal de la aplicación. Ayuda con posibles problemas de inicio de sesión, por ejemplo al cambiar una conexión de un servidor a otro. Ver [borrar cookies antes de conectar](/help/using/troubleshoot.md#cannot-login-cookies-issue).

* Se ha agregado una nueva opción que, si se selecciona, permite a la aplicación cargar carpetas y archivos con nombres de nodo en [!DNL Adobe Experience Manager] que coincidan con los nombres de archivo y carpeta locales. Este proceso garantiza la coherencia entre los nombres locales y cargados.

  Este comportamiento es similar al comportamiento predeterminado en la versión 1 de la aplicación de escritorio. Mientras que en la versión actual, si la opción no está habilitada, los espacios en blanco y los caracteres `% ; # , + ? ^ { } "` de los nombres de carpeta se reemplazan con guiones en las rutas de carpeta. Además, los caracteres en mayúsculas se convierten en minúsculas en las rutas de carpetas. Sin embargo, en los nombres de archivo, los caracteres `# % { } ? &` se reemplazan por guiones; pero se conservan los espacios en blanco y las mayúsculas y minúsculas. Para obtener más información, consulte [Preferencias de la aplicación](/help/using/install-upgrade.md#set-preferences) y [Cargar y agregar nuevos recursos](/help/using/using.md#upload-and-add-new-assets-to-aem).

**Actualización en la aplicación v2.1.1.0**

* Una configuración avanzada permite que la aplicación emule el comportamiento de la aplicación v1.10 al cargar carpetas. En la versión 1.10, los nombres de nodo creados en el repositorio respetan los espacios y mayúsculas de los nombres de carpeta proporcionados por el usuario. En la versión 2.1, el comportamiento predeterminado no cambia: los espacios múltiples en los nombres de carpeta se sustituyen por guiones en el nombre del nodo del repositorio y los nombres de nodo se convierten a minúsculas. Ver [las preferencias de la aplicación](/help/using/install-upgrade.md#set-preferences).

**Actualización en la aplicación v2.1.0.0**

* Para cargar recursos, los usuarios ahora pueden arrastrar los archivos o carpetas a la interfaz de la aplicación, directamente desde el Explorador de Windows o el Buscador de Mac. Este proceso funciona además de la opción de carga disponible en la aplicación. Ver [cargar recursos](/help/using/using.md#upload-and-add-new-assets-to-aem) <!-- CQ-4309527 -->

**Actualización en la aplicación v2.0.3**

El error corregido en esta versión es:

* Se ha corregido el problema de inicio de sesión de los usuarios de la aplicación en Windows que intentaban acceder al repositorio DAM en [!DNL Adobe Experience Manager] 6.5.5.0.

**Actualizaciones en la aplicación v2.0.2**

Las correcciones de errores y actualizaciones son:

* La configuración de aceleración de carga ya está disponible para mejorar el rendimiento de carga. Cuando esta configuración está activada, la aplicación se carga más rápido usando más subprocesos locales de CPU y consume más recursos.

* Se carga un recurso cuando se corrigen los nombres de archivo o las rutas que contienen determinados caracteres GB18030. <!-- CQ-4283494 -->

* La opción Ordenar por relevancia está disponible después de cambiar a otro tipo de ordenación en los resultados de búsqueda. <!-- CQ-4286874 -->

* La aplicación de escritorio ahora enumera subcarpetas sin necesidad de una actualización explícita. <!-- CQ-4285711 -->

* (Windows) Se ha corregido un problema poco frecuente de interfaz de aplicación inutilizable en algunos equipos con Windows. Los usuarios no pueden hacer clic en la interfaz de la aplicación porque parece distorsionada con el área de clics de los elementos de la interfaz &quot;desplazada&quot; de lado. <!-- CQ-4280785 -->

**Actualizaciones en la aplicación v2.0.1**

Las correcciones de errores y actualizaciones son:

* Permitir que la opción configure el directorio `%Temp%` para que coincida con la ruta de acceso `%APPDATA%`. <!-- CQ-4282665 -->

* Permitir que los usuarios inicien sesión en el autor de [!DNL Experience Manager] mediante la autenticación SAML de Okta. <!-- CQ-4278134 -->

## Instrucciones de instalación {#installation-instructions-v2}

Para saber cómo instalar y configurar la aplicación, consulta [Instalar [!DNL Experience Manager] aplicación de escritorio](install-upgrade.md).

Si está actualizando desde una aplicación de escritorio [!DNL Experience Manager] anterior, debe seguir estas prácticas recomendadas para la transición que se enumeran en [actualizar desde la versión anterior](install-upgrade.md#upgrade-from-previous-version).

## Notas importantes sobre el funcionamiento de la aplicación {#how-app-works}

Es importante comprender lo siguiente sobre la aplicación y su funcionamiento.

* La aplicación proporciona control total sobre las operaciones que requieren la transferencia completa de archivos binarios de recursos desde y hacia [!DNL Experience Manager] (**Abrir**, **Editar**, **Cargar cambios** y **Cargar Assets**).

   * Si desea trabajar con el recurso en el escritorio, debe abrir, editar o descargar contenido en el mismo escritorio, ya sea de forma individual, en una carpeta o mediante selección múltiple.

   * Si desea realizar cambios locales en los recursos cargados en [!DNL Experience Manager], debe seleccionar [!UICONTROL Upload Changes], ya sea de forma individual o mediante selección múltiple.

   * La aplicación no es un &quot;cliente de sincronización&quot; que sincroniza recursos en el escritorio y en [!DNL Experience Manager].

   * La aplicación no proporciona un recurso compartido de red que asigne el repositorio [!DNL Experience Manager] como una estructura de carpetas virtuales.

* La aplicación muestra una lista de recursos que se basa en el estado del repositorio de Assets. Los archivos descargados localmente y posteriormente renombrados en los archivos locales o en la carpeta de caché no se muestran ni administran con la aplicación.

* Si la aplicación no muestra los resultados esperados, haga clic en el icono de actualización situado en la barra superior.

* El recurso compartido de red local, que se muestra cuando se usa la acción [!UICONTROL Reveal File], solo muestra los archivos (y carpetas) disponibles a nivel local. [!UICONTROL Reveal File] y [!UICONTROL Reveal Folder] descarga previamente los recursos para que se muestren los que son correctos en el recurso compartido de red local.

* El recurso compartido de red local SMB (Mac)/WebDAV (Win) se utiliza cuando una aplicación de Adobe Creative Cloud lee los archivos de recursos vinculados o colocados en un archivo nativo de la aplicación de Creative Cloud.

El diagrama siguiente ilustra el flujo de recursos y archivos desde la nube al sistema de archivos local y viceversa, cuando este proceso se inicia mediante las acciones del usuario.

![Flujo de recursos desde el servidor [!DNL Experience Manager] a las aplicaciones de escritorio nativas a través de la aplicación de escritorio](assets/da20_flow_diagram.png)

## Problemas conocidos {#known-issues-v2}

**Problemas de la interfaz de usuario:**

* A veces, la interfaz de la aplicación de escritorio puede quedar en blanco. Haga clic con el botón derecho y haga clic en [!UICONTROL Refresh] para volver a cargar la aplicación. Después de esta actualización, debe comenzar en la raíz del repositorio de DAM. Se conservan las actualizaciones o los estados de los recursos. <!-- CQ-4270267 -->

* Dificultad al desplazarse por las carpetas o los resultados de búsqueda sin un panel de seguimiento o un puntero de ratón. La barra de desplazamiento no aparece con dispositivos de ratón sin rueda. <!-- CQ-4269947 -->

* De forma poco frecuente, la barra de progreso no se muestra correctamente cuando se producen cambios en el recurso que se carga.

* Después de aplicar y quitar el filtro para buscar todos los recursos editados a nivel local, la aplicación no lleva a los usuarios a la vista de carpetas o a los resultados de búsqueda con los que los usuarios empezaron. La aplicación muestra la carpeta raíz del repositorio de DAM.

* En ocasiones, cuando se conecta a una dirección URL que no tiene un servidor [!DNL Experience Manager] en ejecución, la pantalla de conexión deja de responder. Salga de la aplicación y vuelva a iniciarla.

**Problemas de CRUD (Crear, Leer, Actualizar y Eliminar):**

* Al cargar cambios en un recurso con comentarios, los comentarios se almacenan con el recurso en [!DNL Experience Manager], pero no se pueden ver como comentarios de versiones. Este problema se resolvió en [!DNL Experience Manager] 6.4.5 y [!DNL Experience Manager] 6.5.1. Adobe recomienda instalar los Service Packs más recientes. <!-- CQ-4268990 -->

* Un usuario no puede cancelar las transferencias de recursos. Si ha activado una transferencia de gran volumen sin querer, salga de la aplicación y vuelva a iniciarla. <!-- CQ-4278940 -->

**Problemas de la plataforma:**

* En ocasiones, en Windows, el estado de un recurso puede cambiar inmediatamente a [!UICONTROL Edited Locally] después de abrirlo, aunque no lo haya editado. Haga clic en [!UICONTROL Refresh] para actualizar.

>[!MORELIKETHIS]
>
>* [[!DNL Experience Manager] como [!DNL Cloud Service] documentación](https://experienceleague.adobe.com/es/docs/experience-manager-cloud-service)
>* [[!DNL Experience Manager] documentación de as a [!DNL Cloud Service] [!DNL Assets]](https://experienceleague.adobe.com/es/docs/experience-manager-cloud-service/content/assets/overview)
>* [Cómo usar [!DNL Experience Manager] aplicación de escritorio](using.md)
>* [Instalación y actualización de la aplicación de escritorio](install-upgrade.md)
>* [Procedimientos recomendados y sugerencias para la solución de problemas](troubleshoot.md)
