---
title: ER importera en konfiguration från Lifecycle Services
description: I följande steg förklaras hur en användare i rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan importera en ny version av en konfiguration för elektronisk rapportering (ER) från Microsoft Lifecycle Services (LCS).
author: NickSelin
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERWorkspace, ERSolutionTable,  ERSolutionRepositoryTable, ERSolutionImport
audience: Application User
ms.reviewer: kfend
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0830707885e8ed52581aa789df0279d78e3a9c10
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2184840"
---
# <a name="er-import-a-configuration-from-lifecycle-services"></a>ER importera en konfiguration från Lifecycle Services

[!include [task guide banner](../../includes/task-guide-banner.md)]

I följande steg förklaras hur en användare i rollen Systemadministratör eller Utvecklare för elektronisk rapportering kan importera en ny version av en konfiguration för elektronisk rapportering (ER) från Microsoft Lifecycle Services (LCS).

I det här exemplet ska du välja önskad versio av ER-konfigurationen och importera den för exempelföretaget, Litware, Inc. Dessa steg kan utföras i alla företag eftersom ER-konfigureringar delas mellan företag. För att slutföra dessa steg måste du först slutföra stegen i proceduren "Överföra en ER-konfiguration till Lifecycle Services”. Åtkomst till LCS krävs även för att slutföra dessa steg.

1. Gå till Organisationsadministration > Arbetsytor > Elektronisk rapportering.
2. Klientkonfigurationer.

## <a name="delete-a-shared-version-of-data-model-configuration"></a>Ta bort en delad version av konfiguration av datamodell
1. Välj "Konfiguration av exempelmodell" i trädet.
    * Den första versionen av en konfiguration av exempeldatamodell har skapats och har publicerats till LCS under proceduren "Överför en ER-konfiguration till Lifecycle Services". I den här proceduren kommer du ta bort den här versionen av ER-konfigurationen. Denna version av en konfiguration av exempeldatamodell kommer att importeras senare från LCS.  
2. Hitta och markera önskad post i listan.
    * Välj versionen av den här konfigurationen som har statusen "Delad". Statusen visar att konfigurationen har publicerats till LCS.  
3. Klicka på Ändra status.
4. Klicka på Upphör.
    * Ändra status för den valda versionen från ”Delad" till "Upphörd" om du vill göra det tillgänglig för radering.  
5. Klicka på OK.
6. Hitta och markera önskad post i listan.
    * Välj versionen av den här konfigurationen som har statusen "Upphörd".  
7. Klicka på Ta bort.
8. Klicka på Ja.
    * Observera att den enda utkastversionen 2 i den valda konfigurationen av datamodell är tillgänglig.  
9. Stäng sidan.

## <a name="import-a-shared-version-of-data-model-configuration-from-lcs"></a>Importera en delad version av konfiguration av datamodell från LCS
1. Markera vald rad i listan.
    * Öppna listan över databaser för Litware, Inc. konfigurationsleverantör.  
2. Klicka på Databaser.
3. Klicka på Öppna.
    * Välj LCS-databasen och öppna den.  
4. Markera vald rad i listan.
    * Välj den första versionen av "Konfiguration av exempelmodell" i versionlistan.  
5. Klicka på Importera.
6. Klicka på Ja.
    * Bekräfta importen av den valda versionen från LCS.  
    * Observera att informationmeddelandet (över formuläret) bekräftar lyckad import av den valda versionen.  
7. Stäng sidan.
8. Stäng sidan.
9. Klientkonfigurationer.
10. Välj "Konfiguration av exempelmodell" i trädet.
11. Hitta och markera önskad post i listan.
    * Välj versionen av den här konfigurationen som har statusen "Delad".  
    * Observera att den enda delade versionen 1 i den valda konfigurationen av datamodell nu också är tillgänglig.  
