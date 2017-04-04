---
title: "Navigeringsökning"
description: "I den här artikeln beskrivs hur du använder sökfunktionen om du vill navigera till sidor i Microsoft Dynamics 365 för operationer."
author: aneesmsft
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, Developer, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 25991
ms.assetid: eef0676f-c4b1-490e-a032-e9c8580f3fea
ms.search.region: Global
ms.author: aneesa
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 4bb647cfd3f012efbffa93a81462c538a24ac850
ms.openlocfilehash: 87fed576f8cf358520d94f5cd5b326ff9801913a
ms.lasthandoff: 03/31/2017


---

# <a name="navigation-search"></a>Navigeringsökning

I den här artikeln beskrivs hur du använder sökfunktionen om du vill navigera till sidor i Microsoft Dynamics 365 för operationer.

Dynamics 365 för operationer finns funktioner för en mängd olika branscher och lodräta annonser. Programmet innehåller ett antal områden och sidor som hjälper dig att utföra olika uppgifter. Söker snabbt efter kan du gå igenom dina uppgifter genom att använda sökfunktionen navigering. Använd funktionen genom att klicka på ikonen **Sök** för att öppna rutan **Sök**. Du kan då skriva en eller flera ord i rutan. Systemet söker ögonblickligen efter relevanta sidor i programmet som matchar orden som du har angett. Du kan till exempel skriva "leverantörsfaktura" och sedan visar systemet resultat som matchar detta. **Notering:** Rutan **Sök** hjälper dig att hitta och navigera till sidor. Den hjälper dig inte att hitta specifika data eller åtgärder. 

[![sökrutan](./media/search-box.png)](./media/search-box.png) navigering sökfunktionen fungerar även som ett bra sätt att snabbt gå till en viss sida. Till exempel om du är en Leverantörsreskontra ansvarig som ofta används i **betalningsjournal** sida, kan du ange "betalningsjournal" i sökrutan. Eftersom indata är en exakt matchning för rubriken, sidan visas längst upp i sökresultaten kan du snabbt navigera till. 

[![sökning-för--betalningsjournal](./media/searching-for-payment-journal.png)](./media/searching-for-payment-journal.png) 

Sökresultatet innehåller en rubrik och navigeringssökvägen. På så sätt blir du medveten om platsen för sidan i programmet. Det hjälper dig även att skilja mellan två eller flera liknande sidor i resultaten. När du söker efter en sida matchas dina uppgifter mot sidrubriken samt dess navigeringssökväg. Om du anger "Kundreskontra" i till exempel den ** ** sökrutan visas resultaten för sidorna kan du få modulen Kundreskontra – även om sidrubrikerna inte innehåller ordet "Kundreskontra". 

[![Sök-för-the-word-Kundreskontra](./media/search-for-the-word-receivable.png)](./media/search-for-the-word-receivable.png) 

Från ett administrations- och säkerhetssynpunkt Sök endast visar sig navigeringsrutan:

-   Sidor som aktiverats i den aktuella konfigurationen (med konfigurationsnycklar).
-   Sidor som användaren har åtkomst till baserat på användarens roll

Listan med sökresultat begränsas till tio objekt. Om du inte hittar vad du söker efter i resultaten, försök att begränsa eller uppdatera indata. Från ett utvecklingsperspektiv är navigeringssökfunktionen mycket lätt att utnyttja, eftersom det inte finns någon faktiskt fördröjning mellan distributionen av menyalternativ och deras förmåga att visas i sökresultat. Så länge som menyalternativen länkas till från antingen navigeringsfönstret eller instrumentpanelen kommer dessa automatiskt att bli sökbara. Navigeringssökfunktionen innehåller även en begärd funktion för avancerade användare: förmågan att snabbt navigera till en sida som baseras på det tekniska formulärnamnet. Många användare är bekanta med systemet så att de vet vilka exakta formulärnamn de arbetar med. Om du är en av dessa användare, kan du ange **formulär:** följt av namnet på det formulär du söker efter. Om du till exempel anger **formulär: levfaktura**, kommer sökresultaten att visa alla sidor där formulärnamnet börjar med. **levfaktura** 

[![Sök för formuläret vendinvoice](./media/search-for-form-vendinvoice.png)](./media/search-for-form-vendinvoice.png)


