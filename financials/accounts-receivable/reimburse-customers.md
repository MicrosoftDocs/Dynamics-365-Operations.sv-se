---
title: "Återbetala kunder"
description: "Det här avsnittet innehåller en beskrivning av hur du skapar återbetalningstransaktioner för en kundgrupp. Om en kund har ett kreditsaldo, kan du återbetala kunden för beloppet för saldot."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: LedgerJournalTransCustPaym, LedgerJournalTransVendPaym
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14191
ms.assetid: 53533ee3-470e-458a-ac8b-3815aa4cb502
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: fd3392eba3a394bd4b92112093c1f1f9b894426d
ms.openlocfilehash: f8a46f5d961ff7629db7f9af8f3955ddfc338736
ms.contentlocale: sv-se
ms.lasthandoff: 04/25/2017


---

# <a name="reimburse-customers"></a>Återbetala kunder

[!include[banner](../includes/banner.md)]


Det här avsnittet innehåller en beskrivning av hur du skapar återbetalningstransaktioner för en kundgrupp. Om en kund har ett kreditsaldo, kan du återbetala kunden för beloppet för saldot. 

Följande tabell visar förutsättningarna som krävs och måste finnas på plats innan du startar

| Förutsättning                                                            | Beskrivning                                                                                                                                                                                 |
|-------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Ange det minsta återbetalningsbeloppet för den juridiska personen.          | Ange minimibeloppet som går att återbetala för kundöverbetalningar på sidan **Parametrar för kundreskontra** i området **Allmänt** i fältet **Minimiåterbetalning**. |
| Du kan även: Lägg till ett leverantörskonto i varje kund som kan återbetalas. | Välj leverantörskontot för kunden på sidan **Kunder** på snabbfliken **Diverse detaljer** i fältet **Leverantörskonto**.                                           |

När du skapar återbetalningstransaktioner, skapas en leverantörsfaktura för beloppet i kreditsaldot. Återbetalningsprocessen tar bort kreditsaldot för kundkontot och skapar ett förfallet saldo för det leverantörskonto som motsvarar kundens.

1.  Kör processen **Återbetalning** i kundreskontra.
2.  Gör något av följande:
    -   Om du vill återbetala vissa kundkonton klickar du på **Välj** och anger kundkontona i frågan.
    -   Om du vill återbetala alla kundkonton klickar du på **OK**.

    Kreditbeloppen överförs till kundernas leverantörskonton och bearbetas som normala betalningar. Om en kund inte har ett leverantörskonto skapas ett engångsleverantörskonto automatiskt för den kunden.
3.  Om du vill visa de återbetalningstransaktioner som skapades använder du sidan **Återbetalning**.
4.  Skapa en betalning för leverantörsfakturor som har skapats i återbetalningsprocessen i leverantörsreskontra.





