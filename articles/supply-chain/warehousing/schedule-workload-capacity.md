---
title: Tidsplanera kapacitet för lagerställe
description: Det här avsnittet beskrivs hur du ställer in och schemalägger den arbetsbelastningskapacitet för arbetare i ett lagerställe eller en hel lagerställe.
author: MarkusFogelberg
manager: tfehr
ms.date: 05/26/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WMSWorkloadCapacity
audience: Application User
ms.reviewer: kamaybac
ms.custom: 269384
ms.search.region: Global
ms.author: mafoge
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 8db243949b2aeee0a8263276234d439652905449
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4965587"
---
# <a name="schedule-workload-capacity"></a>Tidsplanera kapacitet för lagerställe

[!include[banner](../includes/banner.md)]

Du kan tidsplanera arbetsbördakapacitet för lagerställen och även förutse de aktuella och framtida arbetsbördorna för arbetarna i enskilda lagerställen. Du kan förutse arbetsbelastningen för hela lagerstället, eller så kan du förutse arbetsbelastningen separat för inkommande och utgående arbetsbelastningar.

Om du förutser arbetsbelastningen som tillverkats för valda huvudplaneringdata, måste lagerställen vara tillgängliga för de valda lagerställen. För mer information se [Översikt över huvudplaner](../master-planning/master-plans.md).

## <a name="schedule-and-view-workloads-for-a-warehouse"></a>Tidsplanera och visa arbetsbördor för ett lagerställe

Om du vill Tidsplaneringen för arbetsbördakapacitet för ett lagerställe, skapar du en arbetsbelastning som har ställts in för en eller flera lagerställen, och kopplar sedan den arbetsbelastningen med en huvudplan. I arbetsbördakapacitetinställningar kan du definiera gränser för vikt och volym för inkommande och utgående transaktioner. Du kan också skapa fler än en inställning för varje lagerställe, och sedan koppla enskilda inställningen med huvudplaner. Du kan till exempel göra detta för att rätta säsongsbetonade ändringar i Personal.

Om arbetarna för ett lagerställe arbetar med transaktioner för både inkommande och utgående arbetsbelastningar, kan du konfigurera lagerställekapacitetinställningar till att förutse arbetsbelastningen i en kombinerad vyn.

Du planering och visa arbetsbelastningar för lagerställen måste du utföra följande uppgifter:

1. Skapa en arbetsbördakapacitetinställning och definiera arbetsbördakapacitetgränser för ett eller flera lagerställen.
2. Koppla arbetsbördakapacitetinställningar med en huvudplan för att skapa arbetsbördaprojektioner och för att ange hur länge projektionerna ska gälla.

### <a name="create-a-workload-capacity-setup-for-a-warehouse"></a>Skapa en arbetsbördakapacitetinställning för ett lagerställe

1. Välj **lagerhantering**\>**inställningar**\>**Övervakning av lagerställe**\>**Arbetsbelastningskapacitet**.
2. I åtgärdsfönstret, välj **Ny** för att skapa en inställning för arbetsbelastningskapacitet.
3. På snabbfliken **Lagerställen** väljer du **Ny** och anger sedan värden på raden som ska associeras med arbetsbördakapacitetinställningar ett lagerställe.
4. Välj kryssrutan **Kombinerade arbetsbelastningen för inkommande och utgående** om rapporten **arbetsbelastningskapacitet** visa den totala arbetsbelastningen för inkommande och utgående transaktioner i en enda vy.
5. Välj inkommande och utgående arbetsbördagränserna för de transaktionstyper som ska användas för, på snabbfliken **Transaktionstyper**.

    > [!NOTE]
    > Du måste välja minst en transaktionstyp för både inkommande och utgående arbetsbördorna.

#### <a name="define-limits-for-volume-or-weight"></a>Definiera gränser för volym eller vikt

Du kan ställa in gränser för vikt och volym, beroende på begränsningar som är relevant för lagerställepersonalen. Gränserna som du anger, inkluderas i arbetsbördakapacitetprojektionen som du kan visa i rapporten **arbetsbördakapacitet**.

Till projektinformation om volym och vikt för artiklar, måste standardvolym för en artikel i lager och vikt för en lagerartikel, anges för alla produkter. Obligatoriska fält är tillgängliga i följande fältgrupper på snabbfliken **hantera lager** på sidan **Information om frisläppt produkt**:

- Hantering
- Fysiska dimensioner
- Viktmått

Om den här informationen inte anges korrekt, visas ett meddelande när du genererar rapporten **Arbetsbelastningskapacitet**. Från rapporten kan du gå ner för att identifiera den information som saknas till förutse den framtida arbetsbelastningen.

### <a name="associate-a-workload-capacity-setup-with-a-master-plan"></a>Koppla en in arbetsbördakapacitetinställning med en huvudplan

1. Välj **Lagerhantering** \> **Periodiska uppgifter** \> **Tidsplanera arbetsbelastning**.
2. Välj den huvudplan som ska användas för arbetsbördaprojektioner, i fältet **huvudplan**.
3. Ange det antal dagar som täcker arbetsbördaprojektionen, i fältet **Antal dagar**.
4. Välj arbetsbördainställningar som ska associeras med huvudplanen i fältet **arbetsbörda**.

### <a name="view-workload-capacity"></a>Visa arbetsbelastningskapacitet

1. Välj **lagerhantering**\>**förfrågningar och rapporter**\>**Rapporter om fysiskt lager**\>**Arbetsbelastningskapacitet**.
2. Ange det antal kolumner som ska visas på rapporten, i fältet **Antal kolumner**.
3. På fältet **Ordertyp** välj **planerat och bekräftat**, **planerat**, eller **bekräftat** för att bestämma vilken typ av order till projekt i rapporten.
4. Välj en beläggningtyp om du vill visa att arbetsbördakapaciteten ska förutses för volym eller vikt, i fältet **Beläggningstyp**.
5. Välj en inställning för arbetsbelastningskapacitet i fältet **Arbetsbelastningskapacitet**.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]