---
title: Importerade inköpsorder visar felaktiga radnummer
description: När inköpsorder importeras via datahantering följer inte inköpsordernummer det steg som definieras i systemparametrar
author: kamaybac
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: PurchTable, PurchTablePart
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: yanansong
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: e1cf5cf1d04824213f495ac3ebf556796c96611a
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477587"
---
# <a name="imported-purchase-orders-show-incorrect-line-numbers"></a>Importerade inköpsorder visar felaktiga radnummer

## <a name="symptoms"></a>Symtom

Som standard genereras automatiskt radnummer för inköpsorderrader som importeras via dataentiteten *Inköpsorderrader V2* använder inte det systemradnummer som anges i systemparametrar. Om du skapar en inköpsorder manuellt och lägger till rader via användargränssnittet (UI), ökas radnumren korrekt. Om du använder DMF (ramverk för datahantering) ökas de emellertid inte korrekt.

Det här problemet beror på att när du importerar rader via DMF, om radnummer inte redan har tilldelats i den importerade enheten, använder systemet DMF-metoden för att tilldela dem. Den metoden ökar alltid radnummer med en.

## <a name="workaround"></a>Lösning

Kontrollera att de önskade radnumren redan ges i fälten för radnummer för dataenhet när du importerar inköpsorderraderna. I det här fallet skrivs inte radnumren över med DMF.
