---
title: När en faktisk/nominell kvanitet delas upp används minimikvantitet i stället för nominell kvantitet.
description: När en faktisk/nominell kvantitet delas upp i batchar använder fältet Plocka kvantitet den minsta kvantitet som har angetts för artikeln, inte den nominella kvantiteten.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: WMSPickingRegistration
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 185365ced5c4516d8fcdbdca88794d0078615888
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026924"
---
# <a name="when-a-catch-weight-quantity-is-split-minimum-quantity-is-used-instead-of-nominal-quantity"></a>När en faktisk/nominell kvanitet delas upp används minimikvantitet i stället för nominell kvantitet.

KB-nummer: 4612073

## <a name="symptoms"></a>Symtom

När en faktisk/nominell kvantitet delas upp i batchar använder fältet **Plocka kvantitet** den minsta kvantitet som har angetts för artikeln, inte den nominella kvantiteten.

## <a name="resolution"></a>Upplösning

Systemet beter sig som det är utformat. Systemet använder varje artikels minsta kvantitetsinställningar för plockning.
