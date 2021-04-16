---
title: Trevägsmatchningspolicyer
description: Den här ämnet innehåller exempel på trevägsmatchning.
author: abruer
ms.date: 10/26/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: VendInvoicePostingHistory
audience: Application User
ms.reviewer: roschlom
ms.custom: 2761
ms.assetid: 70f3cb1a-18b7-4474-95ec-28b2410dd8f8
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 829c9c5549c337c5c2b118f3027111831f2632ca
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5814306"
---
# <a name="three-way-matching-policies"></a>Trevägsmatchningspolicyer

[!include [banner](../includes/banner.md)]

Den här ämnet innehåller exempel på trevägsmatchning.

<a name="example-three-way-matching-for-items"></a>Exempel: trevägsmatchning för artiklar
-------------------------------------

**Sammanfattning:** Ken är kontrollant på högkvarteret för av en juridisk person som heter Fabrikam. Ken bestämmer att alla leverantörsfakturor som baseras på inköpsorder ska matchas med inköpsorder (tvåvägsmatchning). Vid inköp av artiklar som ska användas som anläggningstillgångar, fakturor ska matchas med både inköpsorderrader och produktinleveransrader (trevägsmatchning).

Fabrikam arbetar med flera juridiska personer och medarbetare i hela världen. När volymen av transaktionökningar ökar, ökar även avvikelser mellan inleveranser och fakturor. Detta resulterar i att tillgångar skrivs av. Fakturor från leverantörer betalas, men processen innefattar inte att identifiera avvikelser när färre artiklar tas emot eller när artiklar inte tas emot i alla butiker. Utgifter ökar också eftersom anställda fortfarande behöver verktyg och annat material för att göra sitt jobb. Ken vill vara säker på att leverantörerna skickar de beställda produkterna och att artiklarna tas emot av Fabrikams anställda. Därför behöver Ken tvåvägs- och trevägsmatchning för alla juridiska personer i organisationen. Fakturamatchning ser till att problem med artiklar som har försvunnit eller inte mottagits kan spåras och lösas. 

Fakturamatchningpolicyerna i det här exemplet hjälper människor i följande roller att uppnå sina mål:

-   Ken är kontrollanten för företaget Fabrikam. Han kan hjälpa människor i sin organisation att identifiera och korrigera problem med beställning, mottagning och betalning av artiklar (varor och tjänster) från leverantörer.
-   Phyllis och April är redovisningchefer på ekonomiavdelningen i Fabrikams amerikanska avdelning. De kan tillämpa företagets policy och kontrollera att fakturor betalas, endast efter att fakturorna matchas med inköpsordern och mottagning av varor och tjänster.
-   Tony är produktionchefen för Fabrikams amerikanska avdelning. Han och annan produktionpersonal kan kontrollera att artiklar tas emot som de har beställts från leverantörerna och dessutom bokförs så att personalen har vad de behöver för att kunna utföra sitt arbete.

### <a name="prerequisites"></a>Förutsättningar

-   Ken anger matchningspolicyn på juridisk personnivån till trevägsmatchning.
-   Ken anger Automatiskt uppdatering av växling av huvudmatchningsstatus för den juridiska personen till Ja.
-   Ken anger fältet Matchprissummor för den juridiska personen till Procentsats och anger 15 % som toleransprocent.
-   Ken anger matchningspolicyn på artikelnivån för artikel 1500 – CNC Milicron-datorn till trevägsmatchning. Denna artikel är en tillgångsartikel som används för tillverkning på Fabrikam. Fakturor för artikeln matchas med inköpsorderrader för priser och med produktinleveranser för kvantiteter.
-   Tony anger en rekvisition för fem CNC Milicron-datorer. Alicia, en inköpsorderansvarig på Fabrikam, visar en inköpsorder för en juridisk person som heter Contoso för att leverera artiklarna.

    | Artikelnummer                 | Kvantitet | Enhetspris | Nettobelopp | Kod för avgifter        | Avgiftsvärde |
    |-----------------------------|----------|------------|------------|---------------------|---------------|
    | 1500 – CNC Milicron-dator | 5        | 8 000,00   | 40 000,00  | Transport och hantering | 3 000,00      |

-   Arnie, en kundreskontraansvarig på Contoso, granskar veckans försändelser. Arnie väljer försändelsetransaktioner för att fakturera Fabrikam för leverans av CNC Milicron-datorerna. Arnie inkluderar en avgift för distribution och hantering. Fabrikam ska beakta om avgiften ska ingå i kostnaden för tillgången.

### <a name="scenario"></a>Scenario

1.  Sammy, en anställd på inleveransavdelninen på Fabrikam, tar emot den totala kvantiteten av datorer som levereras från Contoso. Han anger en kvantitet på 5 på en produktinleverans. Eftersom inköpsordern har inlevererats helt, ändras statusen för inköpsordern till Inlevererad.
2.  April, leverantörsreskontrakoordinatorn på Fabrikam, matar in och verifierar fakturan som skickas in av Contoso. Hon verifierar följande information:
    -   För artiklar, som kräver trevägsmatchning, matchar kvantiteten på fakturaraden den kvantitet som har tagits emot. Den mottagna kvantiteten anges på produktinleveransen som är matchad till fakturan.
    -   För artiklar som kräver tvåvägs- eller trevägsmatchning ligger priserna på fakturaraden inom toleranserna som definieras i Microsoft Dynamics 365 Finance. Detta omfattar följande typer av prismatchning:
        -   Matchning av nettopris – Nettopriset per enhet på fakturaraden matchar nettopriset per enhet på inköpsorderraden, inom toleransprocenten. I det här exemplet är nettoenhetspristoleransen +8 %.
        -   Matchning av prissummor – Nettobelopp per enhet på fakturaraden matchar nettobelopp per enhet på inköpsorderraden, inom toleransprocenten, belopp eller procentsats och belopp.  I det här exemplet är toleransen för matchning av prissummor +15 %.

Pappersfakturan från Contoso innehåller följande information.

| Artikel                        | Kvantitet | Enhetspris | Nettobelopp |
|-----------------------------|----------|------------|------------|
| 1500 – CNC Milicron-dator | 5        | 8 100,00   | 40,500.00  |
| Transport och hantering       |          |            | 4,000.00   |
| Skatt                         |          |            | 0,00       |
| Totalt                       |          |            | 44,500.00  |

Fakturaraden inkluderar följande information.

| Artikelnummer                 | Kvantitet | Enhetspris | Nettobelopp för rad | Matchningspolicy    | Matchning av kvantitet för produktinleverans | Prismatchning | Prissummematchning |
|-----------------------------|----------|------------|-----------------|--------------------|--------------------------------|-------------|-------------------|
| 1500 – CNC Milicron-dator | 5        | 8 100,00   | 40 500,00       | Trevägsmatchning | Genomförda                         | Genomförda      | Genomförda            |

Eftersom denna rad genomgår fakturamatchningprocessen, kan fakturan bokföras.

## <a name="example-three-way-matching-for-item-and-vendor-combinations"></a> Exempel: Trevägsmatchning för artikel- och leverantörskombinationer
Sammanfattning: Ken är kontrollant på högkvarteret för av en juridisk person som heter Fabrikam. Ken bestämmer att alla fakturor som baseras på inköpsorder ska matchas med inköpsorder (tvåvägsmatchning). Cassie är bokföringsansvarig på Fabrikans malaysiska avdelning. Hon anger att valda artiklar som har beställts från vissa leverantörer i Malaysia ska matchas med både inköpsorderrad och produktinleveransrader (trevägsmatchning). Hon kan också åsidosätta matchningspolicyn till en högre nivå för att matcha för specifika inköpsorder. 

Volymen och beloppen är små och det har funnit har problem vid leverans från alla leverantörer i Malaysia. Av denna anledning anger Cassie kontrollnivån för vissa artiklar och leverantörskombinationer som anskaffas i Malaysia till trevägsmatchning. 

Fakturamatchningpolicyerna i det här exemplet hjälper människor i följande roller att uppnå sina mål:
-   Ken är kontrollanten för företaget Fabrikam. Han kan hjälpa människor i sin organisation att identifiera och korrigera problem med beställning, mottagning och betalning av artiklar (varor och tjänster) från leverantörer.
-   Cassie är bokföringsansvarig för Fabrikans malaysiska avdelning. Hon kan tillämpa företagets policy och kontrollera att fakturor betalas, endast efter att de matchas med inköpsorderrader och produktinleveranser som representerar inleverans av varor och tjänster. Hon kan även öka kontrollnivån för trevägsmatchning för specifika artiklar för att kontrollera driftskostnader.

### <a name="prerequisites"></a>Förutsättningar

-   Ken anger matchningspolicyn på juridisk personnivån till tvåmatchning.
-   Ken anger fältet Matchprissummor för den juridiska personen till Procentsats och anger 10 % som toleransprocent.
-   Ken kan ange pristoleransinformation för alla artiklar 2 %.
-   Cassie anger matchningspolicyn på artikeln och leverantörkombinationsnivån för artikeln PH2500 – dator och leverantör Contoso till trevägsmatchning.
-   Alicia, en inköpsordeansvarig på Fabrikams malaysiska avdelning, utfärdar inköpsorder till Contoso för att leverera tre artiklar som visas i följande tabell. När hon skapar inköpsordern åsidosätter hon matchningspolicyn för att den trådlösa musen ska vara trevägsmatchning i stället för tvåvägsmatchning.

    | Artikelnummer           | Kvantitet | Enhetspris | Nettobelopp | Matchningspolicy (standardvärde) | Matchningspolicy (på inköpsorderraden) |
    |-----------------------|----------|------------|------------|---------------------------------|----------------------------------------------|
    | PH2500 – dator     | 2        | 2 500,00   | 5 000,00   | Trevägsmatchning              | Trevägsmatchning                           |
    | MM01 – Trådlös mus | 2        | 40,00      | 80,00      | Tvåvägsmatchning                | Trevägsmatchning                           |
    | USB-enhet             | 200      | 10,00      | 2 000,00   | Tvåvägsmatchning                | Tvåvägsmatchning                             |

### <a name="scenario"></a>Scenario

1.  Artiklarna har levererats. Sammy, en anställd på inleveransavdelningen på Fabrikans malysiska avdelning, blir störd och bokför inte produktinleveransen på en gång.
2.  April, leverantörsreskontrakoordinatorn på Fabrikam, matar in och verifierar fakturan som skickas in av Contoso. Hon verifierar följande information:
    -   För artiklar, som kräver trevägsmatchning, matchar kvantiteten på fakturaraden den kvantitet som har tagits emot. Den mottagna kvantiteten anges på produktinleveransen som är matchad till fakturan.
    -   För artiklar som kräver tvåvägs- eller trevägsmatchning ligger priserna på fakturaraden inom toleranserna som definieras i appen. Detta omfattar följande typer av prismatchning:
        -   Matchning av nettopris – Nettopriset per enhet på fakturaraden matchar nettopriset per enhet på inköpsorderraden, inom toleransprocenten. I det här exemplet är nettoenhetspristoleransen +2 %.
        -   Matchning av prissummor – Nettobelopp per enhet på fakturaraden matchar nettobelopp per enhet på inköpsorderraden, inom toleransprocenten, belopp eller procentsats och belopp.  I det här exemplet är toleransen för matchning av prissummor +10 %.

Pappersfakturan från Contoso innehåller följande information.

| Artikel                  | Kvantitet | Enhetspris | Nettobelopp |
|-----------------------|----------|------------|------------|
| PH2500 – dator     | 2        | 2 500,00   | 5 000,00   |
| MM01 – Trådlös mus | 2        | 41.00      | 82.00      |
| USB-enhet             | 200      | 10.05      | 2,010.00   |
| Total faktura         |          |            | 7,092.00   |

Fakturaraden inkluderar följande information.

| Artikelnummer           | Kvantitet | Enhetspris | Nettobelopp för rad | Matchningspolicy    | Matchning av kvantitet för produktinleverans | Prismatchning | Prissummematchning |
|-----------------------|----------|------------|-----------------|--------------------|--------------------------------|-------------|-------------------|
| PH2500 – dator     | 2        | 2 500,00   | 5 000,00        | Trevägsmatchning | Ej genomförda                         | Genomförda      | Genomförda            |
| MM01 – Trådlös mus | 2        | 41,00      | 82,00           | Trevägsmatchning | Ej genomförda                         | Ej genomförda      | Genomförda            |
| USB-enhet             | 200      | 10,05      | 2 010,00         | Tvåvägsmatchning   |                                | Genomförda      | Genomförda            |

Observera följande artiklar:
-   För PH2500EN – datorraden, har kolumnen för produktinleveransmatchning en varningsikon, eftersom fakturarraden inte matchas till en produktinleverans.
-   För MM01 – trådlös mus, har kolumnen för produktinleveransmatchning en varningsikon, eftersom fakturarraden inte matchas till en produktinleverans. Kolumnen Matchning av enhetspris har en varningsikon, eftersom nettopristoleransen på 2 % överskrids.
-   För USB-enhetsraden är kolumnen Matchning av kvantitet för produktinleverans tom eftersom tvåvägsmatchning inte matchar fakturarad och kvantiteter för produktinleveransrad.

Om godkännande krävs för att fakturorna ska bokföras med fakturamatchningsavvikelser, måste Godkänn bokföring med växling av matchningsdiskrepans på sidan Fakturamatchningsdetaljer väljas innan fakturan kan bokföras med prismatchningsfel och kvantitetmatchningsfel. Om godkännande inte krävs kan fakturabearbetning fortsätta om det inte finns några andra bokföringsfel.


Mer information finns i [Översikt över fakturamatchning för leverantörsreskontra](accounts-payable-invoice-matching.md).





[!INCLUDE[footer-include](../../includes/footer-banner.md)]