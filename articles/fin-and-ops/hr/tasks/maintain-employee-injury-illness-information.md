---
title: Underhålla information om medarbetares skador och sjukdomar
description: Vi rekommenderar att du slutför uppgiftsguiden Ställ in skador och sjukdomar först eftersom en del av inställningsinformationen används här.
author: andreabichsel
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: HRMInjuryIncident, HcmWorkerLookUp
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7324a1ce08bfe07a7ef96f4a733ebd44cd392ba6
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2019
ms.locfileid: "1510415"
---
# <a name="maintain-employee-injury-and-illness-information"></a>Underhålla information om medarbetares skador och sjukdomar

[!include [task guide banner](../../includes/task-guide-banner.md)]

Vi rekommenderar att du slutför uppgiftsguiden Ställ in skador och sjukdomar först eftersom en del av inställningsinformationen används här. 



Registreringen av den här uppgiften omfattar de grundläggande stegen för att skapa ett skade- eller sjukdomsärende. Förutom att följa information om skadan eller sjukdomen finns det en ärendestatus som dessutom följs.  Ärendet har som standard en öppen status.  Statusarna kan hanteras via menyn Ärendestatus i programfältet högst upp i formuläret.

1. Gå till Personal > Arbetare > Skador och sjukdomar > Skade- eller sjukdomsincidenter.
2. Klicka på Ny.
3. I fältet Ärendebeskrivning, skriv ett värde.
    * Exempel: handledskada  
4. I fältet Arbetare, ange eller välj ett värde.
    * Exempel: Ahmed Barnett  
5. I fältet Datum och tid för incident, ange datum och tid.
    * Exempel: 2016-01-20 kl. 10:00  
6. I fältet Typ av skada eller sjukdom, ange eller välj ett värde.
    * Exempel:  Brott  
7. I fältet Kroppsdel, ange eller välj ett värde.
    * Exempel:  Handled  
8. I fältet Resultattyp, ange eller välj ett värde.
    * Exempel:  Terapi  
9. I fältet Rapporterat datum och rapporterad tid, ange datum och tid.
    * Datumet och tiden som rapporteras måste infalla senare än datumet och tiden för incidenten.  
10. I fältet Person som rapporterade ärendet, ange eller välj ett värde.
    * Detta kan vara medarbetaren eller ett annat vittne till incidenten.  Exempel: Ahmed Barnett  
11. Expandera avsnittet Incident.
12. I fältet Var incidenten inträffade, skriv ett värde.
    * Exempel: lagerställe  
13. Välj Ja i fältet På arbetsplatsen.
    * Välj ja om incidenten inträffade på arbetsplatsen.  
14. I fältet Datum och tid då arbetet började, ange datum och tid.
    * Ange datumet och tiden då den påverkade individen började arbeta, innan incidenten inträffade.  
15. I fältet Medarbetarens jobb eller uppgift, skriv ett värde.
    * Ange jobbet eller uppgiften som arbetaren utförde när incidenten inträffade.  Exempel: lastning av lådor  
16. I fältet Orsak till incident, ange ett värde.
    * Ange orsaken till incidenten.  Exempel: halkade på vått golv  
17. I fältet Allvarlighetsnivå, ange eller välj ett värde.
18. I fältet Åtgärd som ska utföras, ange ett värde.
    * Exempel: städa upp spill omedelbart  
19. I fältet Förväntade dagar borta från arbetet, ange ett nummer.
    * Ange antal dagar som personen förväntas vara borta från arbetet.  När personen kommer tillbaka till arbetet, uppdatera fältet Dagar borta från arbetet med den verkliga antalet frånvarodagar.  
20. Expandera avsnittet Kostnader för skadan eller sjukdomen.
21. Klicka på Lägg till.
22. Ange ett datum i fältet Datum.
23. I fältet Kostnadstyp, ange eller välj ett värde.
    * Exempel: terapi. Du kan även ange ett belopp och koppla all stödjande dokumentation såsom fakturor eller en läkares anteckningar till kostnaden.  
24. Klicka på Lägg till.
25. Ange ett datum i fältet Datum.
26. I fältet Kostnadstyp, ange eller välj ett värde.
    * Exempel: läkare  
27. Expandera avsnittet Behandlingar av skada eller sjukdom.
28. Klicka på Lägg till.
29. I fältet Behandlingsdatum, ange datum och tid.
30. I fältet Behandlingstyp, ange eller välj ett värde.
    * Exempel: spjäla  
31. Du kan även välja Ja för avsnittet Besök på akutmottagning.
32. I fältet Behandlingskommentarer, ange ett värde.
    * Exempel: spjälad under två veckor  
33. Skriv ett värde i fältet Läkarens namn.
    * Example: doktor Anderson  
34. I fältet Behandlingsanläggning och plats, ange ett värde.
    * Exempel: Elm St. akutmottagningen  
35. I fältet Behandlingsdetaljer, ange ett värde.
    * Exempel: röntgenundersökning bekräftar fraktur, spjälning måste göras  
36. Klicka på Spara.
    * Ärendets status kan när som helst uppdateras.  Ange ärendet till pågående om behandlingen av sjukdomen eller skadan pågår.  När du stänger incidenten kan du bara lägga till eller ta bort kostnader, behandlingar eller arkiveringar som är relaterade till incidenten.  Öppna ärendet på nytt för att ändra annan information.  

