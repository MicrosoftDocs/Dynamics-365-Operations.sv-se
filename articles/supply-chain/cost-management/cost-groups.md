---
title: Kostnadsgrupper
description: "Kostnadsgrupper utgör grunden för segmentering och analysering av kostnadsbidraget i en tillverkad artikels beräknade kostnad, till exempel kostnadsbidragen för material, arbete och omkostnader. Kostnadsgruppssegmentering har flera synonymer inom tillverkningen, till exempel kostnadsuppdelning eller kostnadsklassificering."
author: AndersGirke
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BOMCostGroup
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 50871
ms.assetid: 1855f744-f73f-4fa8-8290-a7ee126d368b
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 022cca99bc5ad1f4c023b0b7aba748a2ef6b1d60
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---

# <a name="cost-groups"></a>Kostnadsgrupper

[!include[banner](../includes/banner.md)]


Kostnadsgrupper utgör grunden för segmentering och analysering av kostnadsbidraget i en tillverkad artikels beräknade kostnad, till exempel kostnadsbidragen för material, arbete och omkostnader. Kostnadsgruppssegmentering har flera synonymer inom tillverkningen, till exempel kostnadsuppdelning eller kostnadsklassificering. 

Kostnadsgruppssegmentering har flera synonymer inom tillverkningen, till exempel kostnadsuppdelning eller kostnadsklassificering. Kostnadsgruppssegmentering kan fylla flera syften. Nedan följer några exempel:

-   Den kan segmentera kostnader för olika typer av material, till exempel ingredienser och förpackningsmaterial för konserverade produkter, baserat på de kostnadsgrupper som tilldelas artiklarna.
-   Den kan segmentera kostnader för olika typer av verksamhetsresurser, till exempel olika typer av arbete eller maskiner, baserat på de kostnadsgrupper som har tilldelats till kostnadskategorier som relaterar till verksamhetsresurser och flödesoperationer.
-   Den kan segmentera kostnader för inställningstid och körning i flödesoperationer, baserat på de kostnadsgrupper som tilldelas kostnadskategorierna som relateras till flödesoperationerna.
-   Den kan segmentera kostnader för olika typer av omkostnader, till exempel arbetsrelaterade och maskinrelaterade omkostnader, baserat på de kostnadsgrupper som tilldelas indirekta kostnader i kostnadsredovisningsinställningarna.
-   Den kan fungera som bas för beräkning av olika typer av tillverkningsomkostnader i inställningarna för kostnadsredovisning. Denna omkostnad kan innehålla olika typer av omkostnader relaterade till flödesinformationen om verksamhetsresurser eller för information om inställningstid och körtid. Tillverkningsomkostnader kan också relateras till kostnadsbidragen för komponentmaterial, som återspeglar en resurssnål tillverkningsfilosofi som eliminerar behovet av flödesinformation.

Kostnadsgruppssegmentering tillämpas på en tillverkad artikels beräknade kostnad oavsett om den kostnaden baseras på standardkostnader eller planerade kostnader. Sidan **Sammanfattning** visar den här segmenteringen efter kostnadsgrupp, nivå eller både kostnadsgrupp och nivå. 

Förmågan att behålla kostnadsgruppssegmentering över flera nivåer i en produktstruktur kallas *uppdelning*. Uppdelning gäller bara för tillverkade artiklar med en lagermodell för standardkostnad. Utan uppdelning behandlas kostnaden för en tillverkad komponent som ett materialkostnadsbidrag. Lagerparametern för kostnadsuppdelning efter redovisning anger att kostnadsgruppsegmenteringen ska behållas över flera nivåer i standardkostnadsberäkningar. Döremot, om en policy inte har några nivåer gäller kostnadsgruppsegmenteringen bara för en enskild nivåberäkning. Till exempel sidan **Kostnader samlade efter kostnadsgrupp** visar kostnadsgruppssegmenteringen över flera nivåer för standardkostnadsartiklar. 

Kostnadsgruppssegmentering kan också tillämpas på varianter av en standardkostnadsartikel. En andra lagerparameter definierar om varianterna ska identifieras efter kostnadsgrupp, eller bara sammanfattas. 

En kostnadsgrupp kan tilldelas en kostnadsgruppstyp och ett beteende för extra segmenteringssyften.

-   **Typ av kostnadsgrupp** − Varje kostnadsgrupp måste tilldelas en kostnadsgruppstyp, som bestämmer kostnadsgruppen som hänför sig till direkt material, direkt tillverkning, eller direkt outsourcing eller utse den som indirekt eller odefinierad. En kostnadsgrupp som är utsedd som direkt material kan tilldelas artiklar. En kostnadsgrupp för direkttillverkning kan tilldelas kostnadskategorier. En direktkontrakterad kostnadsgrupp kan tilldelas till en serviceprodukttyp som gör att du kan klassificera kostnader som är associerade med tjänstinköpet till legotillverkningsaktiviteter. En indirekt kostnadsgrupp kan tilldelas indirekta kostnader för tillägg eller tariffer. En kostnadsgrupp som är odefinierad kan tilldelas artiklar, kostnadskategorier eller indirekta kostnader. Tilldelningen av en kostnadsgrupptyp fyller flera syften. Först begränsar det kapaciteten att tilldela en kostnadsgrupp och visa en lista över tillämpliga kostnadsgrupper. För det andra innehåller det ytterligare segmentering för rapporteringsändamål. För det tredje kan den användas för att tilldela redovisningskonton för avvikelser.
-   **Beteende** − Varje kostnadsgrupp kan också tilldelas ett beteende för att ange att kostnadsgruppen ska gälla fasta kostnader eller variabla kostnader. En kostnadsgrupp som har ett null-värde för beteende behandlas som en variabel kostnad. Tilldelningen av beteende har bara ett rapporteringssyfte. Kostnader kan till exempel visas med segmentering av fasta och variabla kostnader i kostnadsredovisningen, och på sidan**Kostnader samlade efter kostnadsgrupp**. Om du tilldelar ett avkastningsmål i form av en procentsats till varje kostnadsgrupp ger strukturlisteberäkningen ett föreslaget försäljningspris utifrån en kostnad plus pålägg-metod.





