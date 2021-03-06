---
title: Du får ett felmeddelande när du kör den inbyggda huvudplaneringsmotorn
description: När du kör den inaktuella inbyggda huvudplaneringsmotorn får du ett felmeddelande.
author: ankubik
ms.date: 06/10/2021
ms.topic: troubleshooting
ms.search.form: Dialog_ReqCalcScheduleItemTable
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: ankubik
ms.search.validFrom: 2021-06-10
ms.dyn365.ops.version: 10.0.20
ms.openlocfilehash: 9c950292a4f43319d21a7deafdfb341b7bef15d8
ms.sourcegitcommit: 18ca2df785e9656fdd4e8c0734eca2b2624fda10
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/22/2021
ms.locfileid: "6294183"
---
# <a name="you-receive-an-error-when-running-the-built-in-master-planning-engine"></a>Du får ett felmeddelande när du kör den inbyggda huvudplaneringsmotorn

Felkod: ReqCalcScheduleItemTablePlanningOptimizationFitError

## <a name="symptoms"></a>Symtom

När du kör huvudplanering med den inbyggda huvudplaneringsmotorn får du följande felmeddelande:

> Det här felmeddelandet visas eftersom den inbyggda huvudplaneringsmotorn användes för scenarier som stöds vid planeringsoptimering. Du bör migrera till planeringsoptimering nu eftersom den aktuella inbyggda huvudplaneringen är föråldrad. Observera att huvudplaneringskörningen slutfördes utan fel. Om migreringen har starka beroenden på väntande funktioner kan det krävas ett undantag till fortsatt användning av den inbyggda huvudplaneringsmotorn. Fyll i följande enkät för att komma igång och om relevant undantag från migreringen till planeringsoptimering. [Planera optimeringsmigrering och undantagsenkät](https://go.microsoft.com/fwlink/?linkid=2144962)

## <a name="cause"></a>Orsak

Om du kör planering och inte använder produktionskontrollfunktioner bör du migrera till Planeringsoptimering. Den inbyggda huvudplaneringsmotorn avaktiveras. Om du vill fortsätta att använda det utan att få felmeddelandet måste du därför ansöka om ett undantag från Microsoft.

## <a name="resolution"></a>Lösning

Mer information om hur du migrerar till Planeringsoptimering eller hur du ansöker om ett undantag så att du kan fortsätta att använda den inbyggda planeringsmotorn som avaktiveras finns i [Migrering till planeringsoptimering för huvudplanering](/dynamics365/supply-chain/master-planning/new-master-planning-engine).
