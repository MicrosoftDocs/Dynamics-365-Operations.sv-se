---
title: Fältet Senaste testdatum uppdateras inte när flera kvalitetsorder skapas
description: Fältet Senaste testdatum uppdateras inte när flera kvalitetsorder skapas.
author: niwang
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: InventBatch
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: smnatara
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 46523c55f4fd42b0985397752f0c62a3e1a55e177f2308e20b7064e339758269
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6742038"
---
# <a name="the-last-tested-date-field-isnt-updated-when-multiple-quality-orders-are-created"></a>Fältet Senaste testdatum uppdateras inte när flera kvalitetsorder skapas

KB-nummer: 4612803

## <a name="symptoms"></a>Symtom

Fältet **Senaste testdatum** uppdateras inte när flera kvalitetsorder skapas.

## <a name="resolution"></a>Upplösning

Systemet beter sig som det är utformat. Det senaste testdatumet är inte relaterat till kvalitetsorder. Här lagras det datum då de färdiga varorna först köpts in eller tillverkats. Detta datum används för att beräkna hållbarhetstid.
