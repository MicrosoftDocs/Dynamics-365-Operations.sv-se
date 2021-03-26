---
title: Omallokering vid intäktsredovisning – scenario 3
description: Det här avsnittet innehåller en genomgång av ett omallokeringsscenario där en ny rad läggs till en befintlig, fakturerad försäljningsorder. När en ny artikel läggs till i ett kontrakt kan den läggas till i en ny försäljningsorder eller i den befintliga försäljningsordern.
author: kweekley
manager: aolson
ms.date: 12/21/2020
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: Customer
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: kweekley
ms.search.validFrom: 2020-12-21
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: ca61a64199d9a61d0ddaa95c49e847e4be35c07b
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5238338"
---
# <a name="revenue-recognition-reallocation--scenario-3"></a>Omallokering vid intäktsredovisning – scenario 3

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller en genomgång av ett omallokeringsscenario där en ny rad läggs till en befintlig, fakturerad försäljningsorder. När en ny artikel läggs till i ett kontrakt kan den läggas till i en ny försäljningsorder eller i den befintliga försäljningsordern. I det här scenariot visas även vad som händer när Kundreskontra uppdateras på grund av omallokeringen.

För det här scenariot ska alternativet **Bokför fakturakorrigeringar i Kundreskontra** anges till **Ja** på fliken **Intäktsredovisning** på sidan **Redovisningsparametrar** (**Intäktsredovisning \> Inställningar \> Redovisningsparametrar**).

[![Alternativet Bokför fakturakorrigeringar i Kundreskontra inställt på Ja](./media/25_rev-rec-scenarios.png)](./media/25_rev-rec-scenarios.png)

En försäljningsorder skapas för kunden US\_SI\_0003. Kunden köper en bärbar dator (artikelnummer S0012) och en supportplan för den (artikelnummer S0008, "Teknisk service"). Intäkterna för den bärbara datorn redovisas omedelbart. Intäkterna för supportplanen kommer att periodiseras och redovisas under 12 månader, enligt definitionen av datumintervallet i kontraktet.

[![Försäljningsorderrader för den bärbara datorn och supportplanen](./media/26_rev-rec-scenarios.png)](./media/26_rev-rec-scenarios.png)

Försäljningsordern bekräftas. Eftersom båda artiklarna har ställts in för allokering av intäktspris, beräknas intäktspriset när försäljningsordern bekräftas. Du kan visa den intäkt som kommer att redovisas på sidan **Allokering av intäktspris** (gå till sidan **Försäljningsorder**, åtgärdsfönstret, fliken **Hantera**, gruppen **Intäktsredovisning** och välj **Allokering av intäktspris**). Intäkterna för den bärbara datorn kommer att bokföras på kontot Intäkt med beloppet $1 008,01. Intäkterna för supportplanen kommer att bokföras på kontot Periodiserad intäkt med beloppet $190,99. Summan av intäktspriserna måste vara lika med summan av raderna som skapats för att samla in allokeringen av intäktspris ($1 199,00).

[![Sidan Allokering av intäktspris](./media/27_rev-rec-scenarios.png)](./media/27_rev-rec-scenarios.png)

Försäljningsordern är helt fakturerad. I bilden nedan visas den redovisningstransaktion som bokförs för fakturan.

[![Redovisningstransaktion för den helt fakturerade försäljningsordern](./media/28_rev-rec-scenarios.png)](./media/28_rev-rec-scenarios.png)

Intäktsredovisningsplanen skapas också. Efter en tid har två av månaderna redovisat intäkter för supportplanen.

[![Sidan Intäktsredovisningsplan efter att två månader har gått](./media/29_rev-rec-scenarios.png)](./media/29_rev-rec-scenarios.png)

Vid denna tidpunkt bestämmer kunden sig för att lägga till installationstjänster (artikelnummer S0001). Artikeln läggs till i den befintliga försäljningsordern. Kunden uppmanas bekräfta att han eller hon vill ändra den helt fakturerade försäljningsordern och väljer **Ja**.

[![Försäljningsorder efter raden för installationstjänsterna lagts till](./media/30_rev-rec-scenarios.png)](./media/30_rev-rec-scenarios.png)

Om den här nya artikeln är den enda ändringen av kundens kontrakt kan omallokeringsprocessen nu köras. I försäljningsordern väljer du **Allokera om pris med nya orderrader** för att öppna sidan **Allokera om pris med nya orderrader**. Markera alla försäljningsorderrader för den här försäljningsordern och välj sedan **Uppdatera omallokering**. Kolumnen **Omallokerat belopp** visar det nya intäktspriset för varje försäljningsorderrad.

[![Nya intäktspriser på sidan Allokera om pris med nya orderrader](./media/31_rev-rec-scenarios.png)](./media/31_rev-rec-scenarios.png)

Därefter väljer du **Förväntad verifikation** för att visa redovisningstransaktionerna. Eftersom alternativet **Bokför fakturakorrigeringar i kundreskontra vid omallokering** anges till **Ja** på fliken **Redovisningsparametrar** kommer dessa redovisningsposter att bokföras i redovisningen via kreditdokumentet och den nya fakturan skapas i Kundreskontra.

[![Redovisningstransaktioner på sidan Förväntad verifikation](./media/32_rev-rec-scenarios.png)](./media/32_rev-rec-scenarios.png)

På sidan **Förväntad verifikation** återför de sista fyra raderna den ursprungliga redovisningstransaktionen från den bokförda fakturan. De första fem raderna är de nya redovisningstransaktionerna som bokförs för fakturan. Det är viktigt att du förstår att en ny faktura inte visas för kunden. Efter omallokeringen är kunden fortfarande skyldig $1 276,94, vilket är det belopp som måste bokföras på Kundreskontra i den nya redovisningstransaktionen. Den motbokade momsen och intäkten eller de periodiserade intäkterna är lika med $995,83 + $188,69 + $77,94 = $1 262,46. Beloppet för intäkt eller periodiserad intäkt har ändrats på grund av omallokeringen. Skillnaden på -$14,48 bokförs på kontot Delvis clearing av fakturaintäkt. Det här saldot tas bort när fakturan bokförs för den nya artikeln som lagts till på försäljningsordern.

När du vill slutföra omallokeringen väljer du **Bearbeta**. Ett bokföringsdatum anges. När omallokeringen har slutförts visar sidan **Allokering av intäktspris** omallokeringen av priset för alla tre artiklar.

[![Omallokering av pris för alla tre artiklar på sidan Allokering av intäktspris](./media/33_rev-rec-scenarios.png)](./media/33_rev-rec-scenarios.png)

Intäktsredovisningsplanen uppdaterades också, baserat på det nya omallokerade intäktspriset. Öppna sidan **Intäktsredovisningsplan** från försäljningsordern. Tidigare fanns det 13 rader för artikel S0008 (en 12-månadersplan tilldelades den här artikeln). Det finns nu 39 rader: de 13 ursprungliga planraderna, 13 planrader för återföring och 13 rader som baseras på det nya intäktspriset.

[![Den uppdaterade sidan Intäktsredovisningsplan med 39 rader för artikel S0008](./media/34_rev-rec-scenarios.png)](./media/34_rev-rec-scenarios.png)

När du väljer **Verifikation** visas den ursprungliga redovisningsposten i fakturajournalen. Om du vill visa återföringsposten och den nya redovisningsposten från försäljningsordern väljer du **Intäktsjusteringar** i åtgärdsfönstret och sedan **Verifikation**.

Öppna sedan sidan **Alla kunder** (**Kundreskontra \> Kunder \> Alla kunder**), välj kunden **US\_SI\_0003** och välj sedan **Transaktioner**. På sidan **Kundtransaktioner** visas den ursprungliga fakturan (000006), återföringsdokumentet (000006-1) och den nya fakturan (000006-2). Den ursprungliga fakturan och återföringsdokumentet kvittas mot varandra och får ett saldo på 0 (noll). Visa verifikationen för varje dokument för att se effekten i redovisningen.

[![Ursprunglig faktura, återföringsdokumentet och ny faktura på sidan Kundtransaktioner](./media/35_rev-rec-scenarios.png)](./media/35_rev-rec-scenarios.png)

Försäljningsordern faktureras igen för artikeln som lagts till. Den totala fakturan som visas för kunden är på $300 00 + $19,50 = $319,50. I bilden nedan visas den redovisningstransaktion som bokförs.

[![Sidan Verifikationstransaktion med redovisningsposten som bokförs](./media/36_rev-rec-scenarios.png)](./media/36_rev-rec-scenarios.png)

Eftersom summan av intäkten och försäljningen är större än $319,50, bokförs skillnaden $14,48. Detta belopp rensar saldot från kontot Delvis clearing av fakturaintäkt. Det saldot uppdaterades i den nya redovisningsposten som bokfördes efter omallokeringen.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]