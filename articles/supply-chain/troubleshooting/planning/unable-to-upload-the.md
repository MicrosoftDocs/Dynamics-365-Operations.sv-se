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
ms.openlocfilehash: c8ea8322a6c7bafe2dfcaaee3e9989f753c85e2a
ms.sourcegitcommit: c011a2ef66b38e71ddaf003f7d243677bb2707c5
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "6026919"
---
# <a name="you-cant-update-the-forecasted-unit-cost-when-you-import-demand-forecast-records"></a>Du kan inte uppdatera den prognostiserade enhetskostnaden när du importerar poster för efterfrågeprognoser

KB-nummer: 4614109

## <a name="symptoms"></a>Symtom

När du använder dataenheter för att importera poster för efterfrågeprognoser, uppdateras inte värdet **Prognostiserad enhetskostnad** för befintliga poster så att den matchar importerade data.

## <a name="cause"></a>Orsak

**Prognostiserad enhetskostnad** är ett skrivskyddat fält. Värdet baseras på produktenhetskostnaden och kan inte ställas in direkt via import.

## <a name="resolution"></a>Upplösning

Eftersom fältet är skrivskyddat kan du inte importera värden för det. Värdet beräknas enligt den befintliga affärslogiken.
