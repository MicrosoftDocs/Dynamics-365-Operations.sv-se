---
title: Återbetala kunder
description: Det här avsnittet innehåller en beskrivning av hur du skapar återbetalningstransaktioner för en kundgrupp. Om en kund har ett kreditsaldo, kan du återbetala kunden för beloppet för saldot.
author: JodiChristiansen
manager: AnnBe
ms.date: 09/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalTransCustPaym, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14191
ms.assetid: 53533ee3-470e-458a-ac8b-3815aa4cb502
ms.search.region: Global
ms.author: jchrist
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 65ee884fb22c1a38e2d3022085fed7e3e6077d1f
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644547"
---
# <a name="reimburse-customers"></a>Återbetala kunder

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller en beskrivning av hur du skapar återbetalningstransaktioner för en kundgrupp. Om en kund har ett kreditsaldo, kan du återbetala kunden för beloppet för saldot. 

Följande tabell visar förutsättningarna som krävs och måste finnas på plats innan du startar

| Förutsättning                                                            | Beskrivning |
|-------------------------------------------------------------------------|-------------|
| Ange det minsta återbetalningsbeloppet för den juridiska personen.          | Ange minimibeloppet som går att återbetala för kundöverbetalningar på sidan **Parametrar för kundreskontra** i området **Allmänt** i fältet **Minimiåterbetalning**. |
| Du kan även: Lägg till ett leverantörskonto i varje kund som kan återbetalas. | Välj leverantörskontot för kunden på sidan **Kunder** på snabbfliken **Diverse detaljer** i fältet **Leverantörskonto**. |

När du skapar återbetalningstransaktioner, skapas en leverantörsfaktura för beloppet i kreditsaldot. Återbetalningsprocessen tar bort kreditsaldot för kundkontot och skapar ett förfallet saldo för det leverantörskonto som motsvarar kundens.

1. I Kundreskontra, kör processen **Återbetalning** (**Kundreskontra \> Periodiska uppgifter \> Återbetalning**).
2. Om du vill gruppera alla transaktioner, oavsett redovisningsdimensioner, anger du **Ja** för alternativet **Sammanfatta kund**. Om du bara vill gruppera transaktioner som har liknande redovisningsdimensioner anger du alternativet till **Nej**.
3. Välj **Inkludera kunder med utestående debettransaktioner** om du vill välja kunder som har oreglerade debiteringsbelopp.
4. Om du vill återbetala specifika kundkonton välj **Filter** på snabbfliken **Poster som ska ingå** och ange sedan kundkontona i frågan.

    Kreditbeloppen överförs till kundernas leverantörskonton och bearbetas som normala betalningar. Om en kund inte har ett leverantörskonto skapas ett engångsleverantörskonto automatiskt för den kunden.

5. Om du vill visa de återbetalningstransaktioner som har skapades använder du rapporten **Återbetalning** (**Kundreskontra \> Förfrågningar och rapporter \> Återbetalning (rapport)**).
6. Skapa en betalning för leverantörsfakturor som har skapats i återbetalningsprocessen i leverantörsreskontra. Information om hur du betalar leverantörer finns i [Översikt över leverantörsbetalning](../accounts-payable/Vendor-payments-workspace.md).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]