---
title: "Justera personalfärdigheter med verksamhetens behov"
description: "Du kan spåra de färdigheter som anställda, sökanden eller kontaktpersoner har eller bör ha för att genomföra deras roller på ett effektivt sätt. Du kan även ange de färdigheter som krävs för ett visst jobb."
author: rschloma
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: HcmSkill, HcmSkillGapProfile, HcmSkillMapping, HcmSkillType
audience: Application User
ms.reviewer: rschloma
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 3361
ms.assetid: c2ce94c0-933d-4edb-822c-7f0e7b49e4ee
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: ae940cdbab2166d8fe3f2f396c84ed4a09c2ca7e
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017


---

# <a name="align-workforce-skills-with-business-needs"></a>Justera personalfärdigheter med verksamhetens behov

[!include[banner](includes/banner.md)]


Du kan spåra de färdigheter som anställda, sökanden eller kontaktpersoner har eller bör ha för att genomföra deras roller på ett effektivt sätt. Du kan även ange de färdigheter som krävs för ett visst jobb.

Exempel på färdigheter som du kan följa inkluderar följande:
-   Handledning - förmåga att handleda andra i arbetet.
-   Ledarskap – förmåga att leda medarbetare och affärsdomäner.
-   Planering – Förmåga att se framåt, att formulera visioner och att se till att de genomförs.
-   HTML – Förmågan att skriva HTML-kod.

Innan du kan tilldela en färdighet till en person eller ett jobb, skapa en färdighetsmappningssökning eller skapa en kompetensprofil, måste du ange information om färdigheterna på sidan **Färdigheter**. För varje kompetens kan du välja en kompetenstyp och en värderingsmodell.

## <a name="rating-models"></a>Bedömningsmodeller
Bedömningsmodeller gör det enklare att utvärdera en persons faktiska färdighetsnivå, den nivå de ska arbeta för att uppnå eller den färdighetsnivå som krävs för ett jobb. Du kan ange upp till 10 nivåer för en värderingsmodell.  Varje nivå i en värderingsmodell tilldelas en faktor.  Faktorvärdet ska användas för att normaliserar förfrågningar om partier av färdighetsluckor som använder olika värderingsmodeller.  Faktorn måste vara ett nummer mellan 0-9, och varje nivå måste ha en unik faktor.  Nivåer med högre faktorvärden innehåller mer vikt i en värderingsmodell.

## <a name="specify-job-skills"></a>Ange jobbfärdigheter
När du anger information om ett jobb, kan du ange de färdigheter som en person måste ha för att arbeta med jobbet.  Dessutom kan du ange önskad nivå för varje färdighet samt hur viktig färdigheten är. Olika jobb kan kräva olika nivåer av betydelse för samma färdighet.

## <a name="enter-skills-for-workers-applicants-or-contacts"></a>Ange kompetenser för arbetstagare, sökande eller kontakter
Du kan ange eller målfärdigheter verkliga färdigheter för anställd, sökande eller kontakter. En målfärdighet är en färdighet som en person planerar att uppnå. En faktisk färdighet är en färdighet som en person redan har.

## <a name="skill-mapping-and-skill-mapping-profiles"></a> Färdighetsmappning och Profiler för färdighetsmappning
Du kan skapa en färdighetsmappning för att hitta en anställd, sökande eller kontaktperson som är kvalificerad för en viss typ av uppgift. Färdighetsmappning letar genom färdigheter, utbildning, certifikat, förtroendeuppdrag eller projekterfarenhet och returnerar ett resultat som matchar de villkor som angetts.  Exempelvis kan det vara bra att veta vilka arbetare i organisationen som har fått sina CPA.

Färdighetsmappningsprofiler låter dig hitta nuvarande anställda eller kandidater med kvalifikationer som direkt motsvarar verksamhetens behov.  Exempelvis kan du skapa en kompetensmappningsprofil för en öppen befattning i företaget. Genom att skapa en profil för ett visst jobb och kopiera färdigheter, intyg och utbildning från det jobbet till profilen, kan du snabbt söka anställda, sökande och kontaktpersoner som matchar en eller flera av de kriterier som har angetts i profilen och visa en lista över de kandidater som har färdigheter som bäst matchar de färdigheter som krävs för jobbet.

>**Obs!** Endast anställda, sökande och kontaktpersoner som valts för inkludering i sökningar efter kompetensmappning kan visas i resultatlistan från en kompetensmappning eller inkluderas i kompetensprofil. Om du vill ta med en anställd, sökande eller kontaktperson i färdighetsmappningsökningar markerar du Ja i alternativet **Inkludera i färdighetsmappning** på följande sidor:

> + Arbetare
> + Medarbetare
> + Sökande
> + Kontakter

## <a name="skill-gap-analysis-and-skill-profile-analysis"></a>Analys av färdighetsluckor och analys av kompetensprofil
Du kan skapa en analys till färdighetsmappning profil som du vill visa en lista med kompetenserna för en anställd, sökande eller kontaktperson för ett visst datum. Du kan skapa en analys för luckor i kompetens om du vill jämföra en persons kompetenser med de kompetenser som krävs för ett visst jobb.  



<a name="see-also"></a>Se även
--------

[Personal](index.md)




