--- 
title: "Kör ett format som använder horisontellt expanderbara intervall för att lägga till kolumner dynamiskt i Excel-rapporter för elektronisk rapportering (ER)"
description: "Följande steg beskriver hur en användare som är tilldelad rollen som systemadministratör eller elektronisk rapporteringutvecklare kan konfigurera ett elektroniskt rapporteringsformat (ER) för att generera rapporter som OPENXML-kalkylblad (Excel), där erforderliga kolumner kan skapas dynamiskt som horisontellt expanderbara intervall."
author: NickSelin
manager: AnnBe
ms.date: 10/28/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: kfend
ms.search.scope: Operations
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 4b859151edd28e39c1f97b2f600da6e304b1d065
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---
# <a name="run-a-format-that-uses-horizontally-expandable-ranges-to-dynamically-add-columns-in-excel-reports-for-electronic-reporting-er"></a>Kör ett format som använder horisontellt expanderbara intervall för att lägga till kolumner dynamiskt i Excel-rapporter för elektronisk rapportering (ER)

[!include[task guide banner](../../includes/task-guide-banner.md)]

Följande steg beskriver hur en användare som är tilldelad rollen som systemadministratör eller elektronisk rapporteringutvecklare kan konfigurera ett elektroniskt rapporteringsformat (ER) för att generera rapporter som OPENXML-kalkylblad (Excel), där erforderliga kolumner kan skapas dynamiskt som horisontellt expanderbara intervall. Dessa steg kan utföras i DEMF-företaget.

För att slutföra dessa steg måste du först avsluta stegen i proceduren "ER Use horizontally expandable ranges to dynamically add columns in Excel reports (Part 1: Design format)".

Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations version 1611.


## <a name="find-created-format"></a>Sök skapat format
1. Gå till Organisationsadministration > Elektronisk rapportering > Konfigurationer.
2. Expandera "Financial dimensions sample model" i trädet.
3. Välj "Financial dimensions sample model\Sample report with horizontally expandable ranges" i trädet.

## <a name="execute-format-to-create-excel-output"></a>Kör formatet för att skapa Excel-utleverans
1. Klicka på Kör.
2. Ange "BusinessUnit;CostCenter;Department" i fältet Dimensions name.
    * Ange eller välj ett värde i namnfältet Dimensions.  För att välja samtliga dimensioner för aktuellt företag, ange: BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project  
3. Expandera avsnittet Poster som ska ingå.
4. Klicka på Filter.
5. Markera raden för redovisningsjournalregistret (Ledger journal table) och fältet för journalens batchnummer (Journal batch number).
6. Ange "00057..00058" i fältet Criteria.
    * 00057..00058  
7. Klicka på OK.
8. Klicka på OK.
    * Granska den genererade utleveransen. Observera att den nyss skapade Excel-filen innehåller samma antal kolumner som valdes för ekonomiska dimensioner. Rapporthuvudet i dessa kolumner representerar namnen på de ekonomiska dimensionerna. Transaktionsraderna i dessa kolumner representerar ekonomiska dimensioner. Kör denna rapport och välj olika dimensioner för att se att rapporten inte är beroende av antalet valda dimensioner eller antalet dimensioner som konfigureras för denna Dynamics 365 for Finance and Operations, Enterprise edition-instans.  

