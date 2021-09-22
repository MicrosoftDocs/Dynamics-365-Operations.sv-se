---
title: Gör lagerstatusändring för delkvantitetsarbete
description: På den här sidan beskrivs hur du skapar en menyartikel med de inställningar som behövs för att medarbetarna ska kunna göra en lagerstatusändring för delkvantitet av en batch.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 056ce412955808ddf126025ad917b874c54a5e62
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477582"
---
# <a name="enable-inventory-status-change-for-partial-quantity-work"></a>Aktivera lagerstatusändring för delkvantitetsarbete

## <a name="symptoms"></a>Symtom

Du behöver utföra en lagerstatusändring för en delkvantitet av en batch.

## <a name="resolution"></a>Lösning

Om du vill att arbetare ska kunna göra denna ändring kan du skapa ett menyalternativ för mobilappen för distributionslagerhantering. På sidan **Menyalternativ på mobil enhet** skapa (eller redigera) ett menyalternativ för följande inställningar:

- **Läge:** *arbete*
- **Använd befintligt arbete:** *Nej*
- **Arbetsskapandeprocess:** *Rörelse*
- **Visa lagerstatus:** *Ja*

Du kan ställa in andra fält på sidan efter behov.
