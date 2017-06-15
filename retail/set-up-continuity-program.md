---
title: "Ställ in ett kontinuitetsprogram för en kundtjänst"
description: "Det här avsnittet innehåller en beskrivning av hur du ställer in ett kontinuitetsprogram för en kundtjänst."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core, Retail
ms.custom: 16081
ms.assetid: 426a9be7-a931-4780-b372-e06f6083dd60
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: c0a9eec6bdf67deca885b30082b958869e64aae2
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017


---

# <a name="set-up-a-continuity-program-for-a-call-center"></a>Ställ in ett kontinuitetsprogram för en kundtjänst

[!include[banner](includes/banner.md)]


Det här avsnittet innehåller en beskrivning av hur du ställer in ett kontinuitetsprogram för en kundtjänst.

I ett kontinuitetsprogram, som kallas också för ett återkommande orderprogram, får kunder vanliga produktleveranser enligt en fördefinierad tidsplan. Varje leverans kan innehålla olika produkter, till exempel månadens bok, eller samma produkt som skickas igen och igen. Om du vill ställa in ett kontinuitetsprogram måste du göra följande.

1.  Ange kontinuitetsparametrarna på sidan **Parametrar för kundtjänst**.
2.  Skapa ett kontinuitetsprogram som anger information, till exempel betalningsplan, leveranstid och om betalningen görs direkt. Du måste även lägga till en lista med produkter som ingår i kontinuitetsprogrammet. Varje produkt får ett händelse-ID-nummer som tilldelas i ordningsföljd med början på 1. Händelsen-ID-numret bestämmer ordningen som produkterna skickas i.
    -   Om kunder får olika produkter i varje leverans, skickas produkterna i sekventiell ordning enligt deras händelse-id:n, baserat på händelse-id:na och som börjar med den aktuella händelsen.
    -   Om kunder får likadana produkten i varje leverans, innehåller listan endast en produkt som har ett händelse-id. Samma händelsen inträffar flera gånger. Du kan ange hur många gånger varje händelse ska upprepas.

3.  Skapa en överordnad produkt som motsvarar det kontinuitetsprogram som du skapade i uppgift 2. Om du lägger till produkten till en försäljningsorder öppnas sidan **Kontinuitet**. Du kan sedan använda sidan för att skapa kontinuitetsordern. Överordnad produkt anger inte de enskilda produkter som kunden får i varje leverans.

När du har ställt in ett kontinuitetsprogram enligt beskrivningen ovan kan du skapa en kontinuitetsorder för en kund. Du kanske också måste utföra de ytterligare underhållsåtgärderna nedan.

-   **Uppdatera den aktuella händelseperioden för kontinuitet** – Ställ in ett batchjobb som informerar systemet om vad den aktuella händelseperioden är.
-   **Skapa underordnade kontinuitetsorder** – Skapa underordnade order från överordnad kontinuitetsorder.
-   **Bearbeta kontinuitetsbetalningar** – Bearbeta fakturering och meddelanden för betalningar som är associerade med kontinuitetsförsäljningsorder.
-   **Utöka kontinuitetsrader** (vid behov) – Utöka antalet gånger som en kontinuitetshändelse kan upprepas. Repetitionen av försändelser kan överskrida tidsgränsen som anges i fältet **Tröskel för upprepa kontinuitet** i kundtjänstparametrarna.
-   **Utför en kontinuitetsuppdatering** (vid behov) – Synkronisera ändringar mellan kontinuitetsprogrammet och överordnade kontinuitetsförsäljningsorder.
-   **Stäng överordnade kontinuitetsrader och kontinuitetsorder** – Stäng kontinuitetsorder.




