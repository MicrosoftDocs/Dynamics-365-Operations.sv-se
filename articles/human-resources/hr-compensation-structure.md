---
title: Utveckla en struktur för kompensation
description: Den här artikeln leder dig genom att skapa en fast kompensationsplan och registrera anställda i planen genom behörighetsregler.
author: andreabichsel
manager: AnnBe
ms.date: 02/10/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: DefaultDashboard, HcmCompensationWorkspace, HcmCompFixedPlansPart, HRMCompFixedPlanTable, HRMCompCreateGridDialog, HRCCompGridView, HRMCompEligibility,  HRCCompGrid
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 124d0f7f83feebabf622f00732c25bfa0f6eccdd
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4420618"
---
# <a name="develop-a-compensation-structure"></a>Utveckla en struktur för kompensation

Den här artikeln leder dig genom att skapa en fast kompensationsplan och registrera anställda i planen genom behörighetsregler. I den här artikeln används USMF demodata och gäller kompensations- och förmånsansvariga.

## <a name="create-a-fixed-compensation-plan"></a>Skapa en fast kompensationsplan

1. Välj **Kompensationshantering**.

2. Välj **Planer för fast kompensation**.

3. Välj **Ny**.

4. I fältet **Plan** ange ett värde.

5. I fältet **Beskrivning** anger du ett värde.

6. Ange ett datum i fältet **Giltighetsdatum**.

7. I fältet **Typ** välj om den fasta kompensationsplanen är en **Band-**, **Grad-** eller **Steg**-plan.

8. Kryssrutan **Rekommendation tillåts** fungerar som ett standardvärde för de åtgärder som läggs till i den här planen i en processhändelse. Om du tillåter rekommendationer kan du åsidosätta det beräknade riktlinjebeloppet när du bearbetar kompensation.

9. Med **Tolerans utanför intervallet** kan du ange hur du vill hantera kompensationsbelopp som ligger utanför det angivna kompensationsstrukturintervallet för den angivna nivån. Om du ställer in fälten **Tolerans utanför intervallet** till **Ingen** kan du använda ett kompensationsbelopp. **Mjuk tolerans** varnar användarna om kompensationsbeloppet är lägre än minimum eller högre än de maximala referenspunktsbeloppen för den nivån. Användare kan ignorera varningen och fortsätta. En **Hård tolerans** skapar ett fel om en medarbetares kompensation anges utanför den minsta och högsta nivån för referenspunkten och justerar automatiskt en medarbetares kompensation så att den är inom intervallet.

10. Fältet **anställningsregel** beräknas en medarbetares kompensation under en processhändelse. En **Anställningsregel** av **Procent** beräknas en ökning som är proportionell mot tidslängden som arbetaren har varit anställd i cykeln.

11. Ange ett värde i fältet **Valuta**.

12. Ange eller välj ett värde i fältet **Lönesatskonvertering**.

13. Visa avsnittet **Matris för utnyttjande inom löneintervall**. Lägg eventuellt till poster med intervallutnyttjande för att få medarbetare att komma snabbare till mittpunkten och långsammare till maxvärdet i ett intervall.

14. Välj **Spara**. Då aktiveras knappen **Ställ in kompensation** och fortsätter definiera din kompensationsstruktur för planen.

15. Välj **Ställ in kompensationsplaner**. Du kan skapa en kompensationsstruktur genom att använda en av dessa tre metoder:

    - Skapa en helt ny struktur genom att välja en uppsättning referenspunkter och lägga till nivåer om du vill skapa dina egna strukturer.
    - Kopiera en kompensationsstruktur från en befintlig plan som utgångspunkt och ändra den för den nya planen.
    - Välj ett befintligt kompensationsrutnät. Om en annan plan redan använder kompensationsnätet återspeglar den andra planen alla ändringar du gör i nätet.

16. Välj **Skapa ny från befintlig kompensationsmatris**.

17. Ange eller välj ett värde i fältet **Kopiera från rutnät**. Du kan även ändra namnet på det nya kompensationsrutnätet, som skapas som en kopia av det valda rutnätet.

18. Välj **OK**.

19. Välj **Massförändring**. **Massändringar** låter dig underhålla kompensationsmatrisbeloppen genom att du anger procent eller ett fast belopp som ökning för en eller flera nivåer eller referenspunkter.

20. Ange ett tal i fältet **Justeringsbelopp**.

21. Markera eller avmarkera alla rader i listan.

22. Klicka på **Använd i rutnät**.

23. Stäng sidan. När du har skapat kompensationsstrukturen kan du välja vilka av referenspunkterna som ska användas som kontrollpunkt för den fasta kompensationsplanen. Kontrollpunkten används för att beräkna en medarbetares jämförelsekvot för löneberäkning.

24. Ange eller välj ett värde i fältet **Kontrollpunkt**.

25. Stäng sidan.

## <a name="create-an-eligibility-rule-for-the-fixed-compensation-plan"></a>Skapa en berättiganderegel för den fasta kompensationsplanen

Du kan inte tilldela en fast kompensationsplan till en anställd förrän du definierar behörighetsregler för planen.  

1. Visa **berättiganderegler**.

2. Välj **Ny**.

3. I fältet **Berättigande** anger ett värde.

4. I fältet **Beskrivning** anger du ett värde.

5. Ange ett datum i fältet **Giltighetsdatum**. Både fasta och rörliga kompensationsplaner använder behörighetsregler. Välj typ av plan i fältet **Typ**.

6. I fältet **Plan**, ange eller välj ett värde. Markera det villkor som en medarbetare måste uppfylla för att kunna berättigas till kompensationsplanen. Kriterier kan vara:

    - **Avdelning**
    - **Fackförening**
    - **Plats** (**kompensationsregion**)
    - **Jobb**
    - **Funktion**
    - **Jobbtyp**
    - **Kompensationsnivå**
    
    En medarbetare måste uppfylla alla angivna villkor för att kunna berättigas till kompensationsplanen. Om du inte anger några kriterier är alla medarbetare berättigade till kompensationsplanen. Om en medarbetare inte uppfyller kriteriet som ställts in i berättiganderegeln, eller en berättiganderegel inte har ställts in för en kompensationsplan, kommer kompensationsplanen inte att visas i sökningen när du skapar en post med fast kompensation för en medarbetare.

7. Stäng sidan.

8. Stäng sidan.



[!INCLUDE[footer-include](../includes/footer-banner.md)]