---
title: Produktionsplanering tar inte hänsyn till säkerhetsmarginalerna
description: Vid produktionsplaneringen beaktas inte de säkerhetsmarginaler som ställs in för artikeldisponering för peggad leverans
author: ChristianRytt
ms.date: 05/31/2021
ms.topic: troubleshooting
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: crytt
ms.search.validFrom: 2021-05-31
ms.dyn365.ops.version: 10.0.13
ms.openlocfilehash: 738296b7570ded0a4ee806e4445204a68e6a08c8
ms.sourcegitcommit: 2d6e31648cf61abcb13362ef46a2cfb1326f0423
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/07/2021
ms.locfileid: "7477611"
---
# <a name="production-scheduling-doesnt-consider-the-safety-margins"></a>Produktionsplanering tar inte hänsyn till säkerhetsmarginalerna

## <a name="symptoms"></a>Symtom

Huvudplaneringen tar hänsyn till säkerhetsmarginalerna. Säkerhetsmarginalerna ignoreras dock när planerade tillverkningsorder planeras.

## <a name="resolution"></a>Lösning

Marginaler beaktas endast vid huvudplanering, inte vid manuell tidsplanering. Marginaler är utformade för att fungera som buffert under planeringsfasen, vilket ger en del "marginal" för den faktiska processen.

Du kan få önskat resultat genom att ta bort marginalen. Flödet måste sedan uppdateras så att det innehåller önskad tid (t.ex. kötid). Samma resultat skapas då i både huvudplanering och manuell planering.
