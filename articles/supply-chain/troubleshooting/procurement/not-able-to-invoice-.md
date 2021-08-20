---
title: Du kan inte fakturera en kundutställd försäljningsorder
description: Du kan inte längre fakturera den ursprungliga försäljningsordern och den ursprungliga inköpsordern för direktleverans när du har aktiverat alternativet Bokför faktura automatiskt.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: SalesEditLines
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 30c485be79be5ebbec8b51272b8bbe6e0c7df9d81bbaaaef316dbfede03abf68
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6756761"
---
# <a name="you-cant-invoice-a-customer-facing-sales-order"></a>Du kan inte fakturera en kundutställd försäljningsorder

KB-nummer: 4611793

## <a name="symptoms"></a>Symtom

Du kan inte längre fakturera den ursprungliga försäljningsordern och den ursprungliga inköpsordern för direktleverans när du har aktiverat alternativet **Bokför faktura automatiskt** på sidan **Koncernintern** för en leverantör.

## <a name="resolution"></a>Upplösning

Synkroniseringsbeteendet för koncerninterna och direkta leveransorderfakturor styrs och tvingas av de parametrar som beskrivs i [Ställ in parametrar för att bokföra en koncernintern order](/dynamicsax-2012/appuser-itpro/set-up-parameters-to-post-an-intercompany-order).

När du har angett dessa parametrar måste du fakturera den koncerninterna försäljningsordern först. Ursprungliga försäljningsorder och inköpsorder synkroniseras sedan.
