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
ms.openlocfilehash: 6f796bdaa88d32b1c58dd8a4bca19f0ce4f3943d
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026926"
---
# <a name="the-last-tested-date-field-isnt-updated-when-multiple-quality-orders-are-created"></a>Fältet Senaste testdatum uppdateras inte när flera kvalitetsorder skapas

KB-nummer: 4612803

## <a name="symptoms"></a>Symtom

Fältet **Senaste testdatum** uppdateras inte när flera kvalitetsorder skapas.

## <a name="resolution"></a>Upplösning

Systemet beter sig som det är utformat. Det senaste testdatumet är inte relaterat till kvalitetsorder. Här lagras det datum då de färdiga varorna först köpts in eller tillverkats. Detta datum används för att beräkna hållbarhetstid.
