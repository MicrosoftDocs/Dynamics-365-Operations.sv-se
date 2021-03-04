---
title: " Skjut produkter från distributionscenter till butik med centraliserad distribution"
description: Den här proceduren går igenom stegen för att skapa och bearbeta en centraliserad distribution för att distribuera produkter från en plats till en eller flera butiker.
author: rubencdelgado
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: RetailBuyersPush, InventLocationIdLookup, InventItemIdLookupSimple, RetailReplenishmentTreeLookup
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Retail
ms.author: rubendel
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dad74855ab9a9c225a5cd64a8c27663aedcd21e4
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415866"
---
# <a name="push-products-from-distribution-center-to-store-using-buyers-push"></a> Skjut produkter från distributionscenter till butik med centraliserad distribution

[!include [banner](../includes/banner.md)]

Den här proceduren går igenom stegen för att skapa och bearbeta en centraliserad distribution för att distribuera produkter från en plats till en eller flera butiker. Användaren kan definiera flera konfigurationer och låta systemet att föreslå hur du fördelar produkterna, eller ange manuellt var produkterna fördelas till och hur mycket som distribueras till varje butik. Den här proceduren inkluderar inte inställningen av data som kan användas i centraliserad distribution, till exempel påfyllnadsregler, organisationshierarkier och butikvikter. I den här proceduren används demonstrationsföretaget USRT.

1. Gå till Centraliserad distribution.
2. Klicka på Ny.
3. Ange ett värde i fältet Beskrivning.
4. Ange eller välj ett värde i fältet Plats.
5. I fältet Lagerställe, ange eller välj ett lagerställe som har produkter med lagerbehållning.
6. Klicka på Lägg till.
7. Markera vald rad i listan.
8. I fältet Artikelnummer, ange eller välj en produkt.
9. Klicka på Lägg till.
10. Markera vald rad i listan.
11. I fältet Artikelnummer, ange eller välj en variantprodukt.
    * När du anger en variantprodukt, rader skapas för varje variant.  
12. Markera en rad i listan.
13. I fältet Distribuerad kvantitet, ange hur många av den valda produkten du vill distribuera.
14. I fältet Ytterligare kvantitet att distribuera, ange kvantiteten för de produkter som har tillgänglig kvantitet att distribuera.
15. I fältet Fördelning, ange Platsvikt.
    * Du kan välja de andra typerna om du vill använda andra regler för fördelningen.  
16. I fältet Påfyllnadshierarki, ange eller välj ett värde.
17. Välj Ja i fältet Respektera sortiment.
18. Klicka på Beräkna kvantiteter och granska de kvantiteter som läggs till för raderna i lagerställeavsnittet.
19. Klicka på Skapa order.
20. Klicka på Ja.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]