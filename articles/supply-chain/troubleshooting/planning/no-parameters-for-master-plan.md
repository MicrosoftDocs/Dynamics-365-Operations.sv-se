---
title: Parametrar för huvudplanen finns inte
description: När du försöker bekräfta planerade order visas ett felmeddelande som anger att inga parametrar finns för huvudplanen.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: ReqTransPo
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: d4b64af2e30109b8560d40c4c532504611528bbe
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294184"
---
# <a name="parameters-for-the-master-plan-dont-exist"></a>Parametrar för huvudplanen finns inte

Felkod: SYS25368

## <a name="symptoms"></a>Symtom

När du har bekräftat planerade order visas följande felmeddelande:

> Parametrar för huvudplan %1 finns inte.

## <a name="cause"></a>Orsak

På grund av konfigurationsproblem hittar systemet inte inställningarna för den angivna planen.

## <a name="resolution"></a>Lösning

- Gå till **Huvudplanering \> Inställningar \> Planer \> Huvudplaner** och se till att det finns en plan med det angivna namnet.
