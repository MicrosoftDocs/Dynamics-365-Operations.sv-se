---
title: Hantera AI-ML-baserade produktrekommendationsresultat
description: I det här avsnittet beskrivs hur du skräddarsyr resultat för produktrekommendationer baserat på maskininlärning med artificiell intelligens (AI-ML) till ditt företag.
author: bebeale
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
ms.author: bebeale
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: 669b056c38614c8ac9be2d7b244a0ab0c73bc9f8
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770080"
---
# <a name="manage-ai-ml-based-product-recommendation-results"></a>Hantera AI-ML-baserade produktrekommendationsresultat

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

I det här avsnittet beskrivs hur du skräddarsyr resultat för produktrekommendationer baserat på maskininlärning med artificiell intelligens (AI-ML) till ditt företag. 

När du har aktiverat produktrekommendationer börjar standardinställningarna att gälla. Dessa parametrar fungerar kanske för många behov. Det är bäst att planera att ägna en stund åt att bedöma om resultatet passar produkternas försäljningsrörelse. Vi föreslår utvärdering av resultat under några dagar innan parametrarna ändras efter behov innan de testas igen. 

## <a name="understanding-recommendation-list-parameters"></a>Förstå parametrar för rekommendationslista

Innan du ändrar parametrarna ska du lära dig hur de påverkar resultaten nedan.

### <a name="trending-product-list"></a>Produktlista för trender

Produktlistan **trender** har två parametrar som kan ändras: ![exempel på standardparametrar för trendlista](./media/exampletrendingparameters.png)
1. **Inkludera nya produkter från de senaste X dagarna** – produkter som har lagts till inom det angivna antalet dagar innan det aktuella datumet kan användas för att välja produktkandidater. Standardvärdet i bilden föreslår att produkter som är så gamla som 180 dagar kan användas i produktlistan för trender.
1. **Inkludera nya försäljningar från de senaste X dagarna** – Försäljningstransaktioner som har inträffat till inom det angivna antalet dagar innan det aktuella datumet kan användas för att beställa produkterna. Standardvärdet ovan innebär att alla inköp av en produkt under de senaste 30 dagarna ska användas för att fastställa produktens placering i produktlistan för trenden. 

### <a name="best-selling-product-list"></a>Produktlistan bästsäljare

Beroende på din verksamhet kan bästsäljare få andra resultat än trender, även om de båda använder transaktionsdata för att beställa produkter. Eftersom bästsäljare inte har något upphörande baserat på sortimentdatum, kan bästsäljare fortfarande markera mycket populära äldre produkter som har släppts från trendlistan. 

Produktlistan **bästsäljande** har en parameter som kan ändras:

![Exempel på standardparameter för bästsäljarlista](./media/examplebestsellingparameters.PNG)
1. **Inkludera nya försäljningar från de senaste X dagarna** – Försäljningstransaktioner som har inträffat till inom det angivna antalet dagar innan det aktuella datumet kan användas för att beställa produkterna. Standardvärdet ovan innebär att alla inköp av en produkt under de senaste 30 dagarna ska användas för att fastställa produktens placering i produktlistan för bästsäljare. 

## <a name="manually-add-or-remove-products-from-recommendation-lists"></a>Lägga till eller ta bort produkter manuellt från rekommendationslistor

### <a name="for-new-trending-or-best-selling"></a>För ny, trend eller bästsäljare

1.  Gå till **Butik** > **Produktrekommendationer** > **Rekommendationsparametrar**.
1.  I listan över delade butiksparametrar, välj **Rekommendationslistor**.
1.  Välj listan att lägga till eller ta bort produkter från.
1.  För att lägga till produkter i tabellen, välj **Lägg till rad**. 
1.  Under kolumnen produkt, sök efter en ny produkt efter **Namn** eller **Produktnummer.**
![Exempel på sökning efter en produkt i listan Ny produkt](./media/examplenewlistconfiguration1.png)
1.  Välj ett av två alternativ under kolumnen Radtyp:
    -   **Inkludera** – framtvingar en produkt överst i listan
    -   **Exkludera** – tar bort en produkt från att visas i listan ![exempel på inkludering av eller exkludering av en produkt från den nya produktlistan](./media/examplenewlistconfiguration2.png)
1.  Att ändra **Visningsorder** ändrar ordningen där produkter som markerats **inkludera** visas i listan.
    - Om två produkter har samma **visningsordningsvärde** kan den slutgiltiga ordningen på dessa två resultat skilja sig från backoffice.
1.  Så här tar du bort produkter från registret: Markera raden som du vill ta bort och välj **ta bort**.


### <a name="for-people-also-like-or-frequently-bought-together-lists"></a>För listorna Människor gillar också eller Ofta köpt tillsammans

I samband med **Ofta köpt tillsammans** eller **Människor gillar också** används maskininlärning för att analysera konsumenternas inköpsmönster för att rekommendera relaterade produkter som vanligtvis köps tillsammans för en unik startprodukt. 
 
En **startprodukt** är den produkt som du vill generera resultat för. I samband med att du manuellt justerar rekommendationslistor lägger du till eller tar bort resultat för den här produkten. 

Följ dessa steg för att lägga till eller ta bort resultat för en startprodukt manuellt:
1.  Välj **startprodukt**. 
1.  Under kolumnen **produkt** sök efter en ny produkt efter **Namn** eller **Produktnummer.**
![Exempel på sökning efter en produkt i listan Ofta köpt tillsammans](./media/exampleFBTlistconfiguration1.png)
1. Välj ett av två alternativ under kolumnen **Radtyp**:
    - **Inkludera** – framtvingar en produkt överst i listan
    - **Exkludera** – tar bort en produkt från listan     
![Exempel på inkludering eller exkludering av en produkt i listan som ofta köps ihop](./media/exampleFBTlistconfiguration2.png)
1.  Så här tar du bort produkter från registret: Markera raden som du vill ta bort och välj ta bort.


## <a name="additional-resources"></a>Ytterligare resurser

[Översikt av produktrekommendationer](product-recommendations.md)

[Aktivera produktrekommendationer](enable-product-recommendations.md)

[Lägg till produktrekommendationer på sidor](add-reco-list-to-page.md)
