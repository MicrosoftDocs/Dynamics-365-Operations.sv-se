---
title: Felsöka befattningsbudgetering
description: Den här artikeln innehåller svar på frågor som du kan ha när du konfigurerar befattningsbudgetering. Det handlar om vanliga frågor och svar om hur du skapar budgetkostnadselement, kompensationsgrupper och kompensationsrutnät.
author: panolte
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmBudgetPurposeType, HcmPositionForecast
audience: Application User
ms.reviewer: roschlom
ms.custom: 88253
ms.assetid: c44df01b-8700-4022-b4c6-c4b1cb84d31d
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 492a0798d1934b0fe1adf4f0546013f394beab06948f02f92358bae408e7748f
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6726072"
---
# <a name="position-budgeting-troubleshooting"></a>Felsöka befattningsbudgetering

[!include [banner](../includes/banner.md)]

Den här artikeln innehåller svar på frågor som du kan ha när du konfigurerar befattningsbudgetering. Det handlar om vanliga frågor och svar om hur du skapar budgetkostnadselement, kompensationsgrupper och kompensationsrutnät. 

## <a name="why-cant-i-find-the-forecast-position-page-in-human-resources"></a>Varför inte kan hitta jag sidan Prognosposition i Personal?

Prognospositioner har flyttats till Budgetering.

## <a name="why-cant-i-delete-a-budget-cost-element"></a>Varför kan jag inte ta bort ett budgetkostnadselement?
Du kan inte ta bort ett budgetkostnadselement som är tilldelat till en prognosbefattning. Innan du kan ta bort budgetkostnadselementet måste du ta bort det från alla prognospositioner. **Tips:** För att hitta alla positioner som ett budgetkostnadselement är tilldelat till, välj kostnadselementet på sidan **Budgetkostnadselement** och klicka sedan på **Uppdatera positioner**. De befattningar som använder kostnadselementet anges i det övre rutnätet.

## <a name="how-can-i-remove-a-cost-element-from-multiple-forecast-positions-without-opening-each-one"></a>Hur kan jag ta bort ett kostnadselement från flera prognospositioner utan att öppna vart och ett?
Du kan inte ta bort ett kostnadselement. Men om du ändrar start- och slutdatumen så att det hamnar utanför budgetplaneringscykeln kommer kostnadselementet inte längre att tilldelas till prognospositioner i budgetplaneringscykeln. Du gör den här ändringen genom att öppna budgetkostnadselementet, och sedan på snabbfliken **Kostnadsberäkning** klicka på **Ändra datum** och ändra giltighetsdatumet eller utgångsdatumet. Klicka sedan på **OK** om du automatiskt vill uppdatera alla prognospositioner kostnadselementet har tilldelats till. **Tips:** Om du använder den här metoden, ska du vara medveten om att den tar bort budgetkostnadselementet från **alla** prognospositioner i vilka start- och slutdatumen inte längre är inom lämpligt intervall. Om denna effekt inte är vad du tänker dig, måste du öppna varje prognosposition som du vill ta bort budgetkostnadselementet från och manuellt göra ändringen.

## <a name="why-cant-i-enter-an-annual-amount-on-the-cost-calculation-fasttab-for-the-budget-cost-element"></a>Varför kan jag inte ange ett årligt belopp på snabbfliken Kostnadsberäkning för budgetkostnadselementet?
Du kan inte ange ett årligt belopp om det finns kostnader för budgetkostnadselementen på snabbfliken **Beräkningsbas** eftersom systemet kräver en procentsats för att kunna beräkna värdet. För att ändra värdet, ta bort alla budgetkostnadselement från snabbfliken **Beräkningsbas**.

## <a name="why-cant-i-change-the-budget-cost-type-from-earning-to-another-budget-cost-type"></a>Varför kan jag inte ändra budgetkostnadstypen från inkomst till en annan budgetkostnadstyp?
Vissa budgeterade kostnadselement använder intäktskostnadselementet som beräkningsbas. För att ändra fältet **Budgetkostnadstyp**, ta bort intäktskostnadselementet från snabbfliken **Beräkningsbas** för alla budgetkostnadselement.

## <a name="why-cant-i-change-the-date-on-budget-cost-element-lines-for-a-budget-cost-element"></a>Varför kan jag inte ändra datumet på budgetkostnadselementrader för ett budgetkostnadselement?
Du kan inte ändra datumet på budgetkostnadselementraden när ett budgetkostnadselement används av en prognosbefattning. Denna begränsning garanterar att prognospositionerna alltid är inom riktlinjerna för budgetkostnadselementet. Om du vill ändra datumet, på **Kostnadsberäkning** snabbfliken klicka **Ändra datum** och ange de nya datumen. Klicka sedan på **OK** för att uppdatera positionerna kostnadselementet har tilldelats till.

## <a name="why-cant-i-change-the-costs-for-a-budget-cost-element-on-the-compensation-group-page"></a>Varför kan jag inte ändra kostnaderna för ett budgetkostnadselement på sidan Kompensationsgrupp?
Du kan skapa och ändra kostnader för budgetkostnadselement bara på sidan **Budgetkostnadselement**.

## <a name="why-do-i-receive-an-error-message-when-i-change-the-dates-for-a-cost-element-on-a-forecast-position"></a>Varför får jag ett felmeddelande när jag ändrar datumen för ett kostnadselement i en prognosposition?
Datumen på prognospositionens kostnadselementrad måste vara inom följande intervall:

-   Aktiverings- och avyttringsdatum för befattningen.
-   Aktiverings- och utgångsdatum för budgetkostnadselementet.
-   Start- och slutdatumen för den budgetcykel som associeras med budgetplaneringsprocessen för prognosbefattningen.






[!INCLUDE[footer-include](../../includes/footer-banner.md)]