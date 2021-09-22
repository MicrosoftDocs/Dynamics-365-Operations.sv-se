---
title: Definiera kompensationsprocessen och beräkna resultat
description: Kompensationsprocesser används för att bestämma nya kompensationsbelopp och belöningar för medarbetare som har anmälts till fasta och variabla kompensationsplaner.
author: twheeloc
ms.date: 08/25/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: HRMCompProcess, HRMCompProcessLine, HRMCompEvent, HRMCompEventEmpl, HcmCompensationWorkspace
audience: Application User
ms.search.scope: Human Resources
ms.search.region: Global
ms.author: twheeloc
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 883948c6e3f7b205d7e0f1f2b6adef1173616dc1
ms.sourcegitcommit: a8ac6d9b63eb67d14dd17a086ef4f1eccd7f9fc1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/27/2021
ms.locfileid: "7431135"
---
# <a name="define-compensation-process-and-calculate-results"></a>Definiera kompensationsprocessen och beräkna resultat

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Kompensationsprocesser används för att bestämma nya kompensationsbelopp och belöningar för medarbetare som har anmälts till fasta och variabla kompensationsplaner. Kompensationsprocesser kan köras för att utföra ”vad händer om"-analyser, för att kontrollera att alla ändringar och inställningarna är korrekta. Den här proceduren skapar en kompensationsprocess, kör processen och visar resultatet. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF.


## <a name="create-a-compensation-process"></a>Skapa en kompensationsprocess
1. Gå till **Kompensationshantering** > **Process** > **Kompensationsprocesser**.
2. Klicka på **Ny kompensationsprocess**.
3. Skriv ett värde i fältet **Process**.
4. I fältet **Beskrivning** anger du ett värde.
5. Välj ett alternativ i fältet **Processtyp**.
    * En cykel anger den tidsperiod som utvärderas för att avgöra kompensationen. Utvärderingen tar hänsyn till vilka befattningar som innehades av medarbetarna, vilka resultatvärderingar som ska inkluderas, beräkningen av procentandelen av tid som medarbetaren var anställd under cykeln med mera. Ett exempel på ett cykelstartdatum kan vara den första dagen i det föregående räkenskapsåret.  
6. Ange ett datum i fältet **Periodstart**.
    * Cykelns slutdatum är viktigt eftersom det används för att bestämma vilka medarbetare som var aktivt anställda och anmälda till en eller flera kompensationsplaner.  
7. Ange ett datum i fältet **Periodslut**.
    * Det aktiva transaktionsdatumet är det datum då de nya kompensationstarifferna börjar gälla. Många företag inkluderar några månader innan slutet på en cykel och tiden när de nya kompensationstarifferna börjar gälla. Den extra tiden används för att bearbeta och granska den nya kompensationen.  
8. Ange ett datum i fältet **Aktivt transaktionsdatum**.
    * Tidpunktsdatumet används för variabla kompensationsplaner som bestämmer medarbetarens belöningsbelopp som baseras på deras kompensationssats vid den här tidpunkten.  
    * Den fasta lönen proportionellt från anställningsdatumet används tillsammans med fasta kompensationsplaner med en anställningsregel i procent.  Medarbetare som anställs mellan cykelstarten och den fasta lönen proportionellt från anställningsdatumet får 100 % av den beräknade kompensationsökningen, i stället för dem proportionella procentandelen.  
9. Ange ett datum i fältet **Fast lön proportionellt från anställningsdatumet**.
    * Deadline för granskning är det datum då alla processresultat ska granskas så att de kan läsas in i medarbetarens post för kompensation före det aktiva transaktionsdatumet. Det här fältet är endast till för information.  
10. Ange ett datum i fältet **Granska deadline**.
11. Klicka på **Spara**.

## <a name="setup-the-compensation-plans-and-actions-for-a-compensation-process"></a>Ställ in kompensationsplanerna och åtgärderna för en kompensationsprocess
1. Klicka på **Inställningar**.
    * Sidan **Konfigurera** används för att välja vilka planer som ska behandlas som en del av den här kompensationsprocessen samt vilka åtgärder ska utföras för varje plan.  
2. I fältet **Plan**, ange eller välj ett värde.
3. Klicka på **Spara**.
4. Klicka på **Lägg till**.
5. Välj en åtgärd av typen **Eget kapital** i fältet **Åtgärd**.
6. Klicka på **Lägg till**.
7. Välj en åtgärd av typen **Merit** i fältet **Åtgärd**.
    * Kompensationsåtgärder kan ”kedjas fast” tillsammans med fältet **Använd tidigare resultat** för att ange om den valda åtgärden ska använda medarbetarens grundlön eller resultatet för den föregående åtgärden som startpunkt för beräkningen av den här åtgärden.  
8. Välj **Ja** i fältet Använd tidigare resultat.
9. Klicka på **Lägg till**.
10. Välj en åtgärd av typen **Allmänt** i fältet **Åtgärd**.
    * Olika kompensationsåtgärdstyper aktiverar olika fält. För en allmän kompensationsåtgärdstyp kan en ökningsprocent eller ett ökningsbelopp anges.  
11. Välj alternativet **Välj ökningsbelopp**.
12. Ange ett tal i fältet **Ökningsbelopp**.
13. Klicka på **Lägg till**.
14. Välj en åtgärd av typen **Befordran** i fältet **Åtgärd**.
    * Befordringar och andra nivåändrande åtgärdstyper gör det möjligt för användarna att göra manuella justeringar för medarbetarkompensationen. Rekommendationer kan aktiveras för att dessa åtgärdstyper samt andra åtgärdstyper för att möjliggöra att ange ett nytt rekommenderat kompensationsvärde för en medarbetare.  
15. Klicka på **Lägg till**.
16. Välj ett alternativ i fältet **Typ**.
    * Fasta och variabla kompensationsplaner kan köras i samma kompensationsprocess.  
17. I fältet **Plan**, ange eller välj ett värde.
    * Använd kryssrutan **Aktivera prestationslön** för att fastställa om fasta och variabla kompensationsbelopp ska justeras baserat på medarbetarens resultatvärdering.  
    * Hävstångsverkan kan åsidosättas i variabla kompensationsplaner.  
18. Klicka på **Spara**.
19. Klicka på **Lägg till**.
20. Stäng sidan.

## <a name="run-the-compensation-process"></a>Kör kompensationsprocessen
1. Klicka på **Kör process**.
    * Kontrollen **Visa bearbetningsresultat** gör det möjligt att visa bearbetningsmeddelanden för den färdiga kompensationsprocessen när denna har avslutats.  
2. Välj **Ja** i fältet **Visa bearbetningsresultat**.
3. Klicka på **OK**.

## <a name="view-the-results"></a>Visa resultaten
1. Klicka på **Processresultat**.
2. Klicka på **Medarbetarresultat**.
3. Hitta och markera önskad post i listan.
4. Expandera avsnittet Fast kompensation.
    * Expandera snabbflikarna om du vill visa resultaten av processen. Om **Aktivera rekommendationer** var markerat för en kompensationsåtgärd aktiveras fälten **Rekommendation** för den åtgärden.  
5. Hitta och markera önskad post i listan.
    * Resultaten för en enskild medarbetare kan visas genom att klicka på knappen **Visa resultat**.  
    * Du kan skriva över det beräknade kompensationsbeloppet genom att justera procenttalet eller öka beloppet i fälten **Rekommendation**.  
6. I fältet **Rekommenderad procent**, ange ett tal.
7. Hitta och markera önskad post i listan.
8. I fältet **Rekommenderad procent**, ange ett tal.
    * Omberäkna kan användas för att ignorera ändringar som gjorts för befintliga poster och skapa ett nytt kompensationsresultat för den valda medarbetaren.  
    * Ändra statusen till **Godkänt** när alla ändringar är färdiga för en medarbetare.  
9. Klicka på **Ändra status**.
10. Klicka på **Godkänt**.
    * När posten har godkänts kan den läsas in till medarbetarens officiella kompensationspost. Den nya kompensationen blir giltig på det transaktionsdatum som anges i kompensationsprocessen.  



[!INCLUDE[footer-include](../includes/footer-banner.md)]
