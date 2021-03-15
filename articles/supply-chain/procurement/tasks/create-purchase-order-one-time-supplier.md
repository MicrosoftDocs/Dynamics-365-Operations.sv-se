---
title: Skapa en inköpsorder för en engångsleverantör
description: Den här proceduren visar hur du skapar en inköpsorder för en engångsleverantör.
author: RichardLuan
manager: tfehr
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: PurchTable, PurchTablePart, PurchCreateOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: c4885547cdf2f8496446761e27ce39e67e670f15
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/16/2021
ms.locfileid: "5016412"
---
# <a name="create-a-purchase-order-for-a-one-time-supplier"></a>Skapa en inköpsorder för en engångsleverantör

[!include [banner](../../includes/banner.md)]

Den här proceduren visar hur du skapar en inköpsorder för en engångsleverantör. Leverantören skapas automatiskt med inköpsordern, snarare än att du måste skapa leverantörskontot manuellt. Inköpsorder används vanligtvis av inköpsagenter. De exempel som visas i den här handboken kan användas i demoföretaget USMF. Det är en förutsättning att ett konto för engångsleverantör har ställts in på sidan Obetalda parametrar för konto.


## <a name="create-a-purchase-order-for-a-one-time-supplier"></a>Skapa en inköpsorder för en engångsleverantör
1. Gå till Anskaffning och källa > Inköpsorder > Alla inköpsorder.
2. Klicka på Ny.
3. Välj Ja i fältet Engångsleverantör.
    * Ett leverantörskonto skapas automatiskt och tilldelas inköpsordern. Leverantörskontot är baserat på mallen som visas på fliken Allmänt på sidan Parametrar för leverantörsreskontra.  
4. Ange ett namn för leverantören i fältet Namn.
5. Klicka på OK.
    * Inköpsordern kan nu slutföras och bearbetas som alla andra order. Det finns inga särskilda resursegenskaper som är relaterade till hur detta ska göras. Fakturan tar hänsyn en transaktion som förfaller på leverantörskontot som skapades med ordern och betalningen bearbetas därefter.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]