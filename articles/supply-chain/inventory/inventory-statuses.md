---
title: Lagerstatus
description: "Det här avsnittet innehåller en beskrivning av hur du kan använda lagerstatusar för att kategorisera och spåra lagret."
author: MarkusFogelberg
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: EcoResStorageDimensionGroup, WHSInventStatus
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 21331
ms.assetid: b35f495f-de4f-48a0-9d09-4d06781d7650
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 5caa5620db428f18d451fdfe2aeae9e2a76a24f8
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="inventory-statuses"></a>Lagerstatus

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller en beskrivning av hur du kan använda lagerstatusar för att kategorisera och spåra lagret.

Du kan använda lagerstatusar för att kategorisera lagret. Du kan sedan initiera rätt åtgärder, till exempel påfyllnad eller platsarbete.

Nedan följer några exempel på hur du kan använda lagerstatus:

-   Skapa lagerstatusar för lagerbehållning, inkommande transaktioner och utgående transaktioner.
-   Ange en standardlagerstatus för lagerställetransaktioner.
-   Ändra en lagerstatus för artiklar före införsel, under införsel, eller när artiklarna inlagras under lagerrörelser.
-   Använd en lagerstatus för prissättning av artiklar som har returnerats och för att planera artikeldisponering vid huvudplaneringen.

En lagerstatus är en av dimensionerna i lagringsdimensionsgruppen. Lagerstatusar kan kategoriseras som tillgängliga eller inte tillgängliga, och du kan använda parametern **Lagerspärr** om du vill spärra artiklar som har en otillgänglig lagerstatus. Artiklar med en blockerad status betraktas som fysiskt lager och kan inte användas i en produktionsorder, försäljningsorder, överföringsorder eller en utgående transaktion.

Du kan använda lagerställeartiklar med tillgänglig eller inte tillgänglig lagerstatus för inkommande arbete. Till exempel skapar du en tillgänglig status med namnet **Klart**, en otillgänglig status med namnet **Skadat** och en blockerad status med namnet **Spärrad**. När du skapar en inköpsorder för inlevererade eller returnerade artiklar och om sådana artiklar skadas, kan du ändra lagerstatus på de artiklarna till **Skadat** på inköpsorderraden. När artiklarna har kommit, anges statusen automatiskt till **Spärrad**. Om du skannar de skadade artiklarna med hjälp av en mobil enhet kan Microsoft Dynamics 365 for Finance and Operations använda platsdirektiv och arbetsmallar för att visa information om lämpliga platser eller platsintervall där du kan placera artiklarna. För returnerade artiklar skapas utleveranstypen **Reservation** på sidan **Lagertransaktioner**.

För utgående arbete, använd artiklar med tillgänglig lagerstatus. Om det finns artiklar med statusen **Trasig** och huvudplaneringen körs på dessa artiklar, betraktas artiklarna som saknade och lagret fylls automatiskt på.

När du har ställt in lagerstatusarna kan du ange standardlagerstatus för en plats, en artikel och ett lagerställe. Du kan även ange en standardstatus för försäljningsorder, överföring och inköpsorder. Standardstatusen för försäljningsorder och utgående överföringsorder kan inte ha alternativet **Lagerspärr** med värdet **Ja**. Lagerstatusen, som ärvs från standardinställningarna för en plats, ett lagerställe, en artikel, en inköpsorder, överföringsorder eller försäljningsorder, kan ändras genom att använda den mobila enheten eller på försäljningsorderraden, inköpsorderraden eller överföringsorderraden.

Planera täckning för artiklar med lagerstatusen tillgänglig genom att välja alternativet **Disponera per dimension** för en lagringsdimension på sidan **Lagringsdimensionsgrupper**. När du öppnar guiden **Artikeldisponering** visas artiklar som har en tillgänglig status på sidan **Status**. Välj lagerstatus ID för de tillgängliga lagerstatus för att skapa disponeringsinställningar för artiklarna. Baserat på disponeringsinställningarna kan du beräkna artikelbehov och prognostisera tillgång och efterfrågan på tillgängliga artiklar under huvudplaneringen. Du kan inte skapa inställningar för artikeldisponering med en blockerad lagerstatus. Alternativt kan du använda sidan **Artikeldisponering** om du vill skapa eller ändra artikeldisponeringsparametrarna.

