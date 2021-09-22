---
title: Orderstatus förblir Delvis släppt även efter att den har fakturerats
description: I vissa fäll kan statusen för en försäljningsorder förbli Delvis frisläppt även när ordern har fakturerats. På den här sidan förklaras varför och en möjlig lösning.
author: perlynne
ms.date: 06/24/2021
ms.topic: troubleshooting
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2021-06-24
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 8bfe7ecfd4beb6e77e8dd1e23ccd896d067bdb51
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477642"
---
# <a name="order-status-remains-partially-released-even-after-the-sales-order-is-invoiced"></a>Orderstatus förblir Delvis släppt även efter att försäljningsordern har fakturerats

## <a name="symptoms"></a>Symtom

En försäljningsorder är en leveransorder, men en eller flera artiklar på den har ett annat leverans sätt. När ordern har fakturerats har den fortfarande frisläppningsstatus som *delvis släppts*.

En försäljningsorder har till exempel två artiklar: en för leverans och en för upphämtning. Både leveransen och upphämtningen har utförts. Därför har båda raderna fakturerats. Frisläppnings status visas fortfarande som *delvis utsläppt*, vilket är missvisande.

## <a name="workaround"></a>Lösning

Frisläppningsstatus gäller bara för orderrader där artiklarna är aktiverade för lagerstyrning. Därför fortsätter frisläppningsstatusen att vara *delvis släppts* i det här scenariot. Microsoft har utvärderat det här problemet och har fastställt att det är en funktionsbegränsning. Ett tillägg kan läggas till som en del av följesedeln och faktureringsprocessen för att uppdatera frisläppningsstatus.
