---
title: Lägg till variantprodukter i inköpsorder med hjälp av variantvikter
description: Den här proceduren går igenom stegen vid användning av variantvikt för att automatiskt fylla i inköpsorderrader för varje variant av en produkt.
author: ShylaThompson
manager: tfehr
ms.date: 11/14/2016
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 27ff3784074a36d073930ba68c8dec8b1121356e
ms.sourcegitcommit: e3f4dd2257a3255c2982f4fc7b72a1121275b88a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "4018294"
---
# <a name="add-variant-products-to-purchase-orders-using-variant-weights"></a>Lägg till variantprodukter i inköpsorder med hjälp av variantvikter

[!include [banner](../../includes/banner.md)]

Den här proceduren går igenom stegen vid användning av variantvikt för att automatiskt fylla i inköpsorderrader för varje variant av en produkt. När du väljer kvantiteten av produkten som du vill köpa, inköpsorderrader skapas för alla varianter av produkten med föreslagna kvantiteter som baseras på de vikter som konfigureras på produktvarianterna. Den här proceduren inkluderar inte steg för att konfigurera viktvärden på produktdimensioner och produktvarianter. I proceduren används demonstrationsföretaget USRT.

1. Gå till leverantörsskulder > inköpsorder > Alla inköpsorder.
2. Klicka på Ny.
3. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Leverantörskonto.
4. Klicka på länken på den valda raden i listan.
5. Växla utökningen av avsnittet Allmänt.
6. Öppna sökningen genom att klicka på listruteknappen i fältet Plats.
7. Klicka på länken på den valda raden i listan.
8. Öppna sökningen genom att klicka på den nedrullningsbara knappen i fältet Lagerställe.
9. Hitta och markera önskad post i listan.
10. Klicka på länken på den valda raden i listan.
11. Klicka på OK.
12. Växla expanderingen av avsnittet Raddetaljer.
13. Klicka på fliken Varianter.
14. Klicka på Lägg till rad.
15. Markera vald rad i listan.
16. Skriv 0140 i fältet Artikelnummer.
17. Ställ in kvantiteten på 1000.
18. Klicka på Spara.

