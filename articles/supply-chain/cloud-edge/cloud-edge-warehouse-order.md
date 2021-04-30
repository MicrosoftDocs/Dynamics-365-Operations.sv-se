---
title: Lagerställeorder för moln- och kantskalningsenheter
description: Det här ämnet ger information om den lagerställeorderkapacitet som används som en del av arbetsbelastningen för lagerställeenheter.
author: perlynne
ms.date: 04/13/2021
ms.topic: article
ms.search.form: WHSWarehouseOrderLine, WHSWarehouseReceiptEntry, PurchTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-04-13
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: c24c08771c83453bb65312700cf994c7a800b7fd
ms.sourcegitcommit: 639175a39da38edd13e21eeb5a1a5ca62fa44d99
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/15/2021
ms.locfileid: "5899129"
---
# <a name="warehouse-orders-for-cloud-and-edge-scale-units"></a>Lagerställeorder för moln- och kantskalningsenheter

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

> [!WARNING]
> Inte alla företagsfunktioner stöds fullt ut i den allmänna förhandsgranskningen när enheter för belastningsenheter används. Om du använder skalningsenheter, se till att bara använda de processer som det här ämnet explicit beskriver som det stöds.

## <a name="what-are-warehouse-orders"></a>Vad är lagerställeorder?

*Lagerställeorder* är en typ av order som skapades för att stödja distributioner av hubb och lagerställe skalningsenheter. De låter dig ta emot lager när du kör en lagerställearbetsbelastning på en skalenhet. De används för närvarande bara för inköpsorder.

Lagerställeorder används som en del av bearbetningen av lagerstyrning, till exempel när mobilappen för distributionslagerhantering används för att registrera fysisk lagerbehållning under bearbetning av en inkommande inköpsorder. Lagerställeorder skapas som en del av processen *Släpp till distributionslager* som är tillgänglig för inköpsorder som anger ett lagerställe i skalningsenhet som är aktiverad för att använda lagerstyrningsprocesser.

> [!IMPORTANT]
> Lagerställeorder är bara tillgängliga i distributioner som använder [arbetsbelastning i distributionslagerhantering för moln- och kantskalningsenheter](cloud-edge-workload-warehousing.md).

## <a name="create-a-warehouse-order"></a>Skapa en lagerorder

Följ dessa steg för att skapa en lagerorder.

1. Logga in på instansen av Microsoft Dynamics 365 Supply Chain Management som körs i hubben. (Du måste initiera processen *Släpp till distributionslager* när du är inloggad på hubben.)
1. Gå till **Anskaffning och källa \> Inköpsorder \> Alla inköpsorder**.
1. I åtgärdsfönstret **Lagerställe**, flik **åtgärder**, välj **Släpp till lagerställe**.
1. För att se relaterade orderrader för lagerställe, öppna relevant inköpsorder, välj en rad i avsnittet **Inköpsorderrader** och sedan i verktygsfältet, välj **lagerställe \> orderrader för lagerställe**. Om du vill visa alla raderna går du till **Hantering av distributionslager \> Förfrågningar och rapporter \> Orderrader för lagerställe**.

Du kan också utlösa processen *Frisläpp till lagerställe* från ett batchjobb genom att gå till **Lagerstyrning > Frisläpp till lagerställe > Automatisk frisläppning av inköpsorder**. När du ställer in batchjobbet kan du välja specifika inköpsorderrader baserade på en frågeställning. Ett vanligt scenario är att ställa in ett återkommande batchjobb som frisläpper alla bekräftade inköpsorderrader som förväntas komma in nästa dag.

## <a name="cancel-a-warehouse-order"></a>Annullera en lagerorder

Som en del av processen *Släpp till distributionslager* är lagertransaktioner för inköpsorder kopplade till lagerorder och låsta från att uppdateras av hubben. Om du av misstag frisläppt till lagerstället, eller om du har någon annan orsak till att skapa orderrader för lagerställe, kan du begära att annullera orderraderna för lagerstället.

Följ dessa steg för att annullera orderrader för lagerstället.

1. Logga in på instansen av Supply Chain Management som körs i hubben.
1. Gå till **Hantering av distributionslager \> Förfrågningar och rapporter \> Orderrader för lagerställe**.
1. Välj relevant rad.
1. I åtgärdsfönstret, markera **Annullera orderrader för lagerstället**.

> [!NOTE]
> En begäran om att annullera rader nekas för alla rader som redan väntar på att annulleras eller som har förs del i ett lagerställe där arbetsbelastningen körs på en skalningsenhet.

## <a name="monitor-a-warehouse-order"></a>Övervaka en lagerorder

I vyn **Orderrader för lagerställe** kan du övervaka förloppet för inkommande meddelanden genom att granska värdena i kolumnen **kvantitet kvar att inleverera**. Om du vill visa information om arbete som har utförts med hjälp av mobilappen för distributionslagerhantering följer du ett av stegen nedan.

- Gå till **Hantering av distributionslager \> Förfrågningar och rapporter \> Orderrader för lagerställe** och använd filtret för att hitta de rader du letar efter.
- Gå till **Anskaffning och källa \> Inköpsorder \> Alla inköpsorder** och öppna relevant inköpsorder. I avsnittet **Inköpsorderrader**, markera en eller flera rader och välj sedan **lagerställe \> Inleveransposter för lagerställe** i verktygsfältet.

[!INCLUDE [cloud-edge-privacy-notice](../../includes/cloud-edge-privacy-notice.md)]


[!INCLUDE[footer-include](../../includes/footer-banner.md)]
