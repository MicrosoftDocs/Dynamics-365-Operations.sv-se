---
title: "Navigeringsökning"
description: "Det här avsnittet innehåller en beskrivning av hur du använder sökfunktionen för att navigera till olika sidor i Microsoft Dynamics 365 for Finance and Operations."
author: aneesmsft
manager: AnnBe
ms.date: 04/27/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, Developer, IT Pro
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.custom: 25991
ms.assetid: eef0676f-c4b1-490e-a032-e9c8580f3fea
ms.search.region: Global
ms.author: aneesa
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 6159f78e57752b9519ccf88677a7fc9010ada35a
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="navigation-search"></a>Navigeringsökning

[!include[banner](../includes/banner.md)]


Det här avsnittet innehåller en beskrivning av hur du använder sökfunktionen för att navigera till olika sidor i Microsoft Dynamics 365 for Finance and Operations.

Finance and Operations innehåller funktioner för många olika branscher och vertikaler. Programmet innehåller ett antal områden och sidor som hjälper dig att utföra olika uppgifter. För att snabbt hitta de sidor de behöver för att slutföra dina uppgifter kan du använda funktionen för navigeringssökning. 

Använd funktionen genom att klicka på ikonen **Sök** för att öppna rutan **Sök**. Du kan då skriva en eller flera ord i rutan. Systemet söker ögonblickligen efter relevanta sidor i programmet som matchar orden som du har angett. Du kan till exempel skriva "leverantörsfaktura" och sedan visar systemet resultat som matchar detta. 

**Notering:** Rutan **Sök** hjälper dig att hitta och navigera till sidor. Den hjälper dig inte att hitta specifika data eller åtgärder. 

[![sökrutan](media/navigation-search.png "sökrutan") 

## <a name="quickly-navigate-to-a-particular-page"></a>Navigera snabbt till en viss sida
Navigeringsökningen fungerar även som ett bra sätt att snabbt navigera till en viss sida. Till exempel om du är en leverantörsreskontraansvarig som ofta använder sidan **betalningsjournal** kan du ange "betalningsjournal" i **sökrutan**. Eftersom indata är en exakt matchning för sidrubriken visas sidan högst upp i sökresultaten, och du kan snabbt navigera dit. 

Sökresultatlistan visar sidrubriken samt navigeringssökvägen. Här visas platsen för sidan i programmet. Det hjälper dig även att skilja mellan två eller flera liknande sidor i resultaten. 

När du söker efter en sida matchas dina uppgifter mot sidrubriken samt dess navigeringssökväg. Om du till exempel anger "fordran" i **sökrutan** visas resultaten för sidorna som är tillgängliga för dig i området kundreskontra även om sidrubrikerna inte inkluderar ordet "fordran". 

## <a name="quickly-navigate-to-a-page-based-on-the-technical-form-name"></a>Navigera snabbt till en sida baserat på tekniska formulärnamn
Navigeringssökfunktionen innehåller även en begärd funktion för avancerade användare: förmågan att snabbt navigera till en sida som baseras på det tekniska formulärnamnet. Många användare är bekanta med systemet så att de vet vilka exakta formulärnamn de arbetar med. Om du är en av dessa användare, kan du ange **formulär:** följt av namnet på det formulär du söker efter. Om du till exempel anger **formulär: levfaktura**, kommer sökresultaten att visa alla sidor där formulärnamnet börjar med. **levfaktura** 

## <a name="administration-and-security"></a>Administration och säkerhet
Från ett administrations- och säkerhetsperspektiv visar navigeringsökningen bara två typer av resultat:

-   Sidor som aktiverats i den aktuella konfigurationen (med konfigurationsnycklar).
-   Sidor som användaren har åtkomst till baserat på användarens roll.

Listan med sökresultat begränsas till tio objekt. Om du inte hittar vad du söker efter i resultaten, försök att begränsa eller uppdatera indata. 

## <a name="development"></a>Utveckling 
Från ett utvecklingsperspektiv är navigeringssökfunktionen mycket lätt att utnyttja, eftersom det inte finns någon faktiskt fördröjning mellan distributionen av menyalternativ och deras förmåga att visas i sökresultat. Så länge som menyalternativen länkas till från antingen navigeringsfönstret eller instrumentpanelen kommer dessa automatiskt att bli sökbara. 

