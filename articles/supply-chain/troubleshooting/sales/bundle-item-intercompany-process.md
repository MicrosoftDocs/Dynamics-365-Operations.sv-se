---
title: Buntad artikel stöds inte i en koncernintern process
description: Den buntade artikeln är inte tillgänglig för inköp. Försäljningsordern köper bara komponenterna i den buntade artikeln inte själva buntade artikeln.
author: SmithaNataraj
ms.date: 06/24/2021
ms.topic: troubleshooting
ms.search.form: SalesTable, SalesTableListPage, SalesTableListPage_SalesCancelOrder
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 21adc7d071837b762157364f6f8ed370c69c7fd3
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477634"
---
# <a name="a-bundle-item-isnt-supported-in-an-intercompany-process"></a>En buntad artikel stöds inte i en koncernintern process

## <a name="symptoms"></a>Symtom

Buntad artikel är inte tillgänglig för inköpsordern eftersom du, om du granskar försäljningsorderraderna för buntad artikel ser du att kvantiteten är *0* (noll) och statusvärdet *annullerad*.

## <a name="resolution"></a>Lösning

Detta beteende är av design. Försäljningsordern köper endast komponenterna i buntad artikel. Den handlar inte om själva buntade artikeln. Om du måste köpa en buntad bör du fundera över om du måste markera det som buntad artikel, eftersom denna funktion verkligen är utformad för scenarier för intäktsredovisning. Mer information om buntad artikel, se [buntade](/dynamics365/finance/accounts-receivable/revenue-recognition-setup).
