---
title: Konfigurera delning ekonomiska data mellan företag
description: I den här proceduren visas hur du konfigurerar, aktiverar, validerar och löser konflikter när data delas mellan företag.
author: aprilolson
manager: AnnBe
ms.date: 06/26/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DataManagementWorkspace, DMFQuickImportExportRnr, DMFExecutionHistoryWorkspace, DMFExecutionHistorySummary, DMFExecutionHistoryEntities,  SysDataSharingConfiguration, SysDataSharingDiscrepencies
audience: Application User
ms.reviewer: sericks
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: aeb9e85d3263d78a8412bd3c300dae8bb1d840ef
ms.sourcegitcommit: 659375c4cc7f5524cbf91cf6160f6a410960ac16
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/05/2020
ms.locfileid: "4685203"
---
# <a name="configure-financial-cross-company-data-sharing"></a>Konfigurera delning ekonomiska data mellan företag

[!include [banner](../../includes/banner.md)]

I den här proceduren visas hur du konfigurerar, aktiverar, validerar och löser konflikter när data delas mellan företag. Den använder USMF-företaget och finansiella datas delningsmall.

Den här uppgiftsguiden kräver Dynamics AX plattform 7.1 eller senare.

1. Gå till **Navigeringsfönster > Moduler > Systemadministration > Arbetsytor > Datahantering**.
2. Klicka på **Importera**.
3. Skriv ett värde i fältet **Namn**.
4. Välj pakettypen i fältet **Källdataformat**. Klicka på **Skicka**. Navigera till platsen för paketfilen för finansiella datas delningsmall och välj den filen.
5. Klicka på **Spara**.
6. Markera vald rad i listan. Välj datadelningpolicyn som just har skapats.  
7. Klicka på **Importera**.
8. Klicka på **Stäng**.
9. Uppdatera sidan.
10. Stäng sidan.
11. Stäng sidan.
12. Stäng sidan.
13. Gå till **Navigeringsfönster > Moduler > Systemadministration > Inställningar > Konfigurera datadelning mellan företag**.
14. Hitta och välj **Betalningsdagar** i listan.
15. Klicka på **Lägg till**.
16. Markera vald rad i listan.
17. Ange "USSI" i fältet **Företag**.
18. Klicka på **Lägg till**.
19. Ange "USMF" i fältet **Företag**.
20. Klicka på **Spara**.
21. Klicka på **Aktivera**.
22. Klicka på **Ja**.
23. Klicka på **Hitta delningsproblem**.
24. Klicka på **Ja**.
25. Klicka på **Uppdatera fältvärde**.
26. Klicka på **Använd värde från Företag 1**.
27. Uppdatera sidan.
28. Stäng sidan.

