---
title: Lagerbokföring
description: Det här ämnet förklarar fliken Lagerbokföring på sidan Bokföringsprofil för lager.
author: rachelprofitt
ms.date: 04/25/2022
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: InventPosting, InventItemGroup
audience: Application User
ms.search.region: Global
ms.author: raprofit
ms.openlocfilehash: 7fd507dd171b0d49673bdd0d0900b3f02dbcb65b
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8891563"
---
# <a name="inventory-posting"></a>Lagerbokföring

Fliken **Lager** på sidan **Lagerbokföringsprofiler** används för att styra hur lagertransaktioner bokförs i redovisningen. Lagertransaktioner är transaktioner som inte skapas från försäljningsorder, inköpsorder eller tillverkningsorder. De bokför automatiskt de fysiska och ekonomiska uppdateringarna av lagret samtidigt. Ett undantag är överföringsorder som separata fysiska och ekonomiska uppdateringar när du levererar och tar emot lagret.

Följande tabell anger några exempel på lagertransaktioner.

| Transaktionstyp | Inleverans eller utleverans | Fysisk bokföring, ekonomisk bokföring eller båda | Beskrivning |
|---|---|---|---|
| Rörelse | Båda | Båda | <p>En rörelsejournal är en lagerjournal som du kan använda för att lägga till eller ta bort lager. Det fungerar som en lagerjusteringsjournal. En viktig skillnad är dock att huvudkontot som kompenserar för posten anges.</p><p>I rörelsejournalen registrerar du ingående saldon och enstaka justeringar som måste kostnadsförd. Det används till exempel när lager tas bort för ett försäljningsexempel.</p><p>När journalen bokförs sker de fysiska och ekonomiska uppdateringarna samtidigt.</p><p>Positiva kvantiteter på journalraderna representerar inleveranser och negativa kvantiteter representerar utleveranser.</p> |
| Lagerjustering | Båda | Båda | En lagerjusteringsjournal används för att lägga till eller ta bort lager. Du kan inte välja ett motkonto på den. Endast de konton som anges på sidan **Bokföringsprofil** för lager används för att uppdatera redovisningsposten. |
| Överför (journal) | Båda | Båda | <p>En överföringsjournal används för att flytta lager från en plats till en annan (genom att använda lagringsdimensioner). Produktinformationen i en lagertransaktion uppdateras med en ny produkt eller spårningsdimensioner.</p><p>En överföringsjournal skapar en rad för en artikels rörelse. Den här raden har fälten "från" och "till" för lagerdimensionerna. Varje rad i en överföringsjournal skapar två lagertransaktioner. En transaktion skapas för lagerdimensionerna "från". Den representerar utleverans och har en negativ kvantitet. Den andra transaktionen skapas för lagerdimensionerna "till". Den representerar inleverans och har en positiv kvantitet.</p><p>Överföringsjournaler kanske inte skapar en verifikation om lagerrörelse betraktas som en icke-ekonomisk överföring. Lagerdimensioner som skiljer sig för värdena "från" och "till" är inte markerade med alternativet **Ekonomiskt lager** på sidan **Lagringsdimensionsgrupp** eller **Spårningsdimensionsgrupp**. Om alternativet **Ekonomiskt lager** inte har markerats på dimensionen **Plats** och du flyttar lager från en plats till en annan plats på samma webbplats och lagerställe, skapas ingen verifikation.</p><p>Överföringsjournaler skiljer sig från överföringsorder på så sätt att det inte finns några dokument för förflyttningen. Uppdateringen utförs i en transaktion genom att journalen bokförs. En överföringsorder kan till skillnad generera plocknings- och leveransdokument och kräva två uppdateringar för att transaktionen ska kunna bearbetas.</p> |
| Överföringsorderförsändelse | Problem | Båda | <p>När du skapar en ny överföringsorder har varje kombination av en rad och en lagerdimension två lagertransaktioner: en för överföringsorderförsändelsen och en för överföringsorderinleveransen. När du levererar överföringsordern uppdateras två lagertransaktioner och två ytterligare lagertransaktioner skapas för transit av varor för sammanlagt fyra lagertransaktioner.</p><ol><li>Den första lagertransaktionen används för att ta bort artikeln från källlagerstället och platsen. Utleveransstatus för den här transaktionen är **Såld** för att ange att artikeln inte längre är tillgänglig i lagerstället.</li><li>Den andra lagertransaktionen används för att lägga till artikeln på det transitlager som valts för det lagerställe som artikeln överförs från. Den här transaktionens inleveransstatus är **Inköpt**.</li><li>Den tredje lagertransaktionen gäller överföring från transitlagret till lagerstället vid destinationen. Den här transaktionens utleveransstatus är **Fysiskt reserverat**. Denna status garanterar att artikeln inte kan förbrukas av en annan process medan den fortfarande är under transport.</li><li>Den fjärde lagertransaktionen gäller inleverans av varor i lagerstället vid destinationen. Den här transaktionens inleveransstatus är **Beställt**.</li></ol> |
| Överföringsorderinleverans | Inleverans | Båda | När en överföringsorder tas emot i destinationslagret uppdateras lagerstatusen för lagertransaktionen som finns i transitlagret (nummer 3 i föregående exempel) till **Såld** och lagerstatusen för lagertransaktionen för destinationslagret uppdateras till **Inköpt**. |
| Strukturlistor | Båda | Båda | Du kan använda en strukturlistejournal om du vill rapportera en produkt som färdig och förbruka råmaterial som förbrukats under processen utan att använda en tillverkningsorder. En strukturlistejournal innehåller vanligtvis minst en positiv rad för den färdiga varan och en eller flera negativa rader för de råmaterial som förbrukas. Den färdiga varuraden är en inleverans i lagret, medan de negativa raderna är varor från lager för råvarorna. När du skapar en strukturlistejournal är den första raden strukturlisterubriken, och efterföljande rader som läggs till är strukturlisteraderna. |
| Lagerägarskapsändring | Båda | Båda | Ändringsjournalen för lageräganderätt används för att byta ägaren till försändelselager från leverantören till din organisation. Lagerjournal för ägarskapsändring liknar lageröverföringsjournaler då två lagertransaktioner är relaterade till varje kombination av en rad och en lagerdimension. En lagertransaktion tar bort lagret från leverantören i dimensionen **Ägarskap** och den andra lägger till objektet till den juridiska personen i dimension **Ägarskap**. |
| Artikelinförsel | Inleverans | Fysiskt | En journalnamn för artikelankomst används för att uppdatera inleveransstatusen för lagret till **Registrerad**. Det används vanligtvis för inleveranslista för inköpsorder av varor och försäljningsorderreturer. |
| Produktionsinleverans | Inleverans | Fysiskt | En journal för produktionsinleverans liknar en journal för artikelankomst. Produktionsinleverans används för att ta emot färdiga varor från en tillverkningsorder i lagerstället. När journalen bokförs uppdateras statusen för lagertransaktionen till **Registrerad**. |
| Inventering | Båda | Båda | En inventeringsjournal används för att registrera kvantiteten av artiklar som har inventeras för en viss kombination av lagerdimensioner. Lagertransaktioner skapas när raden i journalen har en inventeringsdifferens. En rad med en högre inventeringskvantitet orsakar en inleverans till lagret. En rad med en mindre inventeringskvantitet orsakar en utleverans till lagret. Rader där den inventade kvantiteten matchar den förväntade kvantiteten har inga lagertransaktioner. |
| Märkesinventering | Inte tillämpligt | Inte tillämpligt | En märkesinventeringsjournal används för att spåra lagertaggar som tilldelas och används i en fullständig lagerinventering. Du kan använda journalen för att tilldela ett taggnummer till en viss kombination av en artikel och en lagerdimension och för att spåra status för det märket under ett fullständigt lager. Märkesinventeringsjournaler skapar inte lagertransaktioner. |
| Kvalitetsorder | Problem | Fysiskt | <p>En kvalitetsorder används för att registrera testresultat för ett visst parti i lagret. Varje kvalitetsorder är relaterad till en befintlig lagertransaktion eller en del av en lagertransaktion.</p><p>En kvalitetsorder genererar en ny lagertransaktion i två situationer:</p><ul><li>Kvalitetsordern markeras som **Destruktivt test** på fliken **Allmänt**.</li><li>Kvalitetsordern markeras som **Karantän vid valideringsfel** på fliken **Allmänt** och testet misslyckas vid valideringen. I detta fall skapas två förväntade lagertransaktioner. En lagertransaktion tar bort artikeln från den ursprungliga kombinationen av lagerdimension och plats och den andra lägger till artikeln i karantänlagerstället.</li></ul> |
| Karantänorder | Båda | Båda | <p>En karantänorders lagertransaktioner ser ut som en överföringsorder. Ett karantänlagerställe används för att spåra lagret. Det finns två inleveranstransaktioner och två utleveranstransaktioner.</p><p>När du skapar ordern skapas två transaktioner. Inleveranstransaktionen har statusen **Beställt** för karantänlagerstället som är länkat till det lagerställe där artikeln finns. Utleveranstransaktionen har status **Har beställts** för lagerstället där artikeln lagras.</p><p>När du startar karantänordern skapas två ytterligare transaktioner och de befintliga transaktionerna uppdateras. Statusvärdet för inleveranstransaktionen för karantänlagerstället uppdateras till **Inleverans** och statusen för utleveranstransaktionen för lagerstället uppdateras till **Avdragen**.</p><p>De två nya transaktionerna används för att indikera den slutliga förflyttningen tillbaka till lagerstället. Inleveranstransaktionen har statusen **Beställt** för lagerstället för lagring och den utleveranstransaktionen har statusen **Reserverad fysisk** för karantänlagerstället.</p><p>När du rapporterar en karantänorder som färdig representerar denna operation den fysiska uppdateringen av karantänordern. Inleveransstatusen i lagerstället för lagring uppdateras till **Inleverans**.</p><p>När du avslutar karantänordern representerar denna operation den ekonomiska uppdateringen av karantänsordern. Utleveranstransaktionerna uppdateras till **Såld** och statusen för inleveranstransaktionerna uppdateras till **Inköpt**.</p><p>Alternativt kan du kassera karantänordern. Den här åtgärden tar bort artikeln från lagret. När du kasserar en karantänorder finns bara tre transaktioner kvar. Inleveranstransaktionen för lagerstället tas bort och statusen för den återstående inleveranstransaktionen uppdateras till **Inköpt**. Statusen för de två utleveranstransaktionerna uppdateras till **Såld**. Operationen är en fysisk och ekonomisk uppdatering av ordern.</p> |

## <a name="fixed-receipt-price-posting"></a>Bokföring av fast inleveranspris

Med fast inleveranspris kan du använda en standardkostnad för en produkt. Det är ett alternativ till att välja alternativet **Standardkostnad** på sidan **Artikelmodellgrupp** för en artikel. Den största skillnaden när du använder ett fast inleveranspris är att den självkostnad som för närvarande konfigureras kommer att användas för artikeln när inleveransen till lagret bokförs. Det finns ingen kostnadsomvärderingsprocess för ett fast inleveranspris. När en ekonomisk uppdatering bokförs används den aktuella självkostnaden vid bokföringen. Om självkostnaden som används vid inleverans och fakturan skiljer sig åt, bokförs avvikelsen på det fasta inleveransprisets vinst- och förlustkonton.

Om du vill använda ett fast inleveranspris för en produkt måste du göra följande:

- Markera kryssrutan **Bokför fysiskt lager** på sidan **Artikelmodellgrupp** för artikeln som är vald på lagertransaktionsraden.
- Markera kryssrutan **Fast inleveranspris** för en artikel på sidan **Artikelmodellgrupp**.
- Ange huvudkontona för följande inläggstyper på sidan **Bokföringsprofil för lager**:

    - Fast inleveransprisdifferens (+)
    - Fast inleveransprisdifferens (-)

Mer information finns i [Fast inleveranspris](/supply-chain/cost-management/fixed-receipt-price.md).

## <a name="catch-weight-posting"></a>Bokföring av faktisk/nominell vikt

Produkter med faktisk/nominell vikt används ofta i branscher som till exempel livsmedel, där produkterna kan variera något efter vikt, storlek eller båda. Produkter med faktisk/nominell vikt använder två måttenheter: en lagerenhet och en enhet för faktisk/nominell vikt. Vikten av lagret när det gäller i ett lagerställe kan skilja sig från vikt när lagret utfärdas från lagerstället. Produktbearbetning med faktisk/nominell vikt justerar lagret.

Om det finns en avvikelse i faktisk/nominell vikt bokförs skillnaderna på de konton som anges i fälten **Förlust för faktisk/nominell vikt** och **Vinst för faktisk/nominell vikt** på sidan **Lagerbokföringsprofil**. Vanligtvis anges samma huvudkonto i båda fälten.

Följande tabell innehåller exempel på standardbokföringstyper och inkludera exempelhuvudkonton och beskrivningar.

- "Debet/Kredit?" kolumnen anger om transaktionen normalt är debet eller kredit. I vissa fall kan en transaktion bokföra antingen debet eller kredit.
- Kolumnen Clearingkonto visar att bokföringstypen är ett clearingkonto. Med andra ord innebär att det belopp som bokförs på detta konto återförs automatiskt när en senare transaktion bokförs.
- I kolumnen "P/F" anges bokföringstypen. "P" representerar fysisk bokföring och "F" representerar ekonomisk bokföring.
- Kolumnen Följ visar om huvudkontot för en bokföringstyp normalt är samma som huvudkontot för en annan bokföringstyp. Specifikt visar detta den bokföringstyp som vanligtvis används för bokföringen.

> [!NOTE]
> Huvudkontona och huvudkontonamnen i tabellen är bara förslag. Vi rekommenderar att du arbetar med revisorn för att avgöra vilken konfiguration som passar bäst för verksamheten.

| Bokföringstyp | Huvudkonto exempel | Huvudkonto namnexempel | Kontotyp | Debet/kredit? | Clearingkonto | P/F | Följ | Beskrivning |
|---|---|---|---|---|---|---|---|---|
| Förlustkonto för faktisk/nominell vikt | 510520 | Lagerjustering | Utgift | | Nej | Båda | Vinstkonto för faktisk/nominell vikt | Det här kontot används när du bokför en lagertransaktion där beloppet för faktisk/nominell vikt är lägre. |
| Vinstkonto för faktisk/nominell vikt | 510520 | Lagerjustering | Utgift | | Nej | Båda | Förlustkonto för faktisk/nominell vikt | Det här kontot används när du bokför en lagertransaktion där beloppet för faktisk/nominell vikt är högre. |

För mer information om produkter i faktisk/nominell vikt, se [Artiklar med faktisk/nominell vikt](/dynamicsax-2012/appuser-itpro/about-catch-weight-items.md) och [Bearbeta produkt i faktisk/nominell vikt med lagerstyrning](/supply-chain/warehousing/catch-weight-processing.md).

## <a name="inventory-to-fixed-asset-transfer-posting"></a>Inventering till överföring av anläggningstillgångar

Lagret till anläggningstillgångsjournalen (**Anläggningstillgångar** \> **Journaler** \> **Journal för lager till anläggningstillgångar**) används för att flytta artiklar ur lagret och omvandla dem till anläggningstillgångar. Mer information finns i [Integrering av anläggningstillgångar](/fixed-assets/fixed-asset-integration.md).

Följande tabell innehåller exempel på standardbokföringstyper och inkludera exempelhuvudkonton och beskrivningar.

- "Debet/Kredit?" kolumnen anger om transaktionen normalt är debet eller kredit. I vissa fall kan en transaktion bokföra antingen debet eller kredit.
- Kolumnen Clearingkonto visar att bokföringstypen är ett clearingkonto. Med andra ord innebär att det belopp som bokförs på detta konto återförs automatiskt när en senare transaktion bokförs.
- I kolumnen "P/F" anges bokföringstypen. "P" representerar fysisk bokföring och "F" representerar ekonomisk bokföring.
- Kolumnen Följ visar om huvudkontot för en bokföringstyp normalt är samma som huvudkontot för en annan bokföringstyp. Specifikt visar detta den bokföringstyp som vanligtvis används för bokföringen.

> [!NOTE]
> Huvudkontona och huvudkontonamnen i tabellen är bara förslag. Vi rekommenderar att du arbetar med revisorn för att avgöra vilken konfiguration som passar bäst för verksamheten.

| Bokföringstyp | Huvudkonto exempel | Huvudkonto namnexempel | Kontotyp | Debet/kredit? | Clearingkonto | P/F | Följ | Beskrivning |
|---|---|---|---|---|---|---|---|---|
| Utleverans av anläggningstillgång | 180100 | Materiell anläggningstillgång | Tillgång | Kredit | Nej | Båda | Inte tillämpligt | Det här kontot används när du bokför ett lager i en anläggningstillgångsjournal för att ta bort en artikel från lagret och konvertera den till en anläggningstillgång. |

## <a name="moving-average-posting"></a>Bokföring av glidande medelvärde

Glidande medelvärde är en beständig kostnadsredovisning som baseras på medelvärdesprincipen. Kostnaderna i lagerinventering ändras inte när inköpskostnaden gör det. Skillnaden kapitaliseras och baseras på en proportionell beräkning. Beloppet som kvarstår kostnadsförs.

Följande tabell innehåller exempel på standardbokföringstyper med exempelhuvudkonton och beskrivningar.

- "Debet/Kredit?" kolumnen anger om transaktionen normalt är debet eller kredit. I vissa fall kan en transaktion bokföra antingen debet eller kredit.
- Kolumnen Clearingkonto visar att bokföringstypen är ett clearingkonto. Med andra ord innebär att det belopp som bokförs på detta konto återförs automatiskt när en senare transaktion bokförs.
- I kolumnen "P/F" anges bokföringstypen. "P" representerar fysisk bokföring och "F" representerar ekonomisk bokföring.
- Kolumnen Följ visar om huvudkontot för en bokföringstyp normalt är samma som huvudkontot för en annan bokföringstyp. Specifikt visar detta den bokföringstyp som vanligtvis används för bokföringen.

> [!NOTE]
> Huvudkontona och huvudkontonamnen i tabellen är bara förslag. Vi rekommenderar att du arbetar med revisorn för att avgöra vilken konfiguration som passar bäst för verksamheten.

| Bokföringstyp | Huvudkonto exempel | Huvudkonto namnexempel | Kontotyp | Debet/kredit? | Clearingkonto | P/F | Följ | Beskrivning |
|---|---|---|---|---|---|---|---|---|
| Prisdifferens för rörligt genomsnitt | 510600 | Prisdifferens för glidande medelvärde | Utgift | Båda | Nej | Båda | Inte tillämpligt | Detta konto används när det finns en skillnad i kostnaden mellan inleveransen och fakturan. |
| Omvärdering för rörligt genomsnitt | 510610 | Omvärdering av rörligt genomsnitt | Utgift | Båda | Nej | Båda | Inte tillämpligt | Detta konto används när du justerar den glidande medelvärdeskostnaden för en produkt |

## <a name="sample-posting-profile-configuration"></a>Exempel på konfiguration av bokföringsprofil

Följande tabell innehåller exempel på standardbokföringstyper med exempelhuvudkonton och beskrivningar.

| Bokföringstyp | Huvudkonto exempel | Huvudkonto namnexempel | Kontotyp | Debet/kredit? | Clearingkonto | P/F | Följ | Beskrivning |
|---|---|---|---|---|---|---|---|---|
| Utleverans från lager | 140100 | Materiallager | Tillgång | Kredit | Nej | Båda | Lagerinleverans | Det här kontot används när en lagertransaktion som bokförs är en utartikel (negativ kvantitet) och inte är relaterad till försäljning, inköp eller produktion. Motkontot till detta konto är lagerutgift, förlustkonto. Detta konto representerar vanligtvis varulager i balansräkningen. |
| Lageromkostnad, förlust | 510100 | Lagervinst och -förlust | Utgift | Debet | Nej | Båda | Lageromkostnad, vinst | Det här kontot används när en lagertransaktion som bokförs är en utartikel (negativ kvantitet) och inte är relaterad till försäljning, inköp eller produktion. Motkontot till detta konto är lagerutleveranskonto. |
| Lagerinleverans | 140100 | Materiallager | Tillgång | Debet | Nej | Båda | Utleverans från lager | Det här kontot används när en lagertransaktion som bokförs är en inleverans (positiv kvantitet) och inte är relaterad till försäljning, inköp eller produktion. Motkontot till detta konto är lagerutgift, vinstkonto. Detta konto representerar vanligtvis varulager i balansräkningen. |
| Lageromkostnad, vinst | 510100 | Lagervinst och -förlust | Utgift | Kredit | Nej | Båda | Lageromkostnad, förlust | Det här kontot används när en lagertransaktion som bokförs är en inleverans (positiv kvantitet) och inte är relaterad till försäljning, inköp eller produktion. Motkontot till detta konto är lagerinleveranskontot. |
| Enhetsintern skuld | 231500 | Enhetsintern skuld | Skulder | Debet | Nej | Båda | | Det här kontot används när lager överförs mellan lagerdimensioner, till exempel webbplatser och kostnaden för en artikel skiljer sig mellan webbplatserna. |
| Enhetsintern fordran | 131500 | Enhetsintern fordring | Tillgång | Kredit | Nej | Båda | | Det här kontot används när lager överförs mellan lagerdimensioner, till exempel webbplatser och kostnaden för en artikel skiljer sig mellan webbplatserna. |
