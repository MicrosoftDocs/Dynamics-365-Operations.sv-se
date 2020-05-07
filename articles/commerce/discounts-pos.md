---
title: Visa rabatter i kassan
description: I det här avsnittet beskrivs hur Microsoft Dynamics 365 Commerce hjälper säljarna att lära sig mer om erbjudanden och hur de kan användas för korsförsäljning och merförsäljning.
author: ShalabhjainMSFT
manager: AnnBe
ms.date: 03/06/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-Commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail, Commerce
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail, Commerce
ms.author: asharchw
ms.search.validFrom: 2020-02-28
ms.dyn365.ops.version: Application update 10.0.10
ms.openlocfilehash: 89f7b79733f01c089a16c507b127b23ada5df1a6
ms.sourcegitcommit: 02640a0f63daa9e509146641824ed623c4d69c7f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2020
ms.locfileid: "3265601"
---
# <a name="show-discounts-in-pos"></a>Visa rabatter i kassan

[!include [banner](includes/banner.md)]

Erbjudanden spelar en viktig roll när det gäller att motivera kunder som fattar köp beslut. Helgdagar kan till exempel producera det högsta antalet försäljningar för detaljhandlare, eftersom hela detaljhandels marknaden är översvämmad med lockande kampanjer och rabatter. Om butiksintressena känner till och förstår de erbjudanden som är tillgängliga kan de enkelt utnyttja dessa erbjudanden för att sälja och merförsälja artiklar. I det här avsnittet beskrivs hur Microsoft Dynamics 365 Commerce hjälper säljarna att lära sig mer om erbjudanden och hur de kan användas för korsförsäljning och merförsäljning.

## <a name="learn-about-store-discounts"></a>Lär dig mer om butiksrabatter

Commerce inkluderar en operation med namnet "Visa alla rabatter". Den här åtgärden visar alla rabatter som för närvarande körs i en butik. Åtgärden "Visa alla rabatter" kan mappas till en knapp i kassan (POS), och den knappen kan läggas till på **Välkomstsidan** eller på **transaktionssidan**. Följande illustration visar ett exempel på listsidan **alla rabatter** som är öppna.

![Sidan alla rabatter](./media/View_all_discounts.png "Sidan alla rabatter")

Om du vill visa rabatter letar systemet efter alla rabatter som matchar ett eller flera av följande villkor:

- Prisgruppen för rabatten matchar butikens prisgrupp.
- Rabattens prisgrupp mappas till ett anknytning eller förmånsprogram.
- Rabattens prisgrupp mappas till en katalog som är kopplad till butiken.

Sidan **Alla rabatter** sidan visar bara några kupongbaserade rabatter, eftersom detaljhandlare vanligtvis skapar tusentals kuponger och motsvarande rabatter för unika kunder, och den här sidan är inte avsedd att visa kundspecifika rabatter. Kupongbaserade rabatter visas bara om alternativet **Använd utan kupongkod** är aktiverat i varje kupongrubrik. I så fall kan kassörerna tillämpa kupongen utan att behöva ange eller skanna kupongkoder eller streckkoder.

När alternativet **Använd utan kupongkod** är aktiverat blir olika scenarier tillgängliga. Kassörer kan till exempel ge ytterligare rabatter till kunder för att blidka kunder eller på grund av produktfel. Tryckta kupongkoder eller streckkoder behöver inte distribueras till kassörer. Kassörer kan istället välja knappen **Använd kupong**. Kupongen används sedan automatiskt på transaktionen. Om det finns flera kuponger för en kupongrubrik väljer systemet automatiskt den första aktiva kupongen på transaktionen.

På sidan **alla rabatter** kan säljarna också söka efter rabatter med nyckelord. Nyckelordssökningen söker i fälten som innehåller rabattnamnet och rabattbeskrivningen. Försäljningspartner kan också filtrera rabatter baserat på om en rabatt krävs för en kupongkod.

## <a name="cross-sell-and-upsell-by-using-discounts"></a>Mellan försäljning och merförsäljning med hjälp av rabatter

Samköpsrabatter, t.ex. kvantitetsrabatter, mixa och matcha-rabatter och tröskelrabatter, är ett utmärkt sätt att motivera kunder för att köpa fler produkter för att få större rabatter. Därför bidrar de också till att öka storleken på kundens kundvagn och återförsäljares intäkter. Dessa rabatter kan publiceras på webbplatser för näthandel, på sociala medier och på banderoller i butiken.

Även när alla dessa annonseringsmetoder används kan kunden missa möjligheten att utnyttja erbjudanden. För att göra det enklare för säljare att ta reda på vilka erbjudanden som gäller för en vald rad, eller till hela kundvagnen, kan återförsäljare lägga till knappen för åtgärden "Visa alla rabatter" i alla knappsatser i kassan. Vi rekommenderar att du lägger till knappen i knappsatsen på sidan **transaktion**. På så sätt kan en säljare välja en transaktionsrad och sedan välja knappen för att visa alla rabatter som är tillgängliga för den valda raden. Säljare kan också välja en annan flik för att Visa rabatter som gäller för hela transaktionen.

Sidan **alla rabatter** som nämnts tidigare visar endast rabatter som inte konkurrerar med någon av de kopplade rabatterna. På så sätt säkerställs att om en säljare informerar en kund om en rabatt och kunden vidtar den åtgärd som krävs (t.ex. kunden köper ytterligare en artikel för att få 10 procents rabatt) används rabatten på transaktionen. Som nämndes tidigare visas endast kupongbaserade rabatter om alternativet **Använd utan kupongkod** är aktiverat.

I ett enkelt scenario där alla rabatter har samma prioritet är concurrency-läge för rabatt **sammansatt** och concurrency-läge för rabatt anges till **Bästa pris och sammansatt inom prioritet, aldrig sammansatt över prioriteringar**, sidan **Alla rabatter** visar alla tillgängliga rabatter för en produkt, eftersom alla rabatter är sammansatta och konkurrerar med varandra.

Följande illustrationer visar logiken som avgör vilka rabatter som ska visas i avancerade scenarier, till exempel ett scenario där läget för rabatt samtid är **Bästa pris** eller **Exklusiv** och två eller flera prioriteter används. I dessa scenarier påverkas rabatterna som visas ytterligare beroende på om rabattkontrollen är inställd på **Bästa pris och sammansatt inom prioritet, aldrig sammansatt över prioriteringar** eller **Bästa pris endast inom prioritet, alltid sammansatt över prioritet**.

Följande bild visar den logik som används när concurrency-läge för rabatt är inställd på **bästa pris och sammansatt inom prioritet, aldrig sammansatt över prioritet**.

![Logik för bästa pris och förening inom prioritet, aldrig sammansatt över prioritet](./media/Model_1.png "Logik för bästa pris och förening inom prioritet, aldrig sammansatt över prioritet").

Följande bild visar den logik som används när concurrency-läge för rabatt är inställd på **bästa pris endast inom prioritet, alltid sammansatt över prioritet**.

![Logik för bästa pris endast inom prioritet, alltid sammansatt över prioritet](./media/Model_2.png "Logik för bästa pris endast inom prioritet, alltid sammansatt över prioritet").
