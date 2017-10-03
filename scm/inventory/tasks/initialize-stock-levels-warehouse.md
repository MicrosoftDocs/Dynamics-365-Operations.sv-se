---
title: "Initiera lagernivåer i lagerstället"
description: "Den här proceduren visar hur du kan uppdatera lagerbehållningen manuellt genom att använda en journal för lagerrörelse."
author: perlynne
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: 953125ae6e9d669bd13a3344c9f679747af6ff93
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---
# Initiera lagernivåer i lagerstället

[!include[task guide banner](../../includes/task-guide-banner.md)]

Den här proceduren visar hur du kan uppdatera lagerbehållningen manuellt genom att använda en journal för lagerrörelse. (Det går också att uppdatera lagerbehållningen genom att importera transaktioner i dataenheter.) Du kan köra den här guiden i demonstrationsdataföretaget USMF där alla förutsättningar som journalnamn, artikelinställningar, bokföringsprofiler och konton är tillgängliga. Guiden föreslår specifika värden för artikeln och dimensioner som används. Om du väljer en annan artikel kan du behöva ange värden för olika dimensioner.

1. Gå till Lagerhantering > Journalposter > Artiklar > Rörelse.
2. Klicka på Ny.
3. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Namn.
4. Välj IMov.
    * Det är ett bra tips att använda olika journalnamnmallar för de olika arbetssyftena.  
5. Klicka på länken på den valda raden i listan.
6. Ange värdena "140200" i fältet Motkonto.
    * Det här är motkontot som används som standardmotkonto på journalrader. Det går att åsidosätta standardinställningen för att tilldela olika motkonton per rad.  
7. Klicka på OK.
8. Klicka på Ny.
9. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Artikelnummer.
10. Välj artikel A0001.
11. Klicka på länken på den valda raden i listan.
12. Klicka på fliken Lagerdimensioner.
13. Öppna sökningen genom att klicka på listruteknappen i fältet Plats.
14. Välj plats 1.
15. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Lagerställe.
16. Välj lagerställe 13.
17. Klicka på länken på den valda raden i listan.
18. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Plats.
19. Välj plats 13.
20. Ange ett tal i fältet Kvantitet.
21. Klicka på Spara.
22. Klicka på Bokför.
23. Markera eller avmarkera kryssrutan Överför alla bokföringsfel till en ny journal.
    * Om du aktiverar det här alternativet kopieras alla rader som inte kan bokföras till en ny journal. Du kan använda informationen i loggen för att korrigera utleveranserna och sedan bokföra raderna igen.  
24. Klicka på OK.
25. Stäng sidan.
26. Stäng sidan.

