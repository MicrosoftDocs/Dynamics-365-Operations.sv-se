---
title: Direktleverera produkter från det mottagande lagerstället till butiker
description: Den här proceduren går igenom stegen för att skapa och bearbeta en direktutleverans om du vill fördela produkter från inleveransplatsen för en inköpsorder till en eller flera butiker.
author: ShylaThompson
manager: tfehr
ms.date: 02/17/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9bf53ba136c446df61893f4703e5951e42ae605d
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3217090"
---
# <a name="cross-dock-products-from-receiving-warehouse-to-stores"></a>Direktleverera produkter från det mottagande lagerstället till butiker

[!include [banner](../../includes/banner.md)]

Den här proceduren går igenom stegen för att skapa och bearbeta en direktutleverans om du vill fördela produkter från inleveransplatsen för en inköpsorder till en eller flera butiker. Användaren kan definiera flera konfigurationer och låta systemet att föreslå hur du fördelar produkterna, eller ange manuellt var produkterna fördelas till och hur mycket som distribueras till varje butik. Proceduren inkluderar inte inställningen av data som kan användas i direktutleveransen, till exempel påfyllnadsregler, organisationshierarkier och butikvikter. Den här proceduren använder demonstrationsföretaget USRT.

1. Gå till Alla inköpsorder.
2. Välj en inköpsorder i listan och klicka på länken för att öppna ordern.
3. Klicka på Butik och handel i åtgärdsfönstret.
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

