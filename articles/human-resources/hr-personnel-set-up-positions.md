---
title: Ställ in befattningar
description: Detta ämne beskriver hur befattningar är ett viktigt element på den lägre nivån i en organisationshierarki.
author: twheeloc
ms.date: 10/28/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, HcmWorkforceWorkspace, HcmWorkerActivityChart, HcmAllWorkersListPart, HcmPosition, HcmPositionNewPosition, HcmJobLookup, HcmPositionReportsToDialog, HcmPositionLookup, FinancialDimensionDefaultTemplatesLookup, DimensionLookup, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: f4b9f09db8465cc55c9b0c4dc403c2c7a3647d7e
ms.sourcegitcommit: e91a1797192fd9bc4048b445bb5c1ad5d333d87d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/01/2021
ms.locfileid: "7728728"
---
# <a name="set-up-positions"></a>Ställ in befattningar

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Befattningar är ett viktigt element i den lägre nivån i en organisationshierarki. En befattning är ett exempel på ett enskilt jobb. Befattningen "Försäljningschef (öst)" är exempelvis bara en de befattningar som associeras med jobbet "Försäljningschef." En befattning finns på en avdelning och kan ha endast har en arbetare associerad med den. I den här uppgiften ska du gå igenom de steg som behövs för att skapa en befattning. Uppgiften är avsedd för en personalresursspecialist.

1. Välj **Personalhantering**.
2. Välj **Lediga befattningar**.
3. Välj **Ny** för att öppna listrutan.
4. I fältet **Jobb** anger eller välje du ett värde.

    Fälten **Jobbeskrivning**, **Rubrik** och **Heltidsmotsvarande anställningsfaktor** kopieras automatiskt fårn valt jobb till befattningen.

5. ResolveChanges jobbet.
6. Välj **Skapa befattning**.
7. I fältet **Avdelning** anger eller väljer du ett värde.
8. I fältet **Befattningstyp** anger eller väljer du ett värde.
9. I fältet **Kompensationsregion** anger eller väljer du ett värde.

    Fältet **Kompensationsregion** bestämmer reglerna för kompensationberättigande och de fasta ökningsbudgeterna som gäller för en medarbetare i den befattningen.

10. I fältet **Tillgänglig för tilldelning** anger du datum och tid.
11. Visa avsnittet **Befattningens varaktighet**.

    Befattningens varaktighet anges som standard utifrån aktivering och avyttringsdatum som angetts tidigare.

12. Visa avsnittet **Rapporter till befattning**.

    När du tilldelar en anställd till en befattning som rapporterar till en annan befattning, skapar du en direktrapporteringsrelation mellan arbetarna som tilldelas de två befattningarna.

13. Välj **Ny** för att öppna dialogrutan i listrutan.
14. I fältet **Rapporter till** anger eller väljer du ett värde.
15. Markera **Skapa**.
16. Visa avsnittet **Medarbetartilldelning**.
17. Visa avsnittet **Relationer**.

    Om din organisation använder en matrishierarki eller en annan anpassad hierarki, kan du ställa in befattninghierarkityper, och sedan lägga till rapporteringrelationer till befattningar för varje hierarkityp som du ställer in.

18. Markera **Lägg till**.
19. Markera vald rad i listan.
20. I fältet **Hierarkinamn** anger eller väljer du ett värde.
21. i fältet **Rapporter till befattning** anger eller väljer du ett värde.
22. Visa avsnittet **Löner**.
23. I fältet **Lönecykel** anger eller väljer du ett värde.
24. I fältet **Betalas senast** anger elelr väljer du ett värde.
25. I fältet **Ordinarie timmar per år** anger du ett nummer.

    Det värde som du anger är antalet regelbundet betalda timmar som medarbetare med den här befattningen förväntas arbeta varje år.

26. Visa avsnittet **Fackförening**.
27. Dölj avsnittet **Fackförening**.
28. Visa avsnittet **Ekonomisk dimension**.
29. I fältet **Fördelningsmall** anger eller väljer du ett värde.
30. I fältet **Avdelning** anger eller väljer du ett värde.
31. Välj **Spara**.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
