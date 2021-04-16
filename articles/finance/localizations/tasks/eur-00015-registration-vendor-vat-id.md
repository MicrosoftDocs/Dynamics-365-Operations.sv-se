---
title: EUR-00015 Registrering av moms-ID för leverantör
description: I den här proceduren visas hur du lägger till momsregistrerings-ID och momsbefrielsenummer i ett leverantörskonto.
author: v-oloski
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: VendTable, LogisticsPostalAddress, RegNumTaxIdLookup
audience: Application User
ms.reviewer: kfend
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 578f961fe1b5e3d06b624b78c278c8314df47f5e
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5822566"
---
# <a name="eur-00015-registration-of-vendor-vat-id"></a>EUR-00015 Registrering av moms-ID för leverantör

[!include [banner](../../includes/banner.md)]

I den här proceduren visas hur du lägger till momsregistrerings-ID och momsbefrielsenummer i ett leverantörskonto. Den här processen påminner om den för juridiska personer och kunder. 

Innan du kan slutföra denna procedur måste du skapa moms-ID:n. Den här proceduren gäller för alla europeiska länder/regioner. Proceduren skapades med hjälp av demonstrationsdataföretaget DEMF, med primär adress i Tyskland. Denna procedur är avsedd för en datahanteringsadministratör, leverantörsreskontrachef eller en kundreskontrachef. Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations version 1611.

1. Gå till leverantörsreskontra > Leverantörer > Alla leverantörer.
2. Hitta och välj leverantören vendor DE-01001 i listan
3. Klicka på Registration IDs.
4. Klicka på Lägg till.
5. Välj moms-ID.
6. Ange ett värde i fältet Registration number.
    * Ange ett moms-ID i Tyskland för den valda leverantören. ID måste matcha det angivna formatet för registreringstypen.  
7. Klicka på fliken Allmänt.
8. Ange ett datum i fältet Giltighet.
9. Klicka på Spara.
10. Klicka på Ny.
11. Skriv ett värde i fältet Namn eller beskrivning.
    * Ange exempelvis ITA.  
12. Ange eller välj ett värde i fältet Land/region.
    * Välj till exempel ITA.  
13. Välj Yes i fältet Primary for country.
14. Klicka på Spara.
15. Klicka på fliken Översikt.
16. Klicka på Lägg till.
17. Ange eller välj ett värde i fältet Registration type.
    * Välj till exempel moms-ID (VAT ID).  
18. Ange ett värde i fältet Registration number.
    * Ange exempelvis ett moms-ID i Italien.  ID måste ha samma format som registreringstypen.  
19. Klicka på Spara.
20. Stäng sidan.
21. Hitta och markera önskad post i listan.
    * Välj till exempel DE-01001.  
22. Klicka på länken på den valda raden i listan.
23. Expandera faktura- och leveransavsnittet.
24. Klicka på Redigera.
25. Ange eller välj ett värde i fältet Momsregistreringsnummer.
26. Klicka på Spara.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]