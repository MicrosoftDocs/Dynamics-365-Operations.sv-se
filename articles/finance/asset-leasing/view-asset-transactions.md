---
title: Visa skuld-, tillgångs- och utgiftstransaktioner
description: I det här ännet beskrivs hur du visar transaktioner för en leasad tillgång. Dessa transaktioner inkluderar leasingskuldtransaktioner och för verkställighetskostnadstransaktioner som har bokförts.
author: moaamer
manager: Ann Beebe
ms.date: 10/28/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations, Retail
ms.custom: 4464
ms.assetid: 5f89daf1-acc2-4959-b48d-91542fb6bacb
ms.search.region: Global
ms.author: moaamer
ms.search.validFrom: 2020-10-28
ms.dyn365.ops.version: 10.0.14
ms.openlocfilehash: 7008891d194dc990d13a9f56db155c6990aae0c0
ms.sourcegitcommit: aeee39c01d3f93a6dfcf2013965fa975a740596a
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/28/2020
ms.locfileid: "4448221"
---
# <a name="view-liability-asset-and-expense-transactions"></a>Visa skuld-, tillgångs- och utgiftstransaktioner

[!include [banner](../includes/banner.md)]

I det här ännet beskrivs hur du visar transaktioner för en leasad tillgång. Dessa transaktioner inkluderar leasingskuldtransaktioner och för verkställighetskostnadstransaktioner som har bokförts. De bokförda värdena för skulden och ROU-tillgången används i flera rapporter. De används också för att beräkna justeringsvärden.

## <a name="liability-transactions"></a>Skuldtransaktioner

Om du vill visa leasingskuldtransaktionerna väljer du en leasing på sidan **Sammanfattning av leasing** och väljer sedan **Böcker** för att öppna de böcker som är kopplade till leasingposten. Efter att ett första redovisningstillfälle, en faktura eller en räntejournal har bokförts väljer du **Skuldtransaktioner**.

På sidan **Skuldtransaktioner** visas de transaktioner som antingen ökar eller minskar leasingskulden. Negativa belopp på den här sidan representerar kredittransaktioner i standardprogrammet. Eventuella upplupna räntor redovisas som negativa värden och ökar den totala leasingskulden. Eventuella leasingjusteringar visas som positiva eller negativa värden, beroende på leasingbokens art och verkan. Det aktuella nettosaldot för leasingskulden för vald leasing visas längst ned till vänster på sidan.

## <a name="asset-transactions"></a>Tillgångstransaktioner

Om du vill visa leasingtillgångstransaktionerna väljer du en leasing på sidan **Sammanfattning av leasing** och väljer sedan **Böcker** för att öppna de leasingböcker som är kopplade till leasingposten. Välj sedan **Transaktioner för tillgångar**.

På sidan **Transaktion för tillgångar** visas de transaktioner som antingen ökar eller minskar leasingtillgången och ackumulerade avskrivningskonton. Debet visas som positiva värden och kredit visas som negativa värden, som på sidan **Skuldtransaktioner**. Den bokförda initiala redovisningen och nästa ackumulerade avskrivning visas längst ned till vänster på sidan som tillgångssaldot. 

## <a name="expenses-transactions"></a>Utgiftstransaktioner

Om du vill visa leasingutgiftstransaktionerna väljer du en leasing på sidan **Sammanfattning av leasing** och väljer sedan **Böcker** för att öppna de leasingböcker som är kopplade till leasingposten. Välj sedan **Utgiftstransaktioner**.

På sidan **Utgiftstransaktioner** visas alla utgifter som har bokförts mot leasingen, till exempel räntekostnader, avskrivningskostnader och eventuella verkställighetskostnader.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]