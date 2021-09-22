---
title: Det går inte att konsolidera flera produktinleveranser till en enda inköpsorder
description: Du kan inte konsolidera flera produktinleveranser till en enda inköpsorder om de olika produktinleveranser raderna har olika redovisningsdatum.
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
ms.openlocfilehash: 485306279281ceb55a140526f4216af35574af42
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477601"
---
# <a name="you-cant-consolidate-multiple-product-receipts-into-a-single-purchase-order"></a>Det går inte att konsolidera flera produktinleveranser till en enda inköpsorder

## <a name="symptoms"></a>Symtom

Du kan inte konsolidera flera produktinleveranser till en enda inköpsorder om de olika produktinleveranser raderna har olika redovisningsdatum.

## <a name="resolution"></a>Lösning

I tidigare versioner av Dynamics 365 Supply Chain Management var konsolideringen tillåten i den här situationen. Men övningen är benägen för fel. Redovisningsdatumet på inköpsorderraderna som skapas ska inte skilja sig från redovisningsdatumet på de produktinleveranser som dessa inköps orderrader skapades från. (Redovisningsdatumet på inköpsorderraderna matchar redovisningsdatumet i inköpsorderrubriken.) Därför är konsolideringen av flera produktinleveranser i en enskild inköpsorder inte längre tillåten.

Redovisningsdatumet används till exempel för budgetreservationer och inteckning. Därför bör den behållas under övergången från produktinleverans till inköpsorder.
