---
title: Problem med valutakonvertering för handelsavtal
description: Handelsavtalspriser räknas inte om enligt valutan när valutan skiljer sig åt på en inköpsorder
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
ms.openlocfilehash: 1b6dc36c5f5ee6b611eebd81f378399ce1748c63
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477596"
---
# <a name="trade-agreement-currency-conversion-issues"></a>Problem med valutakonvertering för handelsavtal

## <a name="symptoms"></a>Symtom

Handelsavtalspriser räknas inte om enligt valutan när valutan skiljer sig åt på en inköpsorder.

## <a name="resolution"></a>Lösning

Med funktionen *allmän valuta* kan du definiera priser och rabatter i bara en valuta. Du kan sedan konvertera till andra valutor efter behov. När konverteringen är klar kan funktionen dessutom automatiskt tillämpa smart avrundning.
