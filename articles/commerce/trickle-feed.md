---
title: Indroppningsbaserat orderskapande för butikstransaktioner
description: Det här ämnet beskriver det indroppningsbaserade orderskapandet för butikstransaktioner i Microsoft Dynamics 365 Commerce.
author: analpert
ms.date: 01/11/2021
ms.topic: index-page
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: 67b66cd4bf2a77f3ab7f33f691156e38cc13770a
ms.sourcegitcommit: 27475081f3d2d96cf655b6afdc97be9fb719c04d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/12/2022
ms.locfileid: "7964639"
---
# <a name="trickle-feed-based-order-creation-for-retail-store-transactions"></a>Indroppningsbaserat orderskapande för butikstransaktioner

[!include [banner](includes/banner.md)]

I Microsoft Dynamics 365 Commerce version 10.0.5 och senare rekommenderar vi att du överför alla bokföringsprocesser för utdrag till indroppningsbaserade bokföringsprocesser för utdrag. Användning av indroppningsfunktionen ger avsevärda prestanda- och affärsfördelar. Försäljningstransaktioner bearbetas under dagen. Transaktioner för betalningsmedels- och kontanthantering bearbetas i bokslutet vid dagens slut. Indroppningsfunktionen gör det möjligt att kontinuerligt bearbeta försäljningsorder, fakturor och betalningar. Därför uppdateras och redovisas lager, intäkter och betalningar i nästan realtid.

## <a name="use-trickle-feed-based-posting"></a>Använd indroppningsbaserad bokföring

> [!IMPORTANT]
> Innan du aktiverar indroppningsbaserad bokföring måste du säkerställa att det inte finns beräknade och ej bokförda utdrag. Bokför alla utdrag innan du aktiverar funktionen. Det går att söka efter öppna utdrag i arbetsytan **Butiksekonomi**.

Aktivera indroppningsbaserad bokföring av butikstransaktioner genom att aktivera funktionen **Butiksutdrag – Indroppning** i arbetsytan **Funktionshantering**. Utdrag delas upp i två typer: transaktionsutdrag och bokslut.

### <a name="transactional-statements"></a>Transaktionsutdrag

Bearbetning av transaktionsutdrag är avsedd att köras med hög frekvens under dagen så att dokument skapas när transaktionerna överförs till Commerce-administration. Transaktioner läses in från butikerna till Commerce-administration när du kör **P-Jobbet**. Du måste även köra jobbet **Validera butikstransaktioner** om du vill validera transaktioner så att transaktionsutdraget hämtar dem.

Schemalägg följande jobb att köras med hög frekvens:

- Beräkna ett transaktionsutdrag genom att köra jobbet **Beräkna transaktionsutdrag i batch** (**Retail och Commerce \> Retail och Commerce IT \> Kassabokföring \> Beräkna transaktionsutdrag i batch**). Det här jobbet hämtar alla ej bokförda och validerade transaktioner och lägger till dem i ett nytt transaktionsutdrag.
- Bokför transaktionsutdrag i en batch genom att köra jobbet **Bokför transaktionsutdrag i batch** (**Retail och Commerce \> Retail och Commerce IT \> Kassabokföring \> Bokför transaktionsutdrag i batch**). Det här jobbet kör bokföringsprocessen och skapar försäljningsorder, försäljningsfakturor, betalningsjournaler, rabattjournaler och intäkts-utgiftstransaktioner för ej bokförda utdrag som inte innehåller fel. 

### <a name="financial-statements"></a>Bokslut

Bokslutsbearbetning är avsedd att vara en dagsavstämningsprocess. Den här typen av utdragsbearbetning stöder endast stängningsmetoden **Skift** och hämtar bara stängda skift. Utdrag begränsas till ekonomisk avstämning. De skapar endast journaler för avvikelsebeloppen mellan det räknade beloppet och transaktionsbeloppet för betalningsmedlen och journaler för andra kontanthanteringstransaktioner.

Bokslut gör det också möjligt att granska följande transaktioner: kassaavstämningstransaktioner, betalningstransaktioner, bankinsättningstransaktioner och betalningsmedeltransaktioner (kassaskåp). Informationssidan för betalningsmedel visas bara när ett bokslut väljs.

![En bild som visar avsnittet betalningsmedelsinformation i det bokförda utdragsformuläret enbart när ett bokslut har valts.](./media/Trickle-feed-posted-statements-transaction-view.png)

Planera start- och sluttiderna för följande bokslutsjobb baserat på förväntad dagsavstämning:

- Beräkna ett bokslut genom att köra jobbet **Beräkna bokslut i batch** (**Retail och Commerce \> Retail och Commerce IT \> Kassabokföring \> Beräkna bokslut i batch**). Det här jobbet samlar in alla ej bokförda ekonomiska transaktioner och lägger till dem i ett nytt bokslut.
- Bokför bokslut i en batch genom att köra jobbet **Bokför bokslut i batch** (**Retail och Commerce \> Retail och Commerce IT \> Kassabokföring \> Bokför bokslut i batch**).

### <a name="manually-create-statements"></a>Skapa utdrag manuellt

Det går även att skapa transaktions- och bokslutstyper manuellt. 

1. Öppna **Retail och Commerce \> Kanaler \> Butiker** och välj **Utdrag**. 
2. Välj **Ny** och välj sedan utdragstypen som du vill skapa. Fält på sidan **Utdrag** och visar data som är relevanta för den valda utdragstypen och åtgärder under **Utdragsgrupper** visar relevanta åtgärder.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
