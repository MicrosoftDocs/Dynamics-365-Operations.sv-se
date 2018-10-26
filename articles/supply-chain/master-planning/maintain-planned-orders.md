---
title: "Underhåll planerade order"
description: "Detta avsnitt innehåller information om hur du hanterar planerade order. Det beskriver hur du kan uppdatera statusen för planerade order, bekräfta dem och filtrera för planerade order som har samma status som en vald planerad order."
author: roxanadiaconu
manager: AnnBe
ms.date: 10/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 19151
ms.assetid: 54123f4c-b4ca-4ce4-9358-b067aa04c968
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: ad0083018d2734cb1e36cbf5f94105376c57cdf9
ms.openlocfilehash: e0e3e86ae85b59b10dc8d9ca9b0130d218469118
ms.contentlocale: sv-se
ms.lasthandoff: 10/02/2018

---

# <a name="maintain-planned-orders"></a>Underhåll planerade order

[!include [banner](../includes/banner.md)]

Detta avsnitt innehåller information om hur du hanterar planerade order. Det beskriver hur du kan uppdatera statusen för planerade order, bekräfta dem och filtrera för planerade order som har samma status som en vald planerad order.

Du kan hantera planerade order från arbetsytan **Huvudplanering**, listan **Planerad order** eller listorna **Planerade produktionsorder**, **Planerade inköpsorder**och **Planerad överföring**. Du kan använda fältet **Status** för att följa dina framsteg. Följande värden används:

-   När huvudplaneringen genererar planerade order, har planerade order statusen **Obearbetad**.
-   Om du väljer att inte bekräfta en planerad order kan du ge den statusen **Slutförd**.
-   När du väljer att inte bekräfta en planerad order kan du ge den statusen **Godkänd**. Denna status betyder att du godkänner att den planerade ordern kan bekräftas, men att den ännu inte är bekräftad.

**Obs!** En godkänd planerad order överförs i sitt aktuella tillstånd till nästa huvudplaneringsberäkning. Bekräfta planerade order genom att klicka på **Bekräfta**. Följande planerade order kan bekräftas:

-   Planerade order som har valts .
-   Flera planerade order.
-   Planerade order som har genererats vid en nedbrytning från sidan **Nedbrytning**. Klicka på **Planerade order** och välj den planerade ordern och klicka sedan på **Bekräfta**.

När en planerad order är bekräftad flyttas den till den relevanta modulens orderavsnitt. 

<a name="additional-resources"></a>Ytterligare resurser
--------

[Huvudplaner](master-plans.md)




