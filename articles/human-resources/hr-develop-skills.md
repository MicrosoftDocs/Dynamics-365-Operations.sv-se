---
title: Konfigurera färdigheter
description: Du kan spåra arbetarens färdigheter i Dynamics 365 Human Resources. Du kan även ange de färdigheter som krävs för ett visst jobb.
author: twheeloc
manager: tfehr
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: HcmSkill, HcmSkillGapProfile, HcmSkillMapping, HcmSkillType, HcmEmployeeDevelopmentWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.custom: 3361
ms.assetid: c2ce94c0-933d-4edb-822c-7f0e7b49e4ee
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Human Resources
ms.openlocfilehash: 13206bb3c961f001620e8b65a8b1bb39bf95ee49
ms.sourcegitcommit: 89655f832e722cefbf796a95db10c25784cc2e8e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/31/2022
ms.locfileid: "8075081"
---
# <a name="configure-skills"></a>Konfigurera färdigheter

> [!IMPORTANT]
> Funktionerna som anges i det här avsnittet är för närvarande tillgängliga för Personal-kunder i ekonomiinfrastrukturen.  


Du kan spåra arbetarens färdigheter i Dynamics 365 Human Resources. Du kan även ange de färdigheter som krävs för ett visst jobb.

Exempel på färdigheter som du kan följa inkluderar:

- Handledning – förmåga att handleda andra i arbetet.
- Ledarskap – förmåga att leda medarbetare och affärsdomäner.
- Planering – Förmåga att se framåt, att formulera visionsinstruktioner och att se till att de genomförs.
- HTML – Förmågan att skriva HTML-kod.

Om du inte redan har ställt in färdighetstyper och värderingsmodeller måste du lägga till några innan du skapar färdigheter.

Följande personer kan ange färdigheter för en arbetare:

- Medarbetare kan själv ange färdigheter i självbetjäning för medarbetare. Dessa färdigheter kräver godkännande av chef.
- Chefer kan ange färdigheter för sina anställda. Du kan skapa ett arbetsflöde där dessa färdigheter godkänns automatiskt.

## <a name="create-a-skill-type"></a>Skapa en färdighetstyp

Färdighetstyper är kategorier som enskilda kompetenser ingår i, t.ex. Administration eller Försäljning.

1. I arbetsytan **Personalutveckling**, välj **Länkar**.

2. Under **Kompetensinställningar**, välj **Färdighetstyper**.

3. Välj **Ny**.

4. Fyll i följande fält:

   - **Färdighetstyp**: Ange ett namn på färdighetstypen.
   - **Beskrivning**: Ange en beskrivning på färdighetstypen.

5. Välj **Spara**.

## <a name="create-a-rating-model"></a>Skapa en bedömningsmodell

Bedömningsmodeller gör det enklare att utvärdera en persons faktiska färdighetsnivå, den nivå de ska arbeta för att uppnå eller den färdighetsnivå som krävs för ett jobb. Varje nivå i en bedömningsmodell tilldelas en faktor.

1. I arbetsytan **Personalutveckling**, välj **Länkar**.

2. Under **Kompetensinställningar**, välj **Bedömningsmodell**.

3. Välj **Ny**.

4. Fyll i följande fält:

   - **Bedömning**: Ange ett namn på bedömningsmodellen, till exempel **Kompetenser**.
   - **Beskrivning**: Ange en beskrivning av värderingsmodellen, till exempel **färdighetsvärderingar**.

5. I avsnittet **Nivåer**, välj **Ny**. Fyll i följande fält för varje nivå du vill lägga till:

   - **Nivå**: Ange ett namn för nivån.
   - **Beskrivning**: Ange en beskrivning av nivån.
   - **Faktor**: Ange ett faktorvärde från 0-9. Faktorer hjälper till att normalisera förfrågningar om partier av färdighetsluckor som använder olika värderingsmodeller. Varje nivå måste ha en unik faktor. Nivåer med högre faktorvärden innehåller mer vikt i en bedömningsmodell.

   Fortsätt att lägga till nivåer om det behövs. Du kan ange upp till 10 nivåer för varje bedömningsmodell.

6. Välj **Spara**.

## <a name="create-a-skill"></a>Skapa en färdighet

Innan du kan tilldela en färdighet eller skapa en färdighetsmappningssökning eller en kompetensprofil, måste du ange information om färdigheterna på sidan **Färdigheter**. För varje kompetens kan du välja en kompetenstyp och en bedömningsmodell.

1. I arbetsytan **Personalutveckling**, välj **Länkar**.

2. Under **Kompetensinställningar**, välj **Färdigheter**.

3. Välj **Ny**.

4. Fyll i följande fält:

   - **Färdighet**: Ange ett namn på färdighet.
   - **Beskrivning**: Ange en beskrivning på färdighet.
   - **Bedömning**: Välj den bedömningsmodell som du vill använda för denna färdighet.
   - **Färdighetstyp**: Välj från listan över färdighetstyper.

5. Välj **Spara**.

## <a name="see-also"></a>Se även

[Ange färdigheter](hr-develop-enter-skills.md)<br>
[Mappa kompetenser](hr-develop-map-skills.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
