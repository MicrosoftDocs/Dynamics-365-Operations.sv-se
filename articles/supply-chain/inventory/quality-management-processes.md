---
title: Kvalitetshanteringsprocesser
description: Det här avsnittet innehåller information om kvalitetshanteringprocessen för avvikande produkter. Det beskriver användning av kvalitetskontrollfunktionen, om att definiera och underhålla avvikelser och hantering av korrigeringar.
author: perlynne
manager: tfehr
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventItemSampling, InventNonConformanceHistory, InventNonConformanceTable, InventQualityOrderLineResults, InventQualityOrderTable, InventTestCorrection, InventTestDiagnosticType, InventTestInstrument, InventTestReportSetup, InventTestTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: 11574
ms.assetid: 5ac8a059-5cb4-4cb5-ba14-b944bd08dae9
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b87fe141c6d53f68e90f5f2346da0633a09b1af1
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4987389"
---
# <a name="quality-management-processes"></a>Kvalitetshanteringsprocesser

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller information om kvalitetshanteringprocessen för avvikande produkter. Det beskriver användning av kvalitetskontrollfunktionen, om att definiera och underhålla avvikelser och hantering av korrigeringar.

Kvalitetssäkring innebär bland annat produkttestning och hantering av avvikande material. Kvalitetshanteringsprocesser gör det enklare att garantera en hög nivå av produktkvalitet i din leveranskedja. Dessa processer kan också optimera distributionskedjeprocesser och öka kundnöjdheten. Kvalitetshantering kan hjälpa dig att hantera handläggningstider när du hanterar avvikande produkter, oavsett deras ursprungspunkt. Du kan koppla diagnostikresultatet till korrigeringsuppgifter. Systemet kan schemalägga uppgifter för att åtgärda problem och därmed förhindra förekomster av dessa problem i framtiden. Kvalitetshantering låter dig också följa upp ärenden (inklusive interna problem) efter problemtyp, och låter dig identifiera lösningar som långfristiga eller kortfristiga. Statistik om KPI:er (Key Performance Indicator) ger insyn i tidigare avvikelseproblem och lösningarna som användes för att korrigera dem. Du kan använda historiska data om du vill granska effektiviteten hos tidigare tagna kvalitetsmått och bestämma lämpliga mått som ska användas i framtiden.

## <a name="controlling-the-quality-management-process"></a>Styra kvalitetshanteringsprocessen
Nedan följer några sätt att styra kvalitetshanteringsprocessen:

-   Skapa kvalitetsorder som baseras på utlösarpoäng som till exempel "i produktinleveransen" för inkommande åtgärder eller "vid produktupphämtning" för utgående operationer.
-   Dokumentera testresultat och bestäm om resultaten uppfyller de etablerade testvillkoren samt godtagbara kvalitetsnivåer.
-   Använd dokumenthantering för detaljerade produktspecifikationer och gör användarspecifika anteckningar till en del av inspektionsprocessen vid rapportering.
-   Underhåll avvikande produkter och korrelera dessa produkter med ytterligare information om avvikelse för att spåra den ursprungliga orsaken till ett problem.
-   Dokumentera kostnaden för att hantera en avvikelse. Denna kostnad kan inkludera artiklarna (till exempel reservdelar), tillägg och tidrapporttimmarna som krävs för att korrigera avvikelsen.
-   Tidsplanera felkorrigeringsprocesser genom att använda korrigeringshantering som är kopplad till kvalitetsorder.

[![Kvalitetshanteringsprocesser](./media/quality-management-process-diagram.png)](./media/quality-management-process-diagram.png)  

## <a name="product-testing-and-quality-orders"></a>Produkttestning och kvalitetsorder
Produkttestning kallas ofta för kvalitetskontroll och innefattar användning av kvalitetsorder. Genom att använda kvalitetskontrollfunktionen kan du göra följande:

-   Definiera de tester som måste utföras för material. Testerna inkluderar kvalitetsspecifikationer, lämpligt testinstrument, de dokument som beskriver testet, en samplingsplan samt godtagbara kvalitetsnivåer (AQL).
-   Skapa en kvalitetsorder som identifierar vilka tester som måste utföras för en viss order, till exempel en inköps- eller produktionsorder eller för en specifik lagerkvantitet. Du kan skapa en kvalitetsorder manuellt eller automatiskt skapa en kvalitetsorder utifrån kvalitetsriktlinjer.
-   Definiera kvalitetsriktlinjer som är relaterade till inköp, karantän, tillverkningsorder eller försäljningsorder i varje affärsprocess för att automatiskt skapa en kvalitetsorder som identifierar testbehoven för inkommande eller utgående material.
-   Registrera testresultaten för en kvalitetsorder, validera testresultatet mot de godtagbara kvalitetsnivåerna och skriv ut ett analyscertifikat med testresultaten.

## <a name="nonconformance"></a>Avvikelse
En avvikelse beskriver en artikel med kvalitetsproblem. Avvikelseprocessen låter dig skapa en avvikelseorder som beskriver en kvantitet med avvikande material, problemkällan, problemtypen samt förklarande noteringar. Du kan definiera en klassificering av problemtyper för att underlätta analysen av avvikande material. Du kan även skriva ut ett avvikelsemärke och en avvikelserapport för att ange hur det avvikande materialet ska användas. Märket och rapporten kan till exempel ange ett villkor för **Oanvändbar** eller **Begränsad användning**.

Följande tabell visar de sex standardavvikelsetyperna och beskriver den information som måste registreras för varje typ.

| Avvikelsetyp   | Källinformation                                                                                                                                                                                                                          |
|-----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Kund              | Kundens kontonummer, försäljningsordernummer eller ett partinummer för en försäljningsordertransaktion. Avvikelsen kan till exempel höra till en viss försäljningsorderleverans eller kundrespons om produktens kvalitet.       |
| Serviceförfrågan       | Kundens kontonummer, försäljningsordernummer eller ett partinummer för en försäljningsordertransaktion. Avvikelsen kan till exempel höra till en viss försäljningsorderleverans eller kundens klagomål om artikelns kvalitet.     |
| Säljare                | Leverantörens kontonummer, inköpsordernummer eller ett partinummer för en inköpsordertransaktion. Avvikelsen kan till exempel vara relaterad till inleverans av en inköpsorder eller en leverantörs oro över en del som levereras. |
| Produktion            | Numret på tillverkningsordern eller ett partinummer för en produktionsordertransaktion. Avvikelsen kan till exempel röra en viss bunt som tillverkades.                                                                      |
| Intern              | Numret på kvalitetsordern eller ett partinummer för en kvalitetsordertransaktion. Avvikelsen kan till exempel röra testerna som utförs som en del av en kvalitetsorder eller en medarbetares oro över produktens kvalitet.     |
| Produktion av samprodukt | Produktionsorderavvikelse för en samprodukt relaterad till en buntproduktionsorder.                                                                                                                                                    |

Avvikelser associeras med en problemtyp. Problemtyper definieras på sidan **Problemtyper**, där du anger problemtyper som kan kopplas till varje avvikelsetyp. Problemtyper för avvikelser i till exempel typen **Servicebegäran** kan återspegla en klassificering av kundklagomål, medan problemtyper för avvikelser av typen **Internt** kan representera en klassificering av defektkoder.

När du skapar en ny avvikelse, välj en avvikelsetyp och problemtypen. Den ursprungliga godkännandestatusen är **Ny**, som representerar åtgärdsbegäran. Nästa steg är att ändra godkännandestatusen till **Godkänd** eller **Avvisad** för att visa om du vidtar eller inte vidtar åtgärder för avvikelsen. Du kan även stänga en avvikelse (genom att markera en separat kryssruta) för att visa att du är klar med den eller öppna en avvikelse på nytt för att visa att saken behöver beaktas ytterligare.

Du kan ange kommentarer för en avvikelse genom att bifoga ett dokument. Det är en bra idé att definiera en unik dokumenttyp för avvikelser genom att använda sidan **Dokumenttyp**. Du kan sedan använda sidan **Rapportinställningar** för att definiera om kommentarer för denna dokumenttyp ska skrivas ut på avvikelserapporten och avvikelsemärket. Avvikelserapporten och avvikelsemärket och kan hjälpa dig med materialets dispositionen. Du kan selektivt generera rapporter och märkningar baserat på urvalsvillkor som hör till en avvikelse. Villkoren inkluderar avvikelsenummer, artikel, kund, leverantör och status.

Avvikelserapporten visar avvikelsenummer, artikel och problemtyp. Beroende på din rapportinställningspolicy kan rapporten också visa relaterade anteckningar om avvikelsen. Avvikelsemärket visar liknande information och innehåller även karantänzonen och typen (till exempel **Begränsad användning** eller **Oanvändbart**) som du tilldelade avvikelsen för att leda dispositionen av det defekta materialet.

## <a name="approved-nonconformance"></a>Godkänd avvikelse
Om du vill kan du även definiera en eller flera relaterade åtgärder för en godkänd avvikelse. En relaterad åtgärd beskriver det arbete som ska utföras, och innehåller en lista med de kvalitetsåtgärder som du har definierat, och en beskrivning av anledningen till arbetet. När du definierar en operation kan du om du vill även definiera de tillägg, artiklar och tidrapporttimmar som krävs för att utföra arbetet. De beräknade kostnaderna visas för den relaterade åtgärden och den totala beräknade kostnaden visas för avvikelsen. Den beräknade kostnaden och den bakomliggande informationen (om artiklar, arbetstimmar och tillägg) är referensinformation och den används bara inom kvalitetshanteringsfunktionen.

Du kan även skapa en kvalitetsorder från avvikelsen genom att först utföra en förfrågan om kvalitetsorder och sedan skapa den nya kvalitetsordern. Exempelvis kan en kvalitetsorder identifiera behovet att testa (eller testa om) det defekta materialet. Den nyligen skapade kvalitetsordern visar länken till den ursprungliga avvikelsen.

Om du vill kan du koppla en avvikelse till en annan och skapa en ny avvikelse från en befintlig. Kopplingen kan exempelvis återspegla sambandet mellan kvalitetsproblem.

## <a name="correction-handling"></a>Korrigeringshantering
Sidan **Korrigeringar** gör det möjligt att skapa en lista över avvikelser som måste korrigeras. Varje korrigeringspost associeras med diagnostypen som orsakade problemet som upptäcktes. Sidan **Korrigeringar** innehåller också information om vem som måste utföra korrigeringsåtgärder, och när. Du kan beskriva detaljer om problemet och den korrigerande åtgärden som krävs genom att bifoga ett dokument till korrigeringen. När avvikelsen har åtgärdats eller har korrigerats kan du "stänga" korrigeringsposten genom att välja alternativet **Slutförd**. Du kan också ange att lösningen var en kortsiktig lösning.

Det är en bra idé att definiera en unik dokumenttyp för avvikelser på sidan **Dokumenttyp**. Du kan sedan använda sidan **Rapportinställningar** för att definiera om kommentarer för denna dokumenttyp skrivs ut på korrigeringsrapporten. En utskriven korrigeringsrapport innehåller information om avvikelsen och tillhörande avvikelseanteckningar. Rapporten innehåller också information om korrigering, till exempel diagnostypen och relaterade korrigeringsanteckningar.

<a name="additional-resources"></a>Ytterligare resurser
--------

[Kvalitetshantering – översikt](enable-quality-management.md)

[Avvikelsehantering](enable-nonconformance-management.md)

[Lagerspärr](inventory-blocking.md)

[Karantänorder](quarantine-orders.md)

[Ställ in kvalitetsorder](tasks/set-up-quality-orders.md)

[Kontrollera kvaliteten på varor](tasks/inspect-quality-goods.md)
