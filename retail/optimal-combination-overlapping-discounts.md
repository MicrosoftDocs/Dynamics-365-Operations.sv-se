---
title: "Avgöra optimal kombination av överlappande rabatter"
description: "När Rabatterna överlappar bestämmer du både överlappande rabatter som ger lägsta transaktionsbeloppet eller högsta totalrabatt. När rabattbeloppet varierar beroende på priset på de produkter som köps, så som gemensamma &quot;Köp 1, får 1 X procent&quot; rabatt (butik) (BOGO), processen blir det en utleverans optimering för combinatorial."
author: kfend
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.reviewer: kfend
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 89643
ms.assetid: 09843c9a-3e19-4e4a-a8ce-80650f2095f9
ms.search.region: global
ms.search.industry: Retail
ms.author: kfend
ms.search.validFrom: 2016-05-31
ms.dyn365.ops.version: AX 7.0.1
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 31e5104045ed5b8fbfa3677a7f5702d551de4231
ms.lasthandoff: 03/31/2017


---

# <a name="determine-the-optimal-combination-of-overlapping-discounts"></a>Avgöra optimal kombination av överlappande rabatter

När Rabatterna överlappar bestämmer du både överlappande rabatter som ger lägsta transaktionsbeloppet eller högsta totalrabatt. När rabattbeloppet varierar beroende på priset på de produkter som köps, så som gemensamma "Köp 1, får 1 X procent" rabatt (butik) (BOGO), processen blir det en utleverans optimering för combinatorial.

Den här artikeln gäller för Microsoft Dynamics AX 2012 R3 kB 3105973 (utgiven den 2 November 2015) eller senare samt februari 2016 övergång av Microsoft Dynamics AX. Fastställ kombination överlappande rabatter gälla inom rimlig tid och att fortsätta att tillhandahålla omfattande discounting funktioner som ingår i Microsoft Dynamics AX for Retail har vi introducerat en metod för att använda överlappande rabatter. Den nya metoden kallas **marginalnummer värdet rangordning**. Rangordning av marginalnummer värdet används när den tid som krävs för att utvärdera möjliga kombinationer av överlappande rabatter överskrider ett tröskelvärde kan konfigureras på den **RETUR** sida i Dynamics AX. I marginalnummer värdet rangordnas metoden beräknas ett värde för varje överlappande rabatt med den rabattvärdet delade produkter. Överlappande rabatter tillämpas sedan från det högsta värdet relativ till lägsta relativa värde. Mer information om den nya metoden finns i avsnittet "Marginalnummer värde" nedan. Rangordning av marginalnummer värde används inte när rabattbelopp för produkter inte påverkas av en annan produkt i transaktionen. Denna metod används exempelvis inte för två enkla rabatter eller för en enkel rabatt och en enda produkt kvantitetsrabatt.

## <a name="discount-examples"></a>Rabatt-exempel
Du kan skapa ett obegränsat antal retail rabatter på en gemensam uppsättning produkter i Dynamics AX. Men eftersom det inte finns någon gräns, kan prestandaproblem uppstå när du försöker att beräkna rabatter som ska användas för olika produkter. Följande exempel visar det här problemet i detalj. I exempel 1 starta med två produkter och två överlappande rabatter. Sedan i exempel 2 visar hur ärendet utvecklas när läggs fler produkter.

### <a name="example-1-two-products-and-two-discounts"></a>Exempel 1: Två produkter och två rabatter

I det här exemplet krävs två produkter i detta syfte för varje rabatt och rabatterna kan inte kombineras. Rabatter i det här exemplet är **princip** rabatter. Båda produkterna uppfyller kraven för både rabatter. Här följer två rabatter. [![Rabatt överlappande kombinationsrutans 01](./media/overlapping-discount-combo-01.jpg)](./media/overlapping-discount-combo-01.jpg) för två produkter bäst av dessa två rabatter är beroende av priserna för de två produkterna. När priset för båda produkterna är nästan lika eller lika, är ränta 1 bättre. När priset på en vara betydligt mindre än övriga produktens pris, är rabatt 2 bättre. Här är matematiskt regeln för att bedöma dessa två rabatter mot varandra: [![Overlapping rabatt kombinerad 02](./media/overlapping-discount-combo-02.jpg)](./media/overlapping-discount-combo-02.jpg) när priset på produkt 1 är lika med priset på produkt 2 väger, två rabatter är lika. I det här exemplet gäller rabattprocenten för rabatten 1 skiljer sig från några procent (när priser för de två produkterna är åtskilda) till högst 25 procent (när de två produkterna har samma pris). Effektiv rabattprocenten för rabatten 2 ändras. Det är alltid 20 procent. Eftersom effektiv rabattprocenten för rabatten 1 har ett intervall som kan vara mer än eller mindre än 2 rabatt, bästa rabatten är beroende av priserna för de två produkter som måste aktualiseras. I det här exemplet slutförd beräkningen snabbt, eftersom endast två rabatter tillämpas på endast två produkter. Det finns två möjliga kombinationer: ett program då rabatten 1 eller en rabatt 2. Det finns inga permutationer ska beräknas. Värdet för varje rabatt beräknas med hjälp av båda produkterna och bästa rabatten används.

### <a name="example-2-four-products-and-two-discounts"></a>Exempel 2: Fyra produkter och två rabatter

Nu ska använder vi fyra produkter och samma två rabatter. Alla fyra produkter uppfyller kraven för både rabatter. Det finns tolv möjliga kombinationer. I slutändan två rabatter ska kopplas till transaktionen i någon av tre kombinationer: 2 eller ett program då rabatten 1 och en rabatt 2 rabatt i två program för 1, i två program. Vi ska titta på två olika uppsättningar med fyra produkter som kan har olika priser för att illustrera möjliga kombinationer:

-   Alla fyra produkter har samma pris $15.00. I det här fallet är den bästa kombinationen av rabatt två program för 1. Två produkter blir fullt pris och två stängs 50 procent. Den rabatterade summan för transaktionen är $45 (15 + 15 + 7,50 + 7,50), vilket är $15 (25 %) av odiskonterade summan av $60. Rabatten 2 är bara $12 (20 %).
-   Två produkter är varje $20, är $15 för en produkt och en produkt är $5. I det här fallet är den bästa kombinationen av rabatt ett program då rabatten 2 och en rabatt 1. Följande tabeller visar rabatterna.

Använd en produkt från en rad och en produkt från en kolumn om du vill läsa register. Till exempel i registret för rabatt 1 får genom att kombinera de två $20 produkterna du $10. I tabellen för rabatt 2 när du kombinerar $15 produkt och produktens $5 får du $4. [![Rabatt överlappande kombinationsrutans 03](./media/overlapping-discount-combo-03.jpg)](./media/overlapping-discount-combo-03.jpg) först vi se den högsta fakturarabatten finns två produkter med någon rabatt. Två tabeller visar rabattbeloppet för alla kombinationer av de två produkterna. Den skuggade delen av tabellerna representerar antingen fall där en produkt är länkat till själva som vi inte eller två produkter som ger samma par omvänd rabattbelopp och kräver inga åtgärder. Genom att titta i tabellerna ser du att rabatten 1 i två $20-poster är största rabatten som är tillgänglig för någon rabatt på alla fyra produkter. (Den här rabatten markeras med grönt i den första tabellen.) Kvar finns då $15 produkten och produkten som $5. Genom att titta på de två tabellerna igen ser du att rabatten 1 ger en $2.50 rabatt för dessa produkter rabatt 2 ger en rabatt på $4. Vi väljer därför rabatten 2. Den totala rabatten är $14. Du kan förenkla den här diskussionsgruppen genom att visualisera är här två ytterligare tabeller som visar effektiv rabattprocenten för alla möjliga kombinationer av två produkter för båda rabatt 1 och 2 rabatt. Endast halva lista över kombinationer ingår eftersom den ordning som de två produkterna övergår till rabatten ingen spelar roll för dessa två rabatter. Den högsta rabatten (25 procent) som effektivt markeras med grönt och lägsta gällande rabatt (10 procent) markeras i rött. [![Rabatt överlappande kombinationsrutans 04](./media/overlapping-discount-combo-04.jpg)](./media/overlapping-discount-combo-04.jpg)**Obs!:** om två eller flera rabatt konkurrera grupprabatt och det enda sättet att garantera den bästa kombinationen av rabatter är att utvärdera både rabatter och jämföra dem.

## <a name="total-possible-combinations"></a>Totalt antal möjliga kombinationer
Det här avsnittet fortsätter exemplet i det föregående avsnittet. Vi ska lägga till fler produkter och en annan rabatt och se hur många kombinationer måste beräknas och jämförs. Tabellen nedan visar antalet möjliga rabattkombinationer som produkten kvantitet ökar. I tabellen visas vad som händer när det finns två överlappande rabatter, som i föregående exempel såväl när tre överlappande rabatter. Antalet möjliga rabattkombinationer bedömas snart överskrider vad även en snabb dator kan beräkna och jämföra tillräckligt snabbt kunna godtas för butikstransaktioner. [![Rabatt överlappande kombinationsrutans 05](./media/overlapping-discount-combo-05.jpg)](./media/overlapping-discount-combo-05.jpg) även när större kvantiteter eller flera överlappande rabatter det totala antalet möjliga rabattkombinationer placeras snabbt miljontals och den tid som krävs för att utvärdera och markera den bästa möjliga kombinationen snabbt blir tydligt. Vissa optimeringar har gjorts i retail pris engine att minska det totala antalet kombinationer som ska utvärderas. Men eftersom inte begränsat antal överlappande rabatter och kvantiteterna i en transaktion kan har ett stort antal kombinationer alltid ska utvärderas när överlappande rabatter. Detta är problem som rör marginalnummer värdet rangordnas metod.

## <a name="marginal-value-method"></a>Värdemetod Bidragsunderlag
Lös problemet för ett antal kombinationer som ska utvärderas som ökar exponentiellt finns en optimering som beräknar värdet per delade produkten av varje rabatten i uppsättningen produkter som två eller flera rabatter som kan tillämpas på. Vi kallar detta värde som det **marginalnummer värdet** rabatten för delade produkter. Bidragsunderlag värdet är medelvärdet per produkt ökning av det totala rabattbeloppet delade produkter som ingår i varje rabatt. Bidragsunderlag värde beräknas genom att det totala rabattbeloppet (DTotal), avdrag för rabattbeloppet utan delade produkter (DMinus\\ Shared), och denna skillnad divideras med antalet delade produkter (ProductsShared). [![Rabatt överlappande kombinationsrutans 06](./media/overlapping-discount-combo-06.jpg)](./media/overlapping-discount-combo-06.jpg) när Bidragsunderlag värdet av alla rabatter på en delad uppsättning produkter beräknas rabatterna tillämpas på produkterna som är delade måste omfattande, från marginalnummer bokstavsordning till marginalnummer lägsta värde. För den här metoden inte alla resterande radrabatt möjligheter jämfört med varje gång efter en instans av en rabatt har tillämpats. Istället överlappande rabatter jämfört med en gång och sedan tillämpas i ordning. Inga ytterligare jämförelser görs. Du kan konfigurera tröskelvärdet för att växla till metoden Bidragsunderlag värdet den **rabatt** för den **RETUR** sida. Godtagbar tid att beräkna den totala rabatten varierar mellan branscher retail. Nu använder dock vanligtvis mellan tiotals millisekunder en sekund.


