---
title: Tidsfönster
description: Du kan använda tidsfönster för att optimera planeringen av serviceorderraderna.
author: ShylaThompson
manager: tfehr
ms.date: 02/20/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMATimeAgreement
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2f64718e6a96cacc005644cbf4286e743111c02f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4996512"
---
# <a name="time-windows"></a>Tidsfönster  

[!include [banner](../includes/banner.md)]

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



[!INCLUDE[footer-include](../../includes/footer-banner.md)]