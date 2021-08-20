---
title: Intäktsredovisning på försäljningsorder
description: I det här avsnittet beskrivs de grundläggande funktionerna för intäktsredovisning på försäljningsorder och fakturor. Intäktsredovisning kan användas för försäljningsorder och motsvarande faktura som skapas från försäljningsordern.
author: kweekley
ms.date: 08/24/2018
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2018-08-30
ms.dyn365.ops.version: 8.0.4
ms.openlocfilehash: 1807e00f5f93bf9359da710af7c9a1f6de652e7ae78cf9604351af969b057b11
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6752235"
---
# <a name="revenue-recognition-on-sales-orders"></a>Intäktsredovisning på försäljningsorder

[!include [banner](../includes/banner.md)]

> [!NOTE]
> Intäktsredovisningsfunktionen kan inte aktiveras via funktionshantering. För närvarande måste du använda konfigurationsnycklar för att aktivera den.

I det här avsnittet beskrivs de grundläggande funktionerna för intäktsredovisning på försäljningsorder och fakturor. Intäktsredovisning kan användas för en försäljningsorder och motsvarande faktura som skapas från försäljningsordern. Försäljningsordern kan även skapas via ett tids- och materialprojekt.

> [!NOTE]
> I illustrationerna i det här avsnittet har kolumner dolts eller lagts till i rutnäten så att begreppen blir lättare att förstå. Därför kan sidorna och data i illustrationerna skilja sig från vad du ser i produkten.

## <a name="enter-a-sales-order"></a>Registrera en försäljningsorder

Följande försäljningsorder registreras och omfattar tre artiklar som har konfigurerats för intäktsredovisning.

[![Registrera en försäljningsorder.](./media/revenue-recognition-so-basic-sales-order-header.png)](./media/revenue-recognition-so-basic-sales-order-header.png)

Det finns två begrepp du bör känna till när det gäller intäktsredovisning:

- **Fastställa intäktspriset.** Intäktspriset beräknas baserat på inställningarna för de frisläppta produkterna. Intäktspriset visas aldrig för kunden utan används bara för redovisning av försäljningsorderfakturan. På försäljningsorderraderna och i dokumenten som skrivs ut som en del av försäljningen visas enhets- eller listpriset även fortsättningsvis.
- **Fastställa när intäktsredovisning ska ske.** Intäktsplaner används för att bestämma när intäkten ska redovisas.

    I det här exemplet tilldelas den första artikeln, S0001, till intäktsplanen **1O** (en förekomst). Den här raden representerar ett scenario med milstolpar, där intäkten redovisas efter att installationen utförts i framtiden. Därför kommer intäkten att skjutas upp tills installationen är slutförd.

    Den andra artikeln, S0008, är en serviceartikel som konfigureras som en kontraktsartikel. Enligt kontraktet får kunden teknisk service under 12 månader. Därför tilldelas intäktsplanen **12M** som standard till produkten. Eftersom artikeln är en kontraktsartikel måste kontraktets start- och slutdatum definieras. Kontraktets start- och slutdatum finns som standard på fliken Artikelinformation – Inställningar. I intäktsplanen definieras inställningen för **12M** så att kontraktsvillkoren fylls i automatiskt på det sätt som visas i bilden nedan.

    [![Intäktsplaner.](./media/revenue-recognition-so-basic-revenue-schedules.png)](./media/revenue-recognition-so-basic-revenue-schedules.png)

    Den tredje artikeln, S0012, är maskinvara och ingen intäktsplan tilldelas som standard. Intäkten för maskinvaran redovisas så fort artikeln faktureras.

## <a name="confirm-the-sales-order"></a>Bekräfta försäljningsordern

Om du vill visa mer information om intäktspris och intäktsplan använder du knapparna i gruppen **Intäktsredovisning** på fliken **Hantera** i åtgärdsrutan för försäljningsordern. Eftersom försäljningsordern ännu inte har bekräftats, är de knappar som används för intäktsredovisning inte tillgängliga. Dessa knappar blir tillgängliga allteftersom, då försäljningsordern bearbetas i olika faser som leder fram till uppfyllelse.

[![Försäljningsorderhuvud.](./media/revenue-recognition-so-basic-sales-order-header-02.png)](./media/revenue-recognition-so-basic-sales-order-header-02.png)

De första tre knapparna ger information om intäktspriset för artiklarna i försäljningsorderinställningarna för intäktsredovisning.

- **Allokering av intäktspris** – Den här knappen blir tillgänglig när försäljningsordern har bekräftats eller när fakturan har bokförts. Både försäljningsorderbekräftelse och fakturabokföring beräknar intäkten till att identifiera priset som ska redovisas eller skjutas upp i redovisningsposten. Beroende på inställningarna kan det beräknade intäktspriset skilja sig från det enhetspris som visas för kunden.
- **Allokera om pris med nya orderrader** – Den här knappen blir tillgänglig när försäljningsordern har bekräftats eller när fakturan har bokförts. Omallokeringsprocessen används för att räkna om intäkten som måste redovisas efter att en ny rad har lagts till på den aktuella försäljningsordern, efter att den har fakturerats, eller på en ny försäljningsorder. I båda fallen innebär de nya artiklarna att kontraktet ändras. Därför måste intäktspriset allokeras om.
- **Uppdatera allokering av intäktspris** – Den här knappen blir tillgänglig när försäljningsordern bekräftas, men inte när försäljningsordern faktureras. Uppdateringen används för att köra allokeringen av intäktspriset på nytt, utan att försäljningsordern måste bekräftas. När försäljningsordern har fakturerats går det inte att räkna om intäktspriset.

De två sista knapparna ger information om intäktsplanen för de artiklar på försäljningsordern som har en intäktsplan.

- **Förväntad intäktsredovisningsplan** – Den här knappen blir tillgänglig när försäljningsordern bekräftas, men inte när försäljningsordern faktureras. Den öppnar en sida som visar den förväntade intäktsplanen. Den slutliga planen kan ändras eftersom den förväntade planen använder det begärda transportdatumet, medan den slutliga planen använder det faktiska transportdatumet.
- **Intäktsredovisningsplan** – Den här knappen blir tillgänglig när försäljningsordern har fakturerats. Det slutliga intäktsredovisningsplanen skapas inte när bekräftelsen sker eller när en följesedel skapas. Den skapas bara när försäljningsordern faktureras.

I följande exempel utfördes allokeringen av intäktspriset när försäljningsordern bekräftades. Även om intäktspriserna allokeras på olika sätt måste det totala beloppet i fältet **Intäkt att redovisa** fortfarande vara lika med summan av de försäljningsorderrader som faktureras kunden. Summan av försäljningsorderraderna, exklusive moms, är till exempel 1 499 USD. Därför måste summan av värdena för **Intäkt att redovisa** också vara 1 499 USD.

[![Allokering av intäktspris.](./media/revenue-recognition-so-basic-revenue-price-allocation.png)](./media/revenue-recognition-so-basic-revenue-price-allocation.png)

Det förväntade intäktsredovisningsplanen skapas också. I intäktsplanen används värdet för **Intäkt att redovisa** som summan som ska skjutas upp. Artikel S0001 skjuter upp 321,21 USD i stället för 300 USD och artikel S0008 skjuter upp 160,61 USD i stället för 100 USD. Artikel S0012 visas inte i den förväntade planen eftersom intäkten inte skjuts upp. När bokföringen sker kommer artikel S0012 att bokföra 1 017,18 USD direkt på huvudbokskontot för intäkten.

[![Förväntad intäktsredovisningsplan.](./media/revenue-recognition-so-basic-expected-rev-rec-schedule.png)](./media/revenue-recognition-so-basic-expected-rev-rec-schedule.png)

## <a name="create-the-packing-slip"></a>Skapa följesedeln

Nu kan följesedeln skapas för försäljningsordern. Ingen intäkt redovisas när följesedeln bokförs. Om försäljningsordern inte bekräftas, sker ingen beräkning av intäktspriset när följesedeln bokförs. Den förväntade eller slutliga intäktsredovisningsplanen skapas heller inte. Om artikelmodellgruppen har ställts in för att skjuta upp intäkt på följesedeln, sker bokföringen även fortsättningsvis genom att använda huvudbokskontona för bokföringsprofilerna, inte de nya kontona för uppskjuten intäkt som används för fakturabokföringen.

## <a name="create-the-invoice"></a>Skapa fakturan

Det sista steget är att fakturera försäljningsordern. Om du tittar på fakturans verifikation ser du att intäkterna för artiklarna S0001 och S0008 har skjutits upp (321,21 + 160,61 = 481,82 USD) och resten av beloppet för artikel S0012 har bokförts till intäkten (1 017,18). Dessa värden uppgår till 1 499 USD, vilket motsvarar summan av försäljningsorderraderna.

[![Verifikationstransaktioner.](./media/revenue-recognition-so-voucher-transactions.png)](./media/revenue-recognition-so-voucher-transactions.png)

När fakturan har skapats blir knapparna **Allokering av intäktspris**, **Allokera om pris med nya orderrader** och **Intäktsredovisningsplan** för intäktsredovisning tillgängliga, men knapparna **Uppdatera allokering av intäktspris** och **Förväntad intäktsredovisningsplan** är inte tillgängliga.

[![Tillgänglighet för knappen Tillgänglig intäktsredovisning.](./media/revenue-recognition-so-basic-after-invoice-buttons.png)](./media/revenue-recognition-so-basic-after-invoice-buttons.png)

Knappen **Allokering av intäktspris** är fortfarande tillgänglig så att du kan visa beräkningen av intäktspriset. Om inget ändras på försäljningsordern efter att den bekräftats, kommer det beräknade beloppet i fältet **Intäkt att redovisa** inte att ändras när fakturan bokförs.

Den förväntade intäktsredovisningsplanen tas bort och ersätts med den slutliga intäktsredovisningsplanen. Intäktsplansdetaljerna underhålls för varje försäljningsorderrad och används för att frisläppa den uppskjutna intäkten till faktisk intäkt allteftersom de avtalsenliga skyldigheterna uppfylls.

[![Slutlig intäktsredovisningsplan.](./media/revenue-recognition-so-revenue-recognition-schedule.png)](./media/revenue-recognition-so-revenue-recognition-schedule.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]