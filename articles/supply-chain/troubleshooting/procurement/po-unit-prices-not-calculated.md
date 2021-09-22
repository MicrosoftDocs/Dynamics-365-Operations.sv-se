---
title: Enhetspriser på inköpsorder beräknas inte grundat på enhetskonverteringen
description: Enhetspriser på inköpsorder beräknas inte grundat på enhetskonverteringen
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
ms.openlocfilehash: 4695f4661c3abb8ab38e3ca74b513e8529e37d20
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477627"
---
# <a name="unit-prices-on-purchase-orders-arent-calculated-based-on-the-unit-conversion"></a>Enhetspriser på inköpsorder beräknas inte grundat på enhetskonverteringen

## <a name="symptoms"></a>Symtom

När en enhet ändras på en inköpsorder räknas inte handelsavtalets priser om enligt enhetskonverteringens definitioner.

## <a name="cause"></a>Orsak

Priser hämtas alltid från handelsavtal (eller andra prisinställningar i systemet, t.ex. försäljningsavtal eller artikelpriser) och ställs in för en enhet.

Om enheten ändras på en orderrad letar systemet efter ett pris för den nya enheten och tillämpar det priset. Om det inte finns något pris för enheten tillämpar inte systemet priset. Enhetskonverteringen kan inte användas för att räkna om priset till en annan enhet. Teoretiskt sett får priset för en ruta på tio inte vara lika med tio gånger priset för en ruta.

## <a name="workaround"></a>Lösning

Ett sätt att undvika det här problemet är att se till att det finns handelsavtal för enheterna som du förväntar dig kommer att använda på orderrader för artikeln.
