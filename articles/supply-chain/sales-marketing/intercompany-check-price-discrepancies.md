---
title: Kontrollera avvikelser mellan koncerninterna orderpriser
description: I det här avsnittet beskrivs hur du kontrollerar koncerninterna avvikelser i orderpris
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: PurchTable, PurchTablePart, PurchLineOpenOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 3167077e653f2316f5ce54c2a07ef9c2978ecebb
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/03/2022
ms.locfileid: "8678330"
---
# <a name="check-intercompany-order-price-discrepancies"></a>Kontrollera avvikelser mellan koncerninterna orderpriser

[!include [banner](../../includes/banner.md)]

Du kan använda den här proceduren när du vill söka efter prisdiskrepanser på koncerninterna order.

1. Gå till **Anskaffning och källa\> Periodisk \> Rensa \> Kontrollera avvikelser mellan koncerninterna orderpriser**.
1. Ställ in ett batchjobb om det behövs, och klicka sedan på **OK** för att kontrollera priser och rabatter för koncerninterna försäljningsorder och inköpsorder. Annars klickar du på **Avbryt** och stänger sidan utan att utföra kontrollen.

    > [!TIP]
    > Om det finns vissa synkroniseringsfrågor eller frågor med priser, kommer dessa anges i ett informationsmeddelande som ska visas. Du kan skriva ut informationsmeddelande för referens.

1. I informationsmeddelande, dubbelklicka på relevant rad för att öppna ordern i det aktuella juridisk person. Öppna ordern i den relaterade juridiska personen genom att välja **Koncernintern** och sedan **Koncernintern inköpsorder** eller **Koncernintern försäljningsorder**.

    > [!NOTE]
    > Om du vill tillåta uppdatering av den koncerninterna ordern:
    >
    > 1. Gå till **Leverantörsreskontra \> Kunder \> Alla kunder**.
    > 1. I Åtgärdsfönster, på fliken **Allmänt** och välj sedan **koncernintern**.
    > 1. På sidan **Koncernintern** väljer du **inköpsorderpolicyer** eller **försäljningsorderpolicyer**.
    > 1. Välj **Tillåt prisredigering** och **Tillåt rabattredigering** i båda områdena.

1. Öppna den aktuella koncerninterna order där du vill behålla priset.
1. För varje orderrad ändrar du fältet **Enhetspris** för raden, och återställer den sedan till ursprungligt värde. Ändra fältet **Rabatt** för raden och återställ den sedan, och ändra slutligen värdet för **Avgifter på inköp** eller **Försäljningsavgifter** och återställ dem sedan. När du ändrar och återställer värdena utlöser det en synkronisering av priser, rabatter och tillägg, från den aktuella koncerninterna orderraden till den koncerninterna orderrad den refererar till, så att de justeras automatiskt.

    > [!NOTE]
    > Den här synkroniseringen fungerar bara om den koncerninterna försäljningsordern inte har fakturerats. Om den koncerninterna försäljningsordern har fakturabokförts och en kundfakturajournal har skapats, måste ändringarna utföras direkt på den koncerninterna inköpsorderraden genom att priser, rabatter och tillägg justeras till motsvarande värden i journalen för koncernintern kundfaktura. Om inte detta görs kan inte den koncerninterna inköpsordern bokföras som fakturerad, eftersom ordersummorna inte matchar.

1. Upprepa proceduren tills alla koncerninterna inköps- och försäljningsorder är synkroniserade.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
