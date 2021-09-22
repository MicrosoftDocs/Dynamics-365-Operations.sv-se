---
title: Inköpsorder återspeglar inte den juridiska personens språkinställningar
description: Produktnamnet på en inköpsorder visas på systemspråket i stället för språket som är inställt för den juridiska person där inköpsordern skapades
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
ms.openlocfilehash: 4deec493b5480dc570ac82876243bc31a2ae87aa
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477621"
---
# <a name="purchase-orders-dont-reflect-the-language-settings-of-the-legal-entity"></a>Inköpsorder återspeglar inte den juridiska personens språkinställningar


## <a name="symptoms"></a>Symtom

Produktnamnet på en inköpsorder visas på systemspråket i stället för språket som är inställt för den juridiska person där inköpsordern skapades.

## <a name="reproduce-the-issue"></a>Återskapa problemet

Följande procedur anger ett sätt att skapa reproducera problemet.

1. Ställ in system språket på *EN-US* (amerikansk engelska).
1. Kontrollera att det finns en produkt där *EN-US* och *DE* (tyska) språken finns kvar för översättningar av produktnamnet.
1. Ändra språket för en juridisk person till *DE*.
1. I den juridiska personen där *DE* har ställts in som språk skapar du en inköpsorder som innehåller produkten.
1. Observera att produktnamnet fortfarande visas i amerikansk engelska (systemspråket).

## <a name="resolution"></a>Lösning

Detta beteende är av design. På inköpsorder visas produkten alltid på systemspråket. Inköpsorderns språk används när en bekräftelsejournal skapas.
