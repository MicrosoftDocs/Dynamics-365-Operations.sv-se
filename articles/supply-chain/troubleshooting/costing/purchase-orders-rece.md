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
ms.openlocfilehash: 49faa2c68d496c5c0d8c7e4abfd93d9a917857220dd23c09a050fa3436e1d49a
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6746877"
---
# <a name="physically-received-purchase-orders-dont-appear-on-the-inventory-closing-report"></a>Fysiskt mottagna inköpsorder visas inte i lagerstängningsrapporten

KB-nummer: 4612595

## <a name="symptoms"></a>Symtom

Fysiskt mottagna inköpsorder visas inte i lagerstängningsrapporten **Kontrollera öppna kvantiteter**.

## <a name="resolution"></a>Upplösning

Rapporten **Kontrollera öppna kvantiteter** visar utleveranstransaktioner som inte kan kvittas mot ekonomiskt uppdaterade lagerinleveranser per det valda slutdatumet. Du kan välja att inkludera fysiska inleveranser i rapporten. I så fall visas fysiska inleveranser om de kan täcka utleveranstransaktionerna som inte kan kvittas. Mer information finns i [Förbered körning av stängning av lager](/dynamicsax-2012/appuser-itpro/preparing-to-run-inventory-close).
