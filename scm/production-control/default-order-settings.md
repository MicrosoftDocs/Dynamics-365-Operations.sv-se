---
title: "Standardorderinställningar för dimensioner och produktvarianter"
description: "Standardorderinställningar definierar site och lagerställe som artiklar kommer att anskaffas från eller lagras, och de minimum-, maximum-, multipla- och standardkvantiteter som ska användas för handel eller lagerhantering, ledtider, stoppflagga och orderlöftesmetod. Standardorderinställningar används när du skapar inköpsorder, försäljningsorder, överföringsorder, lagerjournaler och genom huvudplanering att skapa planerade order. Standardorderinställningar kan vara artikelspecifika, sitespecifika, produktvariantspecifika eller produktdimensionspecifika."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: InventItemOrderSetup
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 223084
ms.assetid: fbfbcd7b-dc75-44ab-bffc-8bad576804a4
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 9ccbe5815ebb54e00265e130be9c82491aebabce
ms.openlocfilehash: 60abaa69debd891b2fe2dd98184c0dab50b0bf9f
ms.lasthandoff: 03/29/2017


---

# <a name="default-order-settings-for-dimensions-and-product-variants"></a>Standardorderinställningar för dimensioner och produktvarianter

Standardorderinställningar definierar site och lagerställe som artiklar kommer att anskaffas från eller lagras, och de minimum-, maximum-, multipla- och standardkvantiteter som ska användas för handel eller lagerhantering, ledtider, stoppflagga och orderlöftesmetod. Standardorderinställningar används när du skapar inköpsorder, försäljningsorder, överföringsorder, lagerjournaler och genom huvudplanering att skapa planerade order. Standardorderinställningar kan vara artikelspecifika, sitespecifika, produktvariantspecifika eller produktdimensionspecifika.

Du definierar standardorderinställningar på sidan **Standardorderinställningar **. Du öppnar den här sidan genom att gå till **produktinformationshantering**&gt;**produkter**&gt;**frisläppta produkter**&gt; en frisläppt produkt markerar &gt;på de **planera** eller *** hantera lager *** åtgärdsfönstret &gt;**beställa inställningar**&gt;**standardorderinställningar**.

## <a name="default-order-settings"></a>Standardorderinställningar
Det finns tre typer av standardorderinställningar för inköp, försäljning och lager. Standardorderinställningarna för inköp används när det skapas:

-   Inköpsorderrader
-   Inköpsavtalsrader
-   Rader i anbudsförfrågan
-   Inköpsrekvisitionsrader
-   Rader för försändelseåteranskaffning
-   Planerade inköpsorder

Standardorderinställningarna för försäljning används när det skapas:

-   Försäljningsorderrader
-   Försäljningsavtalsrader
-   Försäljningsoffertrader
-   Returorderrader och artikelersättningsrader
-   Rader i efterfrågeprognos

Standardinställningen för försäljningsorder gäller även när det skapas:

-   Projektartikelkrav
-   Artikelbehov för serviceorder

Standardorderinställningarna för lager används när det skapas:

-   Lagerjournaler.
-   Överföringsorder
-   Planerade överföringsorder

Standardinställningen för lagerorder gäller även när det skapas:

-   Karantänorder
-   Kvalitetsorder
-   Produktionsorder
-   Strukturlisterader
-   Planerade produktionsorder

## <a name="full-definition-of-a-released-product"></a>Fullständig definition av en frisläppt produkt
Du måste ange hur frisläppt produkt på raden för Dynamics 365 för operationer ska försöka identifiera standardorderinställningar när du skapar en transaktion. Hur frisläppt produkt innebär att artikelnumret och alla de aktiva produktdimensioner, till exempel konfiguration, storlek, stil och färg, specificeras för transaktionen. Om du till exempel manuellt skapar en inköpsorderrad för en frisläppt produktvariant, måste du ange alla nödvändiga produktdimensioner innan site, lagerställe, kvantitet och produktionstid visas som standard på orderraden. 

Alla parametrar för standardorderinställningar används inte när du skapar order eller journalrader. Kvantiteter och ledtider visas som standard när så är lämpligt. Exempelvis när en journalrad räkning, visas plats och lagerställe som standard när raden skapas. Givetvis ingen kvantitet standardvärden eller flera kontroller och lägsta sker när du skapar raden eller journalen bokförs. 

Systemet försöker alltid att hitta en standardsite och lagerställe, när en order eller en journalrad skapas. Siten visas inte alltid som standard från orderinställningarna. Till exempel när du skapar en försäljningsorder eller inköpsorder används siten från orderrubriken automatiskt på orderraderna. När du skapar en strukturlisterad används platsen från huvudet Strukturlista. När webbplatsen bestäms används den för att hitta någon plats orderinställningar som sedan kan användas som standard för lagerstället. 

Standardordertypen, inköp och lager ledtider kan åsidosättas av disponeringsregler för artikeln på den **artikeldisponering** sida. Även om standardorderinställningar inte kan för skillnaden mellan produktion och överföring produktionstid, regler för artikeldisponering ta hänsyn till detta. Men om inställningen för artikeldisponering bara kommer att användas av MPS när du skapar planerad produktion och planerade överföringsorder och inte ska användas när du skapar manuell produktion och överföringsorder. 

## <a name="default-order-settings-rules"></a>Regler för standardorderinställningar
Du kan ange allmänna standardorderinställningar och ett valfritt antal regler för standardorderinställningar som endast gäller i vissa villkor, som till exempel site eller en specifik produktdimension eller produktdimensionskombination. Du kan inte ange specifika orderinställningar för ett lagerställe.

### <a name="rank-in-default-order-settings"></a>Rangordna i standardorderinställningar

Reglerna för standardorderinställningar har rangordningar. Ju högre rangordning desto viktigare är regeln vilket innebär att det kommer att ha en högre prioritet och användas innan reglerna med lägre rangordning. De allmänna standardorderinställningarna har rangordningen noll, som inte kan ändras. Det kan bara finnas en regel med rangordning noll. Regler kan ha samma rangordning, förutsatt att dimensionerna som gäller skiljer sig åt. Detta är användbart för att modellerera sitespecifika orderinställningar. När en ny regel för standardorderinställningar skapas, kommer värdena för ordervärden, stoppflagga, etc. att ärvas från regeln med rangordning noll, men kan åsidosättas.

### <a name="default-order-settings-for-released-products"></a>Standardorderinställningar för frisläppta produkter

För specifika frisläppta produkter kan du definiera allmänna orderinställningar eller sitespecifika orderinställningar. De allmäna orderinställningarna kommer alltid att ha rangordning noll. Om du ställer in nya försäljningar, inköp och lagerorderinställningar tillsammans samtidigt, rekommenderar vi att du använder **Informationsvy** på sidan **Standardorderinställningar **. Växla till Detaljvyn genom att gå till den **alternativ** åtgärdsfönstret &gt;**Sidalternativ**&gt;**ändra**&gt;**detaljvy**.

### <a name="site-specific-order-settings"></a>Platsspecifika orderinställningar

För att skapa sitespecifika orderinställningar klickar du på **Nytt**. I **detaljvy**, fyll på platsen i den **inställningar som gäller för**&gt;**Site** fält. I **Diagramvy** fyller du i kolumnen **Site**. Den nya regeln kommer automatiskt att få ett nytt rangordningsvärde, högre än noll. Du kan skapa så många sitespecifika regler som behövs och du kan tilldela alla sitespecifika detaljregler samma rangordning för att visa att de är lika viktiga. 

Om du är i **Detaljvy**, kan du inte få en överblick över reglerna som skapats för artikeln. Växla knappen **Visa/dölj lista** om du vill visa översiktsinformation. När en orderrad betraktas alla typer av skapas och har ingen site anges, söker Dynamics 365 för operationer för en regel med den site som anges. Det gör det enklare att bestämma en standardwebbplats på orderraden. Den här siten används sedan till att söka efter en specifik regel där ett standardlagerställe kan ha ställts in. Detta lagerställe används för orderraden.

### <a name="specific-order-settings-for-product-dimension"></a>Specifika orderinställningar för produktdimension

Du kan definiera orderinställningsregler för alla aktiva produktdimensioner eller kombination av aktiva produktdimensioner. Om ett produktdimensionsfält lämnas tomt, gäller regeln för alla värden av produktdimensionen. 

Beakta följande exempelprodukt.

|                                                     |                                         |
|-----------------------------------------------------|-----------------------------------------|
| **Product name**                                    | Fotoelektrisk sensor                    |
| **Item number**                                     | XW56                                    |
| **Konfiguration** (används till att forma typ av belysning) | C1 - synligt rött ljus, C2 - infrarött ljus |
| **Utförande** (används till att forma ingenjörsrevidering)  | R1 R2, R3                              |

Anta för detta exempel att produkten anskaffas med inte tillverkas. Anta också att konfigurationen C1 används mer allmänt, så den har kortare ledtider. 

Skapa följande standardorderinställningar för att forma det här scenariot.

| Rangordning | Plats | Inställningar | Stil | Inköp - Åsidosätt standardinställningar | Ledtid för inköp | Inköp - Stoppat | Försäljning - Åsidosätt standardinställningar | Försäljning - Stoppad |
|------|------|---------------|-------|--------------------------------------|--------------------|--------------------|-----------------------------------|-----------------|
| 10   |      | C1            |       | Ja                                  | 2                  |                    |                                   |                 |
| 0    |      |               |       |                                      | 5                  |                    |                                   |                 |

När en inköpsorderrad eller en planerad inköpsorder skapas för XW56, konfiguration C1, kommer ledtiden anses vara 2 oavsett revideringen eller siten som raden placeras på. Anta att alla ändringar förutom R3 stoppas.

Du kan skapa följande regler för standardorderinställningar.

| Rangordning | Plats | Inställningar | Stil | Inköp - Åsidosätt standardinställningar | Ledtid för inköp | Inköp - Stoppat | Försäljning - Åsidosätt standardinställningar | Försäljning - Stoppad |
|------|------|---------------|-------|--------------------------------------|--------------------|--------------------|-----------------------------------|-----------------|
| 20   |      |               | R2    | Ja                                  |                    | Ja                | Ja                               | Ja             |
| 20   |      |               | R1    | Ja                                  |                    | Ja                | Ja                               | Ja             |
| 10   |      | C1            |       | Ja                                  | 2                  |                    |                                   |                 |
| 0    |      |               |       |                                      | 5                  |                    |                                   |                 |

De två reglerna för att stoppa de gamla revideringarna har samma rangordning som innebär att de är lika viktiga. Båda av dem har en högre rangordning än regeln för konfiguration C1 vilket innebär att de åsidosätter regeln för konfiguration C1. 

I det här exemplet förklaras behovet av rangordningen. Om en inköpsorder skapas för konfiguration C1 och revidering R2, om det inte finns någon rangordning, kommer de två reglerna som definieras för R2 och C1 att vara otydliga. För att lösa otydligheten kommer Dynamics 365 for Operations att söka genom reglerna i fallande rangordning och tillämpa den första tillämpliga regeln. I den aktuella instansen, när en inköpsorderrad skapas för konfiguration C1 och revidering R2, får användaren ett varningsmeddelande att artikeln är spärrad och att detta orsakas av revideringsvärdet. Om regeln för konfigurationen har en högre rangordning än den för revidering, skulle skapandet av en inköpsorderrad för konfiguration C1 och revidering R2 ha lyckats, och inget meddelande med "artikeln spärrad" skulle visas för användaren. 

Beakta följande regler för standardorderinställningar.

| Rangordning | Plats | Inställningar | Stil | Standardplats | Standardlagerställe | Inköp - Åsidosätt standardlagringsdimensioner | Inköpslagerställe |
|------|------|---------------|-------|--------------|-------------------|------------------------------------------------|--------------------|
| 20   | 2    |               |       |              |                   | Ja                                            | 22                 |
| 10   |      | C1            |  R2   |  2           |  21               |                                                |                    |
| 0    |      |               |       | 1            | 11                |                                                |                    |

Systemet korsar uppsättningen av regler två gånger för att bestämma site och lagerställe. När en inköpsorderrad skapas för konfigurationen C1 utförande R2, bestäms platsen utifrån regeln till 10 grad. Sedan söker systemet efter en regel för plats 2 för att fastställa ett lagerställe. Regel 20 hittas och eftersom den har en högre rangordning, kommer lagerstället på inköpsorderraden vara 22 och inte 21. 

Som en allmän vägledning kommer specifika regler och regler för dimensioner som är viktigare än andra dimensioner att få en högre rangordning, medan mer allmänna regler får lägre rangordning. 

Regeln med rangordning noll fungerar som ett skyddsnät. Om inga andra regler hittas, kommer standardorderinställningarna från regel noll att användas. 

Eftersom rangordningsnumret är så viktigt, finns det på åtgärdsfönstret **Standardorderinställningar ** funktioner som flyttar en regel upp eller ned så att de alltid är i steg om 10. 

Antalet regler som har skapats för en frisläppt produkt kan vara många. För att få en bättre känsla för vad varje regel åsidosätter och varför den behövs, rekommenderar vi att använda **Rutnätsvy** på sidan** Standardorderinställningar**. Du kan visa genom att gå till den **alternativ** åtgärdsfönstret &gt;**Sidalternativ**&gt;**ändra**&gt;**diagramvyn**. Antalet kolumner som visas i rutnätet kan vara ganska betydande, särskilt för försäljnings- och lagerflikarna. Om du vill begränsa antalet kolumner som ska visas i rutnätet kan grupper med kolumner döljs eller visas med hjälp av knapparna på den **standardorderinställningar**&gt;**kolumnvisningen** meny.

### <a name="specific-order-settings-for-released-product-variant"></a>Specifika orderinställningar för frisläppta produktvarianter

Om regelsystemet för standardorderinställningar är för besvärligt finns alternativet att bara definiera standardorderinställningar för varje produktvariant. Följande exempel visar hur detta ser ut för produkten och de fall som beskrivs nedan.

| Rangordning | Plats | Inställningar | Stil | Inköp - Åsidosätt standardinställningar | Ledtid för inköp | Inköp - Stoppat | Försäljning - Åsidosätt standardinställningar | Försäljning - Stoppad |
|------|------|---------------|-------|--------------------------------------|--------------------|--------------------|-----------------------------------|-----------------|
| 10   |      | C2            | R3    | Ja                                  | 5                  |                    |                                   |                 |
| 10   |      | C2            | R2    | Ja                                  | 5                  | Ja                | Ja                               | Ja             |
| 10   |      | C2            | R1    | Ja                                  | 5                  | Ja                | Ja                               | Ja             |
| 10   |      | C1            | R3    | Ja                                  | 2                  |                    |                                   |                 |
| 10   |      | C1            | R2    | Ja                                  | 2                  | Ja                | Ja                               | Ja             |
| 10   |      | C1            | R1    | Ja                                  | 2                  | Ja                | Ja                               | Ja             |
| 0    |      |               |       |                                      | 5                  |                    |                                   |                 |

Rangordningen i det här fallet har ingen betydelse, så du kan välja att dölja den. Den här lösningen har potentiellt ett underhållsproblem. Du kan dock behöva överväga att använda denna inställning om du funderar på att integrera med PML-system (Livscykelhantering för produkt).


