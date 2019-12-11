---
title: Översikt av produktrekommendationer
description: Det här ämnet innehåller allmän information om produktrekommendationer. Med produktrekommendationer kan kunderna enkelt och snabbt hitta produkter som de vill ha och till och med produkter som de ursprungligen inte hade tänkt att köpa.
author: Moonma
manager: AnnBe
ms.date: 10/1/2019
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
ms.openlocfilehash: eb369e6d1356ba13a2310d523b671ac57b9642bf
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770057"
---
# <a name="product-recommendations-overview"></a>Översikt av produktrekommendationer

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

Microsoft Dynamics 365 Commerce kan användas för att visa produktrekommendationer på webbplatsen för e-handel och kassaenheten (POS). Produktrekommendationer är artiklar som en kund kan vara intresserad av. Rekommendationerna bygger på de övriga kundernas inköpstrender i online- och fysiska butiker.

Med produktrekommendationer kan kunderna enkelt och snabbt hitta produkter som de vill ha medan de får en upplevelse som tjänar dem väl. Korsförsäljning och merförsäljning kan användas för att hjälpa kunder att hitta fler produkter än vad de ursprungligen avsåg att köpa. När rekommendationer används för att hjälpa till med produktidentifiering kan de skapa fler konverteringsmöjligheter, hjälpa till att öka försäljningsintäkterna och till och med öka kundens tillfredsställelse och kvarhållande.

I handel drivs produktrekommendationerna av Microsoft maskininlärningsteknik för rekommendationer i en stor skala.


## <a name="scenarios"></a>Scenarier

Produktrekommendationer är tillgängliga för följande scenarier:

- **På valfri butikssida för bläddring eller landnings sida i e-handel:** Om kunder eller butikspartner besöker en butikssida kan rekommendationsmotorn föreslå produkter i listorna **Ny**. **Bästsäljande** och **Trend**.
- **På sidan produktinformation:** om kunder eller säljare besöker en sida med **produktinformation** föreslår rekommendationsmotorn ytterligare artiklar som troligen kommer att köpas. Dessa objekt visas i listan **människor gillar också**.
- **På transaktionssidan eller på utcheckningssidan:** rekommendationsmotorn föreslår artiklar, baserat på den fullständiga listan med artiklar i varukorgen. Dessa objekt visas i listan över **Köps ofta ihop**.

## <a name="recommendation-service"></a>Rekommendationstjänst

Produktrekommendationer använder rekommendationerna för maskininlärningstekniker på följande sätt:

- Data i det format som krävs av rekommendationstjänster extraheras från e-handelns driftsdatabas och skickas till enhetslagringen.
- Rekommendationstjänsten använder data för att träna rekommendationsmodeller för listan **människor gillar också**, **köps ofta ihop**, **ny**, **bästsäljare** och **trend**.

## <a name="additional-resources"></a>Ytterligare resurser

[Aktivera produktrekommendationer](enable-product-recommendations.md)

[Skapa granskade listor över produktrekommendationer](create-editorial-recommendation-lists.md)

[Hantera AI-ML-baserade produktrekommendationsresultat](modify-product-recommendation-results.md)

[Lägg till produktrekommendationer på sidor](add-reco-list-to-page.md)
