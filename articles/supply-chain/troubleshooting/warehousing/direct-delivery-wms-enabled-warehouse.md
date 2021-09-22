---
title: Direktleverans går inte att bearbeta för WMS-aktiverat lagerställe
description: Om lagerstället har WMS aktiverat stöder det inte direktleverans. Om du vill använda direktleverans måste du välja en icke-WMS artikel och lagerställe.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 090e17091e9fb92c2065679bb9b04637214e2eea
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477684"
---
# <a name="direct-delivery-not-able-to-process-for-wms-enabled-warehouse"></a>Direktleverans går inte att bearbeta för WMS-aktiverat lagerställe

## <a name="symptoms"></a>Symtom

Om en artikel läggs till på en försäljningsrad för direktleverans från ett lagerställe som är aktiverat för lagerstyrning (WMS) visas följande felmeddelande när försäljningsraden uppdateras:

> Direktleverans kan inte bearbetas för lagerställe 1% eftersom det har lagerstyrning aktiverat. Ange ett annat lagerställe som inte är aktiverat för lagerstyrning.

## <a name="resolution"></a>Lösning

Microsoft har utvärderat det här problemet och har fastställt att det är en funktionsbegränsning. För närvarande stöder inte WMS direktleverans. Om du vill använda direktleverans måste du därför välja en icke-WMS artikel och lagerställe.
