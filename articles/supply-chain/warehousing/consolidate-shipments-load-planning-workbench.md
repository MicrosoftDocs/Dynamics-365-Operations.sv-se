---
title: Konsolidera leveranser genom att använda Frisläpp till lagerställe från workbench för lastplanering
description: Det här ämnet innehåller ett scenario där flera order frigörs till lagerstället i samma beläggning och sedan automatiskt konsolideras till leveranser.
author: GarmMSFT
manager: tfehr
ms.date: 05/12/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSShipConsolidationPolicy, WHSShipConsolidationWorkbench
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.3
ms.openlocfilehash: c0af6764742532cbe181c8a20e7bf783b0e6d7cf
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4983104"
---
# <a name="consolidate-shipments-by-using-release-to-warehouse-from-the-load-planning-workbench"></a>Konsolidera leveranser genom att använda Frisläpp till lagerställe från workbench för lastplanering

[!include [banner](../includes/banner.md)]

Det här ämnet innehåller ett scenario där flera order frigörs till lagerstället i samma beläggning och sedan automatiskt konsolideras till leveranser.

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

1. Välj **Lager \> Bokning** och välj sedan **Reservera parti** i åtgärdsfönstret för att reservera orderraden.

#### <a name="sales-order-1-2"></a>Försäljningsorder 1-2

1. Skapa en försäljningsorder med följande inställningar:

    - **Kundkonto:** *US-001*
    - **Leveranssätt:** *Flygfrakt*

1. Lägg till en orderrad med följande inställningar:

    - **Artikelnummer:** *A0001* (en artikel som inget **Kod 4**-filter tilldelas till)
    - **Kvantitet:** *1.00*

1. Välj **Lager \> Bokning** och välj sedan **Reservera parti** i åtgärdsfönstret för att reservera orderraden.

#### <a name="sales-order-1-3"></a>Försäljningsorder 1-3

1. Skapa en försäljningsorder med följande inställningar:

    - **Kundkonto:** *US-001*
    - **Leveranssätt:** *10*

1. Lägg till en orderrad med följande inställningar:

    - **Artikelnummer:** *A0001* (en artikel som inget **Kod 4**-filter tilldelas till)
    - **Kvantitet:** *1.00*

1. Välj **Lager \> Bokning** och välj sedan **Reservera parti** i åtgärdsfönstret för att reservera orderraden.
1. Lägg till en andra orderrad med följande inställningar:

    - **Artikelnummer:** *A0002* (en artikel som inget **Kod 4**-filter tilldelas till)
    - **Kvantitet:** *1.00*
    - **Leveranssätt:** *Flygfrakt*

1. Välj **Lager \> Bokning** och välj sedan **Reservera parti** i åtgärdsfönstret för att reservera den andra orderraden.

### <a name="create-order-set-2"></a>Skapa orderuppsättning 2

#### <a name="sales-orders-2-1-and-2-2"></a>Försäljningsorder 2-1 och 2-2

1. Skapa två identiska försäljningsorder som har följande inställningar:

    - **Kundkonto:** *US-002*

1. Lägg till en orderrad med följande inställningar:

    - **Artikelnummer:** *M9200* (en artikel där filtret **Kod 4** har värdet *Brandfarligt*)
    - **Kvantitet:** *1.00*

1. Välj **Lager \> Bokning** och välj sedan **Reservera parti** i åtgärdsfönstret för att reservera orderraden.
1. Lägg till en andra orderrad med följande inställningar:

    - **Artikelnummer:** *M9201* (en artikel där filtret **Kod 4** har värdet *Explosivt*)
    - **Kvantitet:** *1.00*
    - **Leveranssätt:** *Flygfrakt*

1. Välj **Lager \> Bokning** och välj sedan **Reservera parti** i åtgärdsfönstret för att reservera den andra orderraden.

### <a name="create-order-set-3"></a>Skapa orderuppsättning 3

#### <a name="sales-orders-3-1-and-3-2"></a>Försäljningsorder 3-1 och 3-2

1. Skapa två identiska försäljningsorder som har följande inställningar:

    - **Kundkonto:** *US-001*
    - **Kundrekvisition:** *1*

1. Lägg till en orderrad med följande inställningar:

    - **Artikelnummer:** *A0001* (en artikel som inget **Kod 4**-filter tilldelas till)
    - **Kvantitet:** *1.00*

1. Välj **Lager \> Bokning** och välj sedan **Reservera parti** i åtgärdsfönstret för att reservera orderraden.

#### <a name="sales-orders-3-3-and-3-4"></a>Försäljningsorder 3-3 och 3-4

1. Skapa två identiska försäljningsorder som har följande inställningar:

    - **Kundkonto:** *US-001*
    - **Kundrekvisition:** *2*

1. Lägg till en orderrad med följande inställningar:

    - **Artikelnummer:** *A0001* (en artikel som inget **Kod 4**-filter tilldelas till)
    - **Kvantitet:** *1.00*

1. Välj **Lager \> Bokning** och välj sedan **Reservera parti** i åtgärdsfönstret för att reservera orderraden.

### <a name="create-order-set-4"></a>Skapa orderuppsättning 4

#### <a name="sales-orders-4-1-and-4-2"></a>Försäljningsorder 4-1 och 4-2

1. Skapa två identiska försäljningsorder som har följande inställningar:

    - **Kundkonto:** *US-003*

1. Lägg till en orderrad med följande inställningar:

    - **Artikelnummer:** *A0001* (en artikel som inget **Kod 4**-filter tilldelas till)
    - **Kvantitet:** *1.00*

1. Välj **Lager \> Bokning** och välj sedan **Reservera parti** i åtgärdsfönstret för att reservera orderraden.

#### <a name="sales-orders-4-3-and-4-4"></a>Försäljningsorder 4-3 och 4-4

1. Skapa två identiska försäljningsorder som har följande inställningar:

    - **Kundkonto:** *US-004*

1. Lägg till en orderrad med följande inställningar:

    - **Artikelnummer:** *A0001* (en artikel som inget **Kod 4**-filter tilldelas till)
    - **Kvantitet:** *1.00*

1. Välj **Lager \> Bokning** och välj sedan **Reservera parti** i åtgärdsfönstret för att reservera orderraden.

#### <a name="sales-orders-4-5-and-4-6"></a>Försäljningsorder 4-5 och 4-6

1. Skapa två identiska försäljningsorder som har följande inställningar:

    - **Kundkonto:** *US-007*
    - **Plats:** *6*
    - **Lagerställe:** *61*
    - **Pool:** *ShipCons*

1. Lägg till en orderrad med följande inställningar:

    - **Artikelnummer:** *A0001* (en artikel som inget **Kod 4**-filter tilldelas till)
    - **Kvantitet:** *1.00*

1. Välj **Lager \> Bokning** och välj sedan **Reservera parti** i åtgärdsfönstret för att reservera orderraden.

#### <a name="sales-orders-4-7-and-4-8"></a>Försäljningsorder 4-7 och 4-8

1. Skapa två identiska försäljningsorder som har följande inställningar:

    - **Kundkonto:** *US-007*
    - **Plats:** *6*
    - **Lagerställe:** *61*
    - **Pool:** Lämna detta fält tomt.

1. Lägg till en orderrad med följande inställningar:

    - **Artikelnummer:** *A0001* (en artikel som inget **Kod 4**-filter tilldelas till)
    - **Kvantitet:** *1.00*

1. Välj **Lager \> Bokning** och välj sedan **Reservera parti** i åtgärdsfönstret för att reservera orderraden.

## <a name="use-the-load-planning-workbench-to-create-loads-and-release-them-to-the-warehouse"></a>Använd workbench för lastplanering för att skapa beläggningar och släppa dem till lagerstället

Följ dessa steg för att skapa en beläggning för varje orderuppsättning som du har skapat för scenariot och sedan släppa den till lagerstället.

1. Gå till **Hantering av lagerställe \> Beläggningar \> Workbench för lastplanering**.
1. På fliken **Försäljningsrader** letar du upp och markerar alla försäljningsorderrader från en av orderuppsättningar som du skapat för det här scenariot.
1. I åtgärdsfönstret väljer du **tillgång och efterfrågan**, väljer **Lägg till \> Till ny beläggning** om du vill lägga till valda orderlinjer i en ny beläggning.
1. I dialogrutan **Malltilldelning för beläggning**, i fältet **ID för beläggningsmall**, väljer du en beläggningsmall som exempelvis *Stnd Load Template*.
1. Välj **OK** för att stänga dialogrutan. 
1. I avsnittet **Beläggningar** söker du upp samt väljer den beläggning du just skapat.
1. Välj **Släpp \> Släpp till lagerställe** om du vill frisläppa den valda beläggningen till lagerstället.
1. Upprepa den här proceduren för samtliga de tre andra orderuppsättningar som du skapat för det här scenariot.

## <a name="verify-the-shipments"></a>Verifiera leveranserna

Med följande procedur kan du verifiera de leveranser som har skapats eller uppdaterats som ett resultat av leveranskonsolideringen. Granska varje orderuppsättning som du har skapat för det här scenariot, och granska sedan de underavsnitt som följer för att se till att du har fått de förväntade resultaten.

1. Gå till **Lagerstyrning \> Leveranser \> Alla leveranser**.
1. Sök och välj önskad leverans.
1. Om en konsolideringspolicy användes när leveransen skapades eller uppdaterades, bör du se den i fältet **Konsolideringspolicy för leverans**.

### <a name="release-order-set-1-in-one-load"></a>Frisläpp orderuppsättning 1 i en (1) beläggning

Två leveranser bör ha skapats:

- Den första leveransen innehåller tre rader och har skapats med hjälp av konsolideringspolicyn *CustomerMode* för leverans.
- Den andra leveransen, som inte använder transportsättet *Flygfrakt* skapades med hjälp av konsolideringspolicyn *CustomerOrderNo* för leverans.

### <a name="release-order-set-2-in-one-load"></a>Frisläpp orderuppsättning 2 i en (1) beläggning

Tre leveranser bör ha skapats:

- Den första leveransen innehåller de *brandfarliga* artiklarna.
- Var och en av de två andra leveranserna innehåller en rad som har artikeln *explosiv*.

### <a name="release-order-set-3-in-one-load"></a>Frisläpp orderuppsättning 3 i en (1) beläggning

Två leveranser bör ha skapats:

- Den första leveransen innehåller orderrader från den försäljningsorder där fältet **Kundrekvisition** har värdet *1*.
- Den andra leveransen innehåller orderrader från den försäljningsorder där fältet **Kundrekvisition** har värdet *2*.

### <a name="release-order-set-4-in-one-load"></a>Frisläpp orderuppsättning 4 i en (1) beläggning

Fyra leveranser bör ha skapats:

- Rader från två försäljningsorder för kundkonto *US-003* grupperades till en enda leverans med hjälp av leveranskonsolideringspolicyn *Orderpool*.
- Rader från två försäljningsorder för kundkonto *US-004* grupperades till en enda leverans med hjälp av leveranskonsolideringspolicyn *Orderpool*.
- Rader från försäljningsorder 4-5 och 4-6 för kundkonto *US-007* grupperades till en enda leverans med hjälp av leveranskonsolideringspolicyn *Orderpool*.
- Rader från försäljningsorder 4-7 och 4-8 för kundkonto *US-007* grupperades till en enda leverans med hjälp av leveranskonsolideringspolicyn *CrossOrder*.

## <a name="additional-resources"></a>Ytterligare resurser

- [Policyer för leveranskonsolidering](about-shipment-consolidation-policies.md)
- [Konfigurera policyer för leveranskonsolidering](configure-shipment-consolidation-policies.md)
