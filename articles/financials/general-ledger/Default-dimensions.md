---
title: "Ekonomiska dimensioner och bokföring"
description: "När du planerar och ställer in kontoplanen måste du bestämma hur komponenterna fungerar tillsammans när du bokför ett dokument eller en journal. Dessa komponenter inkluderar kontostrukturer, avancerade regler och balansering och fasta dimensioner. Det här avsnittet beskriver vad varje komponent är och hur komponenterna fungerar tillsammans."
author: aprilolson
manager: AnnBe
ms.date: 08/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LedgerChartofAccounts,DimensionDetails
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 14091
ms.assetid: c64eed1d-df17-448e-8bb6-d94d63b14607
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: a0739304723d19b910388893d08e8c36a1f49d13
ms.openlocfilehash: a0530a569978bafffcdcc63c8d502b9bfa645bc5
ms.contentlocale: sv-se
ms.lasthandoff: 03/26/2018

---

# <a name="financial-dimensions-and-posting"></a>Ekonomiska dimensioner och bokföring 

[!include [banner](../includes/banner.md)]

När du planerar och ställer in kontoplanen måste du bestämma hur komponenterna fungerar tillsammans när du bokför ett dokument eller en journal. Dessa komponenter inkluderar kontostrukturer, avancerade regler och balansering och fasta dimensioner. Det här avsnittet beskriver vad varje komponent är och hur komponenterna fungerar tillsammans.

## <a name="chart-of-accounts-and-financial-dimension-components"></a>Import av kontoplan och ekonomiska dimensionskomponenter

Microsoft Dynamics 365 for Finance and Operations, har ett omfattande och regelbaserad system för att definiera giltiga kombinationer av huvudkonto och ekonomiska dimensionsvärdena. Det här avsnittet innehåller en kort översikt över varje komponent och förklarar var du hittar komponenten.

### <a name="account-structures"></a>Kontostrukturer

En kontostruktur krävs när du ställer in i redovisningen. Du måste definiera aktivera minst en kontostruktur och du måste tilldela den till redovisningen. Kontostrukturen måste ha huvudkontot i den. Du kan ange ordningen för segment som passar bäst för verksamheten. När huvudkontot har definierats kan systemet bestämma kontostrukturen som används. Genom att placera huvudkontot först eller nära framför en struktur, kan du begränsa värdena och även hjälpa systemet tillämpa det senaste kända värdet som standardvärde. Du kan ha upp till 10 ytterligare ekonomiska dimensioner i kontostrukturen. Kontostrukturen definierar vilka dimensionsvärden som är giltiga i kombination med andra värden. Den definierar också om dimensionsvärden måste anges.

### <a name="advanced-rules"></a>Avancerade regler

Avancerade regler är en valfri komponent när du ställer in kontoplanen. Du kan lägga till hur många avancerade regler som helst till en kontostruktur. Avancerade regler används ofta för att hantera scenarier där ytterligare ekonomiska dimensioner måste följas när vissa villkor uppfylls. Om du använder ett utgiftskonto för resor kan du till exempel vilja spåra ytterligare information, t.ex. evenemanget som han eller hon reser till. Om det finns flera avancerade regler kan de tillämpas i alfabetisk ordning utifrån namnet på reglerna. Segmenten som en regel lägger till kan endast tillämpas efter segmenten i kontostrukturen.

### <a name="balancing-dimension"></a>Balansera dimension

Du kan som tillval definiera en balanserande ekonomisk dimension. På sidan **redovisning** definierar du den ekonomiska dimension som bör balanseras. När sedan transaktioner har bokförts till den ekonomiska dimensionen kan systemet automatiskt skapa och bokföra transaktionerna så att den ekonomiska dimensionen balanseras.

### <a name="defaultfixed-financial-dimensions-on-the-main-account"></a>Standard/fast ekonomisk dimension för huvudkontot.

Standarddimensioner kommer från olika platser, t.ex. huvudposter (exempelvis kund- eller leverantörsposter), dokument och huvudkontot. Det här avsnittet gäller standarddimensioner för huvudkontot per juridisk person. Du kan ange om ett huvudkonto har ett **inte fast** eller **fast** värde för varje ekonomisk dimension som används i alla kontostrukturer för redovisningen. Om en ekonomisk dimension är **inte fast**, används ett standardvärde, men värdet kan skrivas över. Detta gäller alla standardvärden i systemet, även standardvärden som kommer från huvudposter. Om en ekonomisk dimension är inställt på ett **fast** värde tillämpas alltid det värdet oavsett om den kommer från någon som standardvärde eller om användaren angav det.

## <a name="order-in-which-default-dimensions-are-applied-during-posting"></a>Ordning som standarddimensionerna använder vid bokföring

Användare har ofta frågor om ordningen som olika komponenter körs i. Det är viktigt att du förstår ordningen som standarddimensioner tillämpas i, eftersom detta påverkar den metod som du använder för att ställa in.

> [!NOTE]
> Denna information gäller bara för användning av standarddimensioner i programmet. Om du importerar data med hjälp av Microsoft Excel eller Data Management Framework skiljer sig beteendet.

### <a name="example-1"></a>Exempel 1

**Kontostruktur**

| Huvudkonto            | Affärsenhet           | Avdelning              | Kostnadsställe             |
|-------------------------|-------------------------|-------------------------|-------------------------|
| Alla värden är tillåtna. | Alla värden är tillåtna. | Alla värden är tillåtna. | Alla värden är tillåtna. |

**Huvudkonto**

| Huvudkonto | Namn          | Juridisk person | Avdelning                                 |
|--------------|---------------|--------------|--------------------------------------------|
| 401100       | Produktförsäljning | USMF         | Fast - 022 försäljnings- och marknadsföringsavdelningen |

Följande illustration visar den fasta standarddimension som har angetts för huvudkonto 401100.

[![Ekonomiska standarddimensioner](./media/default-dimensions.png)](./media/default-dimensions.png)

I det här mycket grundläggande exemplet anger vi en allmän journal där avdelningsdimensionen är inställd på att använda standardvärdet **023** (operationer). Vi anger och bokför på ett redovisningskonto. Följande illustration visar den ekonomiska standarddimension i huvudboken.

[![Allmänna journaler](./media/general-journal.png)](./media/general-journal.png)

Standarddimensionen på journalrubrik medför att avdelning 023 använd som standard på försäljningskontoraden. Följande illustration visar allmänna journalraden, där standarddimensionsvärdet **023** från rubriken används.

[![Bokföringsorder](./media/journal-voucher.png)](./media/journal-voucher.png)

När raden bokförs används fast dimension och raden bokförs till avdelning 022. Följande illustration visar bokförda verifikationer där fast dimension används för försäljningskontot.

[![Verifikationstransaktioner](./media/voucher-transactions.png)](./media/voucher-transactions.png)

### <a name="example-2"></a>Exempel 2

Det här exemplet använder samma inställningar som i det första exemplet. Men vi lägger ytterligare en andra komponent och använder avdelningsdimensionen som balanserande dimension. I följande illustration anges **avdelning** som den balanserande ekonomiska dimensionen för USMF-redovisningen.

[![Huvudbok](./media/ledger.png)](./media/ledger.png)

Om samma konfiguration av journalrubrik används och samma transkation bokförs används den fasta dimension först. Sedan används mottransaktionen för att garantera att varje avdelning har en balanserad transaktion. Följande illustration visar verifikationstransaktioner med mottransaktionen efter att den fasta dimensionen används.

[![Verifikationstransaktioner](./media/voucher-transactions2.png)](./media/voucher-transactions2.png)

### <a name="example-3"></a>Exempel 3

I det här exemplet lägger vi till en avancerad regel. Den avancerade regeln anger att om försäljningskontot 401100 och avdelning 022 (försäljning och marknadsföring) används, bör systemet spåra ytterligare ett segment med namnet Kund.

Det här exemplet är viktigt på grund av ordern. Kontostrukturen bestäms efter att huvudkontot har angetts. Om du refererar till kontostrukturens inställningar, kan systemet bestämma att huvudkonto, affärsenhet, avdelning och kostnadsställe är relevanta. Nu har den avancerade regeln inte utlösts, eftersom fasta dimensioner inte används förrän standarddimensioner använts för journalverifikationen vid bokföring. I följande illustration är inte kundsegmentet närvarande eftersom kriterierna för avancerad regel inte har uppfyllts.

[![Redovisningskonto](./media/drop-down.png)](./media/drop-down.png)

Bokföringen kommer inte att lyckas eftersom den fasta dimensionen användes i slutet av processen. Dimensionsvalidering anger att kundsegmentet krävs om huvudkontot är 401100 och avdelningen 022. Bokföring kan inte inträffa på grund av valideringsfelet. Följande bild visar ett meddelande som visas när dimensionsvalidering bestämmer att kunden är ett segment som krävs.

[![Meddelandeinformation](./media/message.png)](./media/message.png)

I det här exemplet måste du skriva över standardvärdet så att den avancerade regeln utlöses och du kan ange kundsegmentet. Den här lösningen är inte alltid möjligt och vissa användare är inte medvetna om bokföringsreglerna. Därför är det viktigt att du förstår den ordning som standarddimensioner används i när du ställer in kontoplanen.

För att uppnå vad du vill i det här exemplet måste ändra konfigurationen på flera olika sätt. Exempelvis kan du skapa en ny kontostruktur för försäljningskonton och inkludera kundsegmentet i strukturen. Du kan också lägga till fler rader i en befintlig kontostruktur och ange huvudkontot och giltiga avdelningsvärden. Sedan i ytterligare kundstrukturen kan det vara användbart att ha en separat kontostruktur för försäljningskonton där kundsegmentet förekommer.

## <a name="additional-resources"></a>Ytterligare resurser 

Några av följande resurser hänvisar till en tidigare version av Finance and Operations. En stor del av informationen om användning av standarddimensioner och många av begreppen är identiska i den tidigare versionen och referenserna är giltiga.

[Balanserade journaler för internredovisning](example-balanced-journals-interunit-accounting.md)

[Planera kontoplanen](plan-chart-of-accounts.md) 

[Planera din kontoplan i AX 2012 blogg](https://blogs.msdn.microsoft.com/axsa/2014/06/12/planning-your-chart-of-accounts-in-ax-2012-part-1-of-7/) – den här länken leder till del 1 av 7.

[Dimension som används som standard i redovisningsfördelningar](https://blogs.msdn.microsoft.com/ax_gfm_framework_team_blog/2013/12/16/dimension-defaulting-in-accounting-distributions-part-1-introduction/)

[Standardvärden i dimensionsramverket](https://blogs.msdn.microsoft.com/ax_gfm_framework_team_blog/2014/09/)

