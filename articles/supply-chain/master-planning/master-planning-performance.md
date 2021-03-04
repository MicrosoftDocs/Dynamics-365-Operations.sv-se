---
title: Förbättra huvudplaneringens prestanda
description: I det här avsnittet beskrivs olika alternativ som kan hjälpa dig att förbättra prestandan vid huvudplanering och felsökning av problem.
author: t-benebo
manager: tfehr
ms.date: 12/18/2019
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
ms.openlocfilehash: fa8426c3a1f19f8607f45e9ac4d57300abddb161
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4437886"
---
# <a name="improve-master-planning-performance"></a>Förbättra huvudplaneringens prestanda

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs olika alternativ som kan hjälpa dig att förbättra prestandan vid huvudplanering och felsökning av problem. Den innehåller information om parametrar och inställningar samt om rekommenderade konfigurationer och åtgärder. Den innehåller också en sammanfattning av de viktiga parametrar som du bör tänka på när du har tidskrävande huvudplaneringsjobb.

Det här avsnittet är avsett för systemadministratörer eller IT-användare som har möjlighet att felsöka. Den är också avsedd för produktion eller leveransplanering, eftersom den innehåller information om parametrar som hör till affärsplaneringskrav. 

## <a name="parameters-related-to-master-planning-performance"></a>Parametrar som är relaterade till huvudplaneringsresultat

Olika parametrar påverkar huvudplaneringens körtid och bör beaktas.

### <a name="number-of-threads"></a>Antal trådar

Parametern **antal trådar** gör att du kan justera huvudplaneringsprocessen så att den fungerar bättre på den specifika datauppsättningen. Denna parameter anger det totala antalet trådar som ska användas för att köra huvudplaneringen. Den orsakar parallellisering av huvudplaneringskörningen som hjälper till att minska körtiden. 

Du kan ställa in parametern **antal trådar** i dialogrutan **huvudplaneringskörning**. Öppna den här dialogrutan genom att gå **Huvudplanering \> Huvudplanering \> Kör \> Huvudplanering**, eller välj **Kör** i arbetsytan **Huvudplanering**. Om du vill fastställa det bästa värdet för den här parametern måste du förlita dig på en försöks- och misstagsprocess. Du kan dock använda följande formler för att beräkna ett startvärde:

- **Om din bransch är tillverkning:** (antal trådar) = (antal planerade order ÷ 1 000)
- **Annars:** (antal trådar) = (antal artiklar ÷ 1 000)

Antalet stödprocesser som används under huvudplaneringen måste vara mindre än eller lika med det maximala antalet trådar som tillåts på batchservern. Om antalet stödprocesser överstiger antalet trådar på batchservern, fungerar inte de extra trådarna som de ska.

> [!NOTE]
> En inställning på **0** (noll) för parametern **antal trådar** ökar huvudplaneringens körtid. Därför rekommenderar vi att du alltid anger ett värde som är större än 0.

### <a name="number-of-tasks-in-helper-task-bundle"></a>Antal uppgifter i hjälpen för uppgiftsbunt

Genom att ändra inställningen **antalet uppgifter i aktivitetsbunt** (dvs. buntstorleken), kan du minska körningstiden. Den här inställningen styr antalet artiklar som planeras tillsammans av en enskild hjälp.

Du kan ange parametern **antalet uppgifter i aktivitetsbunt** i avsnittet **prestanda** på fliken **allmänt** på sidan **huvudplaneringsparametrar** (**huvudplanering \> inställning \> huvudplaneringsparametrar**). Det bästa värdet för den här parametern beror på dina data. Därför rekommenderar vi att du börjar med värdet **1** och använder en försöks- och misstagsprocess för att avgöra vilket värde som är bäst för din inställning.

I allmänhet rekommenderar vi att du ökar antalet uppgifter när antalet artiklar är mycket stort (i hundratusental). Annars bör du minska antalet uppgifter. För följande specifika branscher bör följande rekommendationer beaktas:

- I detaljhandels- och distributionsbranschen, där det finns många oberoende artiklar, använder du många hjälpprogram, eftersom det inte finns något samband mellan artiklarna. 
- I tillverkningsindustrin, där det finns många strukturlistor och delade del komponenter, använder du färre stödprocesser, eftersom beroenden mellan artiklar kan orsaka väntetider.

> [!TIP]
> Om du har prestandaproblem rekommenderar vi att du minskar **antalet stödprocesser i inställningen för uppgiftsbunt** till **1**. Du kan sedan starta försöks- och misstagsprocessen för att hitta det bästa värdet för din inställning. I allmänhet uppstår prestandaproblem när en artikel tar längre tid att bearbeta än återstående artiklar. I det här fallet ser du att två efterföljande uppgifter som har statusen **Disponering** i huvudplaneringskörningen bara tar olika tidsvärden att köra. I extrema fall kan denna skillnad vara ungefär 30 minuter. Du kan härleda hur lång tid det tar innan aktiviteterna körs genom att visa varaktigheten för varje uppgift.

### <a name="use-of-cache"></a>Användning av cache

Parametern **Användning av cache** gör att du kan justera huvudplaneringsprocessen så att den fungerar bättre på den specifika datauppsättningen. Du kan till exempel justera den för att uppnå följande resultat:

- Mer information samlas in i dataminnet om mer cachelagring görs. Förväntan är att data kommer att användas senare. Om data finns i minnet kan du spara vissa databasförfrågningar. Om mer cachelagring görs ökar dock minneskraven.
- Om mindre cachelagring görs kan samma data behöva hämtas från databasen oftare. Dessutom lagrar programobjektserver (AOS) mindre data i minnet under processen.

Det är svårt att förutsäga vilket alternativ som är bättre eftersom varje ärende bara är beroende av data utan även på maskinvaran. Eftersom mindre cachelagring medför ytterligare belastning på databasservern är det förmodligen ingen bra idé att använda det alternativet om databasservern redan är överbelastad.

Du kan ange parametern **användning av cachelagring** i avsnittet **prestanda** på fliken **allmänt** på sidan **huvudplaneringsparametrar** (**huvudplanering \> inställning \> huvudplaneringsparametrar**). Hur effektiv cachelagringen är beror på att kundens data är mycket. Om till exempel cachelagrade data aldrig behövs behöver du bara slösa minnet om du lagrar data till slutet av tidsplaneringsprocessen. Om du i detta fall konfigurerar mindre cachelagring kan prestandan öka eftersom AOS kräver mindre minne och serverresurser frigörs för andra uppgifter.

> [!TIP]
> I allmänhet rekommenderar vi att du ställer in att parametern **Användning av cachelagring** till **maximum** eftersom parametern är avsedd som en funktion för att förbättra prestanda. Vi rekommenderar att du ställer in parametern till **minimal** om du kör på plats och har begränsat minne (ungefär 2 gigabyte\[GB\]).

### <a name="number-of-orders-in-firming-bundle"></a>Antal order i bekräftelsebunten

Parametern **antal eller order i bekräftelsebunt** anger det totala antalet order som kommer att bearbetas åt gången av varje tråd/batch. Det gör parallellisering av autobekräftelsen.

Du kan ange parametern **antal eller order i bekräftelsebunt** i avsnittet **prestanda** på fliken **allmänt** på sidan **huvudplaneringsparametrar** (**huvudplanering \> inställning \> huvudplaneringsparametrar**). Parallellisering för autobekräftelseprocessen baseras på de order som måste behandlas tillsammans. Om denna parameter är inställd på **50**, till exempel, hämtar varje tråd eller batchuppgiften 50 order åt gången och bearbetar dem tillsammans. Vi rekommenderar att du använder en försöks- och misstagsprocessen för att hitta det bästa värdet. Du kan dock använda följande formler för att beräkna ett startvärde:

(Antal order per bunt) = (antal efter efterfrågeobjekt ÷ antalet trådar)

> [!NOTE]
> Om du anger parametern **Antal order i bekräftelsebunten** till **0** (noll), görs ingen parallellisering av autobekräftelsen. Hela processen körs på en enskild batchuppgift och har en kumulativ körtid. Därför kommer körningstiden för huvudplaneringen att öka. Därför rekommenderar vi att du ställer in den här parametern på ett värde som är större än **0** (noll).

### <a name="time-fences"></a>Tidsgränser

Tidsgränser anger hur långt beräkningen och andra krav måste beräknas i huvudplaneringen. Ju större tidsgränsen är, desto längre tid tar huvudplaneringen att köra. Ställ därför in tidsgränsen efter dina affärsbehov. Mer information om tidsgränser finns i [ställa in huvudplanering](master-planning-setup.md).

### <a name="actions"></a>Åtgärder

I tidsgränsen kan du även hitta parametern för **åtgärdsmeddelande**. Beräkningen av åtgärdsmeddelanden gör att en tid körs längre för huvudplaneringen. Om åtgärdsmeddelanden inte analyseras och tillämpas regelbundet (varje dag, vecka o.s.v.) bör du överväga att inaktivera beräkningen under huvudplaneringskörningen. Du inaktiverar beräkningen på sidan **Huvudplaner** ange (**Huvudplanering \> Inställningar \> Planer \> Huvudplaner**), ange tidsgräns för **Åtgärdsmeddelanden** till **0** (noll). Kontrollera också att inställningen **åtgärdsmeddelande** är inaktiverad för alla disponeringsgrupper.

### <a name="futures"></a>Leveransplaner

Beräkningen av leveransplaner gör att en tid körs längre för huvudplaneringen. Om du inte planerar strukturlistor, eller om förseningar inte behöver spridas från till gång till efterfrågan under planering, bör du överväga att inaktivera framtida beräkningar vid huvudplaneringen. Om du vill inaktivera beräkningarna ställer du in tidsgränsen för **leveransplaner** till **0** (noll) för huvudplanen du kör. Kontrollera också att inställningen **leveransplaner** är inaktiverad för alla disponeringsgrupper.

## <a name="one-heavy-routine-at-a-time"></a>En tung rutin åt gången

När du planerar huvudplaneringen ska du inte tidsplanera något annat batchjobb samtidigt. Var särskilt försiktig med att inte schemalägga andra tunga rutiner, t.ex. lagerstängning, samtidigt.

## <a name="review-the-session-log"></a>Granska loggen för session

Systemet kan samla in mer information om de uppgifter som körs under huvudplaneringen. Se till att systemet samlar in den här informationen genom att aktivera inställningen för **Spåra bearbetningstid** i dialogrutan **huvudplaneringskörning**. Den insamlade informationen kan hjälpa dig att hitta flaskhalsar i körningen. När t.ex. parametern **antalet uppgifter i hjälpens uppgiftsbunt** har värdet **1**, kan du identifiera objektet som har den längsta körtiden. Du kan också jämföra körtiderna för de olika trådar som har status som **täckning** och jämföra varaktigheten för varje uppgift.

Om du vill granska huvudplaneringskörningarna i systemet följer du ett av dessa steg.

- Välj arbetsytan **huvudplan**, välj en huvudplanering i listrutan och välj sedan panelen **huvudplanering** och sedan **historik**. Välj ett jobb, välj **förfrågningar** på snabbfliken och välj sedan **processuppgiftens varaktighet**.
- På sidan **huvudplaner**, välj en plan i det vänstra fönstret och välj **historik** på snabbfliken. Välj ett jobb, välj **förfrågningar** på snabbfliken och välj sedan **processuppgiftens varaktighet**.

När du granskar sessionskatalogen bör du tänka på följande:

- **Uppdateringen** bör inte ta lång tid (i allmänhet bör den ta upp till 30 minuter), det är dock en enkel tråd.
- **Kopieringsplanen** ska inte ta lång tid (det bör dröja ungefär en minut).
- **Automatisk bekräftelse** tar vanligtvis cirka 30 minuter. Det kan dock ta upp till flera timmar, beroende på antalet order och artiklarnas komplexitet.
- **Automatisk bekräftelse** ska ta kortare tid än **täckningen**.
- **Täckningen** bör ta längsta tid i förhållande till resten.
- **Åtgärd** och **framtida meddelanden** kan ta lång tid, beroende på data och antal strukturlistor.

## <a name="filtering-of-items"></a>Filtrering av artiklar

Filter som används i dialogrutan **huvudplaneringskörning** påverkar tidslängden på huvudplaneringskörningen. Gå till **Huvudplanering \> Huvudplanering \> Kör \> Huvudplanering**, eller välj **Kör** i arbetsytan **Huvudplanering**. Om du vill undanta objekt från körningen rekommenderar vi att du filtrerar fram artikelns livscykeltillstånd (inte med hjälp av artikelnummer). När du filtrerar efter livscykel steg tar uppdaterings processen kortare tid än när du filtrerar efter artikelnummer.

## <a name="automatically-filter-by-items-with-direct-demand"></a>Filtrera automatiskt efter artiklar med direkt efterfrågan

Om du vill förbättra körningstiden för huvudplaneringen kan du välja att bara inkludera artiklar med direkt efterfrågan. Det här filtret kan bara användas för en fullständig huvudplaneringskörning utan att några andra filter används i fältet **poster som ska inkluderas**. En huvudplaneringskörning med filter ignorerar inställningen filtrera **automatiskt efter objekt med direkt efterfrågan**.

Fältet **filtrera automatiskt efter artiklar med direkt efterfrågan** finns på sidan **Huvudplaneringsparametrar** och kan användas med inställningar för både för förbearbetning och efterbearbetning.

### <a name="pre-processing"></a>Förbearbetning
Parametern **Förbearbetning: filtrera automatiskt efter objekt med direkta behov** säkerställer att förbearbetningsfasen i huvudplaneringen endast innehåller artiklar som uppfyller minst ett av följande villkor:
  - Artikeln har en förväntad inleverans eller utleverans, till exempel en inköpsorder, försäljningsorder, offert, överföringsorder eller produktionsorder. 
  - Artikeln har artikeldisponering med säkerhetslager (minsta lagerbehållning).
  - Prognosticerad efterfrågan efter idag finns för artikeln.
  - Prognosticerad leverans efter idag finns för artikeln.
  - Artikeln innehåller alla kontinuitetsrader från callcentermodulen som ännu inte har skapats.

> [!NOTE]
> En artikel som har fysiskt tillgänglig lagerbehållning kommer inte att visa en behovstransaktion eftersom det inte finns någon efterfrågan på artikeln.

### <a name="post-processing"></a>Efterbearbetar
Alternativet **Efterbearbetning: filtrera automatiskt efter objekt med direkt efterfrågan** är endast relevant om du anger **Strukturlisteversionskrav** i dina disponeringsgrupper. Annars behöver du inte aktivera parametern. 

Innan disponeringssteget börjar, finns det ett steg före täckning under vilka artiklar med disponeringsinställningen **Strukturlisteversionskrav** aktiverad kommer att bearbetas om. Detta görs för att säkerställa att artiklar från den begärda strukturlisteversionen planeras. Artiklar som anses ha efterfrågan under förbehandlingen har inte längre någon efterfrågan och bör därför uteslutas från planeringskörningen.

## <a name="performance-checklist-summary"></a>Sammanfattning av prestandachecklista

- **Antal trådar** – ange ett värde som är större än **0** (noll).
- **Antal uppgifter i hjälpens uppgiftsbunt** – ange ett värde som är större än **0** (noll). (Använd de formler som anges tidigare i det här avsnittet.)
- **Användning av cache** –Ange **Maximum** om inte systemet har ont om ledigt minne.
- **Antal order i hjälpens bekräftelsebunten** – ange ett värde som är större än **0** (noll). (Använd den formel som anges tidigare i det här avsnittet.)
- **Tidsgränser** – anpassa till dina affärsbehov.
- **Åtgärder och framleveransplaner** – inaktivera åtgärder och framtida om du inte använder dem.
- **En tung rutin vid en tidpunkt** – kör inte huvudplanering tillsammans med någon annan tung rutin.
- **Granska loggen för session**
- **Filtrering av artiklar** – Använd livscykelstadiet för att exkludera artiklar från huvudplaneringskörningen. (Använd inte artikelnumren.)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]