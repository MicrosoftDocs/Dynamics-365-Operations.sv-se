--- 
title: "EUR-00015 Partsökning via moms-ID"
description: "I den här proceduren visas hur du utför en partsökning part med hjälp av ett registrerings-ID."
author: v-oloski
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DirPartyTable, DirPartTaxRegistrationSearch
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Austria, Belgium, Czech Republic, Denmark, Estonia, Finland, France, Germany, Hungary, Ireland, Italy, Latvia, Lithuania, Netherlands, Poland, Spain, Sweden, United Kingdom
ms.author: v-oloski
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 0312b8cfadd45f8e59225e9daba78b9e216cff51
ms.openlocfilehash: ec36ead402882c1022811b7b398a03c6325ef7c0
ms.contentlocale: sv-se
ms.lasthandoff: 09/14/2018

---
# <a name="eur-00015-party-search-using-vat-id"></a>EUR-00015 Partsökning via moms-ID

[!include [task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren visas hur du utför en partsökning part med hjälp av ett registrerings-ID. Innan du kan slutföra proceduren måste du skapa moms-ID och ange moms-ID för leverantörer, kunder eller juridiska personer.

Den här proceduren gäller för alla europeiska länder/regioner. Proceduren skapades med hjälp av demonstrationsdataföretaget DEMF, med primär adress i Tyskland. Denna procedur är avsedd för en leverantörsreskontrachef eller en kundreskontrachef. Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations version 1611.

1. Gå till Organization administration > Global address book > Global address book.
2. Klicka på Registration ID search.
3. Klicka på Lägg till.
4. Ange eller välj ett värde i fältet Registration type.
    * Om du till exempel vill hitta parter med ett registrerings-ID av typen moms-ID, välj VAT ID.  
5. Ange eller välj ett värde i fältet Land/region.
    * Ange exempelvis DEU.  
6. Ange ett värde i fältet Registration number.
7. Klicka på Find.
    * Alla parter med detta registrerings-ID visas.  


