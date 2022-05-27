---
title: Skapa en koncernintern försäljningsorder för internt bruk
description: I det här avsnittet beskrivs hur du skapar en koncernintern försäljningsorder för intern användning
author: Henrikan
ms.date: 09/01/2021
ms.topic: article
ms.search.form: SalesTableListPage, SalesCreateOrder, SalesTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: henrikan
ms.search.validFrom: 2021-09-01
ms.dyn365.ops.version: 10.0.22
ms.openlocfilehash: 9b4d2dc450fb5996e0e08c92836c1d1942a05b73
ms.sourcegitcommit: 9166e531ae5773f5bc3bd02501b67331cf216da4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/03/2022
ms.locfileid: "8673702"
---
# <a name="create-an-intercompany-sales-order-for-internal-use"></a>Skapa en koncernintern försäljningsorder för internt bruk

[!include [banner](../../includes/banner.md)]

En koncernintern försäljningsorder skapas automatiskt från en koncernintern inköpsorder. Du kan också skapa en koncernintern försäljningsorder manuellt, som sedan genererar en koncernintern inköpsorder i den koncerninterna kundens juridiska person.

![Koncernintern intern försäljningsprocess](media/intercompanyinternalsalesprocess.png)

## <a name="create-an-intercompany-sales-order-manually"></a>Skapa en koncernintern försäljningsorder manuellt

Utför de här stegen i juridisk person B, som visat i bilden.

1. Gå till **Kundreskontra \> Försäljningsorder \> Alla försäljningsorder**.
1. I åtgärdsfönstret, välj **Försäljningsorder** för att skapa försäljningsorder.
1. På sidan **Skapa försäljningsorder** välj kundkonto. På snabbfliken **Allmänt** se till att kryssrutan **Koncernintern** är markerad. Detta visar att den valda kunden är en koncernintern kund.
1. Ange eller ändra informationen och klicka på **OK** och fyll i orderraderna som vanligt.

    Fältvärdet **Leveransadress** kopieras från det koncerninterna försäljningsorderrubrik till den koncerninterna inköpsorderrubriken. Fältvärdet **artikelnummer** inklusive produktdimensioner och fältvärden **Leveransdatum** och **Valutakod** kopieras från raderna mellan koncernens försäljningsorder till raderna för inköpsorder mellan företag.

1. I orderns sidhuvud, välj **koncernintern** om du vill visa den relaterade koncerninterna inköpsordern.
1. På orderraderna väljer du **Koncernintern** om du vill visa information om lagerbehållning för koncernintern handel.

> [!TIP]
> Du kan visa koncerninterna försäljningsorder på sidan **Koncernintern order**.

> [!NOTE]
> När du arbetar med koncernintern rekommenderar vi att du avmarkerar kryssrutan **Radera order efter fakturering** på sidan **Parametrar för kundreskontra**.  Annars tas den relaterade inköpsordern bort. Vi rekommenderar också att du avmarkerar kryssrutan **Radera inköpsorder efter fakturering** på sidan **Parametrar för leverantörsreskontra**.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
