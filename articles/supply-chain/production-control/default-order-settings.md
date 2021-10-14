---
title: Standardorderinställningar för dimensioner och produktvarianter
description: Standardorderinställningar definierar site och lagerställe som artiklar kommer att anskaffas från eller lagras, och de minimum-, maximum-, multipla- och standardkvantiteter som ska användas för handel eller lagerhantering, ledtider, stoppflagga och orderlöftesmetod.
author: johanhoffmann
ms.date: 09/23/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventItemOrderSetup, InventItemIdLookupByDefaultOrderSetting, EcoResProductReleasedStoppedAllChartPart, UnitTestPartitions
audience: Application User
ms.reviewer: kamaybac
ms.custom: 223084
ms.assetid: fbfbcd7b-dc75-44ab-bffc-8bad576804a4
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: johanho
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 2681a2a13754e240dcc4c99792dc47ae734f6e9e
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/29/2021
ms.locfileid: "7579434"
---
# <a name="default-order-settings-for-dimensions-and-product-variants"></a>Standardorderinställningar för dimensioner och produktvarianter

[!include [banner](../includes/banner.md)]

Standardorderinställningar i Dynamics 365 Supply Chain Management definierar site och lagerställe som artiklar kommer att anskaffas från eller lagras, och de minimum-, maximum-, multipla- och standardkvantiteter som ska användas för handel eller lagerhantering, ledtider, stoppflagga och orderlöftesmetod. Standardorderinställningar används när du skapar inköpsorder, försäljningsorder, överföringsorder, lagerjournaler och genom huvudplanering att skapa planerade order. Standardorderinställningar kan vara artikelspecifika, sitespecifika, produktvariantspecifika eller produktdimensionspecifika.

Om du vill ange standardorderinställningar för en produkt följer du dessa steg.

1. Gå till **Produktinformationshantering** &gt; **Produkter** &gt; **Frisläppta produkter**.
1. Välj relevant produkt i rutnätet.
1. I åtgärdsfönstret, följ ett av dessa steg för att öppna **Standardorderinställningar** för den valda produkten:

    - I fliken **Plan** i gruppen **Orderinställningar** välj **Standardorderinställningar**.
    - I fliken **Hantera lager** i gruppen **Orderinställningar** välj **Standardorderinställningar**.

1. Konfigurera inställningarna enligt beskrivningen i resten av det här avsnittet.

## <a name="default-order-settings"></a>Standardorderinställningar

Det finns tre typer av standardorderinställningar för inköp, försäljning och lager. Standardorderinställningarna för inköp används när det skapas:

- Inköpsorderrader
- Inköpsavtalsrader
- Rader i anbudsförfrågan
- Inköpsrekvisitionsrader
- Påfyllningsrader för försändelse (stöds delvis, se anmärkning)
- Planerade inköpsorder

> [!NOTE]
> När det gäller försändelse påfyllningsorder rader är de enda inställningarna från snabbfliken **Inköpsorder** för sidan **Standard orderinställningar** som används är fältet **standardwebbplats**, fältet **standardlagerställe** och kryssrutan **stoppad**.

Standardorderinställningarna för försäljning används när det skapas:

- Försäljningsorderrader
- Försäljningsavtalsrader
- Försäljningsoffertrader
- Returorderrader och artikelersättningsrader
- Rader i efterfrågeprognos

Standardinställningen för försäljningsorder gäller även när det skapas:

- Projektartikelkrav
- Artikelbehov för serviceorder

Standardorderinställningarna för lager används när det skapas:

- Lagerjournaler.
- Överföringsorder
- Planerade överföringsorder

Standardinställningen för lagerorder gäller även när det skapas:

- Karantänorder
- Kvalitetsorder
- Produktionsorder
- Strukturlisterader
- Planerade produktionsorder

## <a name="full-definition-of-a-released-product"></a>Fullständig definition av en frisläppt produkt

När du skapar en transaktion måste du först ange hela definitionen för en släppt produkt på raden för att Supply Chain Management ska försöka identifiera standardorderinställningarna. "Hela definitionen för en frisläppt produkt" innebär att artikelnumret och alla aktiva produktdimensioner, till exempel konfiguration, storlek, utförande, version och färg specificeras för transaktionen. Om du till exempel manuellt skapar en inköpsorderrad för en frisläppt produktvariant, måste du ange alla nödvändiga produktdimensioner innan site, lagerställe, kvantitet och produktionstid visas som standard på orderraden. 

Alla parametrar för standardorderinställningar används inte när du skapar order eller journalrader. Kvantiteter och ledtider visas som standard endast när så är lämpligt. Exempelvis kommer, vid räkning av en journalrad, endast plats och lagerställe att visas som standard när raden skapas. Av denna anledning utförs ingen standardkvantitet eller kontroller av minimi- och maxvärden att utföras när raden skapas eller journalen bokförs. 

Systemet försöker alltid att hitta en standardsite och lagerställe, när en order eller en journalrad skapas. Siten visas inte alltid som standard från orderinställningarna. Till exempel när du skapar en försäljningsorder eller inköpsorder används siten från orderrubriken automatiskt på orderraderna. När du skapar en strukturlisterad används platsen från sidrubriken Strukturlista. När platsen har fastställts kommer den att användas för att hitta alla eventuella, platsspecifika orderinställningar som sedan kan användas som standardinställningar för lagerstället. 

Standardordertyp, inköp och lagerledtider kan åsidosättas av disponeringsreglerna för artikeln på sidan **Artikeldisponering**. Även om standardorderinställningar inte medger åtskillnad mellan ledtider för produktion och överföring, så medger reglerna för artikeldisponering detta. Men om inställningen för artikeldisponering bara kommer att användas av Huvudplanering (MRP) när du skapar planerad produktion och planerade överföringsorder och inte ska användas när du skapar manuell produktion och överföringsorder. 

## <a name="default-order-settings-rules"></a>Regler för standardorderinställningar

Du kan ange allmänna standardorderinställningar och ett valfritt antal regler för standardorderinställningar som endast gäller i vissa villkor, som till exempel site eller en specifik produktdimension eller produktdimensionskombination. Du kan inte ange specifika orderinställningar för ett lagerställe.

### <a name="rank-in-default-order-settings"></a>Rangordna i standardorderinställningar

Reglerna för standardorderinställningar har rangordningar. Ju högre rangordning desto viktigare är regeln vilket innebär att det kommer att ha en högre prioritet och användas innan reglerna med lägre rangordning. De allmänna standardorderinställningarna har rangordningen noll, som inte kan ändras. Det kan bara finnas en regel med rangordning noll. Regler kan ha samma rangordning, förutsatt att dimensionerna som gäller skiljer sig åt. Detta är användbart för att modellerera sitespecifika orderinställningar. När en ny regel för standardorderinställningar skapas, kommer värdena för ordervärden, stoppflagga, etc. att ärvas från regeln med rangordning noll, men kan åsidosättas.

### <a name="default-order-settings-for-released-products"></a>Standardorderinställningar för frisläppta produkter

För specifika frisläppta produkter kan du definiera allmänna orderinställningar eller sitespecifika orderinställningar. De allmäna orderinställningarna kommer alltid att ha rangordning noll. Om du ställer in nya försäljningar, inköp och lagerorderinställningar tillsammans samtidigt, rekommenderar vi att du använder **Informationsvy** på sidan **Standardorderinställningar**. För att växla till informationsvyn, gå till **Alternativ** &gt; **Sidalternativ** &gt; **Ändra vy** &gt; **Detaljvy**.

### <a name="site-specific-order-settings"></a>Platsspecifika orderinställningar.

För att skapa sitespecifika orderinställningar klickar du på **Nytt**. I **Detaljvyn**, ange platsen i fältet **Plats** i avsnittet **Giltiga inställningar för**. I **Diagramvy** anger du i kolumnen **Plats**. Den nya regeln tilldelas automatiskt ett nytt rangordningsvärde som är större än 0 (noll). Du kan skapa till så många platsspecifika regler som du behöver. Om du vill visa att de är lika viktiga kan du tilldela samma rangordningsvärde till alla platsspecifika regler.

Om du är i **Detaljvy**, kan du inte få en överblick över reglerna som skapats för artikeln. Använd knappen **Visa/dölj lista** om du vill visa översiktsinformation. När en orderrad av något slag skapas och inte har någon angiven plats, söker Supply Chain Management efter en regel utan angiven site. Detta kan hjälpa till att bestämma en standardplats på orderraden. Den här siten används sedan till att söka efter en specifik regel där ett standardlagerställe kan ha ställts in. Detta lagerställe används för orderraden.

### <a name="specific-order-settings-for-product-dimension"></a>Specifika orderinställningar för produktdimension

Du kan definiera orderinställningsregler för alla aktiva produktdimensioner eller kombination av aktiva produktdimensioner. Om ett produktdimensionsfält lämnas tomt, gäller regeln för alla värden av produktdimensionen. 

Beakta följande exempelprodukt.

| Artikel                                                | Värde                                   |
|-----------------------------------------------------|-----------------------------------------|
| **Produktnamn**                                    | Fotoelektrisk sensor                    |
| **Artikelnummer**                                     | XW56                                    |
| **Konfiguration** (används till att forma typ av belysning) | C1 - synligt rött ljus, C2 - infrarött ljus |
| **Version** | V1, V2, V3                              |

Anta för detta exempel att produkten anskaffas med inte tillverkas. Anta också att konfigurationen C1 används mer allmänt, så den har kortare ledtider. 

Skapa följande standardorderinställningar för att forma det här scenariot.

| Rangordning | Site | Inställningar | Version | Inköp - Åsidosätt standardinställningar | Ledtid för inköp | Inköp - Stoppat | Försäljning - Åsidosätt standardinställningar | Försäljning - Stoppad |
|------|------|---------------|-------|--------------------------------------|--------------------|--------------------|-----------------------------------|-----------------|
| 10   |      | C1            |       | Ja                                  | 2                  |                    |                                   |                 |
| 0    |      |               |       |                                      | 5                  |                    |                                   |                 |

När en inköpsorderrad eller en planerad inköpsorder skapas för artikel XW56, konfiguration C1, kommer ledtiden anses vara 2 oavsett version eller platsen som raden placeras på. Anta att alla versioner förutom V3 stoppas.

Du kan skapa följande regler för standardorderinställningar.

| Rangordning | Site | Inställningar | Version | Inköp - Åsidosätt standardinställningar | Ledtid för inköp | Inköp - Stoppat | Försäljning - Åsidosätt standardinställningar | Försäljning - Stoppad |
|------|------|---------------|-------|--------------------------------------|--------------------|--------------------|-----------------------------------|-----------------|
| 20   |      |               | V2    | Ja                                  |                    | Ja                | Ja                               | Ja             |
| 20   |      |               | V1    | Ja                                  |                    | Ja                | Ja                               | Ja             |
| 10   |      | C1            |       | Ja                                  | 2                  |                    |                                   |                 |
| 0    |      |               |       |                                      | 5                  |                    |                                   |                 |

De två reglerna för att stoppa de äldre versionerna har samma rangordning. Därför är de lika viktiga. Eftersom båda av dessa regler har en högre rangordning än regeln för konfiguration C1 vilket innebär att de åsidosätter regeln för konfiguration C1. 

I det här exemplet förklaras behovet av rangordningen. Om rangordningen inte används, när en inköpsorder skapas för konfiguration C1 och version V2, kommer de två reglerna som är definierade för V2 och C1 att vara tvetydiga. För att lösa otydligheten kommer Supply Chain Management att söka genom reglerna i fallande rangordning och tillämpa den första tillämpliga regeln. I den aktuella instansen, när en inköpsorderrad skapas för konfiguration C1 och version V2, får användaren ett varningsmeddelande att artikeln är spärrad och att detta orsakas av versionsvärdet. Om regeln för konfigurationen har en högre rangordning än den för version, skulle skapandet av en inköpsorderrad för konfiguration C1 och version V2 ha lyckats, och inget meddelande med "artikeln spärrad" skulle visas för användaren. 

Beakta följande regler för standardorderinställningar.

| Rangordning | Site | Inställningar | Version | Standardplats | Standardlagerställe | Inköp - Åsidosätt standardlagringsdimensioner | Inköpslagerställe |
|------|------|---------------|-------|--------------|-------------------|------------------------------------------------|--------------------|
| 20   | 2    |               |       |              |                   | Ja                                            | 22                 |
| 10   |      | C1            |  V2   |  2           |  21               |                                                |                    |
| 0    |      |               |       | 1            | 11                |                                                |                    |

Systemet korsar uppsättningen av regler två gånger för att bestämma site och lagerställe. När en inköpsorderrad skapas för konfigurationen C1, version V2, bestäms platsen utifrån regeln med rangordningen 10. Systemet söker sedan efter en regel för plats 2 i syfte att fastställa ett lagerställe. Regel 20 hittas och eftersom den har en högre rangordning, kommer lagerstället på inköpsorderraden vara 22 och inte 21.

Som en allmän vägledning kommer specifika regler och regler för dimensioner som är viktigare än andra dimensioner att få en högre rangordning, medan mer allmänna regler får lägre rangordning. 

Regeln med rangordning noll fungerar som ett skyddsnät. Om inga andra regler hittas, kommer standardorderinställningarna från regel noll att användas. 

Eftersom rangordningsnumret är så viktigt, finns det på åtgärdsfönstret **Standardorderinställningar** funktioner som flyttar en regel upp eller ned så att de alltid är i steg om 10. 

Antalet regler som har skapats för en frisläppt produkt kan vara många. För att få en bättre känsla för vad varje regel åsidosätter och varför den behövs, rekommenderar vi att använda **Rutnätsvy** på sidan **Standardorderinställningar**. Du kan aktivera rutnätsvy genom att gå till **Alternativ** &gt; **Sidalternativ** &gt; **Ändra vy** &gt; **Rutnätsvy**. Antalet kolumner som visas i rutnätet kan vara ganska betydande, särskilt för försäljnings- och lagerflikarna. Om du vill begränsa antalet kolumner som visas i rutnätet, kan du dölja eller visa grupper av kolumner genom att använda knapparna i menyn **Standardorderinställningar** &gt; **Visa kolumn**.

### <a name="specific-order-settings-for-released-product-variant"></a>Specifika orderinställningar för frisläppta produktvarianter

Om regelsystemet för standardorderinställningar är för besvärligt finns alternativet att definiera standardorderinställningar för varje produktvariant. Följande exempel visar hur detta ser ut för produkten och de fall som beskrivs nedan.

| Rangordning | Site | Inställningar | Version | Inköp - Åsidosätt standardinställningar | Ledtid för inköp | Inköp - Stoppat | Försäljning - Åsidosätt standardinställningar | Försäljning - Stoppad |
|------|------|---------------|-------|--------------------------------------|--------------------|--------------------|-----------------------------------|-----------------|
| 10   |      | C2            | V3    | Ja                                  | 5                  |                    |                                   |                 |
| 10   |      | C2            | V2    | Ja                                  | 5                  | Ja                | Ja                               | Ja             |
| 10   |      | C2            | V1    | Ja                                  | 5                  | Ja                | Ja                               | Ja             |
| 10   |      | C1            | V3    | Ja                                  | 2                  |                    |                                   |                 |
| 10   |      | C1            | V2    | Ja                                  | 2                  | Ja                | Ja                               | Ja             |
| 10   |      | C1            | V1    | Ja                                  | 2                  | Ja                | Ja                               | Ja             |
| 0    |      |               |       |                                      | 5                  |                    |                                   |                 |

Rangordningen i det här fallet har ingen betydelse, så du kan välja att dölja den. Den här lösningen har potentiellt ett underhållsproblem. Du kan dock behöva överväga att använda denna inställning om du funderar på att integrera med PML-system (Livscykelhantering för produkt).

## <a name="use-strict-or-standard-validation-of-default-order-quantities"></a>Använda strikt eller standardvalidering av standard orderantal

Du kan välja hur strikt systemet ska vara när de validerar de kvantiteter som anges i **Standardorderinställningar** för en produkt. När du använder det nya strikta alternativet måste **standardkvantiteten** alltid vara en multipel av det angivna **multipla** värdet för inköpsorder, lager och försäljningsorder. Om du använder strikt validering kan du inte spara standardorderinställningar som inte uppfyller dessa krav (och ett fel visas i meddelandefältet). 

Strikt validering gäller de värden för **Standardorderkvantitet** som anges på snabbflikarna **Inköpsorder**, **Lager** och **Försäljningsorder** på sidan **Standardorderinställningar**. Varje snabbflik har en egen inställning för **Flera** som används för att validera värdet **Standardorderkvantitet** som angetts för den valda snabbfliken.

### <a name="enable-the-strict-validation-option"></a>Aktivera strikt valideringsalternativ

Innan du kan använda alternativet strikt validering måste den aktiveras i ditt system. Administratörer kan använda sidan [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs. Här visas funktionen i listan:

- **Modul** - *Produktinformationshantering*
- **Funktionsnamn** - *Strikt validering för standardorderkvantitet*

### <a name="set-the-validation-option"></a>Ange valideringsalternativ

Ange valideringsalternativ:

1. Gå till **Produktinformationshantering \> Konfigurera \> Parametrar för produktinformationshantering**.
1. På fliken **Allmänt** ange **Validering för standardorderkvantitet** till ett av följande värden:
    - **Strikt** – Välj det här alternativet om du vill se till att alla **Standardorderkvantitet** blir en multipel av det **multipla** värdet för varje snabbflik (**inköpsorder**, **lager** och **försäljningsorder**).
    - **Standard** – Välj det här alternativet om du vill använda standardvalidering (som fungerar på samma sätt som funktionen inte aktiverad).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]