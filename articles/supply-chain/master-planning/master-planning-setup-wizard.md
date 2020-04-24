---
title: Installationsguide för huvudplanering
description: Det här ämnet beskriver olika viktiga strategier och parametrar som används för att ställa in huvudplaneringen.
author: t-benebo
manager: tfehr
ms.date: 10/21/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ReqCreatePlanWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: benebotg
ms.search.validFrom: 2019-05-31
ms.dyn365.ops.version: AX 10.0.0
ms.openlocfilehash: b38009cbfdd5444c6643c5c0159a1aa475aaa3ac
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3213594"
---
# <a name="master-planning-setup-wizard"></a>Installationsguide för huvudplanering

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller en guide för **Installationsguide för huvudplanering**. Det förklarar hur parameterförslag beräknas och ger också exempel som visar hur olika företag ställer in huvudplanering, baserat på deras affärsbehov.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3YnSB]

[Inställningsguide för huvudplanering i Dynamics 365 Supply Chain Management](https://youtu.be/c-e6n-8rZb4) video (visas ovan) ingår i [Finance and Operations spellista](https://www.youtube.com/playlist?list=PLcakwueIHoT_SYfIaPGoOhloFoCXiUSyW) som finns på YouTube.


## <a name="specific-requirements-of-your-company"></a>Specifika krav för ditt företag

Den första sidan i guiden frågar om de specifika kraven för ditt företag. Dina svar på dessa frågor behöver inte vara exakta, men du bör kunna ge ungefärligt antal artiklar och planerade order som det kommer att finnas för den juridiska personen. Dina svar används för att konfigurera parametrar som gäller för din juridiska person, inte bara för den huvudplan som du har valt. I följande avsnitt beskrivs de parametrar som beräknas och formlerna som används.

### <a name="number-of-threads"></a>Antal trådar

- **Om du tillverkar någon av artiklarna:** antal trådar = antal planerade order ÷ 1 000
- **Om du inte tillverkar någon av artiklarna:** antal trådar = antal artiklar ÷ 1 000

Om antalet trådar som beräknas överskrider 75 procent av det tillgängliga antalet trådar, är det begränsat till 75 procent av antalet trådar som är tillgängliga för varje kund. (Antalet tillgängliga trådar kommer att bestämmas för varje kund.)

För mer information, se [Antal trådar](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/master-planning/master-planning-performance#number-of-threads).

### <a name="bundle-size"></a>Buntstorlek

Buntstorleken kommer att ställas in på **1**. Det här värdet är ofta det bästa värdet, eftersom det bidrar till att förbättra prestanda för huvudplaneringen.

Mer information finns i [antal aktiviteter i hjälpen för uppgiftsbunt](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/master-planning/master-planning-performance#number-of-tasks-in-helper-task-bundle).

### <a name="firming-bundle-size"></a>Bekräftelsebuntstorlek

- **Om du tillverkar någon av artiklarna:** Bekräftelsebuntstorlek kommer att ställas in på den större av dessa två värden: **10** och buntberäkning
- **Om du inte tillverkar någon av artiklarna:** Bekräftelsebuntstorlek kommer att ställas in på den större av dessa två värden: **50** och buntberäkning

Buntberäkning = (Antal planerade order × (Bekräfta tidsgräns ÷ Disponeringstid) ÷ antal trådar) ÷ 10

### <a name="cache-size"></a>Cachestorlek

Cachestorleken kommer att ställas in på **Maximum**. Det här värdet är ofta det bästa värdet, eftersom det bidrar till att förbättra prestanda för huvudplaneringen.

Mer information finns i [Allokera tid till jobb i en jobbunt](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/allocate-time-jobs-job-bundle).

### <a name="manufacturing-setup"></a>Inställning av tillverkning

Om du tillverkar artiklar kommer en sida för **Inställning av tillverkning** att visas senare i guiden.

## <a name="scope-of-the-current-plan"></a>Omfattning av den aktuella planen

På sidan **omfattningen av den aktuella planen** i guiden svarar du på frågor som är relaterade till hur långt i framtiden olika krav kommer att övervägas och beräknas i huvudplaneringen. Varje fråga frågar om du vill använda en funktion och hur du vill konfigurera den.

För till exempel funktionen prognosplan frågar guiden "vill du använda en prognosplan i huvudplaneringen så att planerade order föreslås för att uppfylla den prognostiserade efterfrågan?"

Följande alternativ är tillgängliga:

- **Nej** – huvudplaneringen kommer inte att föreslå planerade order för att uppfylla en prognos. På fliken **tidsgränser** på sidan **Huvudplaner** (**Huvudplanering \> Installation \> Planer \> Huvudplaner**), kommer guiden att ange alternativet **Prognosplan (tidsgräns)** till **Ja** och ange antalet dagar till **0** (noll). Den här inställningen åsidosätter tidsgränsen som anges i disponeringsgruppen. Eftersom antalet dagar är inställt på **0** (noll) används inte funktionen.
- **Ja, enligt definitionen i den här huvudplanen** – ett fält blir tillgängligt, där du kan ange antalet dagar som huvudplaneringen kommer att föreslå planerade order för att uppfylla den prognostiserade efterfrågan. Guiden anger alternativet **Prognosplan (tidsgräns)** till **Ja** och anger antal dagar som anges i **Prognosplan** på fliken **Tidsgränser** på sidan **Huvudplaner**. Den här inställningen åsidosätter de värden som anges i disponeringsgrupperna.
- **Ja, enligt definitionen i disponeringen** – guiden kommer att ange alternativet **prognosplan (tidsgräns)** till **nej**. Tidsgränser som anges i disponeringsgruppen kommer att användas för att ange hur länge du planerar för prognosen.

De återstående frågorna på den här sidan och deras svar följer samma schema:

- **Nej** – alternativet **prognosplan (tidsgräns)** kommer att anges till **Ja**och antalet dagar anges till **0** (noll).
- **Ja, enligt definitionen i denna huvudplan** – alternativet **prognosplan (tidsgräns)** anges till **ja**. Antalet dagar som du anger kommer att användas och åsidosätter de värden som anges i disponeringsgrupperna.
- **Ja, enligt definitionen i disponeringsgruppen** – alternativet **prognosplan (tidsgräns)** anges till **nej**.

För mer information, se [finplanering](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/job-scheduling).

## <a name="scheduling-options"></a>Planeringsalternativ

Sidan **Planeringsalternativ** visas bara om du svarade **ja** på "tillverkar du något av de planerade artiklarna?" fråga på den första sidan i guiden.

Ditt svar på den första frågan på den här sidan ("behöver du tidsplanera åtgärder uppdelade i enskilda jobb?") bestämmer tidsplaneringsmetoden på fliken **Allmänt** på sidan **huvudplaner**.

- **Ja** – finplanering kommer att användas.
- **Nej** – grovplaneringen kommer att användas.

För mer information, se [grovplanering](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/operations-scheduling) och [finplanering](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/production-control/job-scheduling).

## <a name="updates-of-demand-and-supply"></a>Uppdateringar av efterfrågan och tillgång

Frågorna på sidan **uppdateringar av efterfrågan och tillgång** är relaterade till bekräftelse, åtgärdsmeddelanden och fördröjningar.

Inställningen av huvudplanering kommer att uppdateras baserat på dina svar, enligt samma schema som beskrivs i föregående avsnitt:

- **Nej** – Nej **tidsgräns** på sidan **huvudplaner** anges till **ja**och antalet dagar anges till **0** (noll).
- **Ja, enligt definitionen i denna huvudplan** – alternativet **tidsgräns** anges till **ja**. Antalet dagar som du anger kommer att användas och åsidosätter de värden som anges i disponeringsgrupperna.
- **Ja, enligt definitionen i disponeringsgruppen** – alternativet **tidsgräns** anges till **nej**.

För beräknade **fördröjningar kommer dina svar på frågorna i guiden att uppdatera motsvarande parametrar på fliken beräknade förseningar** på sidan **huvudplaner**.

## <a name="summary-of-your-changes"></a>Sammanfattning av dina ändringar

Den sista sidan i guiden visar de ändringar som rekommenderas baserat på dina svar. Den visar både värdet i din installation (**aktuell inställning**) och det värde som guiden rekommenderar (**ny konfiguration**).

Du kan också ändra parametrarna i den nya konfigurationen. Parametrarna är indelade i parametrar som gäller för din juridiska person och parametrar som gäller endast för den huvudplan som du har valt. Om du vill visa alla inställningsparametrar som kan ändras med hjälp av guiden väljer du **Visa alla parametrar** längst ned på sidan. Du kan sedan ändra parametrarna.

Slutligen, när du väljer **Slutför**, tillämpas den nya konfigurationen. Om du väljer **Avbryt** tillämpas ingen av ändringarna.

## <a name="examples"></a>Exempel

I det här avsnittet beskrivs hur du ställer in två fiktiva företag för att visa hur installationen kan ändras efter varje företags behov.

### <a name="example-1-contoso-manufacturer"></a>Exempel 1: Contoso tillverkare

Contoso tillverkare är ett tillverkande företag som producerar högtalare. Det köper de olika råmaterial och komponenter som används för slutliga högtalare från olika leverantörer. Här är några av de egenskaper som det är leverans och tillverkning:

- De slutgiltiga artiklar som företaget tillverkar har en strukturlistestruktur.
- Alla slutgiltiga artiklar och komponenter planeras av huvudplaneringen. Manuell planering är inte klar.
- En flödesoperation definieras för produktionen av varje slutlig artikel.
- Tillverkningsanläggningen producerar slutgiltiga produkter. Den har ett definierat antal fräs- och borrmaskiner som används för att bearbeta komponenterna. De olika komponenterna måste bearbetas av dessa maskiner.
- Det finns många leverantörer. Genomsnittlig ledtid för artiklar är en vecka. En grupp av artiklar från samma leverantör kommer att ha en ledtid på sju veckor.

I guiden anges följande värden för Contoso tillverkare:

- **Disponering:**

    - **Fråga:** "vill du ange antalet dagar i planeringshorisonten?"
    - **Svar:** "Ja, enligt definitionen i disponeringsgrupperna."

    Eftersom ledtiden för artiklar är mycket olika, behöver Contoso inte planera alla artiklar för samma period i framtiden. Disponeringsgrupper för artiklarna skapas. Artiklar som har en liknande ledtid tilldelas samma disponeringsgrupp. Planeringshorisonten för varje disponeringsgrupp (som är tidsgränsen för disponering) är ungefär ledtiden plus en marginal på en vecka. Huvudplaneringen ser sedan till att artiklarna planeras i förväg, baserat på deras produktionstid.

    Därför kommer två disponeringsgrupper att skapas för det här exemplet. En disponeringsgrupp kommer att ha en disponeringstidsgräns på två veckor och den andra kommer att ha en disponeringstidsgräns på åtta veckor.

    Om **Ja, som definierats i den här huvudplanen** väljs som svar, bör antalet dagar som anges överstiga den längsta ledtiden för alla artiklar. Men eftersom många artiklar inte behöver planeras så långt i förväg, kommer många planerade order att beräknas men aldrig användas. Därför kommer körningstiden för huvudplaneringen att öka.

- **Tidsplanering:**

    - **Fråga:** "behöver du schemalägga operationer uppdelade i enskilda jobb?"
    - **Svar:** "Ja".

    Contoso tillverkning måste planera och schemalägga enskilda jobb som ska utföras på verkstadsgolvet. Därför kommer det att använda finplanering.

- **Kapacitet:**

    - **Fråga:** "vill du schemalägga med resursernas kapacitet?"
    - **Svar:** "Ja, enligt definitionen i den här huvudplanen." **10 dagar** anges.

    Antalet fräs- och borrmaskiner är begränsat. Produktionsplaneringen måste ta hänsyn till denna begränsning och ordna jobben i tid beroende på resursernas kapacitet. Med andra ord kommer jobben som planeras att planeras om baserat på resursernas begränsningar. Planering kommer att använda produktionstiden utöver den period som har definierats. (Planerade produktionsorder kan överlappa varandra.) Eftersom produktionsledtiden för artiklarna är sju dagar, kommer kapaciteten för resurserna för huvudplaneringen att övervägas under 10 dagar.

- **Ordningsföljd:**

    - **Fråga:** "vill du sekvensera planerade order med hjälp av produktens sekvensvärden?"
    - **Svar:** "Ja, enligt definitionen i disponeringsgrupperna."

    Ett flöde definieras för produktionen av varje slutlig artikel. Därför schemalägger huvudplaneringen order i tid enligt de definierade rutterna.

- **Nedbrytning:**

    - **Fråga:** "vill du planera order för alla element i en strukturlista (plan för det överordnade och alla underordnade objekt)?"
    - **Svar:** "Ja, enligt definitionen i disponeringsgrupperna."

    Alla artiklar som används för produktionen måste planeras. Eftersom artiklarna har mycket olika ledtider, kommer huvudplaneringen att ha bättre prestanda när disponeringsgrupperna används. Återigen kan en marginal på en vecka anges, och explosion kan göras för samma tid som disponeringen.

### <a name="example-2-contoso-retailer"></a>Exempel 2: Contoso återförsäljare

Contoso återförsäljare är ett distributionsföretag inom modebranschen. Den använder huvudplanering för att beräkna när inköpsorder ska placeras, baserat på den prognostiserade försäljningen. Här är några av dess egenskaper:

- Contoso återförsäljare använder en efterfrågeprognos för att förutsäga försäljning. Inköpsorder kommer att planeras enligt prognosen.
- Butiker används rekvisitioner för påfyllnad.
- Produktionstiden från huvudlagerställe till varje butik är ungefär två veckor för alla artiklar.

I guiden anges följande värden för Contoso återförsäljare:

- **Efterfrågeprognos:**

    - **Fråga:** "vill du använda en prognosplan i huvudplaneringen så att planerade order kommer att föreslås för att uppfylla prognostiserade efterfrågan?"
    - **Svar:** "Ja, enligt definitionen i den här huvudplanen."

    Contoso har inkluderat en efterfrågeprognos för att förutsäga dess försäljning. Därför måste huvudplaneringen rekommendera planerade order för att uppfylla prognosen.

- **Bekräftelse:**

    - **Fråga:** "vill du att huvudplaneringen automatiskt ska bekräfta planerade order i orderdokument, till exempel produktions- eller inköpsorder?"
    - **Svar:** "Ja, enligt definitionen i den här huvudplanen." **1 dag** anges.

    Eftersom Contoso återförsäljare skapar inköpsorder direkt från de planerade inköpsorder, är det användbart om de planerade inköpsorder bekräftas automatiskt. Eftersom företaget kör huvudplanering varje dag kommer en bekräftelsetidsgräns på en dag automatiskt bekräfta alla beställningar som krävs för nästa dag.

- **Godkända rekvisitioner:**

    - **Fråga:** "vill du inkludera efterfrågan från godkända rekvisitioner för att fylla på butiker?"
    - **Svar:** "Ja, enligt definitionen i den här huvudplanen." **1 dag** anges.

    Contoso använder godkända rekvisitioner från sina butiker för att skapa planerade inköpsorder för att fylla på dessa butiker. Eftersom huvudplaneringen körs varje dag inkluderas rekvisitionerna från den sista dagen i planeringen.
