---
title: Commerce bokföringsparametrar
description: I denna artikel beskrivs de parametrar som är specifika för bokföringen av ekonomiska och fysiska transaktioner i Microsoft Dynamics 365 Commerce.
author: analpert
ms.date: 04/27/2022
ms.topic: article
audience: Application User, Developer, IT Pro
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: analpert
ms.search.validFrom: 2022-04-12
ms.openlocfilehash: 56a2d1d2bcafdcdd9d88c132986e8ef485bf6b24
ms.sourcegitcommit: 6616b969afd6beb11a79d8e740560bf00016ea7f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2022
ms.locfileid: "9027238"
---
# <a name="commerce-posting-parameters"></a>Commerce bokföringsparametrar

[!include [banner](includes/banner.md)]

I denna artikel beskrivs de parametrar som är specifika för bokföringen av ekonomiska och fysiska transaktioner i Microsoft Dynamics 365 Commerce. Commerce-bokföringsparametrar finns i Commerce headquarters på **Butik och handel \> Administrationsinställning \> Parametrar \> Commerce-parametrar \> Bokföring**.

## <a name="periodic-discount-parameters"></a>Parametrar för tidsbegränsad rabatt

Följande tabell listar de periodiska rabattparametrarna som är specifika för bokföringen av ekonomiska och fysiska transaktioner.

| Parameter | Beskrivning |
|-----------|-------------|
| Bokför tidsbegränsad rabatt | Det här alternativet styr om periodiska erbjudanden bokförs till redovisningskontona. Tidsbegränsade rabatter kan till exempel vara Mixa och matcha, Kvantitetsrabatt och Rabatterbjudande. När den här parametern är aktiverad kan ytterligare fält ställas in i avsnittet **Periodiska rabatter**. |
| Typ av redovisningskonto | <p>Välj den typ av konto som används för att lägga ut periodiska rabatter:</p><ul><li>**Standard** – De rabattrelaterade fälten på den här sidan används inte i systemet. Istället använder den kontona som är definierade på sidan **Bokföring** i Commerce headquarters (**Lagerhantering \> Inställning \> Bokföring \> Bokföringsformulär**).</li><li>**Periodisk** – Systemet använder de handelsrabattkonton som anges av rabattrelaterade fält på den här sidan. Om du väljer det här alternativet måste du ange redovisningskonto (GL) för varje typ av erbjudande (rabatt, mix och matcha, kvantitet och tröskel). När du konfigurerar varje rabatt kan du definiera ett konto. När bokföringsfunktionen för rabattkonto används på sidan för rabattinställningar, görs en extra debetpost och kreditpostering för att omklassificera rabattbokningen från handelsrabatter huvudbokskonto till rabatt huvudbokskonto. Mer information finns i [Butiksrabatter](retail-discounts-overview.md).</li></ul> |
| Bokför infokodsrabatt | Det här alternativet används inte längre i standardhandelslösningen och avaktiveras. |
| Bokför tidsbegränsad rabatt för order | Det här alternativet avgör huruvida tidsbegränsade butiksrabatter bokförs i redovisningen för kundorder och kundtjänstorder. |

## <a name="inventory-update-parameters"></a>Uppdaterar lagerparametrar

Följande tabell listar parametrar dör lageruppdatering som är specifika för bokföringen av ekonomiska och fysiska transaktioner.

| Parameter | Beskrivning |
|-----------|-------------|
| Använd standardbatch‑ID när batchnummer inte hittas | Det här alternativet styr om ett standardbatch-ID används för batchaktiverade artiklar om batchnummer inte hittas och negativt lager är tillåtet. |
| Standardbatch‑ID | Batchnumret som ska användas om partinummer för artiklar inte hittas och parametern **Använd standardbatch‑ID när batchnummer inte hittas** är aktiverad. |

## <a name="aggregation-parameters"></a>Sammansättningsparametrar

Följande tabell listar parametrar för sammansättningsparametrar som är specifika för bokföringen av ekonomiska och fysiska transaktioner.

| Parameter | Beskrivning |
|-----------|-------------|
| Lämna pengar i kassaskåp | Aktivera den här parametern om du vill aggregera alla transaktioner under utdragsbokföring och skapa en enskild rad i journalen för bokföring i stället för en separat rad för varje släpp. |
| Bankinsättning | Aktivera den här parametern om du vill aggregera alla transaktioner under utdragsbokföring och skapa en enskild rad i journalen för bokföring i stället för en separat rad för varje släpp. |
| Försäljningstransaktioner | Aktivera den här parametern om du vill konsolidera transaktionerna som en del i bokföringsprocessen för transaktionsutdrag. Vi rekommenderar att du aktiverar den här parametern. Det har tidigare fått namnet **Verifikationstransaktioner**. |
| Sätt inte samman returer | Om det här alternativet väljs bokförs varje returtransaktion som en separat försäljningsorder när du bokför ett butiksutdrag. |

## <a name="batch-processing-parameters"></a>Batchbearbetningsparametrar

Följande tabell listar de batchbearbetningsparametrar som är specifika för bokföringen av ekonomiska och fysiska transaktioner.

| Parameter | Beskrivning |
|-----------|-------------|
| Maximalt antal parallella utdrag | Det här fältet definierar antalet batchuppgifter som används för att bokföra flera utdrag. |
| Maximalt antal trådar för orderbehandling per utdrag | Det här fältet representerar det maximala antalet trådar som batchjobbet för utdragsbokföring använder för att skapa och fakturera försäljningsorder för ett enskilt uttalande. Det totala antalet trådar som satsutläggningsprocessen använder beräknas genom att multiplicera värdet på denna parameter med värdet på parametern **Maximalt antal parallella utdragsbokföringar**. Om du anger värdet för den här parametern för högt kan prestandan i bokföringsprocessen för utdraget påverkas negativt. |
| Max antal transaktionsrader som ingår i en sammansättning | Det här fältet definierar antalet transaktionsrader som ingår i en enstaka aggregerad transaktion innan en ny transaktion skapas. Aggregerade transaktioner skapas utifrån olika sammansättningskriterier, t.ex. kund, affärsdatum eller ekonomiska dimensioner. Notera att raderna från en enda transaktion inte delas mellan olika sammansättningstransaktioner. Därför kan antalet rader i en sammansättningstransaktion vara något högre eller lägre baserat på faktorer som antal specifika produkter. |
| Maximalt antal trådar för att validera butikstransaktioner | Fältet definierar det maximala antalet trådar som kan användas för att validera transaktioner. Validering av transaktioner är ett obligatoriskt steg som måste inträffa innan transaktionerna kan hämtas till kontoutdrag. Du måste också definiera en presentkortsprodukt på **Presentkort** på fliken **Bokföring** på sidan **Commerce-parametrar**, även om organisationen inte använder presentkort. |

I följande tabell visas de rekommenderade värdena för parametrarna i föregående tabell. Dessa värden bör testas och skräddarsys efter användningskonfiguration och tillgänglig infrastruktur. Värden som överskrider de rekommenderade värdena kan påverka annan batchbearbetning negativt och bör valideras.

| Parameter | Rekommenderat värde | Detaljer |
|-----------|-------------------|---------|
| Maximalt antal parallella utdragsbokföringar | <p>Ange den här parametern till antalet batchuppgifter som är tillgängliga för batchgruppen som kör jobbet **utdrag**.</p><p>**Allmän regel:** Multiplicera antalet virtuella servrar för programobjektservern (AOS) med antalet batchuppgifter som är tillgängliga per AOS-virtuell server.</p> | Den här parametern kan inte tillämpas när funktionen **Butiksutdrag – Indroppning** är aktiverad. |
| Maximalt antal trådar för orderbehandling per utdrag | Börja på testvärdena vid **4**. Normalt bör värdet inte överstiga **8**. | Den här parametern definierar antalet trådar som används för att skapa och bokföra försäljningsorder. Det representerar antalet trådar som är tillgängliga för bokföring per utdrag. |
| Max antal transaktionsrader som ingår i en sammansättning | Börja på testvärdena vid **1000**. Beroende på konfiguration av Commerce headquarters kan mindre beställningar vara mer fördelaktiga för prestanda. | Den här parametern definierar hur många rader som tas med i varje försäljningsorder när utdraget bokförs. När detta nummer har nåtts delas raderna upp i en ny order. Antalet försäljningsrader blir inte exakt lika med antalet som du anger, eftersom uppdelningen sker på försäljningsordernivå. Ändå kommer antalet att vara nära det nummer som är inställt. Den här parametern används för att generera försäljningsorder för butikstransaktioner som inte har en namngiven kund. |
| Maximalt antal trådar för att validera butikstransaktioner | Vi rekommenderar att du konfigurerar den här parametern på **4** och att du bara ökar den om du inte uppnår godtagbara prestanda. Antalet trådar som används i den här processen får inte överstiga antalet processorer som är tillgängliga i batchservern. Om antalet trådar är för högt kan andra batchbearbetningar påverkas. | Den här parametern styr antalet transaktioner som kan valideras samtidigt för en given butik. |

> [!NOTE]
> Alla inställningar och parametrar som relateras till bokföring av utdrag och som definieras i butiker och på sidan **Commerce-parametrar**, gäller för den förbättrade funktionen för bokföring av utdrag.

## <a name="invoice-parameters"></a>Fakturaparametrar

Följande tabell listar parametrar för fakturaparametrar som är specifika för bokföringen av ekonomiska och fysiska transaktioner.

| Parameter | Beskrivning |
|-----------|-------------|
| Journalnamn | Namnet på betalningsjournalen som används när kundbetalningsjournaler för försäljningsorderbetalningar skapas. Den här inställningen gäller för alla orderbetalningar som bokförs för försäljningsplatsen (POS), kundtjänst och order för näthandel. |
| Kontonamn | Namn på betalningskonto. |
| Prioritera dimensioner från betalningsmetod | När den flaggan är aktiverad har betalningsjournalen prioriterade dimensioner från betalningsmetoden i stället för dimensioner från butiken. |
| Beräkningsbeteende för moms | Den här parametern anger hur beteendet ska visas när försäljningsorder som skapas vid utdragsbokföring faktureras:<ul><li>**Beräkna om** – Beräkna moms igen.</li><li> **Beräkna inte om** – Använd momsbeloppen som beräknas i kassan.</li></ul> |
| Journalnamn | Journalnamnet som används när en kundbetalningsjournal för återbetalningar skapas. Den här inställningen gäller för alla orderbetalningar som bokförs för kassa, kundtjänst och order för näthandel. |

## <a name="statement-parameters"></a>Utdragsparametrar

Följande tabell listar parametrar för utdragsparametrar som är specifika för bokföringen av ekonomiska och fysiska transaktioner.

| Parameter | Beskrivning |
|-----------|-------------|
| Reservera lager vid beräkning | När den här parametern är aktiverad reserverar utdragsberäkningen tillfälligt lager tills utdraget bokförs. Den här parametern inaktiveras som standard för att förbättra prestandan för utdragsberäkningar. Uppdaterad lagerinformation kan beräknas med hjälp av batchjobbet **Bokför lager**. Observera att batchjobbet **Bokför** lager inte längre används när [indroppningsbaserad](trickle-feed.md) order skapas för butikslagertransaktioner aktiveras. |
| Inaktivera att inventering krävs | Den här flaggan inaktiverar inventering vid bokföring i Commerce headquarters. |
| Räkna om ekonomisk dimension vid fel | När den här parametern är aktiverad kan finansiella dimensioner omvärderas för efterföljande bokföringar av utdrag när bokföringen misslyckas. |
| Använd ekonomiska dimensioner från returbutiken | När den här parametern är aktiverad kan kopplade returförsäljningsorder skapas där butikens ekonomiska dimensioner används i stället för de ekonomiska dimensionerna från den ursprungliga transaktionen. |
| Ta bort länk för returer | När den här parametern är aktiverad kan utdraget skapa returer av icke-bokförd försäljning som blinda returer. Denna parameter är inaktiverad som standard och vi rekommenderar att du håller den inaktiverad. |
| Inaktivera bokföring av avrundningsdifferens | Denna parameter inaktiverar bokföring av avrundningsdifferens mellan transaktionsbetalning och bruttobelopp under bearbetning av betalningar. |
| Kvitta kundinsättningar automatiskt | När den här parametern är aktiverad avräknas kundinsättningar som bokförs under bokföring av kontoutdrag mot öppna kundtransaktioner. |
| Aktivera och använd kassahanteringsavstämning från kassa | När den här parametern är aktiverad görs avstämning av kassahantering i kassan och värdena överförs till bokslutsbokföring för att skapa utdragsrader. |
| Detaljnivå för redovisningsverifikation | Den här parametern definierar hur många detaljer som tas med i redovisningsverifikationen för valda transaktioner som har sitt ursprung i kassan. Transaktionstyper inkluderar inkomst, utgifter och rabatter. För rabatter gäller endast den här parametern när kontonumret för en periodisk rabatt och kontonumret för en vanlig rabatt inte är detsamma. Om inte detaljer krävs, är **sammanfattning** det rekommenderade värdet för dessa bokföringar. När bokföring på sammanfattningsnivå definieras kommer **TransactionDiscountTrans.RecID** inte att fyllas i. I versionsversionen Commerce 10.0.27 har den här flaggan bytt namn och flyttades. Den har tidigare namngetts **detaljnivå** och var i avsnittet **Lageruppdatering**. |
