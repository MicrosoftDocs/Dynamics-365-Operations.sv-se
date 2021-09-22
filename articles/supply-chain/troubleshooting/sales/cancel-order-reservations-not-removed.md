---
title: Det går inte att ta bort reservationer när en order annulleras
description: Du kan inte annullera en försäljningsorder förrän arbetet som är associerat med orden har annullerats och återförts. Gör det genom att följa dessa tre steg.
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
ms.openlocfilehash: a8d947e64568246dba5eff3c21fd3920b6494b73
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477643"
---
# <a name="reservations-cannot-be-removed-when-canceling-an-order"></a>Det går inte att ta bort reservationer när en order annulleras

## <a name="symptoms"></a>Symtom

Om arbete associeras med en försäljningsorder och du försöker annullera den ordern visas följande felmeddelande:

> Du kan inte ta bort reservationer eftersom det finns skapade arbetsuppgifter som är beroende av reservationerna.

Du kan inte annullera försäljningsordern förrän arbetet har annullerats och återförts. Detta krav gäller även om det arbete som är kopplat till försäljningsordern stängs.

## <a name="resolution"></a>Lösning

Följ dessa steg om du vill åtgärda problemet:

1. Avbryt arbetet och sätt tillbaka lagret på önskad plats. Gå till relevant inläsning av försäljningsordern och välj antingen **minska plockad kvantitet** på lastraden eller **återför arbete** i åtgärdsfönstret.

    Arbetet har nu statusen *Annullerat* och nytt lagerrörelsearbete skapas och bearbetas automatiskt för att placera lagret på den plats som beskrivs vid tidpunkten för återföringen.

2. Ta bort lasten. Även leveransen tas bort.

3. Du bör nu kunna gå till försäljningsordern och annullera den.
