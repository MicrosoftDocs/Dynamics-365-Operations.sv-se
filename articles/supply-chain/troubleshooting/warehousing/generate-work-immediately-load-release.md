---
title: Generera plockningsarbete direkt när last frisläpps
description: Om arbete måste genereras direkt när lasten frigörs måste du konfigurera påfyllningsmallen i enlighet med detta. På den här sidan går du genom stegen.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: fdeb0b27f4d2c1a2cc9f8e0c4ba537cdce604bd2
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477650"
---
# <a name="picking-work-isnt-generated-immediately-when-outbound-load-is-released"></a>Plockningsarbete genereras inte direkt när utgående beläggning frisläpps

## <a name="symptoms"></a>Symtom

Du skapar en utgående last genom att använda en försäljnings- eller överföringsorder och frisläppa lasten till lagerstället. Men du observerar att inget plockningsarbete har skapats ännu.

## <a name="resolution"></a>Lösning

Om arbete måste genereras direkt när lasten frigörs måste du konfigurera påfyllningsmallen i enlighet med detta. Ställ in följande alternativ på påfyllningsmallen *Ja*:

- Automatisera skapande av påfyllnad
- Bearbeta påfyllnaden vid släpp till lager
- Automatisera släpp av påfyllnad
