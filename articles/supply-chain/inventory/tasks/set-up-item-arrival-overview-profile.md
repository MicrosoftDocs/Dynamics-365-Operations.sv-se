---
title: Ställ in en översiktsprofil för artikelinförsel
description: Denna uppgift är avsedd för att ställa in en översiktsprofil för införsel.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSArrivalOverviewProfile
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 20472f76a03a2a7bb1a7a87e2687135bce35dfa1
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1845482"
---
# <a name="set-up-an-item-arrival-overview-profile"></a>Ställ in en översiktsprofil för artikelinförsel

[!include [task guide banner](../../includes/task-guide-banner.md)]

Denna uppgift är avsedd för att ställa in en översiktsprofil för införsel. Översiktsprofilen för införsel är en grupp regler som tillämpas när sidan Införselöversikt öppnas av en användare. Du kan köra den här proceduren i demonstrationsdataföretaget USMF. Den här proceduren utförs vanligtvis av en inleveransansvarig.





1. Gå till Lagerstyrning > Inställningar > Distribution > Översiktsprofiler för införsel.
2. Klicka på Ny.
    * Eftersom du nästan ska arbeta på samma lagerställe där fulla lastbilsbeläggningar lastas av, bör du skapa en översiktsprofil för införsel för att förenkla processen att registrera inlevererade artiklar.  
3. Skriv ett värde i fältet Namn på översiktsprofil för införsel.
4. Välj ett alternativ i fältet Visa rader.
    * Välj vilka rader som ska visas för inleveranserna: Alla – visa alla rader, oavsett status.   Pågår – Visa rader för inleveranser där förloppet är Slutfört eller Delvis. Detta innebär att för varje rad har antingen hela kvantiteten eller en del av kvantiteten registrerats i en införseljournal.   Ej fullständigt – Visa rader för inleveranser där förloppet är Inget eller Delvis. Detta innebär för varje rad att ingenting eller bara en del av kvantiteten registrerats i en införseljournal.  
5. Visa eller dölj avsnittet Alternativ för införsel.
6. Skriv ett värde i fältet Dagar framåt.
    * Detta anger ett filter för att visa inleveransraderna som förväntas inlevereras inom de närmsta dagar (beroende på det antal du anger).  
7. Skriv ett värde i fältet Dagar bakåt.
    * Detta anger ett filter för att visa inleveransraderna som förväntas inlevereras ett antal dagar före idag.  
8. Skriv ett värde i fältet Lagerställen.
    * Filtrera på ett eller flera lagerställen.  
9. Välj ett värde i fältet Leveranssätt.
    * Detta anger ett filter för att endast visa de inleveransrader med det här leveranssättet.  
10. Välj WHS i fältet Namn.
11. Välj lagerställe 24 i fältet Lagerställe.
    * Detta är det standardlagerställe som ska användas för registrerade inleveransrader som använder den här profilen.  
12. Markera ett Baydoor i fältet Plats.
    * Detta är den standardplats som ska användas för registrerade inleveransrader som använder den här profilen.  
13. Visa eller dölj avsnittet Detaljer för fråga om införsel.
14. Välj site 2 i fältet Begränsa till plats.
    * Detta anger ett filter för att endast visa inleveransraderna med den här webbplatsen.  
15. Ange alternativet Inköpsorder till Ja.
    * Välj rader från inköpsorder.  
16. Ange alternativet Överföringsorder till Ja.
    * Välj inköpsrader från överföringsorder.  
17. Klicka på Spara.
18. Stäng sidan.

