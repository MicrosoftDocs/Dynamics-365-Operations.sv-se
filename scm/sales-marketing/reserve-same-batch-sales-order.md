---
title: "Reservera samma parti för en försäljningsorder"
description: "Det här avsnittet innehåller en beskrivning av hur du ställer in en produkt om du vill tillåta lagerreservation mot en enda lagerbatch."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: EcoResProductDetailsExtended, EcoResStorageDimensionGroup, EcoResTrackingDimensionGroup, InventBatch, InventModelGroup, PdsAskSameLotForm, PdsCustSellableDays
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 28911
ms.assetid: 5823d75e-f839-46dd-beb3-e09b79fc8aa4
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: e9f48e6e057517bb7632e8c855f4439c446f3d30
ms.lasthandoff: 03/31/2017


---

# <a name="reserve-the-same-batch-for-a-sales-order"></a>Reservera samma parti för en försäljningsorder

Det här avsnittet innehåller en beskrivning av hur du ställer in en produkt om du vill tillåta lagerreservation mot en enda lagerbatch.

Samma batchreservation gör att du kan du reservera lager för en försäljningsorderrad mot en enda lagerbatch. Till exempel kan en kund som beställer tapeter begära att hela ordern ska komma från samma parti för att undvika skillnader i trycket. Om du vill ange att en produkt ska använda samma batchreservation, måste följande inställningar vara aktiva i artikelmodellgruppen, spårningsdimensionsgruppen och lagringsdimensionsgruppen som du tilldelar produkten:

-   **Artikelmodellgrupper** – Artikelmodellgruppen måste ha fälten **Urval från samma batch** och **Konsolidera behov** markerade i fältgruppen **Reservation** för lagerpolicyer.
-   **Spårningsdimensionsgrupper** – Spårningsdimensionsgruppen måste ha fältet **Disponera per dimension** markerat för batchnumret.
-   **Lagringsdimensionsgrupper** – Lagringsdimensionsgruppen måste ha fältet **Disponera per dimension** markerat för **Plats** och **Lagerställe**.

När du reserverar lager för en produkt på en försäljningsorderrad som har ställts in för samma batchval, försöker Microsoft Dynamics 365 for Operations att reservera den beställda kvantiteten från en enda lagerbatch. Alla specifika batchattributkrav beaktas också. Om kvantiteten inte kan fyllas från en enda batch visas sidan **Konflikt: samma batchreservation**. På den här sidan beskrivs problemen och även de åtgärder du måste vidta om du vill fortsätta med reservationen. Följande villkor kan hindra batchen från att reserveras:

-   Batchdispositionskoden har **Blockera reservation** för försäljningar som flaggas som **Spärrad**
-   Batchen har förfallit, baserat på utgångsdatumet och eventuella gällande försäljningsdagar för kunden. Artikeln kan fortfarande användas för reservationer om artikelmodellgruppen för artikeln är FEFO – först utgått, först ut (First Expiry First Out) – och datumkontrollerat, och om bäst före-datumet har valts som plockvillkor.
-   Batchen inte har tillräcklig hållbarhetstid kvar, baserat på utgångsdatum och bäst före-datum, plus eventuella försäljningsdagar för kund.


