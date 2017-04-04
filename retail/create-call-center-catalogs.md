---
title: "Skapa en kundtjänstkatalog"
description: "Den här artikeln ger en översikt över processen för att skapa en katalog för ett callcenter."
author: josaw1
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 16212
ms.assetid: c9d1b9df-82e8-4b3a-a13c-166df8b9718e
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 857d280ab6d846c19102dd053a2c5f27fe14654c
ms.lasthandoff: 03/31/2017


---

# <a name="create-a-call-center-catalog"></a>Skapa en kundtjänstkatalog

Den här artikeln ger en översikt över processen för att skapa en katalog för ett callcenter. 

I en kundtjänst kan du använda produktkataloger för att identifiera de produkter som du vill erbjuda dina kunder. Kundtjänster använder vanligtvis tryckta kataloger. Konstruktionen och tillverkningen av en tryckt katalog hanteras utanför Microsoft Dynamics 365 för operationer. Du kan skapa och spara ett digitalt format med en katalog i butik och handel i Dynamics 365 för operationer med samma formulär som används för att ställa in online (butik) kataloger. Innan du kan skapa en katalog måste du ställa in produktsortiment och tilldela sortimenten till en kundtjänst. Du lägger sedan till produkter till katalogen genom att välja produkter från dessa sortiment. När produkter har lagts till i katalogen och katalogen är klar måste du validera katalogen för att kontrollera data. Du måste sedan skicka katalogen för granskning och godkännande. När katalogen har godkänts, kan den publiceras. När en kundtjänstkatalog skapas, kan du ta en ögonblicksbild av katalogdatan och tidpunkten när katalogen publiceras. Den här funktionen för ögonblicksbilder låter dig öppna en viss version av katalogen, även om katalogen senare ändras och uppdateras. Kundtjänstkataloger kan också ställas in för att innefatta följande tillvalsfunktioner:

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

-   **Källkoder** kan användas av företag som skapar utskrivna kataloger kan använda källkoder för att följa kundsvaret för särskilda kataloger. Ursprungskoder trycks ofta på baksidan av en katalog och registreras i försäljningsorder när en kund gör ett inköp. Lägg till en ursprungskod katalogen måste du först skapa en målgrupp. Vanligtvis mappas till en utskickslista ägs eller hyrda målmarknaden.
-   **Kostnadsfria produkter** är reklamartiklar som ingår kostnadsfritt med kundens order, när katalogen refereras till.
-   **Skript** kan användas till att vägleda arbetarens interaktioner med kunder i samband med en katalog eller en produkt i en katalog.

## <a name="publish-the-catalog"></a>Publicera katalogen
Genom att publicera en katalog för en kundtjänst slutför du produktinformationen i katalogen. Publicering visar också att katalogen är klar för ytterligare åtgärder som du vill utföra, till exempel skapa en skriven ut katalog. Du kan till exempel skapa en utskriven katalog. Du kan publicera dina kataloger manuellt eller använda en batchprocess för att publicera i enlighet med en plan. Innan du kan publicera en katalog måste katalogen valideras och godkännas. Om du vill ändra katalogen, efter att den har publicerats, kan du dra tillbaka katalogen och sedan publicera den på nytt.

