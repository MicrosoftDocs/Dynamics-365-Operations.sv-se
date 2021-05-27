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
ms.openlocfilehash: 707fa9bb30129c3656e10c6756dee770a7712e65
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026916"
---
# <a name="the-indirect-costs-in-process-report-includes-deleted-production-orders"></a>Rapporten Indirekta kostnader i processen innehåller borttagna produktionsorder

KB-nummer: 4612748

## <a name="symptoms"></a>Symtom

Rapporten **Indirekta kostnader i processen** innehåller information om produktionsorder som delvis bearbetats och senare tagits bort.

## <a name="resolution"></a>Upplösning

När du återför en produktionsorder återför du också alla transaktioner i produktionsordern. När du tar bort produktionsordern bevarar redovisningstabellerna och redovisningen alla transaktioner som är relaterade till den. Rapporterna visar transaktionerna i redovisningstabellerna. För den specifika produktionsordern ska nettovärdet vara 0,00.
