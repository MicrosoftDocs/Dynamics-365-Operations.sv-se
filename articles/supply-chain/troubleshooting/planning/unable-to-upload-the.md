---
title: Du kan inte uppdatera den prognostiserade enhetskostnaden när du importerar poster för efterfrågeprognoser
description: När du använder dataenheter för att importera poster för efterfrågeprognoser, uppdateras inte självkostnaden för befintliga poster så att den matchar importerade data.
author: ChristianRytt
ms.date: 4/11/2021
ms.topic: troubleshooting
ms.search.form: DataManagementWorkspace
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: angarmas
ms.search.validFrom: 2021-04-11
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: de471da861785f283eeaa78f97b5d1e1a6b023d71de6fff72ae39edd6bb124cc
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6765380"
---
# <a name="you-cant-update-the-forecasted-unit-cost-when-you-import-demand-forecast-records"></a>Du kan inte uppdatera den prognostiserade enhetskostnaden när du importerar poster för efterfrågeprognoser

KB-nummer: 4614109

## <a name="symptoms"></a>Symtom

När du använder dataenheter för att importera poster för efterfrågeprognoser, uppdateras inte värdet **Prognostiserad enhetskostnad** för befintliga poster så att den matchar importerade data.

## <a name="cause"></a>Orsak

**Prognostiserad enhetskostnad** är ett skrivskyddat fält. Värdet baseras på produktenhetskostnaden och kan inte ställas in direkt via import.

## <a name="resolution"></a>Upplösning

Eftersom fältet är skrivskyddat kan du inte importera värden för det. Värdet beräknas enligt den befintliga affärslogiken.
