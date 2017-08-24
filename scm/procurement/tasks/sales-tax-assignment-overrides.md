--- 
title: "Momstilldelning och åsidosättningar"
description: "I den här proceduren visas hur du tilldelar momsgrupper till butikskanaler."
author: mkirknel
manager: AnnBe
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: 02ed6b5c7d83d9781a842c4b06a5907ad23d0969
ms.contentlocale: sv-se
ms.lasthandoff: 07/28/2017

---
# <a name="sales-tax-assignment-and-overrides"></a>Momstilldelning och åsidosättningar

[!include[task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren visas hur du tilldelar momsgrupper till butikskanaler. Den går också igenom processen att skapa en ny momsåsidosättning och tilldela den till en befintlig momsåsidosättningsgrupp. Den här uppgiften

använder sig av demonstrationsföretaget USRT.

1. Gå till butik och handel > Kanaler > butiker > Alla butiker.
2. Klicka på länken Butikskanal-ID för "Houston" i listan.
3. Klicka på Redigera.
    * Fältet "Momsgrupp" innehåller listan med momsgrupper för det aktuella företaget. Den aktuella tilldelade gruppen är en allmän ”Texas”-momsgrupp. Det finns även momsgrupper för ”Washington” och ”Washington King County”. Momsgrupper kan inkludera tillämpliga skatter för flera kommuner.  
    * I fältet moms ”Åsidosätt moms" kan momsåsidosättgrupper mappas till kanalen. Momsåsidosättgrupper kan användas till att gruppera momsåsidosättningsgrupper som arbetar för flera butiker. Snarare än att manuellt tilldela en momsåsidosättning i taget kan gruppen skapas och tilldelas direkt till kanalerna om du vill spara tid.  
4. Klicka på Spara.
5. Stäng sidan.
6. Gå till Butik och handel > Kanalinställning > Moms > Momsåsidosättning.
7. Klicka på Ny.
8. Ange ett namn för den nya åsidosättningen i fältet Momsåsidosättning.
9. I fältet Beskrivning anger du en kort beskrivning av åsidosättningen.
10. Ange status till "Aktivera".
11. Visa eller dölj avsnittet Åsidosättning.
12. Välj ett alternativ i fältet Typ.
    * Artikelmomsgrupper kan användas för att åsidosätta moms för specifika artiklar som tillhör gruppen. Till exempel beskattas livsmedel vanligtvis annorlunda än fysiska varor och har troligen sin egen momsgrupp.     Momsgrupper är grupper av moms som gäller för en viss kanal. Om en kanal till exempel säljer både till butik och mellan företag kan olika artikelmomsgrupper användas. All tillämplig moms mappas till momsgruppen.  
    * Nu kan du välja ”Från”- och ”Till”-moms eller ”Från momsgrupp" och "Till momsgrupp" för att skapa din momsåsidosättning.    Fältet "Från" anger den moms eller momsgrupp som ska åsidosättas. Åsidosätta efter Artikelmomsgrupp ger olika alternativ än att åsidosätta efter momsgrupp.    Momsåsidosättning kan ställas in för att åsidosätta moms på hela transaktioner eller på särskilda rader i transaktionen.  
13. Klicka på Spara.
14. Stäng sidan.
15. Gå till Butik och handel > Kanalinställning > Moms > Momsåsidosättningsgrupper.
    * I detta steg tilldelar du den nyligen skapade momsåsidosättningen till den momsåsidosättgrupp som tilldelats Houston-kanalen.  
16. Klicka på Redigera.
17. Utöka eller komprimera avsnittet Inställningar.
18. Klicka på Lägg till.
19. I fältet Momsåsidosättning, öppna sökningen genom att klicka på den nedrullningsbara knappen.
20. Välj den tidigare skapade momsåsidosättningen i listan.
21. Klicka på länken på den valda raden i listan.
22. Klicka på Spara.


