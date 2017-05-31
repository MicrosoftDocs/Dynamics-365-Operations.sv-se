---
title: "Underhåll planerade order"
description: "Den här artikeln innehåller information om hur du hanterar planerade order. Det beskriver hur du kan uppdatera statusen för planerade order, bekräfta dem och filtrera för planerade order som har samma status som en vald planerad order."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: YuyuScheller
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 19151
ms.assetid: 54123f4c-b4ca-4ce4-9358-b067aa04c968
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 94f6f28ec4b255930f84a27eb5394503ff59e4c0
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017


---

# <a name="maintain-planned-orders"></a>Underhåll planerade order

[!include[banner](../includes/banner.md)]


Den här artikeln innehåller information om hur du hanterar planerade order. Det beskriver hur du kan uppdatera statusen för planerade order, bekräfta dem och filtrera för planerade order som har samma status som en vald planerad order.

Du kan hantera planerade order från arbetsytan **Huvudplanering**, listan **Planerad order** eller listorna **Planerade produktionsorder**, **Planerade inköpsorder**och **Planerad överföring**. Du kan använda fältet **Status** för att följa dina framsteg. Följande värden används:

-   När huvudplaneringen genererar planerade order, har planerade order statusen **Obearbetad**.
-   Om du väljer att inte bekräfta en planerad order kan du ge den statusen **Slutförd**.
-   När du väljer att inte bekräfta en planerad order kan du ge den statusen **Godkänd**. Denna status betyder att du godkänner att den planerade ordern kan bekräftas, men att den ännu inte är bekräftad.

**Obs!** En godkänd planerad order överförs i sitt aktuella tillstånd till nästa huvudplaneringsberäkning. Bekräfta planerade order genom att klicka på **Bekräfta**. Följande planerade order kan bekräftas:

-   Planerade order som har valts .
-   Flera planerade order.
-   Planerade order som har genererats vid en nedbrytning från sidan **Nedbrytning**. Klicka på **Planerade order** och välj den planerade ordern och klicka sedan på **Bekräfta**.

När en planerad order är bekräftad flyttas den till den relevanta modulens orderavsnitt. **Obs!** Du kan högerklicka på en planerad order med en viss status och filtrera efter andra planerade order som har samma status. Den här funktionen är praktisk om du till exempel vill filtrera efter alla planerade order som har statusen **Godkänd** så att du sedan kan bekräfta dem.

<a name="see-also"></a>Se även
--------

[Huvudplaner](master-plans.md)




