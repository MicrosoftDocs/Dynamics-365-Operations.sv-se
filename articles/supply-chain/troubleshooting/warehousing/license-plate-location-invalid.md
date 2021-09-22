---
title: Ogiltigt ID-nummer eller ogiltig plats i mobilappen
description: När du skannar ett ID-nummer eller en plats kan du få ett felmeddelande om att det är ogiltigt. Se till att licensens ID-nummer inte har reserverats av något annat.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: f9f10dbade0d13b8fc4b0fc92981d84e6e28e83e
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477683"
---
# <a name="invalid-license-plate-or-location-error-when-scanning-in-the-mobile-app"></a>Ogiltigt ID-nummer eller ogiltig plats vid skanning i mobilappen

## <a name="symptoms"></a>Symtom

När du skannar ett ID-nummer eller en plats kan du få följane felmeddelande:

> Registreringsskylten eller platsen är inte giltig

## <a name="resolution"></a>Lösning

Se till att licensens ID-nummer inte har reserverats av något annat. Det här problemet uppstår när värdet som en användare skannade i mobilappen för distributionslagerhantering var både en giltig plats och ett giltigt licensens ID-nummer. Det här problemet löstes emellertid i versionen 10.0.11.
