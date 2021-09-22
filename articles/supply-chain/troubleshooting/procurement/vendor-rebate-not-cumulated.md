---
title: En leverantörsrabatt ackumuleras inte grundat på fakturor
description: En leverantörsrabatt ackumuleras inte grundat på fakturor
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart, PurchRFQTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 9d4596a7351969bf181982a24ea1dcc6f5732831
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477675"
---
# <a name="a-vendor-rebate-isnt-cumulated-based-on-invoices"></a>En leverantörsrabatt ackumuleras inte grundat på fakturor

## <a name="symptoms"></a>Symtom

Om fakturor som bokförs har olika förfallodatum, återspeglas dessa fakturor inte i leverantörsrabatter som genereras från dem.

## <a name="resolution"></a>Lösning

Förfallodatumet beaktas inte när leverantörsrabatten beräknas. Överväg att anpassa systemet så att förfallodatumet och relationen till fakturan blir mer uppenbara när det gäller den faktiska leverantörsrabatten.
