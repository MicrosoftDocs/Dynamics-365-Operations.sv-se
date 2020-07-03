---
title: Vanliga frågor om produktrekommendationer
description: Det här avsnittet innehåller information om processer och verktyg som du kan använda för att felsöka problem som hör till produktrekommendationer eller deras resultat.
author: bebeale
manager: AnnBe
ms.date: 05/26/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: ''
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, Core, Operations
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: e27e4c4d8bdf614d6f55f44daeac3bc152219004
ms.sourcegitcommit: fdc5dd9eb784c7d8e75692c8cdba083fe0dd87ce
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/26/2020
ms.locfileid: "3404312"
---
# <a name="product-recommendations-faq"></a>Vanliga frågor om produktrekommendationer


[!include [banner](includes/banner.md)]

Det här avsnittet innehåller information om processer och verktyg som du kan använda för att felsöka problem som hör till [produktrekommendationer](product-recommendations.md) eller deras resultat.

## <a name="best-practices"></a>Regelverk
Det är mycket viktigt att du använder begreppet produktmallar och varianter. Vettig gruppering av varianter till en överordnad produktmall gör att listan över algoritmer och tjänster skapar bättre modeller. Dessutom kan tjänsten bara hantera en enda instans av en produkt i stället för att placera alla nära relaterade varianter i en lista. När alla nära relaterade varianter placeras i en lista, kan felaktiga eller dubbla resultat inträffa.

## <a name="why-are-products-missing-from-my-recommendation-lists"></a>Varför saknas produkter i mina rekommendationslistor?

Om en artikel saknas i en lista över produktrekommendationer kan det finnas ett problem med produktkonfigurationen. Det kan till exempel vara fel på produktens startdatum eller slutdatum, en dimension kan vara felkonfigurerad eller produkten kanske inte är i rätt kanalsortiment, osv.

Om en artikel saknas i en rekommendationslista som är baserad på artificiell intelligens (AI-ML), kanske objektet inte passar kriteriet i listan över rekommendationer eller så har det inte tillräckligt många inköpstransaktioner för att listan över rekommendationer ska visas filen.

Vi rekommenderar att du kontrollerar följande steg:
1. **Kontrollera att produktrekommendationerna har aktiverats i huvudkontor.** Mer information om hur du aktiverar den här tjänsten finns i [Aktivera produktrekommendationer](enable-product-recommendations.md).
1. **Kontrollera att egenskaperna för nyckelprodukter är inställda.** Produktsortimenten måste till exempel vara inställda på **inkludera**.
1. **För nya, utvalda produkter kan det ta upp till 3 timmar innan produkten börjar visas i den nya listan.**
1. **Om en produkt fortfarande inte visas i trenden, bästsäljare, människor gillar också eller ofta köpt tillsammans kan det hända att produkten inte har tillräckligt med transaktioner.** I detta fall kan du antingen vänta på att fler transaktioner ska uppträda, uppdatera standardparametrarna för rekommendationslistan eller använda manuella åtgärder för att ändra resultaten av en lista över produktrekommendationer. Mer information om parametrar för rekommendationer finns i [hantera AI-ML-baserade resultat för produktrekommendationer](modify-product-recommendation-results.md).
1. **Kontrollera att produkten uppfyller rekommendationskriterierna för listan.** Mer information om parametrar för produktrekommendationer finns i [hantera AI-ML-baserade resultat för produktrekommendationer](modify-product-recommendation-results.md).

## <a name="how-can-i-prevent-poor-recommendation-results-from-being-returned"></a>Hur kan jag förhindra att dåliga rekommendationsresultat returneras?

I rekommendationslistor krävs en stor mängd transaktioner för att ge resultaten. Därför är det viktigt att användarna ger fullständiga historiska transaktionsdata.

Dessutom har produkter som inte har några transaktioner eller få transaktioner vanligtvis inte resultaten **Människor gillar också** eller **Ofta köpt tillsammans** och visas inte i rekommendationslistorna **Trender** eller **Bästsäljande**. Den här situationen kan ofta inträffa för mycket nya produkter eller för gamla produkter som har ett litet antal inköp. Populära nya objekt kan lätt lösa det här problemet.

Vi rekommenderar att du följer dessa steg:
1. **Kontrollera att produkten uppfyller rekommendationskriterierna för listan.** Mer information om parametrar för produktrekommendationer finns i ändra AI-ML-baserade resultat för produktrekommendationer.
1. **Om produkten är ny bör du överväga att ändra en rekommendationslista tills produkten har fler transaktioner.** Mer information om hur du ändrar rekommendationslistans resultat finns i [hantera AI-ML-baserade resultat för produktrekommendationer](modify-product-recommendation-results.md).


- **Kontrollera att produkten uppfyller rekommendationskriterierna för listan.** Mer information om parametrar för produktrekommendationer finns i [hantera AI-ML-baserade resultat för produktrekommendationer](modify-product-recommendation-results.md).
- **Om produkten är ny bör du överväga att ändra en rekommendationslista tills produkten har fler transaktioner**. Mer information om hur du ändrar rekommendationslistans resultat finns i [hantera AI-ML-baserade resultat för produktrekommendationer](modify-product-recommendation-results.md).

## <a name="can-i-remove-a-product-but-still-see-it-in-the-store"></a>Kan jag ta bort en produkt men ändå se den i butiken?

Du kan justera listor som kan genereras med algoritm om en verksamhet behöver uppstå. Om en produkt tas bort från en rekommendationslista kommer produkten att fortsätta vara synlig i butiken. Mer information om hur du ändrar produktrekommendationernas resultat finns i [hantera AI-ML-baserade resultat för produktrekommendationer](modify-product-recommendation-results.md).

Om du måste spärra en artikel från att upptäckas i butiken måste du ändra värdet **Artikelsortiment** till **Exkludera**.

## <a name="how-do-i-add-a-list-to-an-e-commerce-page"></a>Hur lägger jag till en lista på en e-handelssida?

Information om hur du lägger till produktrekommendationssidor på din näthandelsplats finns i [Lägga till listor över produktrekommendationer till sidor](add-reco-list-to-page.md).

## <a name="how-do-i-enable-recommendations-on-pos"></a>Hur aktiverar jag rekommendationer i kassan?

Efter att ha aktiverat produktrekommendationer måste du lägga till rekommendationspanelen till kassans kontrollskärm. För mer information, se [Lägg till en rekommendationskontroll på transaktionsskärmen på kassaenheter](add-recommendations-control-pos-screen.md).

## <a name="additional-resources"></a>Ytterligare resurser

[Översikt av produktrekommendationer](product-recommendations.md)

[Aktivera Azure Data Lake Storage i en Dynamics 365 Commerce-miljö](enable-adls-environment.md)

[Aktivera produktrekommendationer](enable-product-recommendations.md)

[Aktivera anpassade rekommendationer](personalized-recommendations.md)

[Avanmäl anpassade rekommendationer](personalization-gdpr.md)

[Lägg till produktrekommendationer i kassan](product.md)

[Lägg till rekommendationer på transaktionsskärmen](add-recommendations-control-pos-screen.md)

[Justera rekommendationsresultat från AI-ML](modify-product-recommendation-results.md)

[Skapa granskade rekommendationer manuellt](create-editorial-recommendation-lists.md)

[Skapa rekommendationer med demodata](product-recommendations-demo-data.md)
