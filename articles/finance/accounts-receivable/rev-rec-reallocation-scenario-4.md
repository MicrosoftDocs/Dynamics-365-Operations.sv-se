---
title: Omallokering vid intäktsredovisning – scenario 4
description: Den här artikeln innehåller en genomgång av ett omallokeringsscenario där en rad tas bort från en befintlig, delvis fakturerad försäljningsorder. Det här scenariot ger samma resultat, oavsett om raden tas bort från försäljningsordern eller anges till annullerad status.
author: kweekley
ms.date: 12/21/2020
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: kfend
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-12-21
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 06e6322ff55259b5c59d570b73199591ab46c767
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8891678"
---
# <a name="revenue-recognition-reallocation--scenario-4"></a>Omallokering vid intäktsredovisning – scenario 4

[!include [banner](../includes/banner.md)]

Den här artikeln innehåller en genomgång av ett omallokeringsscenario där en rad tas bort från en befintlig, delvis fakturerad försäljningsorder. Det här scenariot ger samma resultat, oavsett om raden tas bort från försäljningsordern eller anges till annullerad status.

För det här scenariot ska alternativet **Bokför fakturakorrigeringar i Kundreskontra** anges till **Nej** på fliken **Intäktsredovisning** på sidan **Redovisningsparametrar** (**Intäktsredovisning \> Inställningar \> Redovisningsparametrar**).

[![Alternativet Bokför fakturakorrigeringar i Kundreskontra inställt på Nej.](./media/37_rev-rec-scenarios.png)](./media/37_rev-rec-scenarios.png)

En försäljningsorder skapas för kunden US\_SI\_0003. Kunden köper en bärbar dator (artikelnummer S0012), installationstjänster (artikelnummer S0001) och en supportplan för den bärbara datorn (artikelnummer S0008, "Teknisk service"). Intäkterna för den bärbara datorn och installationstjänster redovisas omedelbart. Intäkterna för supportplanen kommer att periodiseras och redovisas under 12 månader, enligt definitionen av datumintervallet i kontraktet.

[![Försäljningsorderrader för den bärbara datorn, installationstjänsterna och supportplanen.](./media/38_rev-rec-scenarios.png)](./media/38_rev-rec-scenarios.png)

Försäljningsordern bekräftas. Eftersom alla tre artiklarna har ställts in för allokering av intäktspris, beräknas intäktspriset när försäljningsordern bekräftas. Du kan visa den intäkt som kommer att redovisas på sidan **Allokering av intäktspris** (gå till sidan **Försäljningsorder**, åtgärdsrutan, fliken **Hantera**, gruppen **Intäktsredovisning** och välj **Allokering av intäktspris**). Intäkterna för den bärbara datorn kommer att bokföras på kontot Intäkt med beloppet $995,84. Intäkterna för installationstjänsterna kommer också att bokföras på kontot Intäkt med beloppet $314,47. Intäkterna för supportplanen kommer att bokföras på kontot Periodiserad intäkt med beloppet $188,69. Summan av intäktspriserna måste vara lika med summan av raderna som skapats för att samla in allokeringen av intäktspris ($1 499,00).

[![Sidan Allokering av intäktspris.](./media/39_rev-rec-scenarios.png)](./media/39_rev-rec-scenarios.png)

Kunden faktureras för den bärbara datorn och supportplanen, men inte för installationstjänsterna. I bilden nedan visas den redovisningstransaktion som bokförs för fakturan.

[![Redovisningstransaktion för den fakturerade försäljningsordern.](./media/40_rev-rec-scenarios.png)](./media/40_rev-rec-scenarios.png)

Redovisningsposterna bokför $1 276,94 på Kundreskontra. Men eftersom den här fakturan är en delfaktura, är intäkten eller periodiserad intäkt plus moms inte lika med beloppet på Kundreskontra. Skillnaden på -$14,47 bokförs på kontot Delvis clearing av fakturaintäkt.

Intäktsredovisningsplanen skapas också.

[![Intäktsredovisningsplan för delfakturan.](./media/41_rev-rec-scenarios.png)](./media/41_rev-rec-scenarios.png)

Senare bestämmer sig kunden för att inte köpa installationstjänster. Därför tas den raden bort från försäljningsordern. Observera att försäljningsordern inte kan bekräftas igen, eftersom endast fakturerade rader finns kvar på försäljningsordern.

[![Försäljningsorder efter raden för installationstjänsterna tagits bort.](./media/42_rev-rec-scenarios.png)](./media/42_rev-rec-scenarios.png)

Även om försäljningsordern inte kan bekräftas kan den omallokeras. I försäljningsordern väljer du **Allokera om pris med nya orderrader** för att öppna sidan **Allokera om pris med nya orderrader**. Markera de återstående försäljningsorderraderna och välj sedan **Uppdatera omallokering**. Kolumnen **Omallokerat belopp** visar det nya intäktspriset för varje återstående försäljningsorderrad.

[![Nya intäktspriser på sidan Allokera om pris med nya orderrader.](./media/43_rev-rec-scenarios.png)](./media/43_rev-rec-scenarios.png)

Därefter väljer du **Förväntad verifikation** för att visa redovisningstransaktionerna.

[![Redovisningstransaktioner på sidan Förväntad verifikation.](./media/44_rev-rec-scenarios.png)](./media/44_rev-rec-scenarios.png)

På sidan **Förväntad verifikation** återför de sista fem raderna den ursprungliga redovisningstransaktionen från den bokförda fakturan. De första fyra raderna är de nya redovisningstransaktionerna som bokförs för fakturan. Det är viktigt att du förstår att en ny faktura inte visas för kunden. Efter omallokeringen är kunden fortfarande skyldig $1 276,94, vilket är det belopp som måste bokföras på Kundreskontra i den nya redovisningstransaktionen. Den nya intäkten eller den periodiserade intäkten är lika med $1 276,94. Därför behöver du inte bokföra på kontot Delvis clearing av fakturaintäkt.

När du vill slutföra omallokeringen väljer du **Bearbeta**. Ett bokföringsdatum anges. När omallokeringen har slutförts visar sidan **Allokering av intäktspris** omallokeringen av priset för de två återstående artiklarna.

[![Omallokering av pris för de återstående artiklarna på sidan Allokering av intäktspris.](./media/45_rev-rec-scenarios.png)](./media/45_rev-rec-scenarios.png)

Intäktsredovisningsplanen uppdaterades också, baserat på det nya omallokerade intäktspriset. Öppna sidan **Intäktsredovisningsplan** från försäljningsordern. Tidigare fanns det 13 rader för artikel S0008 (en 12-månadersplan tilldelades den här artikeln). Det finns nu 39 rader: de 13 ursprungliga planraderna, 13 planrader för återföring och 13 rader som baseras på det nya intäktspriset.

[![Den uppdaterade sidan Intäktsredovisningsplan med 39 rader för artikel S0008.](./media/46_rev-rec-scenarios.png)](./media/46_rev-rec-scenarios.png)

När du väljer **Verifikation** visas den ursprungliga redovisningsposten i fakturajournalen. Om du vill visa återföringsposten och den nya redovisningsposten från försäljningsordern väljer du **Intäktsjusteringar** i åtgärdsrutan och sedan **Verifikation**.

Öppna sedan sidan **Alla kunder** (**Kundreskontra \> Kunder \> Alla kunder**), välj kunden **US\_SI\_0003** och välj sedan **Transaktioner**. På sidan **Kundtransaktioner** visas bara den ursprungliga fakturan (000008), tillsammans med den ursprungliga redovisningsposten. Eftersom alternativet **Bokför fakturakorrigeringar i Kundreskontra** ställts in på **Nej** på sidan **Redovisningsparametrar** uppdateras bara redovisningen. Därför visas inte återförande och uppdaterade redovisningsposter. Observera att de intäktsjusteringstransaktioner som har skapats [i scenario 3](rev-rec-reallocation-scenario-3.md) visas.

[![Ursprunglig redovisningspost på sidan Kundtransaktioner.](./media/47_rev-rec-scenarios.png)](./media/47_rev-rec-scenarios.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
