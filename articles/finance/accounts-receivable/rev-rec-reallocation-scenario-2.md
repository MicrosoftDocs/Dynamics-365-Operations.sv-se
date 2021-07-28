---
title: Omallokering vid intäktsredovisning – scenario 2
description: Det här avsnittet innehåller en genomgång av ett omallokeringsscenario där två försäljningsorder registreras, och sedan lägger kunden till en artikel i kontraktet efter att den första försäljningsordern har fakturerats. När en ny artikel läggs till i ett kontrakt kan den läggas till i en ny försäljningsorder eller i den befintliga försäljningsordern.
author: kweekley
ms.date: 12/21/2020
ms.topic: index-page
ms.prod: ''
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-12-21
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 53e5173accb83150b2c76d93b971d8908aba2a3d
ms.sourcegitcommit: c08a9d19eed1df03f32442ddb65a2adf1473d3b6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/06/2021
ms.locfileid: "6356207"
---
# <a name="revenue-recognition-reallocation--scenario-2"></a>Omallokering vid intäktsredovisning – scenario 2

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller en genomgång av ett omallokeringsscenario där två försäljningsorder registreras, och sedan lägger kunden till en artikel i kontraktet efter att den första försäljningsordern har fakturerats. När en ny artikel läggs till i ett kontrakt kan den läggas till i en ny försäljningsorder eller i den befintliga försäljningsordern.

För det här scenariot ska alternativet **Bokför fakturakorrigeringar i Kundreskontra** anges till **Nej** på fliken **Intäktsredovisning** på sidan **Redovisningsparametrar** (**Intäktsredovisning \> Inställningar \> Redovisningsparametrar**).

[![Alternativet Bokför fakturakorrigeringar i Kundreskontra inställt på Nej.](./media/12_rev-rec-scenarios.png)](./media/12_rev-rec-scenarios.png)

En försäljningsorder skapas för kunden US\_SI\_0003. Kunden köper installationstjänster (artikelnummer S0001) och en supportplan (artikelnummer S0008) för en bärbar dator, men har ännu inte valt den bärbara datorn. Intäkten för installationstjänster periodiseras till det datum då den bärbara datorn köps in. Intäkterna för supportplanen kommer att periodiseras och redovisas under 12 månader, enligt definitionen av datumintervallet i kontraktet.

[![Försäljningsorderrader för installationstjänsterna och supportplanen.](./media/13_rev-rec-scenarios.png)](./media/13_rev-rec-scenarios.png)

Försäljningsordern bekräftas. Eftersom båda artiklarna har ställts in för allokering av intäktspris, beräknas intäktspriset när försäljningsordern bekräftas. Du kan visa den intäkt som kommer att redovisas på sidan **Allokering av intäktspris** (gå till sidan **Försäljningsorder**, åtgärdsrutan, fliken **Hantera**, gruppen **Intäktsredovisning** och välj **Allokering av intäktspris**). Intäkterna för installationstjänsterna kommer att bokföras på kontot Periodiserad intäkt med beloppet $250,00. Intäkterna för supportplanen kommer också att bokföras på kontot Periodiserad intäkt med beloppet $150,00. Summan av intäktspriserna måste vara lika med summan av raderna som skapats för att samla in allokeringen av intäktspris ($400,00).

[![Sidan Allokering av intäktspris.](./media/14_rev-rec-scenarios.png)](./media/14_rev-rec-scenarios.png)

Försäljningsordern är helt fakturerad. I bilden nedan visas den redovisningstransaktion som bokförs för fakturan.

[![Redovisningstransaktion för den helt fakturerade försäljningsordern.](./media/15_rev-rec-scenarios.png)](./media/15_rev-rec-scenarios.png)

Intäktsredovisningsplanen skapas också, men ingen av intäkterna redovisas än.

[![Sidan Intäktsredovisningsplan.](./media/16_rev-rec-scenarios.png)](./media/16_rev-rec-scenarios.png)

Några dagar senare väljer kunden en bärbar dator. En andra försäljningsorder registreras för kunden.

[![Försäljningsorderrad för den bärbara datorn.](./media/17_rev-rec-scenarios.png)](./media/17_rev-rec-scenarios.png)

Den andra försäljningsordern bekräftas. Eftersom den här försäljningsordern bara innehåller en rad görs ingen allokering av intäktspris när försäljningsordern bekräftas. Allokeringen av intäktspris sker bara om det finns två eller flera unika artiklar, och om dessa artiklar ställts in för allokering av intäktspris.

Om den här nya försäljningsordern är den enda ändringen av kundens kontrakt kan omallokeringsprocessen nu köras. I en av dessa två försäljningsorder väljer du **Allokera om pris med nya orderrader** för att öppna sidan **Allokera om pris med nya orderrader**. Alternativt går du till **Intäktsredovisning \> Periodiska uppgifter \> Allokera om pris med nya orderrader**. Markera dessa två försäljningsorder och motsvarande försäljningsorderrader och välj sedan **Uppdatera omallokering**. Kolumnen **Omallokerat belopp** visar det nya intäktspriset för varje försäljningsorderrad.

[![Nya intäktspriser på sidan Allokera om pris med nya orderrader.](./media/18_rev-rec-scenarios.png)](./media/18_rev-rec-scenarios.png)

Sedan väljer du **Förväntad verifikation** för att visa redovisningsposterna som bara kommer att bokföras i redovisningen. Eftersom alternativet **Bokför fakturakorrigeringar i Kundreskontra** ställts in på **Nej** på sidan **Redovisningsparametrar** ändras inget i Kundreskontra när omallokeringen bearbetas.

[![Redovisningstransaktioner på sidan Förväntad verifikation.](./media/19_rev-rec-scenarios.png)](./media/19_rev-rec-scenarios.png)

På sidan **Förväntad verifikation** återför de sista tre raderna den ursprungliga redovisningstransaktionen från den bokförda fakturan. De första fyra raderna består av den nya redovisningstransaktionen som bokförs för fakturan. Det är viktigt att du förstår att en ny faktura inte visas för kunden. Efter omallokeringen är kunden fortfarande skyldig $426,00, vilket är det belopp som måste bokföras på Kundreskontra i den nya redovisningstransaktionen. Den motbokade momsen och den periodiserade intäkten är lika med $188,69 + $314,48 + $26,00 = $529,17. Beloppet för periodiserad intäkt har ändrats på grund av omallokeringen. Skillnaden på $103,17 bokförs på kontot Delvis clearing av fakturaintäkt. Det här saldot tas bort när fakturan bokförs för den andra försäljningsordern som inkluderades i omallokeringen.

När du vill slutföra omallokeringen väljer du **Bearbeta**. Du uppmanas att ange ett bokföringsdatum, även om inget är bokfört. När omallokeringen är klar kommer sidan **Allokering av intäktspris** för varje försäljningsorder visa prisallokeringen för alla artiklar på båda försäljningsorder. Med andra ord kommer sidan **Allokering av intäktspris** för varje försäljningsorder att innehålla en artikel som inte finns på den försäljningsordern, eftersom den ingår i samma kontrakt men finns på en annan försäljningsorder.

> [!TIP]
> Om du vill förklara varför dessa ytterligare artiklar visas kan du lägga till andra kolumner i rutnätet, till exempel **Omallokerings-ID** och **Försäljningsorder**.
> 
> [![Ytterligare kolumner på sidan Allokering av intäktspris.](./media/20_rev-rec-scenarios.png)](./media/20_rev-rec-scenarios.png)

I försäljningsorder 00036 uppdaterades också intäktsredovisningsplanen, baserat på det nya omallokerade intäktspriset. Öppna sidan **Intäktsredovisningsplan** från den här försäljningsordern. Tidigare fanns det 13 rader för artikel S0008 (en 12-månadersplan tilldelades den här artikeln). Det finns nu 39 rader: de 13 ursprungliga planraderna, 13 planrader för återföring och 13 rader som baseras på det nya intäktspriset.

[![Den uppdaterade sidan Intäktsredovisningsplan med 39 rader för artikel S0008.](./media/21_rev-rec-scenarios.png)](./media/21_rev-rec-scenarios.png)

Det fanns även tidigare två rader för artikel S0001, men nu finns det sex.

[![Den uppdaterade sidan Intäktsredovisningsplan med sex rader för artikel S0001.](./media/22_rev-rec-scenarios.png)](./media/22_rev-rec-scenarios.png)

När du väljer **Verifikation** i försäljningsorder 000036 visas den ursprungliga redovisningsposten i fakturajournalen. Om du vill visa återföringsposten och den nya redovisningsposten från försäljningsordern väljer du **Intäktsjusteringar** i åtgärdsrutan och sedan **Verifikation**.

[![Försäljningsorder 000036.](./media/23_rev-rec-scenarios.png)](./media/23_rev-rec-scenarios.png)

Öppna sedan sidan **Alla kunder** (**Kundreskontra \> Kunder \> Alla kunder**), välj kunden **US\_SI\_0003** och välj sedan **Transaktioner**. Den öppna fakturan från försäljningsorder 000036 visas. Om du väljer verifikationen kommer den ursprungliga redovisningsposten att visas, inte den nya redovisningsposten från omallokeringen. Återföringsposten och den nya redovisningsposten kan inte visas från Kundreskontra.

Den andra försäljningsordern har nu fakturerats. Den totala fakturan som visas för kunden är på $1 099,00 + $71,44 tax = $1 170,44. I bilden nedan visas den redovisningstransaktion som bokförs.

[![Sidan Verifikationstransaktion med redovisningsposten som bokförs.](./media/24_rev-rec-scenarios.png)](./media/24_rev-rec-scenarios.png)

Eftersom summan av intäkten och försäljningen är större än $1 170,44, bokförs skillnaden -$130,17. Detta belopp rensar saldot från kontot Delvis clearing av fakturaintäkt. Det saldot bokförs i den nya redovisningsposten efter omallokeringen.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]