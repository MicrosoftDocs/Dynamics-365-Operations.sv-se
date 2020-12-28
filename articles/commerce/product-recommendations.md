---
title: Översikt av produktrekommendationer
description: Det här ämnet innehåller allmän information om produktrekommendationer. Med produktrekommendationer kan kunderna enkelt och snabbt hitta produkter som de vill ha och till och med produkter som de ursprungligen inte hade tänkt att köpa.
author: Moonma
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: moonma
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 5aa7db8e53906f9e1416b912fe2c3b70d5430258
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4415705"
---
# <a name="product-recommendations-overview"></a>Översikt av produktrekommendationer

[!include [banner](includes/banner.md)]

Microsoft Dynamics 365 Commerce kan användas för att visa produktrekommendationer på webbplatsen för näthandel och kassaenheten (POS). Produktrekommendationer är artiklar som en kund kan vara intresserad av. Rekommendationerna bygger på de övriga kundernas inköpstrender i online- och fysiska butiker.

Med produktrekommendationer kan kunderna enkelt och snabbt hitta produkter som de vill ha medan de får en upplevelse som tjänar dem väl. Korsförsäljning och merförsäljning kan användas för att hjälpa kunder att hitta fler produkter än vad de ursprungligen avsåg att köpa. När rekommendationer används för att hjälpa till med produktidentifiering kan de skapa fler konverteringsmöjligheter, hjälpa till att öka försäljningsintäkterna och till och med öka kundens tillfredsställelse och kvarhållande.

I näthandel drivs produktrekommendationerna av Microsoft maskininlärningsteknik för rekommendationer i en stor skala.

## <a name="recommendation-service"></a>Rekommendationstjänst

Tjänsten produktrekommendationer använder funktioner för artificiell intelligens och AI-ML (AI-ML) på följande sätt:

- Data i det format som krävs av rekommendationstjänster extraheras från näthandelns driftsdatabas och skickas till enhetslagringen i Azure Data Lake Storage.
- Rekommendationstjänsten använder lagrade data för att träna rekommendationsmodeller för listan **människor gillar också**, **köps ofta ihop**, **ny**, **bästsäljare** och **trend**.

## <a name="scenarios"></a>Scenarier

Produktrekommendationer är tillgängliga för följande scenarier:

- **På valfri butikssida för bläddring eller landnings sida i näthandel:** Om kunder eller butikspartner besöker en butikssida kan rekommendationsmotorn föreslå produkter i listorna **Ny**. **Bästsäljande** och **Trend**.
- **På sidan produktinformation:** om kunder eller säljare besöker en sida med **produktinformation** föreslår rekommendationsmotorn ytterligare artiklar som troligen kommer att köpas. Dessa objekt visas i listan **människor gillar också**.
- **På transaktionssidan eller på utcheckningssidan:** rekommendationsmotorn föreslår artiklar, baserat på den fullständiga listan med artiklar i varukorgen. Dessa objekt visas i listan över **Köps ofta ihop**.
- **Personliga rekommendationer:** inköpare kan ge de inloggade kunderna en anpassad **plockning för dig**, förutom nya funktioner som gör att befintliga listscenarier kan anpassas baserat på den kunden. Mer information finns i [Aktivera anpassade rekommendationer.](personalized-recommendations.md).

### <a name="types-of-product-recommendations"></a>Typer av produktrekommendationer

I följande tabell beskrivs olika typer av automatiska produktrekommendationer som är tillgängliga för återförsäljare att implementera i deras Dynamics 365 Commerce-lösning via [modulen för produktinsamling](product-collection-module-overview.md). Återförsäljare kan också visa anpassade resultat för en inloggad användare om webbplatsförfattaren väljer det alternativet.

| Produktsamlingsmodul  | Typ | beskrivning |
|----------------------------|------|-------------|
| Nytt                        | Algoritmiska | Den här modulen visar en lista över de senaste produkterna som har varit utvalda för kanaler och kataloger. |
| Bästsäljare               | Algoritmiska | Den här modulen visar en lista över produkter som rangordnas med det högsta antalet försäljningar. |
| Trend                   | Algoritmiska | Den här modulen visar en lista över de produkter som har bäst prestanda för en viss period, rangordnade efter högsta antalet försäljningar.  |
| Ofta köpta tillsammans | AI-ML | Den här modulen rekommenderar en lista över produkter som vanligtvis köps tillsammans med innehållet i konsumenten aktuell kundvagn. |
| Andra gillar också           | AI-ML | Den här modulen rekommenderar produkter för en given fröprodukt som baseras på konsument inköpsmönster. |
| Val för dig              | AI-ML | Den här modulen rekommenderar en anpassad lista över produkter som baseras på inköpsmönster för den inloggade användaren. För en gästanvändare kommer den här listan att döljas. |

## <a name="additional-resources"></a>Ytterligare resurser

[Aktivera Azure Data Lake Storage i en Dynamics 365 Commerce-miljö](enable-adls-environment.md)

[Aktivera produktrekommendationer](enable-product-recommendations.md)

[Aktivera anpassade rekommendationer](personalized-recommendations.md)

[Avanmäl anpassade rekommendationer](personalization-gdpr.md)

[Aktivera rekommendationer för "köp liknande produkter"](shop-similar-looks.md)

[Lägga till produktrekommendationer i kassan](product.md)

[Lägg till rekommendationer på transaktionsskärmen](add-recommendations-control-pos-screen.md)

[Justera rekommendationsresultat från AI-ML](modify-product-recommendation-results.md)

[Skapa granskade rekommendationer manuellt](create-editorial-recommendation-lists.md)

[Skapa rekommendationer med demodata](product-recommendations-demo-data.md)

[Vanliga frågor om produktrekommendationer](faq-recommendations.md)
