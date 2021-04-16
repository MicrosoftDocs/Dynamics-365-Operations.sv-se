---
title: Underhåll planerade order
description: Detta avsnitt innehåller information om hur du hanterar planerade order. Det beskriver hur du kan uppdatera statusen för planerade order, bekräfta dem och filtrera för planerade order som har samma status som en vald planerad order.
author: roxanadiaconu
ms.date: 12/10/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqTransPo, ReqTransFirmLog
audience: Application User
ms.reviewer: kamaybac
ms.custom: 19151
ms.assetid: 54123f4c-b4ca-4ce4-9358-b067aa04c968
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7f97dc4627f9bb3a0ac2020b966de7e58aafcedc
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5833675"
---
# <a name="maintain-planned-orders"></a>Underhåll planerade order

[!include [banner](../includes/banner.md)]

Detta avsnitt innehåller information om hur du hanterar planerade order. Det beskriver hur du kan uppdatera statusen för planerade order, bekräfta dem och filtrera för planerade order som har samma status som en vald planerad order.

Du kan hantera planerade order från arbetsytan **Huvudplanering**, listan **Planerad order** eller listorna **Planerade produktionsorder**, **Planerade inköpsorder** och **Planerad överföring**. 

## <a name="planned-order-status"></a>Status på planerad order
Du kan använda fältet **Status** för att följa dina framsteg. Följande värden används:

-   När huvudplaneringen genererar planerade order, har planerade order statusen **Obearbetad**.
-   Om du väljer att inte bekräfta en planerad order kan du ge den statusen **Slutförd**.
-   Om du vill bekräfta en planerad order kan du ändra statusen till **godkänd**. Planerade order med status **godkänd** respekteras i huvudplaneringen, så att de inte ändras eller tas bort under en senare huvudplaneringskörning. För att uppnå detta kopierar planeringslogiken de **godkända** planerade orderna från den gamla planversionen till den nya planversionen under huvudplaneringen.

## <a name="firming-planned-orders"></a>Bekräfta planerade order 
Genom att bekräfta planerade order skapas verkliga order. Dessa är också kända som *frisläppta* eller *öppna order*. När en planerad order är bekräftad flyttas den till den relevanta modulens orderavsnitt.

Du kan välja två bekräftelsealternativ på sidan **planerade order**:

-   **Bekräfta** – detta kommer att bekräfta en eller flera valda planerade order.
-   **Bekräfta alla** – bekräfta alla planerade order i filtret. Med **bekräfta allt** behöver du inte välja den planerade ordern, alla bekräftas inom filtret. Det här alternativet kan vara användbart om du bekräftar ett stort antal planerade order.

> [!NOTE]
> Du kan spåra en planerad order som bekräftats genom att **Bekräftelsehistorik** under **Planerade orderformulär > Visa > Bekräftelsehistorik**.

## <a name="parallelize-firming"></a>Parallell bekräftelse
Om du planerar att bekräfta många order samtidigt kan körningstiden och prestandan öka under tiden för parallellt av körningen. Det här alternativet är tillgängligt när du bekräftar flera planerade order med antingen **bekräfta** eller **bekräfta alla**. Följande parametrar är tillgängliga:

-   **Parallelliseringsbekräftelse** – om **ja** kommer bekräftelseprocessen att vara parallell med antalet trådar som definierats i **antal trådar**.
-   **Antal trådar** – styr antalet trådar som används för att parallellisera bekräftelseprocessen. Parametern visas endast om **Parallelliseringsbekräftelse** anges till **Ja**.

> [!NOTE]
> Alternativet för **parallellisera bekräftelse** visas bara när du har mer än en planerad order som har valts för uppstramande.

<a name="additional-resources"></a>Ytterligare resurser
--------

[Huvudplaner – översikt](master-plans.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]