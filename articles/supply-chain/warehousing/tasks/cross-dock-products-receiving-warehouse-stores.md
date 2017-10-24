--- 
title: "Direktleverera produkter från det mottagande lagerstället till butiker"
description: "Den här proceduren går igenom stegen för att skapa och bearbeta en direktutleverans om du vill fördela produkter från inleveransplatsen för en inköpsorder till en eller flera butiker."
author: BibiSp
manager: AnnBe
ms.date: 02/17/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: daa42bb83d6b988e8fd18db6ad8386c67fd3e6e5
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="cross-dock-products-from-receiving-warehouse-to-stores"></a>Direktleverera produkter från det mottagande lagerstället till butiker

[!include[task guide banner](../../includes/task-guide-banner.md)]

Den här proceduren går igenom stegen för att skapa och bearbeta en direktutleverans om du vill fördela produkter från inleveransplatsen för en inköpsorder till en eller flera butiker. Användaren kan definiera flera konfigurationer och låta systemet att föreslå hur du fördelar produkterna, eller ange manuellt var produkterna fördelas till och hur mycket som distribueras till varje butik. Proceduren inkluderar inte inställningen av data som kan användas i direktutleveransen, till exempel påfyllnadsregler, organisationshierarkier och butikvikter. Den här proceduren använder demonstrationsföretaget USRT.

1. Gå till Alla inköpsorder.
2. Välj en inköpsorder i listan och klicka på länken för att öppna ordern.
3. Klicka på Butik i åtgärdsfönstret.
4. Klicka på Direktleverans.
5. Klicka på Redigera.
    * Kategorin kan användas för att filtrera artiklarna i avsnittet Rader.  
6. Hitta och markera önskad post i listan.
7. I fältet Kvantitet för direktleverans, ange ett värde för att ange hur mycket av kvantiteten för inköpet av den valda produkten som ska fördelas.
8. I fältet Ytterligare direktleveranskvantitet, ange ett värde för att ange kvantiteterna att fördela för de tillgängliga produkterna som köps.
9. I fältet Fördelning, ange Platsvikt.
    * Du kan välja de andra typerna om du vill använda andra regler för fördelningen.  
10. I fältet Påfyllnadshierarki, ange eller välj ett värde.
11. Välj Ja i fältet Respektera sortiment.
12. Klicka på Beräkna kvantiteter.
13. Klicka på Skapa order.
14. Klicka på Ja.
15. I listan, sök efter och välj ett lagerställe som har tagit emot produkter.
16. Klicka på order för att visa de order som skapades för det valda lagerstället


