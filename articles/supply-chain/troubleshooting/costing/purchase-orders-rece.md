---
title: Fysiskt mottagna inköpsorder visas inte i lagerstängningsrapporten
description: Fysiskt mottagna inköpsorder visas inte i lagerstängningsrapporten Kontrollera öppna kvantiteter.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventOpenQtyCritical
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 9508d6d75d8ebee7ca10140ed4c4215d7ad1dda7
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026915"
---
# <a name="physically-received-purchase-orders-dont-appear-on-the-inventory-closing-report"></a>Fysiskt mottagna inköpsorder visas inte i lagerstängningsrapporten

KB-nummer: 4612595

## <a name="symptoms"></a>Symtom

Fysiskt mottagna inköpsorder visas inte i lagerstängningsrapporten **Kontrollera öppna kvantiteter**.

## <a name="resolution"></a>Upplösning

Rapporten **Kontrollera öppna kvantiteter** visar utleveranstransaktioner som inte kan kvittas mot ekonomiskt uppdaterade lagerinleveranser per det valda slutdatumet. Du kan välja att inkludera fysiska inleveranser i rapporten. I så fall visas fysiska inleveranser om de kan täcka utleveranstransaktionerna som inte kan kvittas. Mer information finns i [Förbered körning av stängning av lager](/dynamicsax-2012/appuser-itpro/preparing-to-run-inventory-close).
