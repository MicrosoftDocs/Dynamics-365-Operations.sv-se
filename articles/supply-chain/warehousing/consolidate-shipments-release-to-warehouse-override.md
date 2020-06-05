---
title: Konsolidera leveranser när policyn för leveranskonsolidering åsidosätts från sidan Släpp till lagerställe
description: Detta ämne innehåller ett scenario där en eller flera försäljningsrader måste släppas manuellt till lagerstället från sidan Släpp till lagerställe, och den systemdefinierade policyn för leveranskonsolidering måste åsidosättas före frisläppandet.
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
ms.openlocfilehash: 23379b76367336157edad1bf2e534bf0f10799cb
ms.sourcegitcommit: 8a2127c5af6cdbda30ccc1f9bef9bd4ab61e9e50
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/18/2020
ms.locfileid: "3383868"
---
# <a name="consolidate-shipments-when-the-shipment-consolidation-policy-is-overridden-from-the-release-to-warehouse-page"></a>Konsolidera leveranser när policyn för leveranskonsolidering åsidosätts från sidan Släpp till lagerställe

[!include [banner](../includes/banner.md)]

Detta ämne innehåller ett scenario där en eller flera försäljningsrader måste släppas manuellt till lagerstället från sidan **Släpp till lagerställe**, och den systemdefinierade policyn för leveranskonsolidering måste åsidosättas före frisläppandet. Det kan krävas en åsidosättning av policyn för leveranskonsoliderings om en order som exempelvis normalt sett inte konsolideras med öppna leveranser nu måste konsolideras med öppna leveranser.

Under scenariot kommer du att skapa en uppsättning försäljningsorder och sedan åsidosätta standardpolicyn för leveranskonsolidering innan du släpper orderna i lagerstället.

## <a name="make-demo-data-available"></a>Gör demodata tillgängliga

Scenariot i detta ämne innehåller referensvärden och -poster som ingår i den standarddemodata som finns för Microsoft Dynamics 365 Supply Chain Management. Om du vill använda de värden som finns här på samma sätt som i övningarna måste du arbeta i en miljö där demonstrationsdata har installerats samt ställa in den juridiska personen på **USMF** innan du börjar.

## <a name="set-up-shipment-consolidation-policies-and-product-filters"></a>Ställ in policyer och produktfilter för leveranskonsolidering

Det scenario som beskrivs här förutsätter att du redan har aktiverat funktionen, gjort övningarna i [Konfigurera policyer för leveranskonsolidering](configure-shipment-consolidation-policies.md) samt har skapat de policyer och andra poster som beskrivs där. Var noga med att göra övningarna innan du fortsätter med det här scenariot.

## <a name="create-the-sales-orders-for-this-scenario"></a>Skapa försäljningsorder för det här scenariot

1. Gå till **Kundreskontra \> Order \> Alla försäljningsorder** och skapa sedan tre identiska försäljningsorder med följande inställningar:

    - **Kundkonto:** *US-002*

1. Lägg till en orderrad med följande inställningar:

    - **Artikelnummer:** *A0001* (en artikel som inget **Kod 4**-filter tilldelas till)
    - **Kvantitet:** *1.00*

1. Välj **Lager \> Bokning** och välj sedan **Reservera parti** i åtgärdsfönstret för att reservera orderraden.

## <a name="release-the-sales-orders-from-the-release-to-warehouse-page"></a>Frisläpp försäljningsorder från sidan Släpp till lagerställe

Följ dessa steg om du vill åsidosätta policyn för leveranskonsolidering under frisläppandet till lagerstället.

1. Gå till **Lagerstyrning \> Släpp till lagerställe \> Släpp till lagerställe**.
1. I det övre fönstret väljer du den förstaförsäljnings order som du har skapat för det här scenariot.
1. Välj **Lägg till** om du vill lägga till raden om frisläppande till lagerstället. Observera att konsolideringspolicyn *Standard* för leveranser tillämpas i det nedre fönstret.
1. I det nedre fönstret väljer du **Välj ny konsolideringspolicy för leverans**.
1. Välj en policy som möjliggör konsolidering med andra öppna leveranser tillhörande samma policy. Välj till exempel policyn *CustomerOrderNo*.
1. Välj **Släpp till lagerställe**.
1. Välj den andra och tredje försäljningsorder som du skapat för detta scenario.
1. Välj **Lägg till** om du vill lägga till rader om frisläppande till lagerstället. Observera att policyn *Standard* tillämpas i det nedre fönstret.
1. Markera den andra raden och sedan, i fältet **Välj ny konsolideringspolicy för leverans**, policyn *CustomerORderNo*.
1. Välj **Släpp till lagerställe** för båda raderna.

## <a name="verify-the-shipments"></a>Verifiera leveranserna

Två leveranser bör ha skapats:

- Den första leveransen innehåller två rader och har skapats med hjälp av konsolideringspolicyn *CustomerOrderNo* leverans.
- Den andra leveransen innehåller en rad och har skapats med hjälp av konsolideringspolicyn *Standard* för leverans.

Följ de här stegen för att granska de leveranser som har skapats.

1. Gå till **Lagerstyrning \> Leveranser \> Alla leveranser**.
1. Sök och välj önskad leverans.
1. I fältet **Policy för leveranskonsolidering** granskar du den konsolideringspolicy som användes när leveransen skapades.

## <a name="additional-resources"></a>Ytterligare resurser

- [Policyer för leveranskonsolidering](about-shipment-consolidation-policies.md)
- [Konfigurera policyer för leveranskonsolidering](configure-shipment-consolidation-policies.md)