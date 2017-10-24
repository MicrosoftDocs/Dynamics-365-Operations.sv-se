--- 
title: "Skapa en inköpsorder för en engångsleverantör"
description: "Den här proceduren visar hur du skapar en inköpsorder för en engångsleverantör."
author: FrankDahl
manager: AnnBe
ms.date: 08/23/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: fdahl
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 2d4dabaf6e1d79cbd626294ee4e327f2725a5e43
ms.contentlocale: sv-se
ms.lasthandoff: 09/29/2017

---
# <a name="create-a-purchase-order-for-a-one-time-supplier"></a>Skapa en inköpsorder för en engångsleverantör

[!include[task guide banner](../../includes/task-guide-banner.md)]

Den här proceduren visar hur du skapar en inköpsorder för en engångsleverantör. Leverantören skapas automatiskt med inköpsordern, snarare än att du måste skapa leverantörskontot manuellt. Inköpsorder används vanligtvis av inköpsagenter. De exempel som visas i den här handboken kan användas i demoföretaget USMF. Det är en förutsättning att ett konto för engångsleverantör har ställts in på sidan Obetalda parametrar för konto.


## <a name="create-a-purchase-order-for-a-one-time-supplier"></a>Skapa en inköpsorder för en engångsleverantör
1. Gå till Anskaffning och källa > Inköpsorder > Alla inköpsorder.
2. Klicka på Ny.
3. Välj Ja i fältet Engångsleverantör.
    * Ett leverantörskonto skapas automatiskt och tilldelas inköpsordern. Leverantörskontot är baserat på mallen som visas på fliken Allmänt på sidan Parametrar för leverantörsreskontra.  
4. Ange ett namn för leverantören i fältet Namn.
5. Klicka på OK.
    * Inköpsordern kan nu slutföras och bearbetas som alla andra order. Det finns inga särskilda resursegenskaper som är relaterade till hur detta ska göras. Fakturan tar hänsyn en transaktion som förfaller på leverantörskontot som skapades med ordern och betalningen bearbetas därefter. När detta är slutfört kan leverantörskontot tas bort. Detta görs normalt av leverantörsreskontraavdelningen.  


