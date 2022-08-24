---
title: ER Använd horisontellt expanderbara intervall för att dynamiskt lägga till kolumner i Excel-rapporter (Del 2 - Kör format)
description: I den här artikeln beskrivs hur du konfigurerar ett elektroniskt rapporteringsformat (ER) för att generera rapporter som OPENXML-kalkylblad (Excel). (Del 2)
author: kfend
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: filatovm
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.search.form: ERSolutionTable, SysQueryForm
ms.openlocfilehash: 08755eafa2a18993ba669f0deccd75477bfae410
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/12/2022
ms.locfileid: "9290407"
---
# <a name="er-use-horizontally-expandable-ranges-to-dynamically-add-columns-in-excel-reports-part-2---run-format"></a>ER Använd horisontellt expanderbara intervall för att dynamiskt lägga till kolumner i Excel-rapporter (Del 2 - Kör format)

[!include [banner](../../includes/banner.md)]

Följande steg beskriver hur en användare som är tilldelad rollen som systemadministratör eller elektronisk rapporteringutvecklare kan konfigurera ett elektroniskt rapporteringsformat (ER) för att skapa rapporter som OPENXML-kalkylblad (Excel), där erforderliga kolumner kan skapas dynamiskt som horisontellt expanderbara intervall. Dessa steg kan utföras i DEMF-företaget.

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
    * Granska den skapade utleveransen. Observera att den nyss skapade Excel-filen innehåller samma antal kolumner som valdes för ekonomiska dimensioner. Rapporthuvudet i dessa kolumner representerar namnen på de ekonomiska dimensionerna. Transaktionsraderna i dessa kolumner representerar ekonomiska dimensioner. Kör denna rapport och välj olika dimensioner för att se att rapporten inte är beroende av antalet valda dimensioner eller antalet dimensioner som konfigureras för denna instans.  



[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]
