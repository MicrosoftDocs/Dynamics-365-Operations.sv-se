---
title: "Utgående process"
description: "I det här avsnittet finns en översikt över utgående processer inom lagerhantering."
author: perlynne
manager: AnnBe
ms.date: 10/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: WMSOrder, WMSShipment, MCRPickingWorkbench, WMSPickingRegistration, CustomFilterGroup
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Core, Operations
ms.custom: 274363
ms.assetid: 375807b2-a426-4f1b-bc1f-2fe00fd48413
ms.search.region: global
ms.search.industry: Distribution
ms.author: perlynne
ms.dyn365.ops.intro: AX 7.0.0
ms.search.validFrom: 2016-02-28
ms.translationtype: HT
ms.sourcegitcommit: 0ca19ab9ed7a52328c5dd5252c418bb9343bdc2b
ms.openlocfilehash: f2cae64263769b5168d2bb9614d6388b42e23b49
ms.contentlocale: sv-se
ms.lasthandoff: 12/14/2017

---

# <a name="outbound-process"></a>Utgående process

[!include[banner](../includes/banner.md)]

I det här avsnittet finns en översikt över utgående processer inom lagerhantering.

## <a name="output-orders"></a>Utleveransorder

Utgående order används för att sammanlänka rader i försäljningsorder och rader i överföringsorder med de utgående plockprocesser som använder plocklistor.

När plocklistor skapas ur antingen försäljningsorder eller överföringsorder, skapas utgående order och leveranser automatiskt. En plocklista har en individuell relation till en leverans. Överföringsorderns leverans eller försäljningsorderns packsedel kan bearbetas från leveransen. 

Följande diagram visar en översikt över processen för utgående order. 

[![Översikt över processen för utgående order](./media/outbound-order.png)](./media/outbound-order.png).

Du kan skapa regler för utgående order om du vill definiera hur programmet ska hantera den utgående processen. Du kan använda dessa regler för att styra leveransprocessen. Inte minst kan du använda reglerna för att styra det processtadium under vilket en leverans kan skickas. Följande inställningar anger hur utgående processer hanteras.

## <a name="picking-route-status-for-sales-and-transfer-orders"></a>Välja vidarebefordrandestatus för försäljnings- och överföringsorder 

Gå till **Kundreskontra** \> **Inställningar** \> **Kundreskontraparametrar**. På fliken **Uppdateringar** väljer du sedan ett värde i fältet **Välja status för vidarebefordran**.

[![Välja statusfält för vidarebefordran för försäljningsorder](./media/picking-route-status-sales-order.png)](./media/picking-route-status-sales-order.png)

Om fältet **Välja status för vidarebefordran** har angetts som **Slutförd** sker plockförfarandet automatiskt som ett led i att generera plocklistor. Om fältet har angetts som **Aktiverat** måste raderna för plocklistor uppdateras manuellt.

Samma inställning gäller överföringsorder. Gå till **Lagerhantering** \> **Inställningar** \> **Parametrar för lager- och lagerställehantering**. På fliken **Transport** väljer du sedan ett värde i fältet **Välja status för vidarebefordran**.

[![Välja statusfält för vidarebefordran för överföringsorder](./media/picking-route-status-transfer-order.png)](./media/picking-route-status-transfer-order.png)

## <a name="end-output-inventory-orders"></a>Avsluta utgående lagerorder

Gå till **Lagerhantering** \> **Inställningar** \> **Parametrar för lager- och lagerställehantering**. På fliken **Allmänt** väljer du sedan alternativet **Avsluta utgående lagerorder**.

[![Avsluta alternativet för utgående lagerorder](./media//end-output-inventory-order.png)](./media//end-output-inventory-order.png)

När lagerarbetaren minskar plocklistekvantiteter ska motsvarande lagerorderkvantiteter tas bort från leveransen. När plocklistan uppdateras vid en viss tidpunkt rapporteras återstående kvantiteter tillbaka ordern om alternativet **Avsluta utlagerorder** är **Ja**. Om alternativet **Avsluta utlagerorder** är inställt på **Nr**, behålls återstående kvantiteterna som en öppen utgående orderkvantitet och måste läggas till en ny plocklista som en del av funktionen **öppna utleveransorder**. 

[![Öppna kommandot för utgående order i funktionsmenyn](./media/open-output-order.png)](./media/open-output-order.png)

[![Funktionsmenyn på sidan för att öppna utgående order](./media/open-output-order-function.png)](./media/open-output-order-function.png)

## <a name="reduce-quantity"></a>Minska kvantiteten

Den tredje parametern du kan använda som ett led i processen att skapa plocklistor är parametern **Minska kvantitet**. Inställningen för denna parameter samarbetar med inställningen **Reservation**, som utlöser en reservationsprocess som ett led i frisläppandet till lagret.

[![Parameter för kvantitetsminskning](./media/reduce-quantity.png)](./media/reduce-quantity.png)

## <a name="example-of-an-outbound-process-for-a-sales-order"></a>Exempel på en utgående process för en försäljningsorder

För detta exempel finns en försäljningsorder för två artiklar. I samband med att plocklistan skapas väljer du parametern **Minska kvantitet**. Du frisläpper och skapar plocklinor därför endast för tillgängliga varor. Plocket måste rapporteras via en registreringsprocess för plocklistor (**Status för vidarebefordran av plock** = **Aktiverad**).

De varor som ännu inte har reserverats kommer att reserveras i samband med att plocklistan skapas. Icke tillgängliga varor kan antingen plockas bort från försäljningsordern eller frisläppas till lagret för senare utgående bearbetning när varorna är tillgängliga för plock.

[![Uppdatera plocklistan](./media/update-picking-list.png)](./media/update-picking-list.png)

Så fort samtliga plocklinor har plockats på sidan **Registrera plocklist** har tillhörande leverans slutförts. Processen för försäljningsordrarnas packsedlar kan edan initialiseras baserat på plockade varor.

[![Uppdatera utgående leveranser](./media/outbound-shipments.png)](./media/outbound-shipments.png)

