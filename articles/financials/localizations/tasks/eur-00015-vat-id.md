--- 
title: EUR-00015 Skapa moms-ID
description: "Denna procedur går igenom registreringsförutsättningarna för moms-ID, till exempel hur du skapar en registreringstyp och tilldelar den till en registreringskategori."
author: v-oloski
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: TaxRegistrationType, TaxRegistrationTypeCreate, TaxRegistrationLegislationTypes
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: 66ee7215dc21921f9d8e405c3f77d9b5e0b89a9e
ms.contentlocale: sv-se
ms.lasthandoff: 09/14/2018

---
# <a name="eur-00015-set-up-vat-id"></a>EUR-00015 Skapa moms-ID

[!include [task guide banner](../../includes/task-guide-banner.md)]

Denna procedur går igenom registreringsförutsättningarna för moms-ID, till exempel hur du skapar en registreringstyp och tilldelar den till en registreringskategori. Du kan hitta ytterligare information om registrerings-ID och bearbetning av registrerings-ID, inklusive erforderliga förutsättningar, i hjälpavsnittet för registrerings-ID. 

Informationen här gäller alla europeiska länder/regioner. Uppgiften skapades med hjälp av demonstrationsdataföretaget DEMF, med Tyskland som primär adress för juridisk person. Denna uppgift är avsedd för systemadministratörer. Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations version 1611.

1. Gå till Organization administration > Global address book > Registration types > Registration types.
2. Klicka på Nytt om du vill öppna dialogrutan.
3. Ange "VAT ID" i fältet Name.
4. Ange momsnumret i fältet Description.
5. Ange eller välj värdet DEU i fältet Country/region
6. Välj Yes i fältet Unique.
    * Markera den här kryssrutan för att bekräfta att moms-ID är unikt.  
7. Välj Yes i fältet Primary for country.
    * Markera den här kryssrutan om moms-ID ska gälla för alla adresser som tillhör det land/den region som angetts.  
8. Klicka på Skapa.
9. Klicka på Lägg till.
10. Ange eller välj värdet ITA i fältet country/region
11. I fältet Format anger du "###########".
    * När du anger ett registrerings-ID av denna typ för det land/den region som har valts, kommer registrerings-ID att kontrolleras mot detta format.  
12. Markera kryssrutan Unique.
    * Markera den här kryssrutan för att bekräfta att moms-ID är unikt.  
13. Markera kryssrutan Primary for country.
    * Markera den här kryssrutan om moms-ID ska gälla för alla adresser som tillhör det land/den region som angetts.  
14. Klicka på Spara.
15. Gå till Organization administration > Global address book > Registration types > Registration categories.
16. Klicka på Ny.
17. Ange eller välj värdet DEU för moms-ID i fältet Country/region
18. Välj "VAT ID" i fältet Registration category.
    * Tilldela den registreringstyp som du skapade tidigare till en fördefinierad registreringskategori.  
19. Klicka på Ny.
20. Ange eller välj värdet ITA för moms-ID i fältet Country/region
21. Välj "VAT ID" i fältet Registration category.
    * Tilldela den registreringstyp som du skapade till en fördefinierad registreringskategori.  
22. Klicka på Spara.


