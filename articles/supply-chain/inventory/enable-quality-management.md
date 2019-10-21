---
title: Översikt över kvalitetshantering
description: Det här avsnittet beskriver hur du kan använda kvalitetshantering i Dynamics 365 Supply Chain Management för att förbättra produktens kvalitet inom din leveranskedja.
author: perlynne
manager: AnnBe
ms.date: 11/02/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventTestAssociationTable, InventTestGroup, InventTestItemQualityGroup, InventTestTable, InventTestVariable, InventTestVariableOutcome
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 94003
ms.assetid: a1d9417b-268f-4334-8ab6-8499d6c3acf0
ms.search.region: Global
ms.search.industry: Distribution
ms.author: perlynne
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: c9600e165da76948bb53a0188ec0b212a0fed84a
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/30/2019
ms.locfileid: "2249596"
---
# <a name="quality-management-overview"></a>Översikt över kvalitetshantering

[!include [banner](../includes/banner.md)]

Det här avsnittet beskriver hur du kan använda kvalitetshantering i Dynamics 365 Supply Chain Management för att förbättra produktens kvalitet inom din leveranskedja.

Kvalitetshantering kan hjälpa dig att hantera handläggningstider när du hanterar avvikande produkter, oavsett ursprungspunkten. Eftersom diagnostiktyper länkas till korrigeringsrapporteringen kan Finance and Operations planera uppgifter för att korrigera problem och förhindra dem från att återkomma.

Förutom funktioner för att hantera avvikelser inkluderar kvalitetshantering funktioner för att spåra problem efter problemtyp (även interna problem), och för att identifiera lösningar som kortsiktiga och långsiktiga. Statistik om KPI:er (Key Performance Indicator) ger insyn i historiken över tidigare avvikelseproblem och lösningarna som användes för att korrigera dem. Du kan använda historiska data om du vill granska effektiviteten hos tidigare kvalitetsmått och bestämma lämpliga mått som ska användas i framtiden.

När du ställer in en kvalitetsassociation kan Supply Chain Management skapa kvalitetsorder för olika affärsprocesser, händelser och villkor. Kvalitetsassociationen kan omfatta en viss artikel, en specifik grupp artiklar eller alla artiklar.

## <a name="examples-of-the-use-of-quality-management"></a>Exempel på användningen av kvalitetshantering
Kvalitetshanteringen är flexibel och kan implementeras på olika sätt för att uppfylla kraven för specifika nivåer i distributionskedjeåtgärder. Följande exempel illustrerar hur dessa funktioner kan användas:

-   Starta automatiskt en kvalitetskontrollprocess baserat på fördefinierade villkor (vid lagerställeregistrering av en inköpsorder från en viss leverantör.)
-   Blockera lagret under inspektion för att förhindra icke-godkänt lager från att användas (fullständig blockering av inköpsorderkvantiteter).
-   Använd artikelsamplingen som en del av en kvalitetsassociation för att definiera hur aktuellt fysiskt lager ska inspekteras. Samplingen kan baseras på fasta kvantiteter eller en procentsats.
-   Skapa en kvalitetsorder för delleveranser. Om du vill skapa en kvalitetsorder som baseras på den kvantitet som inlevererats fysiskt till en order måste du markera kryssrutan **Per uppdaterad kvantitet** i formuläret **artikelsampling**.
-   Skapa testtyper som innehåller minimum-, maximum- och måltestvärden och utför testning av typen ”kvalitativ kontra kvantitativ” som har fördefinierade valideringresultat.
-   Ange en godtagbar kvalitetsnivå (AQL) för att kontrollera toleranserna för kvalitetsmått.
-   Ange resurser som en inspektionsåtgärd kräver, till exempel ett testområde och testinstrument.

## <a name="working-with-quality-associations"></a>Arbeta med kvalitetsassociationer
Affärsprocessen som använder en kvalitetsassociation kan relateras till olika källdokument, till exempel inköpsorder, försäljningsorder eller produktionsorder.

Varje kvalitetsassociationspost definierar testuppsättningarna, den godtagbara kvalitetsnivån och provtagningsplanen som gäller genererade kvalitetsorder. Du måste definiera en kvalitetsassociationspost för varje variant i en affärsprocess. Du kan till exempel ställa in en kvalitetsassociation som genererar en kvalitetsorder när en produktinleverans för en inköpsorder uppdateras. Beroende på inställningen för körningsplanen kan själva utlösarprocessen spärras medan det finns en öppen kvalitetsorder, eller så kan de efterföljande processerna, till exempel fakturering av inköpsorder, spärras.

**Obs!** Medan det finns öppna kvalitetsorder spärras lagerkvantiteter automatiskt från att utlevereras. Beroende på inställningen **Fullständig spärr** på sidan **Artikelsamplingar** är kvantiteten antingen kvantiteten på kvalitetsordern eller kvantiteten på källdokumentraden.

För en given affärsprocess identifierar kvalitetsassociationsposten händelsen och villkoren som en kvalitetsorder genereras för. Villkoren kan vara specifikt för antingen en webbplats eller en juridisk person. En kvalitetsorder som innefattar destruktiva test kan bara genereras när det finns lagerbehållning för händelsen.

Följande exempel illustrerar hur en kvalitetsassociationspost definieras för variationerna i varje affärsprocess. För varje exempel sammanfattas i följande tabell de händelser och villkor som definieras av en kvalitetsassociationspost.

<table>
<tbody>
<tr>
<th>Referenstyp</th>
<th>Händelsetyp</th>
<th>Körning</th>
<th>Händelsespärr</th>
<th>Dokumentreferens</th>
</tr>
<tr>
<td>Lager</td>
<td>Inte tillämpligt</td>
<td>Inte tillämpligt</td>
<td>Ingen</td>
<td>Alla</td>
</tr>
<tr>
<td rowspan="7">Försäljning</td>
<td rowspan="4">Plockningsprocess har schemalagts</td>
<td rowspan="4">Före</td>
<td>Ingen</td>
<td rowspan="22">Specifikt ID, Grupp eller Alla</td>
</tr>
<tr>
<td>Plockningsprocess</td>
</tr>
<tr>
<td>Följesedel</td>
</tr>
<tr>
<td>Faktura</td>
</tr>
<tr>
<td rowspan="3">Följesedel</td>
<td rowspan="3">Före</td>
<td>Ingen</td>
</tr>
<tr>
<td>Följesedel</td>
</tr>
<tr>
<td>Faktura</td>
</tr>
<tr>
<td rowspan="15">Inköp</td>
<td rowspan="7">Inleveranslista</td>
<td rowspan="4">Före</td>
<td>Ingen</td>
</tr>
<tr>
<td>Inleveranslista</td>
</tr>
<tr>
<td>Produktinleverans</td>
</tr>
<tr>
<td>Faktura</td>
</tr>
<tr>
<td rowspan="3">Efter</td>
<td>Ingen</td>
</tr>
<tr>
<td>Produktinleverans</td>
</tr>
<tr>
<td>Faktura</td>
</tr>
<tr>
<td rowspan="3">Registrering</td>
<td rowspan="3">Inte tillämpligt</td>
<td>Ingen</td>
</tr>
<tr>
<td>Produktinleverans</td>
</tr>
<tr>
<td>Faktura</td>
</tr>
<tr>
<td rowspan="5">Produktinleverans</td>
<td rowspan="3">Före</td>
<td>Ingen</td>
</tr>
<tr>
<td>Produktinleverans</td>
</tr>
<tr>
<td>Faktura</td>
</tr>
<tr>
<td rowspan="2">Efter</td>
<td>Ingen</td>
</tr>
<tr>
<td>Faktura</td>
</tr>
<tr>
<td rowspan="8">Produktion</td>
<td rowspan="3">Registrering</td>
<td rowspan="3">Inte tillämpligt</td>
<td>Ingen</td>
<td rowspan="12">Alla</td>
</tr>
<tr>
<td>Rapportera som färdig</td>
</tr>
<tr>
<td>Slut</td>
</tr>
<tr>
<td rowspan="5">Rapportera som färdig</td>
<td rowspan="3">Före</td>
<td>Ingen</td>
</tr>
<tr>
<td>Rapportera som färdig</td>
</tr>
<tr>
<td>Slut</td>
</tr>
<tr>
<td rowspan="2">Efter</td>
<td>Ingen</td>
</tr>
<tr>
<td>Slut</td>
</tr>
<tr>
<td rowspan="4">Karantän</td>
<td rowspan="3">Rapportera som färdig</td>
<td rowspan="2">Före</td>
<td>Rapportera som färdig</td>
</tr>
<tr>
<td>Slut</td>
</tr>
<tr>
<td>Efter</td>
<td>Slut</td>
</tr>
<tr>
<td>Slut</td>
<td>Före</td>
<td>Slut</td>
</tr>
<tr>
<td rowspan="3">Flödesoperation</td>
<td rowspan="3">Rapportera som färdig</td>
<td rowspan="2">Före</td>
<td>Ingen</td>
<td rowspan="3">Specifikt ID, Grupp eller Alla och Resursspecifik, Grupp eller Alla</td>
</tr>
<tr>
<td>Rapportera som färdig</td>
</tr>
<tr>
<td>Efter</td>
<td>Ingen</td>
</tr>
<tr>
<td rowspan="3">Produktion av samprodukt</td>
<td>Registrering</td>
<td>Inte tillämpligt</td>
<td rowspan="3">Ingen</td>
<td rowspan="3">Alla</td>
</tr>
<tr>
<td rowspan="2">Rapportera som färdig</td>
<td>Före</td>
</tr>
<tr>
<td>Efter</td>
</tr>
</tbody>
</table>

Följande register innehåller mer information om hur kvalitetsorder kan genereras för specifika typer av processer.
<div class="tableSection">

<table>
<tbody>
<tr>
<th>Typ av process</th>
<th>När kvalitetsorder kan genereras automatiskt</th>
<th>När kvalitetsorder kan genereras om det krävs destruktivt test</th>
<th>Villkorsinformation</th>
<th>Information om manuell generering</th>
</tr>
<tr>
<td>Inköpsorder</td>
<td>Innan eller efter att en inleveranslista eller produktinleverans för materialet som inlevereras bokförs</td>
<td>Efter att produktinleveransen för materialet som inlevereras bokförs eftersom materialet måste vara tillgängligt för destruktiv testning</td>
<td>Behovet av en kvalitetsorder kan återspegla en särskild plats, en artikel eller en leverantör, eller en kombination av dessa betingelser.</td>
<td>En manuellt genererad kvalitetsorder som refererar till en inköpsorder kan använda information i en kvalitetsassociationspost, till exempel testsamplingsplanen.</td>
</tr>
<tr>
<td>Karantänorder</td>
<td>Före eller efter att karantänordern rapporteras som färdig eller avslutad</td>
<td>Kvalitetsorder som kräver destruktiva test kan inte genereras. Det antas att karantänorderfunktionen hanterar dispositionen av materialet som förstörs.</td>
<td>Behovet av en kvalitetsorder kan återspegla en särskild plats, en artikel eller en leverantör, eller en kombination av dessa betingelser.</td>
<td>En manuellt genererad kvalitetsorder som refererar till en karantänorder kan använda information i en kvalitetsassociationspost, till exempel testsamplingsplanen.</td>
</tr>
<tr>
<td>Försäljningsorder</td>
<td>Före en schemalagd uppdatering av plockningsprocess eller följesedel för artiklarna som levereras</td>
<td>I ett obestämt steg</td>
<td>Behovet av en kvalitetsorder kan återspegla en särskild plats, en artikel eller en kund, eller en kombination av dessa betingelser.</td>
<td>En manuellt genererad kvalitetsorder som refererar till en försäljningsorder kan använda information i en kvalitetsassociationspost, till exempel testsamplingsplanen.</td>
</tr>
<tr>
<td>Produktionsorder</td>
<td>Före eller efter att den fullständiga kvantiteten för produktionsordern rapporteras</td>
<td>Efter att den fullständiga kvantiteten för produktionsordern rapporteras</td>
<td>Behovet av en kvalitetsorder kan återspegla en särskild plats eller artikel, eller en kombination av dessa betingelser.</td>
<td>En manuellt genererad kvalitetsorder som refererar till en produktionsorder kan använda information i en kvalitetsassociationspost, till exempel testsamplingsplanen.</td>
</tr>
<tr>
<td>Produktionsorder som har en flödesoperation</td>
<td>Före eller efter att rapporten är färdig för en åtgärd</td>
<td>Efter att rapporteringsproduktionen är färdig för den senaste åtgärden</td>
<td>Behovet av en kvalitetsorder kan återspegla en särskild plats, artikel eller verksamhetsresurs, eller en kombination av dessa betingelser.</td>
<td>En manuellt genererad kvalitetsorder som refererar till en flödesoperation kan använda information i en kvalitetsassociationspost, till exempel testsamplingsplanen.</td>
</tr>
<tr>
<td>Lager</td>
<td>En kvalitetsorder går inte att generera automatiskt för en transaktion i en lagerjournal eller för överföringsordertransaktioner.</td>
<td></td>
<td></td>
<td>En kvalitetsorder måste skapas manuellt för en artikels lagerkvantitet. Fysisk lagerbehållning krävs.</td>
</tr>
</tbody>
</table>

## <a name="quality-management-pages"></a>Kvalitetshanteringssidor
<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th>Sida</th>
<th>Beskrivning</th>
<th>Exempel</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td>Kvalitetsassociationer</td>
<td>Se föregående avsnitt i den här artikeln.</td>
<td>En kvalitetsassociation definierar all följande information för en kvalitetsorder som genereras:
<ul>
<li>Transaktionshändelsen</li>
<li>Uppsättningen med tester som måste utföras på artiklarna</li>
<li>Den godtagbara kvalitetsnivån</li>
<li>Samplingsplanen</li>
</ul>
Du måste definiera en kvalitetsassociation för varje variant i en affärsprocess som kräver automatisk generering av kvalitetsorder. En kvalitetsorder kan till exempel genereras i affärsprocesserna för inköpsorder, karantänorder, försäljningsorder och tillverkningsorder.</td>
</tr>
<tr class="even">
<td>Tester</td>
<td>Använd den här sidan när du vill definiera och visa enskilda tester som fastställer huruvida dina produkter uppfyller kvalitetsspecifikationerna. Du kan tilldela en eller flera enskilda tester till en testgrupp. I detta fall anger du också testspecifik information, till exempel godtagbara måttvärden. Måttvärden används för kvantitativa tester, och testvariabler används för kvalitativa tester.
<ul>
<li>Ett kvantitativt test har testtypen <strong>Heltal</strong> eller <strong>Del</strong> och har också en bestämd måttenhet. Kvalitetsspecifikationer och testresultat uttrycks som nummer.</li>
<li>Ett kvalitativt test har testtypen <strong>Alternativ</strong>. Kvalitetstester kräver mer information om testvariabeln som mäts och dess fasta alternativ. Kvalitetsspecifikationer och testresultat uttryckts baserat på ett resultat.</li>
</ul></td>
<td>Ett tillverkningsföretag utför två tester av inköpt material: ett kvantitativt test om materialkvalitet och ett kvalitativt test om förpackningsskador. Företaget definierar mer information om det kvalitativa testet för att identifiera testvariabeln (skadad förpackning) och dess utfall. Företaget använder sidan <strong>Testgrupper</strong> för att tilldela de två testerna till en testgrupp och ange testspecifik information. Testgruppen tilldelas en kvalitetsorder, så att företaget kan rapportera testresultaten för de två testerna.</td>
</tr>
<tr class="odd">
<td>Testgrupper</td>
<td>Använd den här sidan när du vill ställa in, redigera och visa testgrupper och enskilda tester som har tilldelats en testgrupp. I det övre fönstret visas testgrupper, och i det nedre visas testerna som har tilldelats en vald testgrupp. Du kan tilldela flera principer till en testgrupp, t.ex. en samplingsplan, en godtagbar kvalitetsnivå och behovet av destruktiv testning. När du tilldelar ett enskilt test till en testgrupp definierar du ytterligare information, till exempel sekvensen, dokument och giltighetsdatum. För ett kvantitativt test innehåller informationen som du anger även acceptabla mätvärden. För ett kvalitativt test innehåller informationen testvariabeln och standardresultatet. Den testgrupp som har tilldelats till en kvalitetsorder definierar standarduppsättningen med test som måste utföras på den angivna artikeln. Du kan dock lägga till, ta bort eller ändra tester för en kvalitetsorder. Testresultaten rapporteras för varje test på en kvalitetsorder.</td>
<td>Ett tillverkningsföretag definierar en testgrupp för varje variant av sina kvalitetsriktlinjer. De olika testgrupperna återspeglar skillnaderna i samplingsplanerna, uppsättningarna med tester som måste utföras tillsammans, den godtagbara kvalitetsnivån och andra faktorer. För kvantitativa tester finns det också skillnader i de godtagbara måttvärdena. Om du vill framtvinga kvalitetsriktlinjerna tilldelar företaget en testgrupp till varje regel för automatisk generering av kvalitetsorder på sidan <strong>Kvalitetsassociationer</strong> och tilldelar även en testgrupp till kvalitetsorder som har skapats manuellt.</td>
</tr>
<tr class="even">
<td>Kvalitetsgrupper för artiklar</td>
<td>Använd den här sidan när du vill ställa in, redigera och visa de artiklar som har tilldelats en kvalitetsgrupp eller de kvalitetsgrupper som är tilldelade en artikel. En kvalitetsgrupp representerar gemensamma testbehov för artiklar. När du har definierat testkraven på sidan <strong>Testgrupper</strong> kan du definiera reglerna för automatisk generering av kvalitetsorder. För att förenkla processen definierar du inte regler för enskilda artiklar. I stället definierar du regler för en kvalitetsgrupp genom att använda sidan <strong>Kvalitetsassociationer</strong>. Du kan också använda <strong>Kvalitetsgrupper för artiklar</strong> för en vald kvalitetsgrupp för att tilldela relevanta artiklar till den gruppen. Du kan också använda sidan <strong>Kvalitetsgrupper för artiklar</strong> för en vald artikel för att tilldela relevanta kvalitetsgrupper till den artikeln.</td>
<td>Ett tillverkningsföretag köper in flera olika råmaterial som har samma testbehov för inkommande inspektion. Företaget definierar en kvalitetsgrupp och tilldelar sedan artikelnumren som är kopplade till råmaterialet till den gruppen. Senare köper företaget en ny typ av råmaterial som har samma testbehov. I stället för att konfigurera nya testbehov för det nya materialet lägger företaget till artikelnumret för det nya materialet till den befintliga kvalitetsgruppen. Samma tillverkningsföretag tillverkar också artiklar som har samma krav på tillverkningstest och levererar artiklar med samma krav på testning före leverans. Företaget definierar två ytterligare kvalitetsgrupper och tilldelar sedan relevanta artikelnummer till varje grupp.</td>
</tr>
<tr class="odd">
<td>Testvariabler</td>
<td>Använd den här sidan för att definiera och visa variablerna som hör till ett kvalitativt test. För varje variabel definierar du fasta resultat som representerar de möjliga alternativen. Du definierar testerna på sidan <strong>Tester</strong>. För kvalitativa tester måste du ange testtypen till <strong>Alternativ</strong>. Använd sidan <strong>Testgrupper</strong> för att tilldela en testvariabel till ett enskilt test.</td>
<td>Ett tillverkningsföretag som tillverkar kakor använder ett inspektionstest för den färdiga produkten. Det här inspektionstestet har flera variabler. En variabel är smak, och de möjliga resultaten för denna variabel är bra och dålig. En andra variabel är färg, och de möjliga resultaten är för mörk, för ljus och rätt.</td>
</tr>
<tr class="even">
<td>Resultat från testvariabel</td>
<td>Använd den här sidan när du vill ställa in, redigera och visa möjliga testresultat för en testvariabel som hör till ett kvalitativt test. För varje resultat tilldelar du statusen <strong>godkänt</strong> eller <strong>underkänt</strong>. Du måste definiera en variabel och dess resultat för varje kvalitativt test som definieras på sidan <strong>Tester</strong>. (För kvalitativa tester anges testtypen som <strong>Alternativ</strong> på sidan <strong>Tester</strong>.) Använd sidan <strong>Testgrupper</strong> för att tilldela en testvariabel och standardresultatet till ett enskilt kvalitativt test.</td>
<td>Ett tillverkningsföretag som tillverkar kakor använder ett inspektionstest för den färdiga produkten. Det här inspektionstestet har flera variabler. En variabel är smak, och de möjliga resultaten för denna variabel är bra och dålig. En andra variabel är färg, och de möjliga resultaten är för mörk, för ljus och rätt. Statusen <strong>godkänt</strong> eller <strong>underkänt</strong> tilldelas till varje resultat. Under inspektionstestet av respektive variabel rapporterar inspektören testresultatet genom att välja något av resultaten.</td>
</tr>
</tbody>
</table>



<a name="additional-resources"></a>Ytterligare resurser
--------

[Kvalitetshanteringsprocesser](quality-management-processes.md)

[Aktivera avvikelsehantering](enable-nonconformance-management.md)
