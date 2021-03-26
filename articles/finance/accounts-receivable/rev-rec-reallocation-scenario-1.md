---
title: Omallokering vid intäktsredovisning – scenario 1
description: Det här avsnittet innehåller en genomgång av ett omallokeringsscenario där två försäljningsorder registreras, men de bekräftas bara. Samma scenario kommer att ge liknande resultat om fler än två försäljningsorder är i ett bekräftat tillstånd.
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
ms.openlocfilehash: 25fb32ce72555e573cd37a0ab092b51b99bb4372
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5260887"
---
# <a name="revenue-recognition-reallocation--scenario-1"></a>Omallokering vid intäktsredovisning – scenario 1

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller en genomgång av ett omallokeringsscenario där två försäljningsorder registreras, men de bekräftas bara. Samma scenario kommer att ge liknande resultat om fler än två försäljningsorder är i ett bekräftat tillstånd.

För det här scenariot ska alternativet **Bokför fakturakorrigeringar i Kundreskontra** anges till **Nej** på fliken **Intäktsredovisning** på sidan **Redovisningsparametrar** (**Intäktsredovisning \> Inställningar \> Redovisningsparametrar**).

[![Alternativet Bokför fakturakorrigeringar i Kundreskontra inställt på Nej](./media/06_rev-rec-scenarios.png)](./media/06_rev-rec-scenarios.png)

En försäljningsorder skapas för kunden US\_SI\_0003. Kunden köper en bärbar dator (artikelnummer S0012) och en supportplan för den (artikelnummer S0008, "Teknisk service"). Intäkterna för den bärbara datorn redovisas omedelbart (det finns ingen intäktsredovisningsplan). Intäkterna för supportplanen kommer att periodiseras och redovisas under 12 månader, enligt definitionen av datumintervallet i kontraktet.

[![Försäljningsorderrader för den bärbara datorn och supportplanen](./media/07_rev-rec-scenarios.png)](./media/07_rev-rec-scenarios.png)

Försäljningsordern bekräftas. Eftersom båda artiklarna har ställts in för allokering av intäktspris, beräknas intäktspriset när försäljningsordern bekräftas. Du kan visa den intäkt som kommer att redovisas på sidan **Allokering av intäktspris** (gå till sidan **Försäljningsorder**, åtgärdsfönstret, fliken **Hantera**, gruppen **Intäktsredovisning** och välj **Allokering av intäktspris**). Intäkterna för den bärbara datorn kommer att bokföras på kontot Intäkt med beloppet $1 008,01. Intäkterna för supportplanen kommer att bokföras på kontot Periodiserad intäkt med beloppet $190,99. Summan av intäktspriserna måste vara lika med summan av raderna som skapats för att samla in allokeringen av intäktspris ($1 199,00).

[![Sidan Allokering av intäktspris](./media/08_rev-rec-scenarios.png)](./media/08_rev-rec-scenarios.png)

Kunden valde att inte köpa installationstjänster (artikelnummer S0001) vid tidpunkten för försäljningen men ändrade sig senare. Därför registreras en andra försäljningsorder för samma kund.

[![Försäljningsorderrad för installationstjänster](./media/09_rev-rec-scenarios.png)](./media/09_rev-rec-scenarios.png)

Den andra försäljningsordern bekräftas. Eftersom den här försäljningsordern bara innehåller en rad görs ingen allokering av intäktspris när försäljningsordern bekräftas. Allokeringen av intäktspris sker bara om det finns två eller flera unika artiklar, och om dessa artiklar ställts in för allokering av intäktspris.

Om den här nya försäljningsordern är den enda ändringen av kundens kontrakt kan omallokeringsprocessen nu köras. I en av dessa två försäljningsorder väljer du **Allokera om pris med nya orderrader** för att öppna sidan **Allokera om pris med nya orderrader**. Alternativt går du till **Intäktsredovisning \> Periodiska uppgifter \> Allokera om pris med nya orderrader**. Markera dessa två försäljningsorder och motsvarande försäljningsorderrader och välj sedan **Uppdatera omallokering**. Kolumnen **Omallokerat belopp** visar det nya intäktspriset för varje försäljningsorderrad.

[![Nya intäktspriser på sidan Allokera om pris med nya orderrader](./media/10_rev-rec-scenarios.png)](./media/10_rev-rec-scenarios.png)

Om du väljer **Förväntad verifikation** visas ingenting, eftersom inga fakturor har bokförts.

När du vill slutföra omallokeringen väljer du **Bearbeta**. Du uppmanas att ange ett bokföringsdatum, även om inget är bokfört. När omallokeringen är klar kommer sidan **Allokering av intäktspris** för varje försäljningsorder visa prisallokeringen för alla artiklar på båda försäljningsorder. Med andra ord kommer sidan **Allokering av intäktspris** för varje försäljningsorder att innehålla en artikel som inte finns på den försäljningsordern, eftersom den ingår i samma kontrakt men finns på en annan försäljningsorder.

> [!TIP]
> Om du vill förklara varför dessa ytterligare artiklar visas kan du lägga till andra kolumner i rutnätet, till exempel **Omallokerings-ID** och **Försäljningsorder**.
> 
> [![Ytterligare kolumner på sidan Allokering av intäktspris](./media/11_rev-rec-scenarios.png)](./media/11_rev-rec-scenarios.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]