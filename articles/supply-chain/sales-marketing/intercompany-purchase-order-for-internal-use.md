---
title: Skapa och fakturera en koncernintern inköpsorder för internt bruk
description: I denna artikel beskrivs hur du skapar och fakturerar en koncernintern inköpsorder för internt bruk
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
ms.openlocfilehash: 2260128c276ab7b712f7c97945b188ea42099fb4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8877549"
---
# <a name="create-and-invoice-an-intercompany-purchase-order-for-internal-use"></a>Skapa och fakturera en koncernintern inköpsorder för internt bruk

[!include [banner](../../includes/banner.md)]

Du kan skapa en koncernintern inköpsorder för en koncernintern leverantör. Detta skapar automatiskt en koncernintern försäljningsorder hos den koncernintena leverantören.

![Koncernintern intern inköpsprocess](media/intercompanypurchaseprocess.png)

## <a name="create-an-intercompany-purchase-order-and-a-corresponding-intercompany-sales-order"></a>Skapa en koncernintern inköpsorder och en motsvarande koncernintern försäljningsorder

Utför de här stegen i juridisk person AAA, som visat i bilden.

1. Välj **Leverantörsreskontra** \> **Inköpsorder** \> **Alla inköpsorder**.
1. På listsidan **Alla inköpsorder**, skapa en inköpsorder en koncernintern leverantör. Fältvärdena kopieras från leverantörskontot till inköpsordern.

    Eftersom du arbetar med en koncernintern leverantör skapas en koncernintern försäljningsorder i den juridiska personen som motsvarar leverantören. Numret på den koncerninterna försäljningsordern kan vara samma som numret på den koncerninterna inköpsordern, och det kan inkludera ID:t för den juridiska personen. Nummerstrukturen som används beror på valet i fältet **Nummer på försäljningsorder** på sidan **koncernintern**. Om du till exempel skapar inköpsorder 00029\_064 i juridisk person AAA är försäljningsordernumret i juridisk person BBB AAA00029\_64.

    Ett informationsmeddelande visar att en koncernintern inköpsorder och koncernintern försäljningsorder har skapats. Meddelandet inkluderar numret på den koncerninterna försäljningsordern som upplysning.

1. Lägg till radartiklar i inköpsordern. Motsvarande radartiklar läggs automatiskt till i den koncerninterna försäljningsordern. Om en artikel inte finns i den andra juridiska personen visas ett meddelande, och du kan inte lägga till artikeln i inköpsordern. Växla till den andra juridiska personen och frisläpp produkten till den juridisk person för att åtgärda detta problem. Artikeln kommer att vara tillgänglig för att läggas till i försäljningsorder i den juridiska personen. Växla sedan tillbaka till den juridiska person som hör till inköpsordern och fortsätt lägga till radartiklar.
1. När du är klar att ange information för inköpsordern ska du bekräfta den.

## <a name="process-the-intercompany-packing-slip-and-customer-invoice"></a>Bearbeta den koncerninterna följesedeln och kundfakturan

Utför de här stegen i juridisk person BBB, som visat i bilden.

1. Gå till **Kundreskontra \> Försäljningsorder \> Alla försäljningsorder**.
1. På listsidan **Alla försäljningsorder**, välj koncernintern försäljningsorder.
1. I åtgärdsfönstret, välj **Plocka och packa** och välj **följesedel**.
1. Markera kryssrutan **Bokföring**.
1. Välj **OK**. Följesedeln bokförs i juridisk person BBB.
1. På listsidan **Alla försäljningsorder**, välj koncernintern försäljningsorder.
1. I Åtgärdsfönster, på fliken **Faktura** och välj sedan **Faktura**.
1. Markera kryssrutan **Bokföring**.
1. Välj **OK**.

    Kundfakturan för den koncerninterna försäljningsordern bokförs i juridisk person BBB.

## <a name="process-the-intercompany-product-receipt-and-vendor-invoice"></a>Bearbeta den koncerninterna produktinleveransen och leverantörsfakturan

Utför de här stegen i juridisk person AAA, som visat i bilden.

1. Gå till **Leverantörsreskontra \> Inköpsorder \> Alla inköpsorder**.
1. På listsidan **Alla inköpsorder**, välj koncernintern inköpsorder.
1. I Åtgärdsfönster, på fliken **Inleverera** och välj sedan **Produktinleverans**. Produktinleveransen skapas. Produktinleveransnumret är samma som det koncerninterna följesedelsnumret.
1. Markera kryssrutan **Bokföring**.
1. Välj **OK**.
1. På listsidan **Alla inköpsorder**, välj koncernintern inköpsorder.
1. I åtgärdsfönstret väljer du **Faktura**, och sedan **Faktura**. Leverantörsfakturan skapas. Leverantörsfakturanumret är samma som det koncerninterna kundfakturanumret.
1. Slutför inmatning av leverantörsfakturan och bokför den sedan.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
