---
title: Lagerstatus
description: Det här avsnittet innehåller en beskrivning av hur du kan använda lagerstatusar för att kategorisera och spåra lagret.
author: MarkusFogelberg
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EcoResStorageDimensionGroup, WHSInventStatus, WHSWarehouseStatusChange
audience: Application User
ms.reviewer: kamaybac
ms.custom: 21331
ms.assetid: b35f495f-de4f-48a0-9d09-4d06781d7650
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0c4cad56389c7a8fd6d37591c1ff335fff715707
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "5001834"
---
# <a name="inventory-statuses"></a>Lagerstatus

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller en beskrivning av hur du kan använda lagerstatusar för att kategorisera och spåra lagret.

## <a name="set-up-and-use-inventory-statuses"></a>Ställ in och använd lagerstatus

Du kan använda lagerstatusar för att kategorisera lagret. Du kan sedan initiera rätt åtgärder, till exempel påfyllnad eller platsarbete.

Nedan följer några exempel på hur du kan använda lagerstatus:

- Skapa lagerstatusar för lagerbehållning, inkommande transaktioner och utgående transaktioner.
- Ange en standardlagerstatus för lagerställetransaktioner.
- Ändra en lagerstatus för artiklar före införsel, under införsel, eller när artiklarna inlagras under lagerrörelser.
- Använd en lagerstatus för prissättning av artiklar som har returnerats och för att planera artikeldisponering vid huvudplaneringen.

En lagerstatus är en av dimensionerna i lagringsdimensionsgruppen. Lagerstatusar kan kategoriseras som tillgängliga eller inte tillgängliga, och du kan använda parametern **Lagerspärr** om du vill spärra artiklar som har en otillgänglig lagerstatus. Artiklar med en blockerad status betraktas som fysiskt lager och kan inte användas i en produktionsorder, försäljningsorder, överföringsorder eller en utgående transaktion.

Du kan använda lagerställeartiklar med tillgänglig eller inte tillgänglig lagerstatus för inkommande arbete. Till exempel skapar du en tillgänglig status med namnet *Klart*, en otillgänglig status med namnet *Skadat* och en blockerad status med namnet *Spärrad*. När du skapar en inköpsorder för inlevererade eller returnerade artiklar och om sådana artiklar skadas, kan du ändra lagerstatus på de artiklarna till *Skadat* på inköpsorderraden. När artiklarna har kommit, anges statusen automatiskt till *Spärrad*. Om du skanna de skadade artiklarna med hjälp av en mobil enhet, kan Supply Chain Management använda platsdirektiv och arbetsmallar för att visa information om en lämplig plats eller intervall av platser där du kan placera artiklarna. För returnerade artiklar skapas utleveranstypen *Reservation* på sidan **Lagertransaktioner**.

För utgående arbete, använd artiklar med tillgänglig lagerstatus. Om det finns artiklar med statusen *Trasig* och huvudplaneringen körs på dessa artiklar, betraktas artiklarna som saknade och lagret fylls automatiskt på.

När du har ställt in lagerstatusarna kan du ange standardlagerstatus för en plats, en artikel och ett lagerställe. Du kan även ange en standardstatus för försäljningsorder, överföring och inköpsorder. Standardstatusen för försäljningsorder och utgående överföringsorder kan inte ha alternativet **Lagerspärr** med värdet *Ja*. Lagerstatusen, som ärvs från standardinställningarna för en plats, ett lagerställe, en artikel, en inköpsorder, överföringsorder eller försäljningsorder, kan ändras genom att använda den mobila enheten eller på försäljningsorderraden, inköpsorderraden eller överföringsorderraden.

Planera täckning för artiklar med lagerstatusen tillgänglig genom att välja alternativet **Disponera per dimension** för en lagringsdimension på sidan **Lagringsdimensionsgrupper**. När du öppnar guiden **Artikeldisponering** visas artiklar som har en tillgänglig status på sidan **Status**. Välj lagerstatus ID för de tillgängliga lagerstatus för att skapa disponeringsinställningar för artiklarna. Baserat på disponeringsinställningarna kan du beräkna artikelbehov och prognostisera tillgång och efterfrågan på tillgängliga artiklar under huvudplaneringen. Du kan inte skapa inställningar för artikeldisponering med en blockerad lagerstatus. Alternativt kan du använda sidan **Artikeldisponering** om du vill skapa eller ändra artikeldisponeringsparametrarna.

## <a name="change-inventory-statuses"></a>Ändra lagerstatusar

Du kan ändra lagerstatus antingen med hjälp av sidan **Behållning efter plats** eller genom att använda periodiska uppgiften *lagerstatusändring*.

- När du använder periodiska uppgiften *Ändring av lagerstatus* kan du välja vilka poster som ska inkluderas och ange att aktiviteten ska köras i batchen i önskat intervall.
- Om du vill ändra lagerstatus som en ad hoc-process går du till sidan **Behållning efter plats** välj relevanta poster och sedan knappen **Ändra lagerstatus**.

> [!NOTE]
> Med funktionen *Ändra lagerstatus för artiklar som styrs av spårningsdimensioner* låter dig ändra lagerstatus för objekt som styrs av spårningsdimensioner, inklusive möjligheten att endast uppdatera valda poster. Använd [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) om du vill aktivera funktionen efter behov. När funktionen är aktiverad kan du göra följande:
>
> - På sidan **behållning per plats** kan du gruppera rader baserat på visade dimensioner med hjälp av knappen **Visa dimensioner** och ändra status för de valda raderna.
> - På sidan **behållning per plats** kan du välja flera poster och sedan använda knappen **Ändra lager status** för att ändra alla på en gång.
> - I den periodiska uppgiften **Ändring av lagerstatus** kan du filtrera efter spårningsdimensioner.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]