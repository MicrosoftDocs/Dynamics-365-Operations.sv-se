---
title: Kvalitets- och avvikelsehantering – en översikt
description: Det här ämnet presenterar funktionerna för kvalitet och avvikelsehantering i Microsoft Dynamics 365 Supply Chain Management och förklarar hur de kan förbättra produktkvaliteten i din leveranskedja.
author: perlynne
ms.date: 03/23/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: InventItemSampling, InventNonConformanceHistory, InventNonConformanceTable, InventQualityOrderLineResults, InventQualityOrderTable, InventTestCorrection, InventTestDiagnosticType, InventTestInstrument, InventTestReportSetup, InventTestTable
audience: Application User
ms.reviewer: kamaybac
ms.custom:
- "11574"
- intro-internal
ms.assetid: 5ac8a059-5cb4-4cb5-ba14-b944bd08dae9
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: d8bb3862b2a082dd975af8bbb30961caf209c5ad
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/06/2021
ms.locfileid: "6344530"
---
# <a name="quality-and-nonconformance-management-overview"></a>Kvalitets- och avvikelsehantering – en översikt

[!include [banner](../includes/banner.md)]

Det här ämnet presenterar funktionerna för kvalitet och avvikelsehantering i Microsoft Dynamics 365 Supply Chain Management och förklarar hur de kan förbättra produktkvaliteten i din leveranskedja.

Kvalitetssäkring innebär bland annat produkttestning och hantering av avvikande material. Kvalitetshanteringsprocesser gör det enklare att garantera en hög nivå av produktkvalitet i din leveranskedja. Dessa processer kan också optimera distributionskedjeprocesser och öka kundnöjdheten. Kvalitetshantering kan hjälpa dig att hantera handläggningstider när du hanterar avvikande produkter, oavsett deras ursprungspunkt. Du kan koppla diagnostikresultatet till korrigeringsuppgifter. Systemet kan schemalägga uppgifter för att åtgärda problem och därmed förhindra förekomster av dessa problem i framtiden. Kvalitetshantering låter dig också följa upp ärenden (inklusive interna problem) efter problemtyp, och låter dig identifiera lösningar som långfristiga eller kortfristiga. Statistik om KPI:er (Key Performance Indicator) ger insyn i tidigare avvikelseproblem och lösningarna som användes för att korrigera dem. Du kan använda historiska data om du vill granska effektiviteten hos tidigare tagna kvalitetsmått och bestämma lämpliga mått som ska användas i framtiden.

Kvalitetshantering kan hjälpa dig att hantera handläggningstider när du hanterar avvikande produkter, oavsett ursprungspunkten. Eftersom diagnostiktyper länkas till korrigeringsrapporteringen kan Supply Chain Management planera uppgifter för att korrigera problem och förhindra dem från att återkomma.

Förutom funktioner för att hantera avvikelser inkluderar kvalitetshanteringen funktioner för att spåra problem efter problemtyp (även då problemen är interna) och för att identifiera lösningar som kortsiktiga eller långsiktiga. Statistik om KPI:er (Key Performance Indicator) ger insyn i historiken över tidigare avvikelseproblem och lösningarna som användes för att korrigera dem. Du kan använda historiska data om du vill granska effektiviteten hos tidigare kvalitetsmått och bestämma lämpliga mått som ska användas i framtiden.

När du ställer in en kvalitetsassociation kan Supply Chain Management skapa kvalitetsorder för olika affärsprocesser, händelser och villkor. Kvalitetsassociationen kan omfatta en viss artikel, en specifik grupp artiklar eller alla artiklar.

## <a name="examples-of-the-use-of-quality-management"></a>Exempel på användningen av kvalitetshantering

Kvalitetshanteringen är flexibel och kan implementeras på olika sätt för att uppfylla kraven för specifika nivåer i distributionskedjeåtgärder. Följande exempel illustrerar hur dessa funktioner kan användas:

- Starta en kvalitetskontrollprocess automatiskt baserat på fördefinierade villkor (till exempel vid lagerställeregistrering av en inköpsorder från en viss leverantör).
- Blockera lagret under inspektion för att förhindra icke-godkänt lager från att användas (fullständig blockering av inköpsorderkvantiteter).
- Använd artikelsamplingen som en del av en kvalitetsassociation för att definiera hur aktuellt fysiskt lager ska inspekteras. Samplingen kan baseras på fasta kvantiteter, en procentsats eller komplett registreringsskylt.
- Skapa en kvalitetsorder för delleveranser. Om du vill skapa en kvalitetsorder som baseras på den kvantitet som inlevererats fysiskt med en order måste du markera kryssrutan **Per uppdaterad kvantitet** på sidan **Artikelsampling**.
- Skapa testtyper som innehåller minimum-, maximum- och måltestvärden och utför testning av typen ”kvalitativ kontra kvantitativ” som har fördefinierade valideringresultat.
- Ange en godtagbar kvalitetsnivå (AQL) för att kontrollera toleranserna för kvalitetsmått.
- Ange resurser som en inspektionsåtgärd kräver, till exempel ett testområde och testinstrument.

> [!NOTE]
> Funktionen _Kvalitetshantering för lagerprocesser_ omfattar kvalitetshanteringsfunktioner. Om du använder den här funktionen kan du se [Kvalitetshantering för lagerprocesser](quality-management-for-warehouses-processes.md) för exempel på hur kvalitetshanteringen fungerar när den är aktiverad.

## <a name="controlling-the-quality-management-process"></a>Styra kvalitetshanteringsprocessen

Nedan följer några sätt att styra kvalitetshanteringsprocessen:

- Skapa kvalitetsorder som baseras på utlösarpoäng som till exempel "vid produktinleverans" för inkommande åtgärder eller "vid produktupphämtning" för utgående funktioner.
- Dokumentera testresultat och bestäm om resultaten uppfyller de etablerade testvillkoren samt godtagbara kvalitetsnivåer.
- Använd dokumenthantering för detaljerade produktspecifikationer och gör användarspecifika anteckningar till en del av inspektionsprocessen vid rapportering.
- Underhåll avvikande produkter och korrelera dessa produkter med ytterligare information om avvikelse för att spåra den ursprungliga orsaken till ett problem.
- Dokumentera kostnaden för att hantera en avvikelse. Denna kostnad kan inkludera artiklarna (till exempel reservdelar), diverse avgifter samt och tidrapporttimmarna som krävs för att korrigera avvikelsen.
- Tidsplanera felkorrigeringsprocesser genom att använda korrigeringshantering som är kopplad till kvalitetsorder.

[![Kvalitetshanteringsprocess.](media/quality-management-process-diagram.png)](media/quality-management-process-diagram.png)

## <a name="product-testing-and-quality-orders"></a>Produkttestning och kvalitetsorder

Produkttestning kallas ofta för kvalitetskontroll och innefattar användning av kvalitetsorder. Genom att använda kvalitetskontrollfunktionen kan du göra följande:

- Definiera de tester som måste utföras för material. Testerna inkluderar kvalitetsspecifikationer, lämpligt testinstrument, de dokument som beskriver testet, en samplingsplan samt godtagbara kvalitetsnivåer (AQL).
- Skapa en kvalitetsorder som identifierar vilka tester som måste utföras för en viss order, till exempel en inköps- eller produktionsorder eller för en specifik lagerkvantitet. Du kan skapa en kvalitetsorder manuellt eller generera den automatiskt utifrån kvalitetsriktlinjer.
- Definiera de kvalitetsriktlinjer som är relaterade till inköp, karantän, tillverkning eller försäljningsorder i respektive affärsprocess i syfte att automatiskt skapa en kvalitetsorder som identifierar testbehoven för inkommande eller utgående material.
- Registrera testresultaten för en kvalitetsorder, validera testresultatet mot de godtagbara kvalitetsnivåerna och skriv ut ett analyscertifikat som anger testresultaten.

## <a name="nonconformance"></a>Avvikelse

En avvikelse beskriver en artikel med kvalitetsproblem. Avvikelseprocessen låter dig skapa en avvikelseorder som beskriver en kvantitet med avvikande material, problemkällan, problemtypen samt förklarande noteringar. Du kan definiera en klassificering av problemtyper för att underlätta analysen av avvikande material. Du kan även skriva ut ett avvikelsemärke och en avvikelserapport för att ange hur det avvikande materialet ska användas. Märket och rapporten kan till exempel ange ett villkor för **Oanvändbar** eller **Begränsad användning**.

Följande tabell visar de sex standardavvikelsetyperna och beskriver den information som måste registreras för varje typ.

| Avvikelsetyp | Källinformation |
|---|---|
| Kund | Kundens kontonummer, försäljningsordernummer eller ett partinummer för en försäljningsordertransaktion. Avvikelsen kan till exempel höra till en viss försäljningsorderleverans eller kundrespons om produktens kvalitet. |
| Serviceförfrågan | Kundens kontonummer, försäljningsordernummer eller ett partinummer för en försäljningsordertransaktion. Avvikelsen kan till exempel höra till en viss försäljningsorderleverans eller kundens klagomål om artikelns kvalitet. |
| Säljare | Leverantörens kontonummer, inköpsordernummer eller ett partinummer för en inköpsordertransaktion. Avvikelsen kan till exempel vara relaterad till inleverans av en inköpsorder eller en leverantörs oro över en del som levereras. |
| Produktion | Numret på tillverkningsordern eller ett partinummer för en produktionsordertransaktion. Avvikelsen kan till exempel röra en viss bunt som tillverkades. |
| Intern | Numret på kvalitetsordern eller ett partinummer för en kvalitetsordertransaktion. Avvikelsen kan till exempel röra testerna som utförs som en del av en kvalitetsorder eller en medarbetares oro över produktens kvalitet. |
| Produktion av samprodukt | Produktionsorderavvikelse för en samprodukt relaterad till en buntproduktionsorder. |

Avvikelser associeras med en problemtyp. Problemtyper definieras på sidan **Problemtyper**, där du anger problemtyper som kan kopplas till varje avvikelsetyp. Problemtyper för avvikelser i exempelvis typen **Servicebegäran** kan återspegla en klassificering av kundklagomål, medan problemtyper för avvikelser av typen **Internt** kan representera en klassificering av defektkoder.

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

## <a name="additional-resources"></a>Ytterligare resurser

- [Aktivera kvalitets- och avvikelsehantering](enable-quality-management.md)
- [Lagerspärr](inventory-blocking.md)
- [Karantänorder](quarantine-orders.md)
- [Kontrollera kvaliteten på varor](tasks/inspect-quality-goods.md)

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
