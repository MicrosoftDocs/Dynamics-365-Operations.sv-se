---
title: Flera lagertransaktioner för batchnummer när Vid fysisk uppdatering avaktiveras
description: Flera lagertransaktioner skapas efter att du har justerat en inköpsorderrad för artiklar där alternativet Vid fysisk uppdatering för batchnummergruppen är inställt på Nej.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventNumGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 1fa54cdfdbc5608fb6c7114dced0f96bab47253e
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026929"
---
# <a name="multiple-inventory-transactions-for-batch-numbers-when-on-physical-update-is-disabled"></a>Flera lagertransaktioner för batchnummer när Vid fysisk uppdatering avaktiveras

KB-nummer: 4613390

## <a name="symptoms"></a>Symtom

Flera lagertransaktioner skapas efter att du har justerat en inköpsorderrad för artiklar där alternativet **Vid fysisk uppdatering** för batchnummergruppen är inställt på *Nej*.

När du skapar en artikel där alternativet **Vid fysisk uppdatering** för batchnummergruppen är insätllt på *Nej* skapar systemet automatiskt ett nytt batchnummer om du ändrar kvantitet på en inköpsrad och sparar inköpsordersidan.

## <a name="resolution"></a>Upplösning

Inställningen **Vid fysisk uppdatering** för batchnummergrupper fungerar på följande sätt:

- När alternativet är inställt på *Ja* skapas nya batchnummer endast efter en fysisk uppdatering (till exempel när artiklar skickas eller tas emot).
- När alternativet är inställt på *Nej* skapas ett nytt batchnummer varje gång en tillämplig uppdatering sker (till exempel när en ny kvantitet läggs till i en inköpsorder).
