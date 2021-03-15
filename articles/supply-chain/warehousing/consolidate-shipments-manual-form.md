---
title: Konsolidera leveranser manuellt via sidan Konsolidera leveranser
description: Det här ämnet innehåller ett scenario där flera order frigörs till lagerstället och sedan konsolideras senare genom att använda sidan Konsolidera leveranser.
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
ms.openlocfilehash: 0e580253de0d787b721c2f729ecc96db56b91af0
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4983027"
---
# <a name="consolidate-shipments-manually-by-using-the-consolidate-shipments-page"></a>Konsolidera leveranser manuellt via sidan Konsolidera leveranser

[!include [banner](../includes/banner.md)]

Det här ämnet innehåller ett scenario där flera order frigörs till lagerstället och sedan konsolideras senare genom att använda sidan **Konsolidera leveranser**.

## <a name="make-demo-data-available"></a>Gör demodata tillgängliga

Scenariot i detta ämne innehåller referensvärden och -poster som ingår i den standarddemodata som finns för Microsoft Dynamics 365 Supply Chain Management. Om du vill använda de värden som finns här på samma sätt som i övningarna måste du arbeta i en miljö där demonstrationsdata har installerats samt ställa in den juridiska personen på **USMF** innan du börjar.

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a>Ställ in policyer och produktfilter för leveranskonsolidering

Det scenario som beskrivs här förutsätter att du redan har aktiverat funktionen, gjort övningarna i [Konfigurera policyer för leveranskonsolidering](configure-shipment-consolidation-policies.md) samt har skapat de policyer och andra poster som beskrivs där. Var noga med att göra övningarna innan du fortsätter med det här scenariot.

## <a name="create-the-sales-orders-for-this-scenario"></a>Skapa försäljningsorder för det här scenariot

Börja med att skapa en samling med försäljningsorder som du kan arbeta med. Du måste arbeta med ett lagerställe som är aktiverat för avancerade processer för lagerställe (WMS). Såvida inte ett annat lagerställe uttryckligen anges måste samma lagerställe användas för var och en av följande orderuppsättningar.

Gå till **Kundreskontra \> Order \> Alla försäljningsorder** och skapa en samling försäljningsorder som har de inställningar som beskrivs i följande underavsnitt.

### <a name="create-sales-orders-1-and-2"></a>Skapa försäljningsorder 1 och 2

1. Skapa två identiska försäljningsorder som har följande inställningar:

    - **Kundkonto:** *US-007*
    - **Pool:** *ShipCons*

1. Lägg till en orderrad med följande inställningar:

    - **Artikelnummer:** *A0001* (en artikel som inget **Kod 4**-filter tilldelas till)
    - **Kvantitet:** *1.00*

1. Välj **Lager \> Bokning** och välj sedan **Reservera parti** i åtgärdsfönstret för att reservera orderraden.

### <a name="create-sales-orders-3-and-4"></a>Skapa försäljningsorder 3 och 4

1. Skapa två identiska försäljningsorder som har följande inställningar:

    - **Kundkonto:** *US-007*
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

## <a name="consolidate-shipments"></a>Konsolidera leveranser

1. Gå till **Lagerstyrning \> Leveranser \> Alla leveranser**.
1. Sök efter och välj en leverans som skapades när försäljningsorder 1 släpptes till lagerstället. (Dess fält **Konsolideringspolicy för leverans** ska vara inställt på *Orderpool*.)
1. På fliken **Leveranser** i åtgärdsfältet väljer du **Leveranser \> Konsolidera leveranser**.
1. Verifiera de leveranser som föreslås för konsolidering. Endast en leverans som har samma policy bör föreslås för konsolidering.
1. Stäng sidan **Leveranskonsolidering**.
1. Sök efter och välj en leverans som skapades när försäljningsorder 3 släpptes till lagerstället. (Dess fält **Policy för leveranskonslidering** bör anges som *Standard*.)
1. På fliken **Leveranser** i åtgärdsfältet väljer du **Leveranser \> Konsolidera leveranser**.
1. Bekräfta att inga leveranser föreslås för konsolidering.
1. Välj **Visa filter**.
1. I fönstret **Filter** tar du bort filtret **Ordernummer** och väljer sedan **Verkställ**.
1. Verifiera de leveranser som föreslås för konsolidering. Endast en leverans som har samma policy bör föreslås för konsolidering.

## <a name="additional-resources"></a>Ytterligare resurser

- [Policyer för leveranskonsolidering](about-shipment-consolidation-policies.md)
- [Konfigurera policyer för leveranskonsolidering](configure-shipment-consolidation-policies.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]