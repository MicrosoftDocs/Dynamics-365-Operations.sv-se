---
title: Rapporten Indirekta kostnader i processen innehåller borttagna produktionsorder
description: Rapporten Indirekta kostnader i processen innehåller information om produktionsorder som delvis bearbetats och senare tagits bort.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: ProdIndirectCostInProgress
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 817802f1f2ad3ab07f35c28d3e833a14cd02cf8b9705c576325dc83933a0c6de
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6751779"
---
# <a name="the-indirect-costs-in-process-report-includes-deleted-production-orders"></a>Rapporten Indirekta kostnader i processen innehåller borttagna produktionsorder

KB-nummer: 4612748

## <a name="symptoms"></a>Symtom

Rapporten **Indirekta kostnader i processen** innehåller information om produktionsorder som delvis bearbetats och senare tagits bort.

## <a name="resolution"></a>Upplösning

När du återför en produktionsorder återför du också alla transaktioner i produktionsordern. När du tar bort produktionsordern bevarar redovisningstabellerna och redovisningen alla transaktioner som är relaterade till den. Rapporterna visar transaktionerna i redovisningstabellerna. För den specifika produktionsordern ska nettovärdet vara 0,00.
