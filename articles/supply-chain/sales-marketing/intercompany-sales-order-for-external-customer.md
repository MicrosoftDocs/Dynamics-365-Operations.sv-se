---
title: Skapa och fakturera en koncernintern försäljningsorder för en extern kund
description: Detta ämne förklarar hur du skapar och fakturerar en koncernintern försäljningsorder för en extern kund
author: GalynaFedorova
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: v-gfedorova
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 72273a125da2e6c4a2fc16b449cd5077f3d767df
ms.sourcegitcommit: fcfd85a508c0de52cfe11d1986892219e39ef406
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/23/2021
ms.locfileid: "7548533"
---
# <a name="create-and-invoice-an-intercompany-sales-order-for-an-external-customer"></a>Skapa och fakturera en koncernintern försäljningsorder för en extern kund

[!include [banner](../../includes/banner.md)]

Du kan använda koncernintern handel för att registrera försäljning av en produkt från en juridisk person till en annan juridisk person som finns i samma organisation.

När du skapar en ursprunglig försäljningsorder kan du automatiskt skapa en koncernintern inköpsorder för den koncerninterna leverantören. Detta skapar automatiskt en koncernintern försäljningsorder hos den koncernintena leverantörens juridiska person.

Illustrationen visar flödet för transaktionerna när du skapar en försäljningsorder för en extern kund, men produkten måste beställas från en annan juridisk person inom din organisation innan du kan leverera produkten till kunden. I detta fall skapas en koncernintern inköpsorder för leverantörskontot som representerar den andra juridiska personen. I sin tur skapas en koncernintern försäljningsorder i den andra juridiska personen för det kundkonto som representerar din juridisk person. När en koncernintern inköpsorder faktureras, bokförs fakturan för den ursprungliga försäljningsordern automatiskt om det är en direktleverans.

![Koncernintern extern försäljningsprocess](media/intercompanyexternalsalesprocess.png)

Om du använder direktleverans och väljer **Följesedel** i fältet **Kvantitet** på sidan **Bokföra faktura** kommer den koncerninterna leverantörsfakturan att baseras på den koncerninterna produktinleverans som tidigare har bokförts.

## <a name="prerequisites"></a>Förutsättningar

Innan du börjar kontrollerar du att följande förutsättningar är uppfyllda för att automatiskt bokföra och skriva ut de koncerninterna fakturorna.

1. Gå till **Försäljning och marknadsföring \> Kunder \> Alla kunder**.
1. Välj **Koncernintern** på fliken **Allmänt** i åtgärdsfönstret.
1. Gå till **Anskaffning och källa \> Leverantörer \> Alla leverantörer**.
1. Välj **Koncernintern** på fliken **Allmänt** i åtgärdsfönstret.
1. På sidan **Koncernintern** för antingen leverantören eller kunden, i området **Inköpsorderpolicyer** i fältgruppen **Koncernintern inköpsorder (direktleverans)**, markera kryssrutan **Bokför faktura automatiskt**.
1. I området **Inköpsorderpolicyer** i fältgruppen **Ursprunglig försäljningsorder (direktleverans)**, markera kryssrutan **Bokför faktura automatiskt**. Markera den här kryssrutan om du vill att fakturan för den ursprungliga försäljningsordern ska skrivas ut automatiskt när du bokför den koncerninterna leverantörsfakturan.

> [!NOTE]
> Utskriftsinställningarna för fakturan bestäms av inställningen för modulen, dokumentet eller transaktionen på sidan **Konfiguration för utskriftshantering**.

## <a name="create-an-original-sales-order-for-an-external-customer"></a>Skapa en ursprunglig försäljningsorder för en extern kund

Utför de här stegen i juridisk person A. Den här proceduren motsvarar rutan med etikett 1 i bilden.

1. Gå till **Kundreskontra \> Försäljningsorder \> Alla försäljningsorder**.
1. Från listsidan **Alla försäljningsorder**, skapa den ursprungliga försäljningsordern. Fältvärdena kopieras från kundkontot till försäljningsordern.
1. På sidan **Försäljningsorder**, välj **Huvudvy** i åtgärdsrutan.
1. På snabbfliken **Koncerninterna inställningar** markera kryssrutan **Skapa koncerninterna order automatiskt**.
1. Om du vill att den koncerninterna leverantören ska leverera artikeln direkt till den externa kunden markerar du kryssrutan **Direktleverans**.
1. När du är klar att ange försäljningsordern, stänger du sidan **försäljningsorder**.

Den koncerninterna inköpsordern skapas automatiskt för alla artiklar som tilldelats en koncernintern leverantör, och sedan skapas den koncerninterna försäljningsordern. Ett informationsmeddelande visar att en koncernintern inköpsorder och koncernintern försäljningsorder har skapats. Meddelandet innehåller också länkar till dessa order. Om en artikel inte var hittad visas en röd varning som innebär att orderprocessen inte kunde skapas.

> [!NOTE]
> Om du skapar flera order i olika juridiska personer och artiklarna inte var tillgängliga i en av de juridiska personerna slutar programmet att skapa order, även för de juridiska personer som kunde uppfylla sina order.

## <a name="invoice-an-intercompany-sales-order"></a>Fakturera en koncernintern försäljningsorder

När en koncernintern försäljningsorder faktureras, faktureras motsvarande koncerninterna inköpsorder automatiskt. Då, om den ursprungliga försäljningsordern är en direktleveransorder, faktureras den ursprungliga försäljningsordern automatiskt.

Utför de här stegen i juridisk person B. Den här proceduren motsvarar rutan med etikett 2 i bilden.

1. Gå till **Kundreskontra \> Försäljningsorder \> Alla försäljningsorder**.
1. På listsidan **Alla försäljningsorder**, välj koncernintern försäljningsorder.
1. I Åtgärdsfönster, på fliken **Faktura** och välj sedan **Faktura**.
1. Markera kryssrutan **Bokföring**.
1. Välj försäljningsordern och klicka sedan på **OK**.

Kundfakturan för den koncerninterna försäljningsordern bokförs automatiskt i juridisk person B. Den koncerninterna leverantörsfakturan skapas och bokförs sedan automatiskt i juridisk person A. Om den ursprungliga försäljningsordern har ställts in som en direktleverans skapas kundfakturan för den ursprungliga försäljningsordern i juridisk person A.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
