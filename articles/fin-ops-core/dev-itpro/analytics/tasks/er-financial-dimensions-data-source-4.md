---
title: ER Använd ekonomiska dimensioner som en datakälla (Del 4 - Kör rapporten)
description: I det här avsnittet beskrivs hur du konfigurerar en elektronisk rapporteringsmodell (ER) för användning av ekonomiska dimensioner som datakälla för ER-rapporter. (Del 4)
author: NickSelin
manager: AnnBe
ms.date: 05/27/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ERSolutionTable, SysQueryForm
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: nselin
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c1fe332de84339d3369ba495ca13f50c4901f366
ms.sourcegitcommit: 5192cfaedfd861faea63d8954d7bcc500608a225
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/30/2021
ms.locfileid: "5092285"
---
# <a name="er-use-financial-dimensions-as-a-data-source-part-4---run-the-report"></a>ER Använd ekonomiska dimensioner som en datakälla (Del 4 - Kör rapporten)

[!include [banner](../../includes/banner.md)]

I följande steg beskrivs hur en användare som tilldelats en roll som systemadministratör eller utvecklare för elektronisk rapportering kan konfigurera en modell för elektronisk rapportering (ER) för att använda ekonomiska dimensioner som datakällor för ER-rapporter. Dessa steg kan utföras i DEMF-företaget.

För att slutföra dessa steg måste du först avsluta stegen i proceduren ”ER Use financial dimensions as a data source (Part 3: Design the report)”. Du måste även konfigurera förvalda dokumenttyper på sidan för elektroniska rapporteringsparametrar. Förvalda dokumenttyper anges också när du hämtar och importerar en ER-konfiguration. 


## <a name="run-report"></a>Kör rapport
1. Gå till Organisationsadministration > Elektronisk rapportering > Konfigurationer.
2. Expandera "Financial dimensions sample model" i trädet.
3. Välj "Financial dimensions sample model\Ledger journal report" i trädet.
4. Klicka på Kör.
![Sidan ER-konfigurationer](../media/er-financial-dimensions-guides-run1.png)
5. Ange eller välj ett värde i namnfältet Dimensions.
    * Ange följande information om du vill välja alla dimensioner i det aktuella företaget: BusinessUnit;CostCenter;Department;ItemGroup;MainAccount;Project  
![Sidan ER-konfigurationer](../media/er-financial-dimensions-guides-run2.png)
6. Expandera avsnittet Poster som ska ingå.
7. Klicka på Filter.
8. Markera raden för redovisningsjournalregistret (Ledger journal table) och fältet för journalens batchnummer (Journal batch number).
9. Ange "00057" i fältet Criteria.
10. Klicka på OK.
11. Klicka på OK.
![Sidan ER-konfigurationer](../media/er-financial-dimensions-guides-run3.png)
    * Granska den genererade utleveransen. Ekonomiska dimensioner från den motsvarande dimensioner visas för varje transaktion i den valda batchen. Kör denna rapport och välj olika dimensioner för att se att rapporten inte är beroende av antalet valda dimensioner eller antalet dimensioner som konfigureras för denna instans.  
![Sidan ER-konfigurationer](../media/er-financial-dimensions-guides-run4.png)


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]