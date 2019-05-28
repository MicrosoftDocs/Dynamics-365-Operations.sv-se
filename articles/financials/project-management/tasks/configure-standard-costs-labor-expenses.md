---
title: Konfigurera standardkostnader för arbetskraft och utgifter
description: Den här proceduren visar hur du ställer in standardkostnader för arbete och utgifter för ett projekt.
author: KimANelson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ProjCostPriceHour, ProjSalesPriceHour, ProjCostPriceExpense, ProjSalesPriceCost
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Service industries
ms.author: knelson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f89590c87aec1a7200e95aeac6b2765fc64bb623
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1572406"
---
# <a name="configure-standard-costs-for-labor-and-expenses"></a>Konfigurera standardkostnader för arbetskraft och utgifter

[!include [task guide banner](../../includes/task-guide-banner.md)]

Den här proceduren visar hur du ställer in standardkostnader för arbete och utgifter för ett projekt. I den här uppgiften används datauppsättningen USSI.

1. Klicka på Projekthantering och redovisning > Inställningar > Priser > Självkostnadspris (timme).
2. Klicka på Ny.
3. Ange ett datum i fältet Giltighetsdatum.
4. Ange ett värde i fältet Cost price.
    * Du kan ställa in ett standardsjälvkostnadspris för projektkategorin, eller också kan du ställa in ett självkostnadspris efter medarbetarnummer, projektnummer, kategori, datum eller någon kombination av dessa. Det självkostnadspris som används är det mest detaljerade.  
5. Klicka på Spara.
6. Stäng sidan.
7. Klicka på Projekthantering och redovisning > Inställningar > Priser > Försäljningspris (timme).
8. Klicka på Ny.
9. Ange ett datum i fältet Giltighetsdatum.
10. Välj ett alternativ i fältet Gäller för.
11. Ange ett nummer i fältet Pris.
    * Du kan ställa in ett standardförsäljningspris för timtransaktioner eller för en projektkategori. Du kan också ställa in försäljningspriser efter medarbetarnummer, projektnummer, kategori, transaktionsdatum eller valfri kombination av dessa. Det verkliga försäljningspriset, som används när en medarbetare registrerar en transaktion i timjournalen, är försäljningspriset med den högsta detaljnivån. Om till exempel både ett allmänt försäljningspris och ett medarbetarspecifikt försäljningspris har angivits, används automatiskt det medarbetarspecifika försäljningspriset.  
12. Klicka på Spara.
13. Stäng sidan.
14. Klicka på Projekthantering och redovisning > Inställningar > Priser > Självkostnadspris (utgift).
15. Klicka på Ny.
16. Ange ett datum i fältet Giltighetsdatum.
17. Ange ett värde i fältet Cost price.
    * Flera fält kan fyllas i, men detta är det som krävs för att spara posten.  
18. Klicka på Spara.
19. Stäng sidan.
20. Gå till Projekthantering och redovisning > Inställningar > Priser > Försäljningspris (utgift).
21. Klicka på Ny.
22. Ange ett datum i fältet Giltighetsdatum.
23. Välj ett alternativ i fältet Gäller för.
24. Ange ett nummer i fältet Pris.
    * Det verkliga försäljningspriset, som används när en medarbetare registrerar transaktionerna i en utgiftsjournal, är försäljningspriset med den högsta detaljnivån. Om till exempel både ett allmänt försäljningspris och ett medarbetarspecifikt försäljningspris har angivits, används det medarbetarspecifika försäljningspriset.  
25. Klicka på Spara.

