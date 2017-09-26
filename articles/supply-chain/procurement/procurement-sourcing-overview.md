---
title: "Upphandling och inköp – översikt"
description: "Det här avsnittet ger en översikt över de funktioner som är tillgängliga i modulen Anskaffning och källa."
author: FrankDahl
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 58021
ms.assetid: eea24e23-a803-4de0-a218-6485757cde1b
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: d3669de6314e65c78ce5d401dae2e7481ec38b68
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017

---

# <a name="procurement-and-sourcing-overview"></a>Upphandling och inköp – översikt

[!include[banner](../includes/banner.md)]


Det här avsnittet ger en översikt över de funktioner som är tillgängliga i modulen Anskaffning och källa.

Upphandling och inköp omfattar alla steg från att identifiera ett behov av produkter och tjänster genom att anskaffa produkten, kvitto, fakturering och bearbetning av betalning med säljare. Upphandlingar kan konfigureras mot specifika verksamhetsbehov genom att definiera inköpspolicy och arbetsflöden.

## <a name="identifying-a-need-for-product-and-services"></a>Identifiera ett behov av produkter och tjänster.
Behovet av produkter eller tjänster som kan uppstå från *anmodan*, till exempel när en anställd behöver en produkt. *Produktkataloger *kan ställas in för att styra urvalet av tillgängliga produkter att välja mellan, eller förfrågningar kan göras för produkter som ännu inte är tillgängliga i en katalog, så att inköpsavdelningen att överväga hur produkten kan levereras.  

*Utgiftsramen *kan användas för att begränsa utgifterna för anmodan och*inköp arbetsflöde *ger möjlighet att kräva godkännande innan beställning sker. Det är också möjligt att ange budget anslag, om det behövs.  
  
Upphandling avdelningen identifierar leverantörer för varor och tjänster, och detta kan innebära en*offertförfrågan *som skickas ut till flera potentiella leverantörer. Det är möjligt att dela specifikationer för produkten som begärts och potentiella leverantörer kan visa dessa för att se om de kan leverera en produkt som uppfyller dem. Säljare tillbaka sina anbud som sedan granskas av inköpsavdelning innan de väljer den leverantör som de vill anskaffa från.  

Inköpsorder har ett alternativ för att skicka en *inköpsorder *till leverantören som ett alternativ till en mer omfattande offertförfrågan. Köp undersökning kan användas för att bidra till att skapa villkor som priser, rabatter och leveransdatum. Om leverantörer är inställda för användning av **Leverantör**portalen kommer inköpsförfrågan funktionen att inaktiveras. I stället delas på**säljaren** portal, och när en*begäran om bekräftelse* skickas säljaren kan direkt bekräfta ordern.  

*Säljaren kataloger *kan användas för att samla in information om produktsortiment som leverantörer kan leverera. Säljare kan publicera sin egen katalog, så det är enklare att hålla katalogen aktuell. Det är möjligt att bifoga en*lista över godkända leverantörer* till en produkt, och detta kan vägleda säljaren val när nya inköpsorder är öppnade och förhindra användning av oavsiktliga leverantörer.

## <a name="procurement"></a>Anskaffning
*Inköpsorder *kan skapas på ett antal olika sätt, inklusive:

-   Som resultat av huvudplanering som har identifierat en efterfrågan kräver som ett inköp. Den här processen genererar planerade inköpsorder och när dessa frisläpps skapas inköpsorder.
-   Genom bearbetning av inköpsanmodan som resulterar i en upphandling.
-   Genom bearbetning av inköpsavtal, där inköpsorder skapas som frisläppta order från avtalen. Detta används vanligen när inköpsavtal används för att representera avtalsorder.
-   Manuellt när inköpsordern som skapas är inte baserat på något annat dokument.

Inköpsorder som är konfigurerad med *köpet arbetsflöden för godkännande* godkännande innan de registreras som godkänd, och det krävs innan ordern kan bearbetas ytterligare.  

Inköpsorder *bekräftas* att representera ett avtal har upprättats med säljaren. Inköpsordern kommer därefter gradvis utveckling genom olika medlemsstater tills slutligen ska faktureras eller makulerad.  

När du skapar en inköpsorder fylls många av fälten i med förvalda värden från den information som finns lagrad om leverantören på sidan **Leverantörer**. Detta innebär att det finns ett begränsat antal fält som du behöver fylla i på inköpsordern, men du kan välja att åsidosätta standardvärdena.

### <a name="prices-and-discounts"></a>Priser och rabatter

Priser och rabatter innehåller information om priser, rabatter och avdrag som de erbjuder. Priser och rabatter kan representeras som *handels**avtal*. Handelsavtal representera säljaren prislistor med priser eller rabatter, och har en viss uppsättning datum som avtalet är giltigt. Priser och rabatter kan förhandlas och representeras genom *köpeavtal *med villkor som att köpa vissa kvantiteter eller belopp som en förutsättning för förhandling. *Rabatt avtal *kan skapas med leverantörer där upphandling av specifika produkter eller grupper av produkter kan utlösa en rabatt från leverantören beroende på köpeskillingen eller volym.

### <a name="delivery-options"></a>Leveransalternativ

Det finns olika alternativ för leverans som förknippas med en inköpsorder. Beställda produkter kan delas in i *leveransplaner* , där delar av den beställda kvantiteten kan planeras för leverans vid olika tidpunkter. Leverans kan även innefatta *direktleverans* initierade från en försäljningsorder, som automates generation på följesedeln på försäljningsorder samtidigt som produkten inleverans registreras på inköpsordern. Inköpsorder kan också vara en del av en *koncernintern för *kedjan, även kallad koncernintern inköpsorder, där produkter kan beställas från en matchande koncernintern försäljningsorder. I denna situation har vissa åtgärder är automatiserade över två närstående intern order.

### <a name="supplementary-items"></a>Fyllnadsartiklar

Produkter kan vara inställd på att innefatta *kompletterande artiklar*. Detta är att föreslå produkter som är relaterade till den produkt som beställs. Ytterligare produkter kan behövas, eller vara frivillig. I vissa fall kompletterande artiklar kan läggas till som fria produkter som medföljer köp av andra produkter.

### <a name="purchase-order-charges"></a>Inköpsorderavgifter

Avgifter kan tilldelas till inköpsordern. Detta kan ske automatiskt genom installation av automatiska avgifter eller genom att lägga till avgifter manuellt. Avgifter kan tilldelas ordern på huvudnivån, eller på orderraden. Redovisning av avgifter kan ställas in på olika sätt. Du kan till exempel ställa in en avgift ska redovisas som en produkt. Om du gör detta avgifter måste tilldelas på orderraden nivå innan ordern kan bekräftas. Det är ett alternativ som kan hjälpa fördela kostnader från orderhuvudet till linjerna.

## <a name="product-receipt-and-invoicing"></a>Produkt inleverans och fakturering
Inköpsorder som inkluderar fysiska produkter som vanligen kräver *ankomstregistrering* sker inom ett lager, och efter detta en *produkt inleverans *är registrerade för den aktuella ordern. Inköpsorder med produkter som uppfyller anmodan kan konfigureras så att den person som har begärt att produkter måste också lämna en*bekräftelse på mottagandet*.  

Några inköpsorder med produkter som tjänster eller andra icke-fysiska produkter där inleverans i lager behövs inte. Produkter kan skapas som tjänster eller *upphandling kategorier *kan användas direkt på inköpsordern för sådana beställningar. Med dessa beställningar, redovisning av produktens mottagandet är ibland hoppade och ordern är fakturerad direkt eller alternativt produkt inleverans registrering görs på inköpsordern utan någon föregående ankomstregistrering.  

Mottagande av produkter kan resultera i automatisk energiförbrukning för ett specifikt ändamål. Här ingår underförstådda förbrukning med direktleverans, förbrukning mot en projekt- eller redovisning produkten som en anläggningstillgång.  

När* säljaren fakturor* anländer från säljaren kan de första antecknas i *fakturan registreras *oberoende av inköpsorder och senare godkännas som rekord mot inköpsordern. Registrering av leverantör faktura med inköpsordern innehåller matchning av produkt inleverans mot faktura.  

*Redovisning distributioner* kan anges på inköpsordern för att beskriva hur bokföring ska ske inom redovisning, och kan även ange hur budgeten medelstilldelning erhålls när den ingår i din konfiguration.  

Fakturerade inköpsorder registrera ansvar till säljaren inom payable konton, där *v*e*grogrund för betalning *kan bearbetas.

## <a name="vendor-performance"></a>Leverantörsprestanda
Prestanda och översyn av inköp stöds genom *upphandling och leverantörsskulder rapporter* som inkluderar tillbringa analys och säljaren prestanda-analys.




