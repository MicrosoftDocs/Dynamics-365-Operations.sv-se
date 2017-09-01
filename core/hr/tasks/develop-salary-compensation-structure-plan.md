--- 
title: "Utveckla struktur och planer för lön/kompensation"
description: "Den här uppgiftsguiden är en genomgång av processen att skapa en fast kompensationsplan och låta medarbetare anmäla sig till planen med hjälp av berättiganderegler."
author: kherr75
manager: AnnBe
ms.date: 06/10/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: rschloma
ms.search.scope: Operations
ms.search.region: Global
ms.author: kherr
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: 7182a3babf356f14dc80100e72b0f44f7c53502d
ms.contentlocale: sv-se
ms.lasthandoff: 07/28/2017

---
# <a name="develop-salarycompensation-structure-and-plans"></a>Utveckla struktur och planer för lön/kompensation

[!include[task guide banner](../../includes/task-guide-banner.md)]

Den här uppgiftsguiden är en genomgång av processen att skapa en fast kompensationsplan och låta medarbetare anmäla sig till planen med hjälp av berättiganderegler. Demonstrationdataföretaget som används för att skapa den här uppgiften är USMF, och uppgiften är avsedd för kompensations- och förmånsansvariga.


## <a name="create-fixed-compensation-plan"></a>Skapa fast kompensationsplan
1. Klicka på Kompensationshantering.
2. Klicka på Planer för fast kompensation.
3. Klicka på Ny.
4. Ange ett värde i fältet Plan.
5. Ange ett värde i fältet Beskrivning.
6. Ange ett datum i fältet Giltighetsdatum.
7. Välj om den fasta kompensationsplanen är en band-, grad- eller stegplan i fältet Typ.
8. Kryssrutan Rekommendation tillåts fungerar som ett standardvärde för de åtgärder som läggs till i den här planen i en processhändelse.  Om du tillåter rekommendationer kan du åsidosätta det beräknade riktlinjebeloppet när du bearbetar kompensation.
9. Med Tolerans utanför intervallet kan du ange hur du vill hantera kompensationbelopp som ligger utanför det angivna kompensationsstrukturintervallet för den angivna nivån.  Om Tolerans utanför intervallet är Ingen tillåts alla kompensationbelopp.  En Mjuk tolerans varnar användaren om kompensationbeloppet är mindre än det lägsta referenspunktbeloppet för nivån eller större än det högsta beloppet för nivån. Användaren kan ignorera varningen och fortsätta.  En Hård tolerans genererar ett fel om en medarbetares kompensation anges utanför den minsta och högsta nivån för referenspunkten och justerar automatiskt en medarbetares kompensation så att den är inom intervallet.
10. Fältet Anställningsregel används när en kompensationsprocesshändelse körs för att beräkna medarbetarens kompensation.  Om Anställningsregel är Procent beräknas en ökning som är proportionell mot tidslängden som arbetaren har varit anställd i cykeln.
11. Ange ett värde i fältet Valuta.
12. Ange eller välj ett värde i fältet Lönesatskonvertering.
13. Visa avsnittet Matris för utnyttjande inom löneintervall.
    * Lägg eventuellt till poster med intervallutnyttjande för att få medarbetare att komma snabbare till mittpunkten och långsammare till maxvärdet i ett intervall.  
14. Vid den här punkten måste du spara den fasta kompensationsplanen om du vill aktivera knappen Ställ in kompensation och fortsätta definiera din kompensationsstruktur för planen.  Klicka på Spara.
15. Klicka på Ställ in kompensation.
    * Det finns tre sätt att skapa en kompensationsstruktur. 1: Skapa en helt ny struktur genom att välja en uppsättning referenspunkter och lägga till nivåer om du vill skapa dina egna strukturer. 2: Kopiera en kompensationsstruktur från en befintlig plan som utgångspunkt och ändra den för den nya planen. 3: Välj ett befintligt kompensationsrutnät. Om kompensationsrutnätet redan har använts i en annan plan kommer ändringar som görs i rutnätet att återspeglas i den andra planen.  
16. Markera alternativet Skapa ny från befintlig kompensationsmatris.
17. Ange eller välj ett värde i fältet Kopiera från rutnät.
    * Du kan även ändra namnet på det nya kompensationsrutnätet, som skapas som en kopia av det valda rutnätet.  
18. Klicka på OK.
19. Klicka på Massändra.
    * Massändringar låter dig underhålla kompensationsmatrisbeloppen genom att du anger procent eller ett fast belopp som ökning för en eller flera nivåer och/eller referenspunkter.  
20. Ange ett tal i fältet Justeringsbelopp.
21. Markera eller avmarkera alla rader i listan.
22. Klicka på Använd i rutnät.
23. Stäng sidan.
    * När en kompensationsstruktur har skapats eller valts kan du välja vilken av referenspunkterna som ska användas som kontrollpunkt för den fasta kompensationsplanen.  Kontrollpunkten används för att beräkna en medarbetares jämförelsekvot för löneberäkning.  
24. Ange eller välj ett värde i fältet Kontrollpunkt.
25. Stäng sidan.

## <a name="create-an-eligibility-rule-for-the-new-fixed-compensation-plan"></a>Skapa en berättiganderegel för den nya fasta kompensationsplanen
    * Den nya fasta kompensationsplanen kan inte tilldelas en medarbetare förrän berättiganderegler har definierats för planen.  
1. Klicka på Berättiganderegler.
2. Klicka på Ny.
3. Ange ett värde i fältet Berättigande.
4. Ange ett värde i fältet Beskrivning.
5. Ange ett datum i fältet Giltighetsdatum.
    * Berättiganderegler används både för fasta och variabla kompensationsplaner.  Välj vilken typ av plan den här uppsättningen av berättiganderegler är till för i fältet Typ.  
6. I fältet Plan, ange eller välj ett värde.
    * Markera det villkor som en medarbetare måste uppfylla för att kunna berättigas till kompensationsplanen. Villkor kan vara en avdelning, en fackförening, en plats (kompensationregion), ett jobb, en funktion, en jobbtyp eller en viss kompensationsnivå. En medarbetare måste uppfylla alla angivna villkor för att kunna berättigas till kompensationsplanen. Om inget villkore anges är alla medarbetare berättigade till kompensationsplanen. Om en medarbetare inte uppfyller kriteriet som ställts in i berättiganderegeln, eller en berättiganderegel inte har ställts in för en kompensationsplan, kommer kompensationsplanen inte att visas i sökningen när du skapar en post med fast kompensation för en medarbetare.  
7. Stäng sidan.
8. Stäng sidan.

