---
title: Uppdatering av rapportera som färdig misslyckas med kvantitetsfel som saknas
description: Om du försöker avsluta en produktionsorder och rapporterar felkvantiteten men inte tid eller materialkvantitet, misslyckas uppdateringen av rapporterad som färdig.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 7785549c47063727f2749749940c1a96a351e70f
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477603"
---
# <a name="report-as-finished-update-fails-with-a-missing-quantity-error"></a>Uppdatering av rapportera som färdig misslyckas med kvantitetsfel som saknas

## <a name="symptoms"></a>Symtom

Du försöker rapportera en produktionsorder som färdig medan du rapporterar en felaktig kvantitet, men inte när du rapporterar tid eller materialkvantitet. Uppdateringen av rapportera som färdig misslyckas när du försöker avsluta produktionsordern och följande felmeddelande visas:

> Kvantitet saknad rapporterad som färdig.

## <a name="resolution"></a>Lösning

Om du rapporterar felkvantiteten i en produktionsorder måste du också rapportera den godkända kvantiteten.
