---
title: Finansiell avstämning i butiker
description: Det här ämnet beskriver ekonomisk avstämning i butiker för POS för Microsoft Dynamics 365 Commerce.
author: anpurush
manager: AnnBe
ms.date: 06/09/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ed0f77f7-3609-4330-bebd-ca3134575216
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-05-21
ms.dyn365.ops.version: ''
ms.openlocfilehash: 99c238ecfbb6cb29f4fefefdca32525b99a01dc8
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5251341"
---
# <a name="financial-reconciliation-in-retail-stores"></a>Finansiell avstämning i butiker

[!include [banner](includes/banner.md)]

I Microsoft Dynamics 365 Commerce version 10.0.10 och tidigare tillhandahåller funktionerna som kassaklienten (POS) ger för processerna i slutet av dagen i butikerna och låter butikssäljarna och cheferna utför dagliga åtgärder. De kan till exempel utföra kassaavstämningar, skift som har stängts dolt, stämma av skifttransaktioner och stänga skift. Det finns emellertid ingen möjlighet i POS att slutföra den ekonomiska informationen för skift, så att den kan användas för att bokföra det ekonomiska i Commerce-administration. Normalt är butikschefer ansvariga för att slutföra den här uppgiften. Innan de kan logga ut ett skift måste de granska informationen, göra de ändringar som behövs och slutföra summorna för det skiftet. De färdiga summorna bokförs sedan i de ekonomiska modulerna i Commerce-administration.

I Commerce version 10.0.10 och tidigare kan butikschefer granska och göra justeringar av utdragsraderna i Commerce-administration. Möjligheten är dock begränsad och butikschefer har sällan åtkomst till klienten Commerce-administration. Dessutom kan granskning och justering av butikens ekonomirapporter endast göras när ekonomirapporter skapas i Commerce-administration. Processen är dock vanligtvis en nattlig process. Därför måste butikschefer vänta på att skiftet loggas ut när ekonomirapporter för butik skapas i Commerce-administration.

I Commerce version 10.0.11 och senare kan butikschefer granska, justera och slutföra sina skift i själva kassaklienten. Dessa data används sedan för att skapa och bokföra ekonomirapporter för butiken i Commerce-administration.

> [!NOTE]
> Funktionen som är relaterad till ekonomisk avstämning i butiker fungerar bara om du aktiverar indroppningsbaserad bokföring. För mer information, se [Indroppningsbaserat orderskapande för butikstransaktioner](trickle-feed.md).

## <a name="set-up-financial-reconciliation"></a>Ställ in ekonomisk avstämning

Följ de här stegen om du vill använda funktionen för ekonomisk avstämning.

1. I arbetsytan **Funktionshantering** aktiverar du funktionen **Butiksutdrag – Indroppning**.
1. I kassafunktionsprofilen för den aktuella butiken anger du alternativet **Aktivera ekonomisk avstämning i butiken** till **Ja**.

## <a name="more-information-about-financial-reconciliation"></a>Mer information om ekonomisk avstämning

När funktionen för ekonomisk avstämning är aktiverad synkroniseras vissa av de parametrar som definieras på snabbfliken **Utdrag/stängning** på sidan **Butiker** i Commerce-administration till kanaldatabasen. Samma uppsättning av beräkningskriterier och beloppströsklar som används för butiksutdrag tillämpas.

När åtgärden **Stäng skift** anropas validerar systemet att de systemberäknade beloppen och de deklarerade beloppen matchar. Om de skiljer sig åt och skillnaden överskrider definierade tröskelvärden, tillfrågas användaren och kan göra nödvändiga justeringar.

Justeringar kan göras för varje betalningsmedel. När ett betalnings medel väljs kan användaren visa summorna för olika transaktionstyper och redigera summorna för en viss transaktionstyp. Under redigeringen visar systemet det ursprungliga beräknade beloppet och det åsidosatta beloppet för den transaktionstypen. Användaren kan också spara anteckningar som en del av redigeringsprocessen. Noteringar kan användas för granskningssyfte.

Användare kan ignorera valideringsanvisningar och meddelanden och de kan fortsätta att stänga skiftet. Om en användare däremot ignorerar valideringsfrågorna, kommer samma problem att uppstå och måste åtgärdas när de ekonomiska rapporterna i Commerce-administration bokförs.

I åtgärden **Stäng skift** i POS validerar också att alla transaktioner i offlinedatabasen synkroniseras med kanaldatabasen. Om några transaktioner inte synkroniseras får användaren ett varningsmeddelande, eftersom den här situationen kan medföra att systembeloppen beräknas felaktigt. I det här fallet kan användaren avsluta åtgärden **Stäng skift** och försöka synkronisera offlinetransaktionerna med kanaldatabasen. Alternativt kan användaren manuellt justera de systemberäknade beloppen för att redovisa de transaktioner som inte har synkroniserats, så att rätt uppsättning av ekonomiska nummer slutförs och bokförs. 

När bokföring av indroppningsutdrag används, så att bokföringen av transaktionerna skiljs från bokföring av ekonomi, kan du välja att justera de systemberäknade beloppen för saknade offlinetransaktioner. På så sätt säkerställer du att ekonomierna alltid redovisas och bokförs korrekt, oavsett vilka transaktioner som saknas. Offlinetransaktioner kan synkroniseras med kanaldatabasen och Commerce-administration och sedan bokföras senare oberoende av de ekonomiska bokföringarna.

Information om den ekonomiska avstämningen för ett skift synkroniseras till Commerce-administration med hjälp av P-jobbet.

Ekonomiska butiksutdrag i Commerce-administration beräknar inte summor för att visa detaljer på utdragsraderna. I stället används de slutna beloppen i kassaklienten för att skapa och bokföra ekonomirapporter.


[!INCLUDE[footer-include](../includes/footer-banner.md)]