---
title: "Systemgruppering i en öppen arbetslista"
description: "Det här avsnittet beskriver hur du filtrerar den öppna arbetslistan på en mobil enhet."
author: Mirzaab
manager: AnnBe
ms.date: 05/26/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Core, Operations
ms.custom: 269384
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 0c68d544fec985f325e6472203533f23948cc9b4
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="system-grouping-on-an-open-work-list"></a>Systemgruppering i en öppen arbetslista

[!include[banner](../includes/banner.md)]

Genom att använda ett systemgrupperingsfält kan de filtrera en öppen arbetslista utan att behöva redigera menyalternativet mobil enhet.
Där det går att tillämpa fungerar systemgrupperingen för att filtrera en arbetslista i ett fält för en enskild arbetsrubrik. Du kan inte använda systemgruppering för att filtrera på radnivåfält.

## <a name="set-up-system-grouping-on-an-open-work-list"></a>Ställa in systemgruppering i en öppen arbetslista
Använd dessa steg för att ställa in systemgruppering i en öppen arbetslista.

-   Från ett menyalternativ för en mobil enhet, välj **Läge: indirekt** och **Aktivitetskod: Visa öppna arbetslista**. Följande alternativ blir tillgängliga: Dessa alternativ krävs för systemgruppering av en öppen arbetslista. 

| Alternativ        | beskrivning   | 
| ------------- | ------------- |
| Tillåta systemgruppering   | Möjliggör systemgruppering för ett menyalternativ i en vald arbetslista.| 
| Fält för systemgruppering   | Endast tillgängligt om **Tillåt systemarbete** anges till **Ja**. Välj det fält som bestämmer hur plockningsarbete för arbetare ska grupperas. Om du till exempel väljer fältet **ShipmentId** kommer arbetstagare att skanna leverans-ID:t för att gruppera plockningsarbetet. Allt arbete för leveransen tilldelas sedan till arbetaren. Detta fält kräver att du skapar ett menyalternativ som ska använda befintligt arbete som grupperas av systemet. Använd fältet **Etikett för systemgruppering** för att informera arbetaren om vad denne ska skanna. |
| Etikett för systemgruppering   | Endast tillgängligt om **Tillåt systemarbete** anges till **Ja**. Ange text för att informera arbetstagaren om vad som ska skannas när plockningsarbetet grupperas . Om du till exempel använder fältet **ShipmentId** för att gruppera plockningarbete efter leverans kan du ange Leverans-ID i fältet. Detta fält kräver att du skapar ett menyalternativ som ska använda befintligt arbete som grupperas av systemet. Du måste också välja fältet som du vill gruppera efter i fältet **Systemgruppering**.|

