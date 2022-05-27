---
title: Konfigurera parametrar för arbetsytan för kostnadskontroll
description: Använd den här proceduren för att konfigurera arbetsytan Kostnadskontroll så att chefer på olika nivåer i en organisation kan få inblick i deras kostnadsobjekt, till exempel kostnadsställen och produktgrupper.
author: kfend
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CAMCostControlWorkspaceConfigurationPerUser
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kfend
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c38b6f2664426513ea46b16b4cd54d69d71d1399
ms.sourcegitcommit: 04e6c1c9400e1b582180cf3e0e4767434e736c26
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2022
ms.locfileid: "8710569"
---
# <a name="configure-cost-control-workspace-parameters"></a>Konfigurera parametrar för arbetsytan för kostnadskontroll

[!include [banner](../../includes/banner.md)]

Använd den här proceduren för att konfigurera arbetsytan Kostnadskontroll så att chefer på olika nivåer i en organisation kan få inblick i deras kostnadsobjekt, till exempel kostnadsställen och produktgrupper. Demonstrationsföretaget USP2 användes för att skapa den här inspelningen.

1. Gå till Kostnadsredovisning > Inställningar > Konfiguration av arbetsytan för kostnadsstyrning.
2. Klicka på Ny.
3. Skriv ett värde i fältet Namn.
4. Ange ett värde i fältet Beskrivning.
5. Välj Ja i fältet Publicerad.
    * Om du väljer Ja kan en användare med någon av följande roller se rapporter i arbetsytan Kostnadskontroll: kostnadsredovisningschef, kostnadsrevisor, ansvarig kostnadsredovisare och kostnadsobjektcontroller. Om du väljer Nej kan bara användare med någon av följande roller se rapporter i arbetsytan Kostnadskontroll: kostnadsredovisningschef, kostnadsrevisor och ansvarig kostnadsredovisare.  
6. Expandera avsnittet Filtrering av data.
7. Ange eller välj ett värde i fältet Kostnadsstyrenhet.
8. Ange eller välj ett värde i fältet Ursprunglig budgetversion.
9. Ange eller välj ett värde i fältet Dimensionshierarki för kostnadselement.
10. Ange eller välj ett värde i fältet Dimensionshierarki för kostnadsobjekt.
11. Expandera avsnittet Tilldela beräkningsposter.
12. Klicka på Ny.
13. Markera vald rad i listan.
14. Ange eller välj ett värde i fältet Räkenskapskalenderperiod.
15. Ange eller välj ett värde i fältet Faktisk version.
16. Expandera avsnittet Räkenskapsperioder per kolumn.
17. Välj Ja i fältet Aktuell period.
18. Expandera avsnittet Kolumner att visa för kostnader.
19. Välj Ja i fältet Fast kostnad.
20. Välj Ja i fältet Rörlig kostnad.
21. Välj Ja i fältet Totalkostnad.
22. Klicka på Spara.
23. Stäng sidan.
24. Gå till Kostnadsredovisning > Arbetsytor > Kostnadskontroll.
25. Välj ett utdrag om du vill visa fasta, rörliga, totala och oklassificerade kostnader för valda räkenskapsperioder.
26. Ange eller välj ett värde i fältet Räkenskapskalenderperiod.
27. Ange eller välj ett värde i fältet Dimensionshierarkinod för kostnadsobjekt.
    * När du har valt en dimensionshierarki för kostnadsobjekt ska du expandera kostnadselementets dimensionshierarki om du vill visa önskade kostnadsvärden. Exempelvis kan du expandera hierarkin till Tillverkningsomkostnader för att visa värdet.  



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
