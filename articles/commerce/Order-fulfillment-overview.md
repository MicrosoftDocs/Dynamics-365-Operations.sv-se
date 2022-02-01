---
title: Orderuppfyllelse i butik
description: Det här ämnet ger en översikt över orderuppfyllelse i butik.
author: BrianShook
ms.date: 10/30/2017
ms.topic: overview
ms.prod: ''
ms.technology: ''
ms.search.form: RetailStoreTable, RetailTillLayout
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.search.industry: retail
ms.author: brshoo
ms.search.validFrom: 2017-10-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: 36ce908e81639fbb836d33ff3e84976c395b1473
ms.sourcegitcommit: 3754d916799595eb611ceabe45a52c6280a98992
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2022
ms.locfileid: "7983352"
---
# <a name="store-order-fulfillment"></a>Orderuppfyllelse i butik

[!include [banner](includes/banner.md)]

Många återförsäljare vill optimera orderuppfyllelse genom att låta butiker fylla i order. Orderuppfyllelse på butiksnivå hjälper dig att förenkla scenarier med överlager för en specifik butik eller kan behövas från en logistisk synvinkel i de fall som en butik har extra kapacitet eller ligger inom närmare avstånd för leverans till kunden. För att tillgodose detta behov är ett enhetligt utförande av orderuppfyllelse tillgängligt i POS.

Order för uppfyllelse i en specifik butik har butikens lagerstället tilldelat på rubriken eller raderna på ordern.

Utförande av orderuppfyllelse i butiken ger en enskild arbetsyta i POS som kan användas för att bearbeta order. Detta inkluderar allt från att acceptera ordern, till att markera den som levererad eller påbörja upphämtning i butik.

## <a name="access-unified-order-fulfillment-in-the-point-of-sale"></a>Komma åt enhetligt orderuppfyllande i POS

Orderuppfyllande [Operations-ID 928](pos-operations.md), kan användas för åtkomst till butikens orderuppfyllelsearbete i POS.

Utförande av orderuppfyllelsen har inte sin egen inte har sin egen färdiga behörighet, men användare kommer i framtiden att kunna använda behörigheten **Tillåt hämta order** för att starta en åtgärd från POS.

På butiksnivå finns en konfigurationsinställning tillgänglig för att bestämma om en orderrad måste godkännas manuellt inifrån POS eller inte. Om det alternativet inte anges godtas orderrader som standard. Om det alternativet är aktiverat kommer användarna i POS behöva välja behörigheten **Tillåt acceptera order** för att ta emot order inifrån POS.

Orderrader kan också avvisas från POS. Om du avvisar en orderrad anger du att den inte ska uppfyllas i den här butiken och skickar tillbaka orderraden för tilldelning till en annan butik eller lagerställe. Behörighet att avvisa orderrad tilldelas via behörigheten **Tillåt avvisa order**.

## <a name="order-fulfillment-operation-parameters"></a>Parametrar för utförande av orderuppfyllelse

De färdiga parametrar för utförande av orderuppfyllelse kan användas till åtgärden när den anropas i POS. När parametern **Alla order** är konfigurerad, visas alla order när åtgärden används. Parametern **Order att leverera** visar bara order som måste levereras från butiken och **Order att hämta** visar order som kommer att hämtas i butiken.

## <a name="orders-for-fulfillment"></a>Order för uppfyllelse

Utförandet av orderuppfyllelse visar bara order som antingen kommer att hämtas upp i eller levereras från den aktuella butiken. Order för andra butiker att uppfylla visas inte när du använder utförandet av orderuppfyllelse.

## <a name="line-selection"></a>Radurval

Raderna kan väljas som funktionen **Välj** i åtgärdsfönstret. När **Välj** är aktiverad kan flera rader väljas för bearbetning. Du kan avmarkera valda rader genom att klicka igen på samma rad.

## <a name="line-details"></a>Radinformation

Raddetaljer visas med den utfällda menyn med radinformation. När den här menyn används ges tre flikar som innehåller ytterligare information för den valda raden. Den första fliken **Radinformation** visar information om själva raden såsom beställd kvantitet och återstående. Mer information finns inklusive plockad kvantitet, förpackad och fakturerad samt leveranssätt och leveransadress. Fliken **Orderinformation** ger information om orderrubrik inklusive kund, kund-ID, ordernummer, ordertotal och saldo. Fliken för **lager** visar information om den valda raden när det gäller fysiska inleveranser, reserverat lager och beställt lager.

Om flera rader är markerade indikerar utfällda menyn för orderraddetaljer endast att flera rader är markerade. Rensa raderna om du vill visa detaljer för en enskild rad tills bara en rad återstår.

## <a name="pending-order-lines"></a>Väntande orderrader

Enhetligt orderuppfyllande omfattar möjligheten att acceptera order manuellt. Som standard accepteras redan order för utförande i butiken. Men om affärsprocesser anger att en arbetare på butiksnivå måste acceptera order, kan manuellt godkännande aktiveras på butiksnivån. För att aktivera godkännande av ordern, gå till **Butik och handel** \> **Kanaler** \> **Butiker** \> **Alla butiker**. Öppna önskad butik och på fliken **Allmän** söker du efter underrubriken **Orderuppfyllande**. Denna underrubrik har alternativet **Manuellt godkännande** som är inställt på **Nej** som standard. Genom att ange detta alternativ till **Ja** och synkronisera ändringarna till kanaldatabasen kan orderrader gå igenom processen för godkännande.

Personer med behörigheten **Tillåt acceptera order** kan öppna orderuppfyllande och välj rader för godkännande. När rader har accepterats, deras tillstånd ändras från **väntande** till **accepterade** och fortsätta med resten av utförande av orderprocessen. När **Manuellt godkännande** aktiveras kommer order inte att bearbetas förrän de har godkänts.

För butiken upphämtning i butik har aldrig **väntande** status. Detta görs för att undvika ett scenario där en kund kommer till butiken och orderraden kan inte bearbetas eftersom en arbetare med rätt behörighet inte är tillgänglig.

## <a name="accepted-order-lines"></a>Godkända orderrader

Order med radstatus **Godkänd** kan fortsätta med resten av utförande av orderprocessen. När en order har tagits emot, vidtas eventuella återstående åtgärder mot orderraden.

Exempelvis kan en accepterad orderrad väljas och sedan hämtas direkt utan att gå via plockning och packning.

## <a name="line-actions"></a>Radåtgärder

### <a name="pick"></a>Plocka

Kategorin **Välj** av åtgärder är avsedd som en hjälp vid plockning av orderrader från hyllorna. Plockningsåtgärden kan endast utföras på orderrader som tidigare har accepterats.

**Åtgärd: plockning**

- **Resulterande kassastatus:** Plockning
- **Resulterande back office-status:** Ingen ändring

När en order har tagits emot kan rader väljas och markeras som **plockning**. Att markera en rad som **plockning** är för att visa att plockningsarbetet redan har utförts på en rad. Detta förhindrar två arbetare från att försöka välja samma orderrader samtidigt.

**Åtgärd: Skriv ut plocklista**

- **Resulterande status:** Plockning
- **Resulterande back office-status:** Ingen ändring

Plocklistor kan skrivas ut vid POS för att hjälpa medarbetare att utföra plockningsprocessen. En utskriven plocklista kan köras medan medarbetaren utför plockningen och när produkterna plockas kan medarbetaren manuellt markera dem som plockade på plocklistan.

Plocklistformatet konfigurerats i Commerce och läggs till i kvittoprofilen. Mer information om hur du ställer in kvittoprofiler finns i [Kvittomallar och utskrift](receipt-templates-printing.md).

Om raderna markeras och en plocklista skrivs ut för dessa rader uppdateras de automatiskt med statusen **plockning**.

**Åtgärd: Markera som plockad**

- **Resulterande status:** Plockad eller delvis plockad
- **Resulterande backoffice-status:** Plockad eller delvis plockad

När den fysiska plockningsprocessen har utförts kan raderna markeras som **plockade**. Att välja en rad och markera den som **plockad** utför ett anrop i realtid om att uppdatera orderraden. När raden har markerats som **plockad** i POS, uppdateras även statusen i backoffice till **plockad** och lagertransaktioner visar att den angivna kvantiteten har minskats.

När order bearbetas över tid kan delkvantiteter behandlas för en specifik rad. Om en rad är markerad och åtgärden **Markera som plockad** hämtas och kvantiteten är större än 1, uppmanas användaren till att ange kvantiteten. Resterande kvantitet som ska plockas fylls i automatiskt. Om mindre än det återstående antalet anges blir statusen för raden **Delvis plockad**. När orderraden uppdateras i backoffice återspeglar den även den delvis plockade statusen och den kvantitet som angetts av användaren och används för lageruppdateringen.

Om en orderrad plockas fel, måste hävning av plockningen utföras på orderraden i backoffice. Det finns för närvarande inga hävningsåtgärder som stöds i POS.

Orderrader från olika order kan väljas och markeras som **plockning** utskrivna på samma plocklista eller märkta som **plockade**.

### <a name="pack"></a>Paket

Orderrader kan packas när som helst efter det att orderraden har accepterats.

**Åtgärd: Skriv ut följesedeln.**

- **Resulterande status:** Packad eller delvis packad
- **Resulterande backoffice-status:** levererad eller delvis levererad

Den här åtgärden markerar rader som packade eller delvis packade och skriver ut en följesedel. En följesedel kan skrivas ut för att validera de produkter som har packats ihop. Följesedelformatet konfigureras i Commerce och läggs till i kvittoprofilen. Mer information om hur du ställer in kvittoprofiler finns i [Kvittomallar och utskrift](receipt-templates-printing.md).

**Åtgärd: Markera som packad**

- **Resulterande status:** Packad eller delvis packad
- **Resulterande backoffice-status:** levererad eller delvis levererad

Åtgärden **markeras som packad** kan användas för att ange att raderna förpackas utan att skriva ut en följesedel. Både **Skriv ut följesedel** och **markeras som packad** leder till lagertransaktioner i backoffice. Följesedlar med raderna på försäljningsstället leder till följesedelsjournaler som skapas i backoffice.

Om en orderrad förpackas felaktigt måste följesedeljournalens korrigeras på backoffice.

Endast rader i samma order och med samma leveranssätt kan packas samtidigt.

För närvarande är alternativet för att lagra butiksupphämtningsrader som **Packad** inaktiverat. Den här funktionen läggs till i framtida versioner. Processen att skapa följesedeln kommer att utökas för att stödja injektion av tredje parts leveransinformation till följesedelprocessen.

### <a name="pick-up"></a>Upphämtning

Order för butiksupphämtning kan plockas direkt när de hämtas i POS. Beställningar för butiksupphämtning omfattas inte av godkännande.

**Åtgärd: plockning**

- **Resulterande status:** fakturerat eller delvis fakturerad
- **Resulterande backoffice-status:** fakturerad eller delvis fakturerad

Om en rad är markerad för plockning in från enhetliga orderuppfyllande läses hela ordern till POS och den fullständiga kvantiteten för den valda raden markeras. Andra rader i ordern läses också in i transaktionsvyn i POS, men med kvantiteten som markerad som noll.

När rader för upphämtning har lästs in i transaktionsvyn kan transaktionen genomföras som vanligt.

Rader som är fullständigt fakturerade via upphämtning visas inte längre i enhetlig bearbetning av order. Rader som delvis har hämtats fortsätter att visas i enhetlig orderuppfyllande tills de har hämtats i sin helhet.

Om en rad hämtas av misstag måste en retur utföras för att korrigera felet.

Endast rader i samma order och med samma leveranssätt kan hämtas samtidigt.

### <a name="shipping"></a>Leverans

Orderraderna som ska levereras från lagret kan bearbetas via enhetligt orderutförande med hjälp av åtgärdem **Leverera**. Om godkännande av manuell orderrad har konfigurerats på kanalnivå, måste order godkännas före leverans. När en orderrad har tagits emot och har status **väntande** kan raderna levereras.

**Åtgärd: transport**

- **Resulterande status:** fakturerat eller delvis fakturerad
- **Resulterande backoffice-status:** fakturerad eller delvis fakturerad

Rader som har skickats från enhetlig orderuppfyllelse faktureras från backoffice på liknande sätt som om ordern faktureras direkt från backoffice. Rader som levereras från enhetliga orderuppfyllande läses inte in i transaktionsvyn och det lämnas inga offerter när raderna har levererats.

Orderrader som har levererats fullständigt visas inte längre i enhetlig orderuppfyllelse. Rader som delvis har hämtats fortsätter att visas i enhetlig orderuppfyllande tills de har levererats i sin helhet.

Endast rader från samma order kan levereras samtidigt. Om raderna från samma order har olika leveransformer kan de fortfarande väljas för leverans samtidigt.

### <a name="reject"></a>Avvisa

Rader eller delvisa rader avslås. Detta gör att de kan skickas vidare från backoffice till en annan butik eller lagerställe. Raderna kan bara avvisas om de har ännu inte plockats eller förpackats. Om du vill avvisa en rad som redan har plockats eller förpackats måste den raden upphävas eller packas upp från backoffice.

**Åtgärd: Avvisa**

- **Resulterande status:** Avvisad
- **Resulterande back office-status:** Ingen ändring

De avvisade orderraderna kan visas från arbetsytan **Bearbetning och begäran om försäljningsorder**. Radera personfiltret på arbetsytan om du vill visa alla avvisade orderrader mellan butikerna. Fliken **Avvisade orderrader** under avsnittet **order och favoriter** visar orderraderdetaljerna. Dessutom kan användarna klicka på knappen **Avvisade orderrader** under avsnittet **sammanfattning** för att gå till en försäljningsordervy. Detta visar alla order som har en eller flera avvisade orderrader. Om distribuerad orderhantering (DOM) är aktiverad kommer dessa avvisade order att automatiskt tilldelas de lämpliga butikerna för uppfyllelse, men dessa orderrader kan även tilldelas manuellt. För att göra detta, markera raden som visar **uppfyllelsestatus** som **avvisad** och ändra vid behov platsen/lagerstället. Klicka på listrutan **uppdatera rad** och klicka på **Återställ uppfyllelsestatus** för att ändra uppfyllelsestatusen från **avvisad** till **accepterad** eller **väntande** beroende på inställningen av orderuppfyllelsen. Efter att uppfyllelsestatus har återställts ska butikspersonalen kunna visa orderrader i POS.

## <a name="line-quantity-tracking"></a>Radkvantitetsspårning

En enskild orderrad med kvantitet större än ett kan bearbetas med tiden vilket resulterar i flera underordnade tillstånd för orderraderna. Om till exempel ett verktyg har ett projekt som kräver 500 kort men verktyget bara hämtar upp eller har några få tavlor levererade vid ett tillfälle under projektet, kan det vara kvantiteter som plockas, packas och levereras samtidigt.

Varje gång en rad markeras fylls det återstående beloppet för den raden i automatiskt för att anta att återstående kvantitet bearbetas. Med hjälp av exemplet ovan, om 200 kort redan har plockats och raden för kort väljs för plockning, fylls den återstående kvantiteten på 300 automatiskt i kvantiteten. Detsamma gäller om 200 kort redan har fakturerats. Resterande kvantitet blir då ifylld automatiskt.

Fortsätter med exemplet ovan, om 200 kort markeras som packade och leverans är vald, blir hela beloppet på 500 automatiskt ifyllt. Om endast 200 kort levereras, antar systemet att tidigare packade kort levereras och att den packade kvantiteten minskas. Om 201 kort levereras minskas först de förpackade korten med återstående enkelt kort från den resterande kvantiteten.

## <a name="line-statuses"></a>Radstatusar 

Orderrader i POS har flera statusar som återspeglar status för orderraden. Statusar i POS och backoffice matchar inte alltid. Orderradstatusen kan ses genom den kassa som använder utförande av orderuppfyllelse. I backoffice visas orderraderna från orderdetaljerna. Orderdetaljer kan nås via **Butik och handel** \> **Kunder** \> **Alla kundorder**. Välj **Order-ID** för orderdetaljer. Från orderdetaljer väljer du fliken **Försäljningsorder** och väljer sedan **Detaljerad status** under underrubriken **Visa**.

- **Väntande** – Orderrader som har tilldelats en butik, men som ännu inte accepterat har status **väntande** när den ses i POS. Raderna som väntar på godkännande i POS kommer att ha status **Orderbehandling** i backoffice.
- **Accepterad** – Orderrader som har accepterats manuellt eller accepteras automatiskt får statusen **Accepterad** när de visas i POS. Rader med status **accepterad** visas som **orderbehandling** i backoffice.
- **Plockning** – Raderna som ska plockas för närvarande på butiksnivån har statusen **plockning**. Samma rader, när de visas i backoffice, visas som **Orderbehandling**.
- **Plockad** och **Delvis plockad** – Raderna som plockats eller delvis plockats vid POS får statusen **Plockad** eller **Delvis plockad**. Samma rader i backoffice visas också som **Plockad** eller **Delvis plockad**.
- **Packad** och **Delvis packad** – Raderna som packats eller delvis packats vid POS får statusen **Packad** eller **Delvis packad**. Samma rader i backoffice visas också som **Levererade** eller **Delvis levererade**.
- **Delvis fakturerad** – Raderna som har delvis hämtats eller delvis levererats får statusen **Delvis fakturerade** i POS och backoffice.
- **Fakturerad** – Rader som är fullständigt fakturerade i POS visas inte längre för uppfyllelse. I backoffice är statusen för dessa rader **Fakturerad**.

## <a name="order-fulfillment-filtering"></a>Orderuppfyllelsefiltrering

Orderuppfyllelse i POS innehåller filter för att hjälpa användaren att enkelt hitta vad de behöver. Filter kan ändras via åtgärdsfönstret längst ned på skärmen **Kassa**. Som standard tillämpas filtret **leveranstyp** beroende på hur operationen ställs in. Om operationen ställs in med parametern **alla order** och filtret används vid åtkomst av orderuppfyllelse. Detsamma gäller för parametrarna **Butiksupphämtning** och **Leverans från butik**. Andra filter kan tillämpas på orderuppfyllelsen:

- Kundnummer
- Kundnamn
- Kundens e-postadress
- Ordernummer
- Leveranssätt
- Inleveransnummer
- Kanalreferens-ID
- Ursprungligt butiksnummer
- Radstatus
- Skapades den
- Leveransdatum
- Inleveransdatum


[!INCLUDE[footer-include](../includes/footer-banner.md)]