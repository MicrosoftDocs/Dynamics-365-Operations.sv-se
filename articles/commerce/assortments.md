---
title: Sortimenthantering
description: Det här avsnittet beskriver de grundläggande begreppen för sortimenthantering i Dynamics 365 Commerce och ger överväganden för genomförande av projektet.
author: jblucher
manager: AnnBe
ms.date: 03/12/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: josaw
ms.search.region: Global
ms.author: jeffbl
ms.search.validFrom: 2017-11-21
ms.dyn365.ops.version: Application update 5
ms.openlocfilehash: 981d1c604a7ed461f207e78c8c7f073aff03be9e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4980008"
---
# <a name="assortment-management"></a>Sortimenthantering

[!include [banner](../includes/banner.md)]

## <a name="overview"></a>Översikt

Dynamics 365 Commerce ger *sortiment* som gör att du kan hantera produkttillgänglighet genom olika kanaler. Sortiment avgör vilka produkter som är tillgängliga i vissa butiker och under en viss period.

I Commerce är ett sortiment en katalog med en eller flera kanaler (eller grupper av kanaler när organisationshierarkier används) till en eller flera produkter (eller grupper av produkter när kategorihierarkier används).

Den övergripande produktblandningen för en kanal bestäms av det publicerade sortiment som är tilldelat till kanalen. Därför kan du konfigurera flera aktiva sortiment per kanal.

### <a name="basic-assortment-setup"></a>Grundläggande sortimentinställning

I följande exempel konfigureras ett unikt sortiment för varje butik. I det här fallet är endast produkt 1 tillgänglig i butiken 1 och endast produkt 2 är tillgänglig i butik 2.

![Varje produkt är tillgänglig i en butik](./media/Managing-assortments-figure1.png)

För att göra produkt 2 tillgänglig i butik 1 lägger du till produkten sortimentet 1.

![Produkt 2 läggs till i sortiment 1](./media/Managing-assortments-figure2.png)

Alternativt kan du lägga till butik 1 sortiment 2.

![Lagra 1 läggs till i sortiment 2](./media/Managing-assortments-figure3.png)

### <a name="organization-hierarchies"></a>Organisationshierarkier

I situationer där flera kanaler delar samma produktsortiment kan du konfigurera sortimentet med hjälp av organisationshierarkin för handelssortiment. När du lägger till noder från hierarkin inkluderas alla kanaler i den noden och dess underordnade noder.

![Organisationshierarki](./media/Managing-assortments-figure4.png)

### <a name="product-categories"></a>Produktkategorier

På samma sätt på produktsidan kan du inkludera produktgrupper genom att använda produktkategorihierarkier. Du kan konfigurera sortiment genom att lägga till en eller flera kategorihierarkinoder. I det här fallet inkluderar sortimentet alla produkter i kategorinoden och de underordnade noderna.

![Produktkategorier](./media/Managing-assortments-figure5.png)

### <a name="excluded-products-or-categories"></a>Exkluderade produkter eller kategorier

Förutom att inkludera produkter eller kategorier i sortiment kan du använda alternativet Undanta för att definiera specifika produkter och kategorier som ska uteslutas från sortimentet. I följande exempel vill du inkludera alla produkter i en specifik kategori förutom produkt 2. I detta fall behöver du inte definiera sortimentens produkt efter produkt eller skapa ytterligare kategorinoder. Du kan istället bara inkludera kategorin men exkludera produkten.

> [!NOTE]
> Om en produkt är både inkluderad och exkluderad i ett eller flera sortiment per definition kommer produkten alltid att betraktas som exkluderad.

![Exkluderad produkter ](./media/Managing-assortments-figure6.png)

### <a name="global-and-released-products"></a>Globala och frisläppta produkter

Sortiment definieras på global nivå och kan innehålla kanaler från flera juridiska personer. Produkter och kategorier som ingår i sortiment delas också mellan juridiska personer. En produkt måste emellertid frisläppas innan den kan säljas, beställas, räknas eller tas emot i kanalen (till exempel i försäljningsstället \[kassa\]). Även om två butiker i olika juridiska personer kan dela ett sortiment med samma produkter, är produkterna endast tillgängliga om de har frisläppts till dessa juridiska personer.

### <a name="dynamic-and-static-assortments"></a>Dynamiska och statiska sortiment

Du kan definiera sortiment med specifika kanaler och produkter eller genom att lägga till organisationsenheter och kategorier. Sortiment som inkluderar referenser till dessa grupper betraktas som dynamiska sortiment. Om definitionen eller innehållet i grupperna ändras medan sortimentet är aktivt, påverkas även definitionen av sortimentet.

Ett sortiment definieras till exempel ursprungligen och publiceras så att det refererar till en produktkategori. Om ytterliga produkter läggs till i kategorin kommer dessa produkter att inkluderas automatiskt i definitionen av det befintliga sortimentet. Du behöver inte manuellt lägga till produkterna till sortimentet. På samma sätt, om en organisationsenhet läggs till i en annan nod, justeras den organisationsenhetens sortiment automatiskt baserat på definitionen.

### <a name="stopped-products"></a>Stoppade produkter

Du kan ”stoppa” frisläppta produkter för försäljningsprocessen genom att aktivera en inställning i inställningen **standardorder**. Denna inställning används ofta när en produkt är i slutet av dess livslängd och inte kan säljas till vilken kanal som helst. Sortiment respekterar denna inställning och stoppade produkter kommer inte att väljas, oavsett sortimentkonfiguration.

### <a name="blocked-products"></a>Spärrade produkter

Förutom att stoppa försäljningen av en produkt kan du tillfälligt blockera försäljningen av en produkt. Du kan konfigurera den här inställningen på fliken **Commerce** för frisläppt produkt. Spärrade produkter väljs fortfarande ut, men du får ett meddelande i POS om att produkten inte kan säljas.

### <a name="date-effectivity"></a>Gäller från

Sortiment gäller utifrån datum. Återförsäljare kan därför konfigurera när produkter ska eller inte ska vara tillgängliga per kanal. Du kan definiera och publicera sortiment i förväg och ange start- och slutdatumen. Produkterna kommer automatiskt att bli tillgängliga eller inte tillgängliga på bestämda datum.

### <a name="process-assortments-batch-job"></a>Bearbeta batchjobb för sortiment.

Sortiment som har definierats i Commerce måste bearbetas innan de träder i kraft. Denna bearbetning är viktig av följande skäl:

- Definitioner av sortimentet måste vara avnormaliserade så att kanaler lättare kan förbruka dem.. Du kan definiera en produktkombination för en kanal via flera sortiment som sträcker sig över olika datumintervall. När en del av informationen beräknas förväg på servern kommer prestanda i kanalen att förbättras.
- Produkter och kanaler i sortimentet kan ändras utanför själva sortimentet. Dynamiska sortiment med referenser till kategorier eller organisationsenheter måste bearbetas med jämna mellanrum så att de inkluderar eller exkluderar poster utifrån sina aktuella tilldelningar.

## <a name="implementation-considerations"></a>Implementeringöverväganden

Överväg följande implementeringskrav när du planerar och hanterar sortiment för handelsimplementeringen:

- **Datareplikering och databasstorlek** – även om sortiment hjälper företag att hantera produkttillgänglighet, är de också ett viktigt verktyg för att hantera storleken på kanal- och offline-databaser. Välskötta sortiment minskar mängden data som måste bearbetas och replikeras till kanal- och offline-databaser. De hjälper också till att minska antalet poster som måste behållas. Färre poster i databaserna ökar prestandan när du lägger till artiklar till en transaktion, söker och bläddrar efter produkter.
- **Giltighetsdatum/utgående sortiment** – en av de mest effektiva verktygen för hantering av antalet produkter i kanal- och offline-databaser är sortimentens giltighetsdatum. Om du lämnar öppet (ej utgående) sortiment för säsongsvariationer eller produkter som är i slutet av livscykeln kommer dessa databaser att växa på obestämd tid. Du kan använda olika metoder för att hjälpa hantera denna situation. Du kan till exempel ha separata sortiment för säsongsprodukter och produkter som alltid är tillgängliga.
- **Försäljning och returer utanför sortiment** – denna kunskap hjälper återförsäljare att effektivt hantera sina sortiment genom att låta dem begränsa antalet produkter till produkter som tillhör butikens grundläggande produktkombination. Den här funktionen hjälper dig också återförsäljare att hantera situationer där en produkt utelämnades av misstag från ett sortiment och om en produkt har returnerats utanför giltighetsdatumen för sortimentet.

Om produktdata inte finns i kanaldatabasen ringer POS huvudkontoret i realtid för att hämta den information som krävs så att produkten kan säljas, returneras eller sättas på en kundorder. Produktinformation som hämtas på det här sättet finns endast under tillämpningsområdet för den aktuella transaktionen. Produkten läggs inte till i sortimentdefinitionen. Därför görs följande samtal i realtid om det behövs.


[!INCLUDE[footer-include](../includes/footer-banner.md)]