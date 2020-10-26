---
title: Översikt över kredit och inkasso
description: Detta ämne ger en översikt över funktionaliteten för kredit och inkasso.
author: mikefalkner
manager: AnnBe
ms.date: 09/04/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: roschloma
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: ''
ms.dyn365.ops.version: ''
ms.openlocfilehash: 67e0b3d1058e5fc085f51577ccf0b79e51546de0
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/10/2020
ms.locfileid: "3976605"
---
# <a name="credit-and-collections-overview"></a>Översikt över kredit och inkasso

[!include [banner](../includes/banner.md)]

Du kan hantera kreditgränser för dina kunder och utföra inkassoaktiviteter när de blir nödvändiga.

## <a name="credit-management"></a>Kredithantering

Med hjälp av hantering av kundkredit kan du hantera kreditgränser och styra flödet av försäljningsorder via bokföringsprocessen baserat på de kreditregler som du skapar.

Processen för att använda kredithantering kan omfatta en del av eller alla av följande steg:

- Uppdatera kreditattribut för kunder som ger ytterligare information om deras kreditvärdighet.
- Skapa kreditgränser för kunder genom att använda kreditgränsjusteringar.
- Skapa tillfälliga kreditgränser för kunder genom att använda kreditgränsjusteringar. På det här sättet kan du tillfälligt öka eller minska kundens kreditgränser, baserat på affärsbehoven.
- Lägg till information som kan påverka kreditgränsen, t.ex. information om försäkring och garantier.
- Skapa kundkreditgrupper som kopplar samman kunder så att de kan dela en enda kreditgräns.
- Tilldela riskpoäng till kunder och använd sedan poängen för att automatiskt generera kreditgränser för kunder genom att använda kreditgränsjusteringar.
- Skapa spärrningsregler som gör att en order spärras under en eller flera bokföringsprocesser baserat på faktorer som risk, betalningsvillkor, kreditgränser, förfallna belopp och procent av kreditgräns som används.
- Hantera en lista över försäljningsorder som är spärrade, granska orsakerna till undantaget och minska problemen.
- Frisläpp försäljningsorder och tillåt det att fortsätta under bokföringsprocessen.
- Ställ in arbetsflöde för att hantera godkännandet av kreditgränsändringar och frisläppning av försäljningsorder.

## <a name="collections-management"></a>Inkassohantering

Sidan **Inkasso** ger en centraliserad vy där information om inkasso av kundfordringar hanteras. Inkassoansvariga kan använda denna centraliserade vy för att hantera inkasseringar. Inkassohandläggare kan börja inkassoprocessen från kundlistor som genereras med hjälp av fördefinierade inkassokriterier eller från sidan **Kunder**.

Innan du börjar ställa in eller arbeta med kassaavstämningar, ska du förstå följande begrepp:

- Ögonblicksbilder av åldersfördelningen för kunder innehåller information om åldersfördelade saldon vid en specifik tidpunkt.
- Inkassokundpooler hjälper dig att organisera arbetet.
- Inkassohandläggare kan ha sina egna kundpooler.
- Listsidor organiserar inkassokunder, aktiviteter och fall.
- All information om inkasso för en kund finns på sidan, och du kan vidta åtgärder från den sidan.
- Ränta och avgifter kan avfärdas, återinsättas eller återföras i ett steg.
- Avskrivningstransaktioner kan skapas i ett steg.
- NSF-transaktioner (otillräckliga medel) kan bearbetas i ett steg.

Beskrivningar av dessa begrepp finns i [nyckelbegrepp för inkassohantering](./cm-collections-concepts.md).

## <a name="additional-resources"></a>Ytterligare resurser

[Inställningar för parametrar för kundkredithantering](./cm-credit-mgmt-setup.md)

[Inställningar för information för kundkredithantering](./cm-setup-information.md)

[Lägg till information för kredithantering för en kund](./cm-add-credit-mgmt-information-customer.md)

[Kreditgrupper för kund](./cm-customer-credit-groups.md)

[Justering av kundkreditgräns](./cm-credit-limit-adjustments.md)

[Kreditspärrar för försäljningsorder](./cm-sales-order-credit-holds.md)

[Periodiska kredithanteringsuppgifter för kund](./cm-periodic-tasks.md)
