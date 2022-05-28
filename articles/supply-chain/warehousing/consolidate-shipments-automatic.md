---
title: Konsolidera leveranser när dessa släpps till lagerstället med hjälp av automatiskt släpp av försäljningsorder
description: Detta ämne innehåller ett scenario där flera order frigörs till lagerstället i samma automatiska, periodiska procedur för släpp-till-lagerställe.
author: Mirzaab
ms.date: 05/12/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench, WHSFilterGroupTable, WHSShipmentConsolidation, WHSFilterGenerallyAvail
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: 74d4d9d8429095c3fac80db58f14ac2ef0776798
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/03/2022
ms.locfileid: "8677546"
---
# <a name="consolidate-shipments-released-to-the-warehouse-using-automatic-release-of-sales-orders"></a>Konsolidera leveranser när dessa släpps till lagerstället med hjälp av automatiskt släpp av försäljningsorder

[!include [banner](../includes/banner.md)]

Detta ämne innehåller ett scenario där flera order frigörs till lagerstället i samma automatiska, periodiska procedur för släpp-till-lagerställe. Order konsolideras automatiskt till leveranser, baserat på regler som har definierats som policyer för leveranskonsolidering.

Under scenariot skapar du uppsättningar med försäljningsorder och släpper varje uppsättning till lagerstället. Du kommer sedan att granska de leveranser som skapas eller uppdateras under leveranskonsolideringen, baserat på de konfigurerade policyerna.

## <a name="make-demo-data-available"></a>Gör demodata tillgängliga

Scenariot i detta ämne innehåller referensvärden och -poster som ingår i den standarddemodata som finns för Microsoft Dynamics 365 Supply Chain Management. Om du vill använda de värden som finns här på samma sätt som i övningarna måste du arbeta i en miljö där demonstrationsdata har installerats samt ställa in den juridiska personen på **USMF** innan du börjar.

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a>Ställ in policyer och produktfilter för leveranskonsolidering

Det scenario som beskrivs här förutsätter att du redan har aktiverat funktionen, gjort övningarna i [Konfigurera policyer för leveranskonsolidering](configure-shipment-consolidation-policies.md) samt har skapat de policyer och andra poster som beskrivs där. Var noga med att göra övningarna innan du fortsätter med det här scenariot.

## <a name="create-the-sales-orders-for-this-scenario"></a>Skapa försäljningsorder för det här scenariot

Börja med att skapa en samling med försäljningsorder som du kan arbeta med. Du måste arbeta med ett lagerställe som är aktiverat för avancerade processer för lagerställe (WMS). Såvida inte ett annat lagerställe uttryckligen anges måste samma lagerställe användas för var och en av följande orderuppsättningar.

Gå till **Kundreskontra \> Order \> Alla försäljningsorder** och skapa en samling försäljningsorder som har de inställningar som beskrivs i följande underavsnitt.

### <a name="create-order-set-1"></a>Skapa orderuppsättning 1

#### <a name="sales-order-1-1"></a>Försäljningsorder 1-1

1. Skapa en försäljningsorder med följande inställningar:

    - **Kundkonto:** *US-001*
    - **Leveranssätt:** *Flygfrakt*

1. Lägg till en orderrad med följande inställningar:

    - **Artikelnummer:** *A0001* (en artikel som inget **Kod 4**-filter tilldelas till)
    - **Kvantitet:** *1.00*

#### <a name="sales-order-1-2"></a>Försäljningsorder 1-2

1. Skapa en försäljningsorder med följande inställningar:

    - **Kundkonto:** *US-001*
    - **Leveranssätt:** *Flygfrakt*

1. Lägg till en orderrad med följande inställningar:

    - **Artikelnummer:** *A0001* (en artikel som inget **Kod 4**-filter tilldelas till)
    - **Kvantitet:** *1.00*

#### <a name="sales-order-1-3"></a>Försäljningsorder 1-3

1. Skapa en försäljningsorder med följande inställningar:

    - **Kundkonto:** *US-001*
    - **Leveranssätt:** *10*

1. Lägg till en orderrad med följande inställningar:

    - **Artikelnummer:** *A0001* (en artikel som inget **Kod 4**-filter tilldelas till)
    - **Kvantitet:** *1.00*

1. Lägg till en andra orderrad med följande inställningar:

    - **Artikelnummer:** *A0002* (en artikel som inget **Kod 4**-filter tilldelas till)
    - **Kvantitet:** *1.00*
    - **Leveranssätt:** *Flygfrakt*

### <a name="create-order-set-2"></a>Skapa orderuppsättning 2

#### <a name="sales-orders-2-1-and-2-2"></a>Försäljningsorder 2-1 och 2-2

1. Skapa två identiska försäljningsorder som har följande inställningar:

    - **Kundkonto:** *US-002*

1. Lägg till en orderrad med följande inställningar:

    - **Artikelnummer:** *M9200* (en artikel där filtret **Kod 4** har värdet *Brandfarligt*)
    - **Kvantitet:** *1.00*

1. Lägg till en andra orderrad med följande inställningar:

    - **Artikelnummer:** *M9201* (en artikel där filtret **Kod 4** har värdet *Explosivt*)
    - **Kvantitet:** *1.00*
    - **Leveranssätt:** *Flygfrakt*

### <a name="create-order-set-3"></a>Skapa orderuppsättning 3

#### <a name="sales-order-3-1"></a>Försäljningsorder 3-1

1. Skapa en försäljningsorder med följande inställningar:

    - **Kundkonto:** *US-002*

1. Lägg till en orderrad med följande inställningar:

    - **Artikelnummer:** *M9200* (en artikel där filtret **Kod 4** har värdet *Brandfarligt*)
    - **Kvantitet:** *1.00*

1. Lägg till en andra orderrad med följande inställningar:

    - **Artikelnummer:** *M9201* (en artikel där filtret **Kod 4** har värdet *Explosivt*)
    - **Kvantitet:** *1.00*
    - **Leveranssätt:** *Flygfrakt*

> [!NOTE]
> Ordern är identisk med de två order som du skapade för orderuppsättning 2. Den är dock listad som en orderuppsättning eftersom den frigörs separat senare i det här scenariot.

### <a name="create-order-set-4"></a>Skapa orderuppsättning 4

#### <a name="sales-order-4-1"></a>Försäljningsorder 4-1

1. Skapa en försäljningsorder med följande inställningar:

    - **Kundkonto:** *US-001*
    - **Kundrekvisition:** *1*

1. Lägg till en orderrad med följande inställningar:

    - **Artikelnummer:** *A0001* (en artikel som inget **Kod 4**-filter tilldelas till)
    - **Kvantitet:** *1.00*

### <a name="create-order-set-5"></a>Skapa orderuppsättning 5

#### <a name="sales-orders-5-1-and-5-2"></a>Försäljningsorder 5-1 och 5-2

1. Skapa två identiska försäljningsorder som har följande inställningar:

    - **Kundkonto:** *US-001*
    - **Kundrekvisition:** *2*

1. Lägg till en orderrad med följande inställningar:

    - **Artikelnummer:** *A0001* (en artikel som inget **Kod 4**-filter tilldelas till)
    - **Kvantitet:** *1.00*

#### <a name="sales-order-5-3"></a>Försäljningsorder 5-3

1. Skapa en försäljningsorder med följande inställningar:

    - **Kundkonto:** *US-001*
    - **Kundrekvisition:** *1*

1. Lägg till en orderrad med följande inställningar:

    - **Artikelnummer:** *A0001* (en artikel som inget **Kod 4**-filter tilldelas till)
    - **Kvantitet:** *1.00*

### <a name="create-order-set-6"></a>Skapa orderuppsättning 6

#### <a name="sales-orders-6-1-and-6-2"></a>Försäljningsorder 6-1 och 6-2

1. Skapa två identiska försäljningsorder som har följande inställningar:

    - **Kundkonto:** *US-003*
    - **Kundrekvisition:** *2*

1. Lägg till en orderrad med följande inställningar:

    - **Artikelnummer:** *A0001* (en artikel som inget **Kod 4**-filter tilldelas till)
    - **Kvantitet:** *1.00*

#### <a name="sales-orders-6-3-and-6-4"></a>Försäljningsorder 6-3 och 6-4

1. Skapa två identiska försäljningsorder som har följande inställningar:

    - **Kundkonto:** *US-004*
    - **Kundrekvisition:** *1*

1. Lägg till en orderrad med följande inställningar:

    - **Artikelnummer:** *A0001* (en artikel som inget **Kod 4**-filter tilldelas till)
    - **Kvantitet:** *1.00*

#### <a name="sales-orders-6-5-and-6-6"></a>Försäljningsorder 6-5 och 6-6

1. Skapa två identiska försäljningsorder som har följande inställningar:

    - **Kundkonto:** *US-007*
    - **Plats:** *6*
    - **Lagerställe:** *61*
    - **Pool:** *ShipCons*

1. Lägg till en orderrad med följande inställningar:

    - **Artikelnummer:** *A0001* (en artikel som inget **Kod 4**-filter tilldelas till)
    - **Kvantitet:** *1.00*

#### <a name="sales-orders-6-7-and-6-8"></a>Försäljningsorder 6-7 och 6-8

1. Skapa två identiska försäljningsorder som har följande inställningar:

    - **Kundkonto:** *US-007*
    - **Plats:** *6*
    - **Lagerställe:** *61*
    - **Pool:** Lämna detta fält tomt.

1. Lägg till en orderrad med följande inställningar:

    - **Artikelnummer:** *A0001* (en artikel som inget **Kod 4**-filter tilldelas till)
    - **Kvantitet:** *1.00*

## <a name="automatic-release-of-sales-orders-to-the-warehouse"></a>Automatiskt släpp av försäljningsorder till lagerstället

För varje uppsättning försäljningsorder som du skapade tidigare kommer du att slutföra en procedur för automatiskt släpp till lagerstället. I varje enskilt fall kommer du att arbeta genom den [grundläggande process för släpp-till-lagerställe](#release-procedure) som tillhandahålls här.

### <a name="basic-release-to-warehouse-procedure"></a><a name="release-procedure"></a>Grundläggande procedur för släpp till lagerställe

För varje enskild uppsättning försäljningsorder som du skapade tidigare kommer du att genomföra de tre procedurer som beskrivs i följande underavsnitt.

#### <a name="update-the-wave-template-that-will-be-used-during-release"></a>Uppdatera den påfyllnadsmall som ska användas under släpp

1. Gå till **Lagerstyrning \> Inställningar \> Påfyllnader \> Påfyllnadsmallar**.
1. Ställ in fältet **Malltyp för påfyllnad** som *Levereras*.
1. Hitta och välj den påfyllnadsmall som är kopplad till det lagerställe som du har använt i de orderuppsättningar du skapat för scenariot. Om du till exempel har använt lagerställe *24* ska du välja påfyllnadsmallen **Standardleverans för 24**. Om du använt lagerställe *61* ska du välja påfyllnadsmallen **Leverans för 61**.
1. I åtgärdsfönstret väljer du **Redigera**.
1. Ange alternativet **Bearbeta påfyllnad vid släpp till lagerställe** som *Nej*.

#### <a name="release-to-the-warehouse"></a>Släpp till lagerställe

1. Gå till **Lagerstyrning \> Släpp till lagerställe \> Automatiskt släpp av försäljningsorder**.
1. Ställ in fältet **Kvantitet att släppa** som *Alla*.
1. På snabbfliken **Poster som ska inkluderas** väljer du **Filter** för att öppna dialogrutan för fråga.
1. På fliken **Intervall** väljer du **Lägg till** för att lägga till en rad med följande inställningar i rutnätet:

    - **Register:** *Försäljningsorder*
    - **Härlett register:** *Försäljningsorder*
    - **Fält:** *Försäljningsorder*
    - **Kriterier:** Ange en kommaavgränsad lista med försäljningsordernummer från önskad orderuppsättning.

1. Välj **OK** om du vill spara frågan.
1. Välj **OK** om du vill starta proceduren *Automatiskt släpp till lagerställe*.

#### <a name="review-the-shipment-that-is-created-or-updated"></a>Granska leveransen som har skapats eller uppdaterats

1. Gå till **Lagerstyrning \> Leveranser \> Alla leveranser**.
1. Sök och välj önskad leverans.
1. Om en konsolideringspolicy användes när leveransen skapades eller uppdaterades, bör du se den i fältet **Konsolideringspolicy för leverans**.

### <a name="release-sales-orders-from-order-set-1"></a>Släpp försäljningsorder från orderuppsättning 1

Följ den [grundläggande proceduren för frisläppning till lagerställe](#release-procedure) för att frisläppa försäljningsorder från orderuppsättning 1.

När du är klar bör du se att två leveranser har skapats:

- Den första leveransen innehåller tre rader och har skapats med hjälp av konsolideringspolicyn *CustomerMode* för leverans.
- Den andra leveransen, som inte använder transportsättet *Flygfrakt* skapades med hjälp av konsolideringspolicyn *CustomerOrderNo* för leverans.

### <a name="release-sales-orders-from-order-set-2"></a>Frisläpp försäljningsorder från orderuppsättning 2

Följ den [grundläggande proceduren för frisläppning till lagerställe](#release-procedure) för att frisläppa försäljningsorder från orderuppsättning 2.

När du är klar bör du se att tre leveranser har skapats:

- Den första leveransen innehåller de *brandfarliga* artiklarna.
- Var och en av de två andra leveranserna innehåller en rad som har artikeln *explosiv*.

### <a name="release-sales-orders-from-order-set-3"></a>Frisläpp försäljningsorder från orderuppsättning 3

Följ den [grundläggande proceduren för frisläppning till lagerställe](#release-procedure) för att frisläppa försäljningsorder från orderuppsättning 3.

När du är klar ska du se att följande åtgärder har utförts:

- En befintlig leverans (den som skapades när orderuppsättning 2 släpptes till lagerstället) uppdaterades. En rad med artikeln *brandfarlig* har lagts till.
- En ny leverans som innehåller artikeln *explosiv* skapades.

### <a name="release-sales-orders-from-order-set-4"></a>Frisläpp försäljningsorder från orderuppsättning 4

Följ den [grundläggande proceduren för frisläppning till lagerställe](#release-procedure) för att frisläppa försäljningsorder från orderuppsättning 4.

När du är klar bör du se att en befintlig leverans (där fältet **Kundrekvisition** är inställt på *1*) har uppdaterats. En ny rad lades till i den.

### <a name="release-sales-orders-from-order-set-5"></a>Frisläpp försäljningsorder från orderuppsättning 5

Följ den [grundläggande proceduren för frisläppning till lagerställe](#release-procedure) för att frisläppa försäljningsorder från orderuppsättning 5.

När du är klar ska du se att följande åtgärder har utförts:

- En befintlig leverans (där fältet **Kundrekvisition** är inställt på *1*) har uppdaterats. En rad från försäljningsorder 5-3 (där fältet **Kundrekvisition** är inställt på *1*) har lagts till i den.
- En ny leverans skapades, där rader från försäljningsorder 5-1 och 5-2 grupperas till en och samma leverans.

### <a name="release-sales-orders-from-order-set-6"></a>Frisläpp försäljningsorder från orderuppsättning 6

Följ den [grundläggande proceduren för frisläppning till lagerställe](#release-procedure) för att frisläppa försäljningsorder från orderuppsättning 6.

När du är klar bör du se att fyra leveranser har skapats:

- Rader från två försäljningsorder för kund *US-003* grupperades till en enda leverans med hjälp av leveranskonsolideringspolicyn *Orderpool*.
- Rader från två försäljningsorder för kund *US-004* grupperades till en enda leverans med hjälp av leveranskonsolideringspolicyn *Orderpool*.
- Rader från försäljningsorder 6-5 och 6-6 för kund *US-007* grupperades till en leverans med hjälp av leveranskonsolideringspolicyn *Orderpool*.
- Rader från försäljningsorder 6-7 och 6-8 för kund *US-007* grupperades till en leverans med hjälp av leveranskonsolideringspolicyn *CrossOrder*.

## <a name="additional-resources"></a>Ytterligare resurser

- [Policyer för leveranskonsolidering](about-shipment-consolidation-policies.md)
- [Konfigurera policyer för leveranskonsolidering](configure-shipment-consolidation-policies.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]