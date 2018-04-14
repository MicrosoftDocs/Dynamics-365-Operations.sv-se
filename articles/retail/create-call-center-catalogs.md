---
title: "Skapa en kundtjänstkatalog"
description: "Den här artikeln ger en översikt över processen för att skapa en katalog för ett callcenter."
author: josaw1
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-365-retail
ms.technology: 
ms.search.form: RetailMCRChannelDetailPage, RetailCatalogDetails
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: 16212
ms.assetid: c9d1b9df-82e8-4b3a-a13c-166df8b9718e
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0, Retail July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: 29d005655856fd1eb0f1490c45e07649465539f2
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="create-a-call-center-catalog"></a>Skapa en kundtjänstkatalog

[!INCLUDE [banner](includes/banner.md)]

Den här artikeln ger en översikt över processen för att skapa en katalog för ett callcenter. 

I en kundtjänst kan du använda produktkataloger för att identifiera de produkter som du vill erbjuda dina kunder. Kundtjänster använder vanligtvis tryckta kataloger. Design och produktion av en tryckt katalog hanteras utanför Microsoft Dynamics 365 for Retail. Du kan emellertid skapa och lagra en digital form av en katalog i detaljhandeln och handel i samma formulär som du använder för att konfigurera online butikskataloger. Innan du kan skapa en katalog måste du ställa in produktsortiment och tilldela sortimenten till en kundtjänst. Du lägger sedan till produkter till katalogen genom att välja produkter från dessa sortiment. När produkter har lagts till i katalogen och katalogen är klar måste du validera katalogen för att kontrollera data. Du måste sedan skicka katalogen för granskning och godkännande. När katalogen har godkänts, kan den publiceras. När en kundtjänstkatalog skapas, kan du ta en ögonblicksbild av katalogdatan och tidpunkten när katalogen publiceras. Den här funktionen för ögonblicksbilder låter dig öppna en viss version av katalogen, även om katalogen senare ändras och uppdateras. Kundtjänstkataloger kan också ställas in för att innefatta följande tillvalsfunktioner:

-   **Källkoder** – Koder som används för att spåra kundsvaret för särskilda katalogutskick.
-   **Gratis produkter** – Produkter som inkluderas i en kunds order utan ytterligare avgifter. Dessa produkter läggs automatiskt till på ordern när källkoden för katalogen skrivs in i ordern.
-   **Skript** – Texter som en kundtjänstarbetare läser upp för en kund när en försäljningsorder skapas. Skript kan inkludera hälsningar eller inköpförslag.
-   **Merförsäljning och korsförsäljning** - Artiklar som visas ett förslag när en specifik produkt läggs till på ordern.

Dessa alternativ måste ställas innan katalogen godkänns och publiceras.

## <a name="prerequisites"></a>Krav
Följande uppgifter måste ha slutförts innan du börjar:

-   Ställa in produkter och produktsortiment.
-   Ställ in butiksprodukter.
-   Lägga upp ett sortiment.
-   Skapa en kundtjänst.
-   Ställa in en kundtjänst.
-   Lägg till kundtjänst i en organisationshierarki.
-   Skapa eller ändra en organisationshierarki.

## <a name="create-a-catalog"></a>Skapa en katalog
Du måste första skapa en katalog, lägga till produkter i katalogen och sedan granska och uppdatera attributen för produkterna.

## <a name="validate-the-catalog"></a>Validera katalogen
När du har avslutat inställningen av katalogen måste du validera den. Valideringsprocessen verifierar att data som krävs för kanalattribut och produktattribut är kompletta och giltiga och att katalogen kan publiceras.

## <a name="submit-the-catalog-for-review-and-approval"></a>Skicka katalogen till granskning och godkännande
När en katalog har validerats kan du skicka katalogen för granskning och godkännande. En katalog måste godkännas innan den kan publiceras. Du kan konfigurera arbetsflödet så att kataloger antingen godkänns automatiskt eller kräver manuellt godkännande.

## <a name="optional-add-source-codes-free-products-and-scripts"></a>Du kan även: Lägg till källkoder, lediga produkter och skript
Du kan också lägga till följande artiklar till en kundtjänstkatalog. Dessa artiklar är valfria.

-   **Källkoder** kan användas av företag som skapar utskrivna kataloger kan använda källkoder för att följa kundsvaret för särskilda kataloger. Källkoder skrivs ofta ut på baksidan av en katalog och anges ofta i försäljningsordern när en kund gör ett inköp. För att lägga till en källkod i katalogen måste du först skapa en målmarknad. Vanligtvis mappas målmarknaden till en ägd eller hyrd utskickslista.
-   **Kostnadsfria produkter** är reklamartiklar som ingår kostnadsfritt med kundens order, när katalogen refereras till.
-   **Skript** kan användas till att vägleda arbetarens interaktioner med kunder i samband med en katalog eller en produkt i en katalog.

## <a name="publish-the-catalog"></a>Publicera katalogen
Genom att publicera en katalog för en kundtjänst slutför du produktinformationen i katalogen. Publicering visar också att katalogen är klar för ytterligare åtgärder som du vill utföra, till exempel skapa en skriven ut katalog. Du kan till exempel skapa en utskriven katalog. Du kan publicera dina kataloger manuellt eller använda en batchprocess för att publicera i enlighet med en plan. Innan du kan publicera en katalog måste katalogen valideras och godkännas. Om du vill ändra katalogen, efter att den har publicerats, kan du dra tillbaka katalogen och sedan publicera den på nytt.




