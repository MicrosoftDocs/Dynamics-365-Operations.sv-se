---
title: Reservera samma batch för en försäljningsorder
description: Det här avsnittet innehåller en beskrivning av hur du ställer in en produkt om du vill tillåta lagerreservation mot en enda lagerbatch.
author: omulvad
manager: tfehr
ms.date: 03/17/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResProductDetailsExtended, EcoResStorageDimensionGroup, EcoResTrackingDimensionGroup, InventBatch, InventModelGroup, PdsAskSameLotForm, PdsCustSellableDays
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: 28911
ms.assetid: 5823d75e-f839-46dd-beb3-e09b79fc8aa4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: omulvad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: f1e101473c5b6958c7e0fb5c5fa80dccd3d9b467
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3216032"
---
# <a name="reserve-the-same-batch-for-a-sales-order"></a>Reservera samma batch för en försäljningsorder

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller en beskrivning av hur du ställer in en produkt om du vill tillåta lagerreservation mot en enda lagerbatch.

Samma batchreservation gör att du kan du reservera lager för en försäljningsorderrad mot en enda lagerbatch. Till exempel kan en kund som beställer tapeter begära att hela ordern ska komma från samma parti för att undvika skillnader i trycket. Om du vill ange att en produkt ska använda samma batchreservation, måste följande inställningar vara aktiva i artikelmodellgruppen, spårningsdimensionsgruppen och lagringsdimensionsgruppen som du tilldelar produkten:

- **Artikelmodellgrupper** – Artikelmodellgruppen måste ha fälten **Urval från samma batch** och **Konsolidera behov** markerade i fältgruppen **Reservation** för lagerpolicyer.
- **Spårningsdimensionsgrupper** – Spårningsdimensionsgruppen måste ha fältet **Disponera per dimension** markerat för batchnumret.
- **Lagringsdimensionsgrupper** – Lagringsdimensionsgruppen måste ha fältet **Disponera per dimension** markerat för **Plats** och **Lagerställe**.

När du reserverar lager för en produkt på en försäljningsorderrad som har ställts in för samma batchval försöker systemet att reservera den beställda kvantiteten från en enda lagerbatch. Alla specifika batchattributkrav beaktas också. Om kvantiteten inte kan fyllas från en enda batch visas sidan **Konflikt: samma batchreservation**. På den här sidan beskrivs problemen och även de åtgärder du måste vidta om du vill fortsätta med reservationen. Följande villkor kan hindra batchen från att reserveras:

- Batchdispositionskoden har **Blockera reservation** för försäljningar som flaggas som **Spärrad**
- Batchen har förfallit, baserat på utgångsdatumet och eventuella gällande försäljningsdagar för kunden. Artikeln kan fortfarande användas för reservationer om artikelmodellgruppen för artikeln är FEFO – först utgått, först ut (First Expiry First Out) – och datumkontrollerat, och om bäst före-datumet har valts som plockvillkor.
- Batchen inte har tillräcklig hållbarhetstid kvar, baserat på utgångsdatum och bäst före-datum, plus eventuella försäljningsdagar för kund.

För artiklar som är kopplade till en lagringsdimensionsgrupp som har **Använd lagerstyrningsprocesser** aktiverat kan du reservera specifika batchnummer genom att använda en reservationssekvens med den lagerdimension som definierats ovanför platsdimensionen. Sidan **Batch-reservation** för försäljnings- och överföringsorderrader låter dig också välja och reservera flera rader baserat på tillgängliga batchnummer. Mer information om vad du ska göra om du använder en reservationssekvens med dimensionen för batchnumret under platsen finns i [Flexibel reservationspolicy för dimension på lagernivå](../warehousing/flexible-warehouse-level-dimension-reservation.md).
