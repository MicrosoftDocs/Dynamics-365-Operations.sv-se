---
title: Momstilldelning och åsidosättningar
description: I den här proceduren visas hur du tilldelar momsgrupper till handelskanaler.
author: RichardLuan
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailStoreTable, RetailTaxOverrideCode, RetailTaxOverrideGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 469850d8ed9251a827e834a483653ea7926bd414
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5244073"
---
# <a name="sales-tax-assignment-and-overrides"></a>Momstilldelning och åsidosättningar

[!include [banner](../../includes/banner.md)]

I den här proceduren visas hur du tilldelar momsgrupper till handelskanaler. Den går också igenom processen att skapa en ny momsåsidosättning och tilldela den till en befintlig momsåsidosättningsgrupp. I proceduren används demonstrationsföretaget USRT.

1. Gå till Butik och handel > Kanaler > Butiker >Alla butiker.
2. Klicka på länken kanal-ID för "Houston" i listan.
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
    * Artikelmomsgrupper kan användas för att åsidosätta moms för specifika artiklar som tillhör gruppen. Till exempel beskattas livsmedel vanligtvis annorlunda än fysiska varor och har troligen sin egen momsgrupp. Momsgrupper är grupper av moms som gäller för en viss kanal. Om en kanal till exempel säljer både till butik och mellan företag kan olika artikelmomsgrupper användas. All tillämplig moms mappas till momsgruppen.  
    * Nu kan du välja ”Från”- och ”Till”-moms eller ”Från momsgrupp" och "Till momsgrupp" för att skapa din momsåsidosättning. Fältet "Från" anger den moms eller momsgrupp som ska åsidosättas. Åsidosätta efter Artikelmomsgrupp ger olika alternativ än att åsidosätta efter momsgrupp. Momsåsidosättning kan ställas in för att åsidosätta moms på hela transaktioner eller på särskilda rader i transaktionen.  
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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]