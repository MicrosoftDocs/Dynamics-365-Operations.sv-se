---
title: "Tidsfönster"
description: "Du kan använda tidsfönster för att optimera planeringen av serviceorderraderna."
author: YuyuScheller
manager: AnnBe
ms.date: 02/20/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: SMATimeAgreement
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: Global
ms.author: YuyuScheller
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 4ea10e4c0fbfd21538bba16d2b01deb3e4b3a10d
ms.openlocfilehash: b7268870aa9065e4e52d936e819107094bad3663
ms.contentlocale: sv-se
ms.lasthandoff: 02/20/2018

---

# <a name="time-windows"></a>Tidsfönster  

[!INCLUDE [banner](../includes/banner.md)]

Du kan använda tidsfönster för att optimera planeringen av serviceorderraderna. Du kan ställa in systemet så att serviceorder skapas automatiskt. Du kan ansluta så många serviceorderrader som möjligt till så få serviceorder som möjligt utifrån de kriterier som anges av ett tidsfönster.

Tidsfönstret specificerar hur långt en serviceorderrad kan flyttas från dess beräkningsdatum. Det beräknade datumet är det datum när serviceorderraden har schemalagts. Datumet baseras på dess intervallinställning och den serviceperiod som du har definierat på sidan för **skapa serviceorder**. Du definierar ett tidsfönster med hjälp av värdena i tabellen som följer.

| Metod | beskrivning                                                                                                                                                                                                                                                                                           |
|--------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Vecka   | Det datum då serviceorderraden kan flyttas till en annan öppen dag i samma vecka som det ursprungliga beräkningsdatumet.                                                                                                                                                                                    |
| Månad  | Det datum då serviceorderraden kan flyttas till en annan öppen dag i samma månad som det ursprungliga beräkningsdatumet. Som exempel är 15 february 2017 beräkningsdatumet för en serviceorderrad. Serviceorderraden kan schemaläggas för en veckodag mellan den 1 februari och den 28 februari 2017. |
| Manuell | Du definierar det maximala antalet dagar före och efter det ursprungliga beräkningsdatumet som serviceorderraden kan flyttas till.                                                                                                                                                                           |

Om inget tidsfönster har angetts för en serviceavtalsrad måste serviceorderraden som hämtas från serviceavtalet köras exakt på det datum då det ursprungligen planerades.

## <a name="related-topics"></a>Relaterade ämnen

[Skapa tidsfönster](create-time-windows.md)


