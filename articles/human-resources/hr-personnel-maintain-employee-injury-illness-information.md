---
title: Underhålla information om medarbetares skador och sjukdomar
description: I den här uppgiften beskrivs hur du skapar ett skade- eller sjukdomsfall.
author: twheeloc
ms.date: 11/03/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HRMInjuryIncident, HcmWorkerLookUp, HcmPersonnelManagementWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 06307331db4d420e99de21c0eb0b3cf1c233f0d5
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/31/2022
ms.locfileid: "8066660"
---
# <a name="maintain-employee-injury-and-illness-information"></a>Underhålla information om medarbetares skador och sjukdomar


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Vi rekommenderar att du slutför uppgiftsguiden Ställ in skador och sjukdomar först eftersom en del av inställningsinformationen används här. 



Denna uppgiftsinspelning beskriver de grundläggande stegen för att skapa ett skade- eller sjukdomsärende. Förutom detaljer om skadan eller sjukdomen spåras även en ärendestatus. Som standard har ärendena statusen **Öppen**. Du kan hantera statusen via menyalternativet **Ärendestatus** högst upp på sidan.

1. Gå till **Personal \> Medarbetare \> Skada och sjukdom \> Skade- och sjukdomsincidenter**.
2. Välj **Ny**.
3. I fältet **Ärendeeskrivning** anger du en värde (till exempel, **Handledsskada**).
4. I fältet **Medarbetare** anger eller väljer du ett värde (till exempel **Anna Boman**).
5. I fältet **Datum och tid för incident** anger du datum och tid (till exempel den 20 januari 2016, kl. 10:00).
6. I fältet **Typ av skada eller sjukdom** anger eller väljer du ett värde (till exempel **Fraktur**).
7. I fältett **Kroppsdel** anger eller väljer du ett värde (till exempel **Handled**).
8. I fältet **Resultattyp** anger eller väljer du ett värde (till exempel **Behandling**).
9. I fältet **Rapporterat datum och tid** anger du datum och tid.

    Inrapporterat datum och tid måste infalla senare än datumet och tiden för incidenten.

10. I fältet **Person som rapporterade ärendet** anger eller väljer du ett värde (till exempel **Anna Boman**).

    Angiven person kan vara medarbetaren eller ett annat vittne till incidenten.

11. I avsnittet **Incident**, i fätlet **Plats för incidenten**, anger du ett värde (till exempel **Lager**).
12. På fältet **På arbetsplatsen** väljer du **Ja** om incidenten skett på arbetsplatsområdet.
13. I fältet **Datum och tid då arbete påbörjades** anger du datum och tid då påverkad individ började arbeta innan incidenten inträffade.
14. I fältet **Medarbetares jobb eller uppgift** anger du det arbete eller den uppgift som medarbetaren utförde när incidenten inträffade (till exempel **Lasta kartonger**). 
15. I fältet **Orsak till incident** anger du incidentens orsak (till exempel **Halkade på vått golv**).
16. I fältet **Allvarlighetsnivå** anger eller väljer du ett värde.
17. I fältet **Åtgärd som ska vidtas** anger du ett värde (t.ex. **Omedelbart städa upp spill**).
18. I fältet **Förväntat antal frånvarodagar** anger du det antal dagar som individen förväntas vara borta från jobbet.

    När individen återvänder till jobbet uppdaterar du fältet **Dagar borta från jobbet** med det faktiska antal dagar som individen varit borta.

19. I avsnittet **Kostnader för skada eller sjukdom** väljer du **Lägg till**.
20. Ange ett datum i fältet **Datum.**
21. I fältet **Kostnadstyp** anger eller väljer du ett värde (till exempel **Behandling**).

    Du kan även ange ett belopp och bifoga all stödjande dokumentation till kostnaden (exempelvis fakturor eller läkares anteckningar).

22. Markera **Lägg till**.
23. Ange ett datum i fältet **Datum.**
24. I fältet **Kostnadstyp** anger eller väljer du ett värde (till exempel **Läkare**).
25. I avsnittet **Behandling för skada eller sjukdom** väljer du **Lägg till**.
26. I fältet **Behandlingsdatum** amger du datum och tid.
27. I fältet **Behandlingstyp** anger eller väljer du ett värde (till exempel **Skena**).
28. Valfritt: Ange avsnittet **Besök på akutmottagning** som **Ja**.
29. I fältet **Behandlingskommentarer** anger du ett värde (till exempel **Skena i 2 veckor**).
30. I fältet **Läkares namn** anger du ett värde (till exempel **Dr Andersson**).
31. I fältet **Behandlingsanläggning och plats** anger du ett värde (t.ex. **St Görans sjukhus**).
32. I fältet **Behandlingsdetaljer** anger du ett värde (t.ex. **Röntgen bekräftar fraktur, bär skena**).
33. Välj **Spara**.

Ärendets status kan när som helst uppdateras. Om behandlingen av skadan eller sjukdomen fortfarande pågår anger du statusen som **Pågår**. När du stänger incidenten kan du bara lägga till eller ta bort kostnader, behandlingar eller arkiveringar som är relaterade till incidenten. Om du vill ändra annan information måste du öppna ärendet på nytt.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
