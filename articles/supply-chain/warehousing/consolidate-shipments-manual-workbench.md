---
title: Konsolidera leveranser genom att använda workbench för leveranskonsolidering
description: Det här ämnet innehåller ett scenario där flera order frigörs till lagerstället och sedan konsolideras till leveranser senare genom att använda workbench för leveranskonsolidering.
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
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: v-olbara
ms.search.validFrom: 2020-05-01
ms.dyn365.ops.version: 10.0.6
ms.openlocfilehash: b1a2c9506b4444fc98a9e4f0389cbd69db4ce052
ms.sourcegitcommit: 8a2127c5af6cdbda30ccc1f9bef9bd4ab61e9e50
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/18/2020
ms.locfileid: "3383865"
---
# <a name="consolidate-shipments-by-using-the-shipment-consolidation-workbench"></a>Konsolidera leveranser genom att använda workbench för leveranskonsolidering

[!include [banner](../includes/banner.md)]

Det här ämnet innehåller ett scenario där flera order frigörs till lagerstället och sedan konsolideras till leveranser senare genom att använda workbench för leveranskonsolidering.

## <a name="make-demo-data-available"></a>Gör demodata tillgängliga

Scenariot i detta ämne innehåller referensvärden och -poster som ingår i den standarddemodata som finns för Microsoft Dynamics 365 Supply Chain Management. Om du vill använda de värden som finns här på samma sätt som i övningarna måste du arbeta i en miljö där demonstrationsdata har installerats samt ställa in den juridiska personen på **USMF** innan du börjar.

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a>Ställ in policyer och produktfilter för leveranskonsolidering

Det scenario som beskrivs här förutsätter att du redan har aktiverat funktionen, gjort övningarna i [Konfigurera policyer för leveranskonsolidering](configure-shipment-consolidation-policies.md) samt har skapat de policyer och andra poster som beskrivs där. Var noga med att göra övningarna innan du fortsätter med det här scenariot.

## <a name="turn-on-the-manual-shipment-consolidation-feature"></a>Aktivera funktionen för manuell leveranskonsolidering

Innan du kan använda funktionen *Manuell leveranskonsolidering* måste du aktivera den i systemet. Administratörer kan använda inställningarna [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den. I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:

- **Modul:** *Lagerstyrning*
- **Funktionsnamn:** *Manuell leveranskonsolidering*

Som omnämnts i [Konfigurera policyer för leveranskonsolidering](configure-shipment-consolidation-policies.md) måste du också aktivera funktionen *Konsolidera leverans* innan du kan skapa policyer. Du bör dock redan ha slutfört detta steg.

## <a name="create-the-sales-orders-for-this-scenario"></a>Skapa försäljningsorder för det här scenariot

Börja med att skapa en samling med försäljningsorder som du kan arbeta med. Du måste arbeta med ett lagerställe som är aktiverat för avancerade processer för lagerställe (WMS). Såvida inte ett annat lagerställe uttryckligen anges måste samma lagerställe användas för var och en av följande orderuppsättningar.

Gå till **Kundreskontra \> Order \> Alla försäljningsorder** och skapa en samling försäljningsorder som har de inställningar som beskrivs i följande underavsnitt.

### <a name="create-order-set-1"></a>Skapa orderuppsättning 1

#### <a name="sales-orders-1-1-and-1-2"></a>Försäljningsorder 1-1 och 1-2

1. Skapa två identiska försäljningsorder som har följande inställningar:

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
    - **Leveranssätt:** *Flygfrakt*

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

## <a name="release-the-orders-to-the-warehouse"></a>Släpp order till lagerställe

Följ dessa steg för att släppa varje försäljningsorder som du har skapat för scenariot till lagerstället.

1. Gå till **Kundreskontra \> Order \> Alla försäljningsorder**.
1. Hitta och markera den försäljningsorder som du vill släppa.
1. På fliken **Lagerställe** i åtgärdsfönstret väljer du **Åtgärder \> Släpp till lagerställe** för att släppa vald försäljningsorder.
1. Upprepa den här proceduren för alla andra försäljningsorder som du skapat för det här scenariot.

## <a name="consolidate-the-shipments-by-using-the-shipment-consolidation-workbench"></a>Konsolidera leveranserna genom att använda workbench för leveranskonsolidering

1. Gå till **Lagerstyrning \> Släpp till lagerställe \> Workbench för leveranskonsolidering**.
1. I åtgärdsfönstret väljer du **Redigera fråga**.
1. På fliken **Intervall** i dialogrutan för frågeredigerare väljer du **Lägg till** för att lägga till en rad med följande inställningar i rutnätet:

    - **Register:** *Försäljningsorder*
    - **Fält:** *Försäljningsorder*
    - **Kriterier:** Ange en kommaavgränsad lista med försäljningsordernummer för varje orderuppsättning som du har skapat för det här scenariot.

1. Välj **OK** om du vill spara din fråga och stänga dialogrutan.
1. I åtgärdsfönstret väljer du **Konsolidera leveranser**.
1. Välj alla leveranser och välj sedan **Konsolidera** i åtgärdsfönstret.

## <a name="verify-the-shipments"></a>Verifiera leveranserna

Med följande procedur kan du verifiera de leveranser som har skapats eller uppdaterats som ett resultat av leveranskonsolideringen. Granska varje orderuppsättning som du har skapat för det här scenariot, och granska sedan de underavsnitt som följer för att se till att du har fått de förväntade resultaten.

1. Gå till **Lagerstyrning \> Leveranser \> Alla leveranser**.
1. Sök och välj önskad leverans.
1. Om en konsolideringspolicy användes när leveransen skapades eller uppdaterades, bör du se den i fältet **Konsolideringspolicy för leverans**.

### <a name="related-shipments-for-order-set-1"></a>Relaterade leveranser för orderuppsättning 1

Två leveranser bör ha skapats:

- Den första leveransen innehåller tre rader och har skapats med hjälp av konsolideringspolicyn *CustomerMode* för leverans.
- Den andra leveransen, som inte använder transportsättet *Flygfrakt* skapades med hjälp av konsolideringspolicyn *CustomerOrderNo* för leverans.

### <a name="related-shipments-for-order-set-2"></a>Relaterade leveranser för orderuppsättning 2

Tre leveranser bör ha skapats:

- Den första leveransen innehåller de *brandfarliga* artiklarna.
- Var och en av de två andra leveranserna innehåller en rad som har artikeln *explosiv*.

### <a name="related-shipments-for-order-set-3"></a>Relaterade leveranser för orderuppsättning 3

Två leveranser bör ha skapats:

- Den första leveransen innehåller orderrader från den försäljningsorder där fältet **Kundrekvisition** har värdet *1*.
- Den andra leveransen innehåller orderrader från den försäljningsorder där fältet **Kundrekvisition** har värdet *2*.

### <a name="related-shipments-for-order-set-4"></a>Relaterade leveranser för orderuppsättning 4

Fyra leveranser bör ha skapats:

- Rader från två försäljningsorder för kund *US-003* grupperades till en enda leverans med hjälp av leveranskonsolideringspolicyn *Orderpool*.
- Rader från två försäljningsorder för kund *US-004* grupperades till en enda leverans med hjälp av leveranskonsolideringspolicyn *Orderpool*.
- Rader från försäljningsorder 4-5 och 4-6 för kund *US-007* grupperades till en leverans med hjälp av leveranskonsolideringspolicyn *Orderpool*.
- Rader från försäljningsorder 4-7 och 4-8 för kund *US-007* grupperades till en leverans med hjälp av leveranskonsolideringspolicyn *CrossOrder*.

## <a name="additional-resources"></a>Ytterligare resurser

- [Policyer för leveranskonsolidering](about-shipment-consolidation-policies.md)
- [Konfigurera policyer för leveranskonsolidering](configure-shipment-consolidation-policies.md)
