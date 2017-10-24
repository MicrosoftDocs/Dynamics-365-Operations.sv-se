--- 
title: "Frisläpp en produktionsorder"
description: "I den här proceduren visas hur du frisläpper en produktionsorder."
author: johanhoffmann
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 2ae2d84bd12d338c9bada5518c43178b22112006
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="release-a-production-order"></a>Frisläpp en produktionsorder

[!include[task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren visas hur du frisläpper en produktionsorder. Det demonstrationsdataföretag som används för att skapa den här proceduren är USMF. Detta är den fjärde proceduren av sju som förklarar produktionsorderns livscykel.

1. Gå till Produktionskontroll > Produktionsorder > Alla produktionsorder.
    * Markera en produktionsorder som har statusen Tidsplanerat i rutnätet.  
2. Klicka på Produktionsorder i åtgärdsfönstret.
3. Klicka på Frisläpp.
    * På den här sidan kan du bekräfta leveransen av det valda intervallet av tillverkningsorder. Klicka på, Välj om du vill lägga till order.  
    * Leveranssteget anger när produktionsordern frisläpps till produktion butik våningen, så att operatörerna för arbetsstyrning kan rapportera framsteg på produktionsjobb. Produktionlegitimationshandlingar, som innehåller relevant information om bearbetning av jobb, kan utfärdas. Lagerställearbetet för råvaraplockning genereras för artiklarna som har ställts in för lagerställeprocessen.  
4. Klicka på fliken Allmänt.
    * Välj produktionrapporter som ska skrivas ut. Jobbkortsrapporten skriver ut en sida för varje schemalagt jobb och kräver att tillverkningsordern planeras på jobbnivån. Rapporten innehåller information om den schemalagda start - och sluttid, att producera kvantiteten, och resursen som behandlar jobbet. Flödesjobbrapporten samlar in samma information på samma sida, men inte skriver ut en sida för varje jobb. Flödeskortsrapporten bara vill visa operationerna men inte jobben. Därför måste den här rapporten kan inte finplanering, utan användas, när produktionsorder planeras på operationnivån.  
5. Klicka på kryssrutan Skriv ut ruttkort.
6. Klicka på OK.
7. Stäng sidan.


