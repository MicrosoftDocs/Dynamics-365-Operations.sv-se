---
title: "Stäng redovisningen vid periodslutet"
description: "Det här avsnittet beskrivs de uppgifter som normalt utförs vid en periodstängning för redovisningen."
author: RobinARH
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 14111
ms.assetid: cec9e039-c1a2-482c-bea6-e11d896eea9d
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9ef99caf4570969d2b920cec8b53669ce2094965
ms.openlocfilehash: a7b72dfa98758b14d303d09890bd46729b1cdbe9
ms.lasthandoff: 03/31/2017


---

# <a name="close-the-general-ledger-at-period-end"></a>Stäng redovisningen vid periodslutet

Det här avsnittet beskrivs de uppgifter som normalt utförs vid en periodstängning för redovisningen. 

I redovisningen kan du slutföra stängningsprocedurerna för en period eller ett år. Stängningsprocesser förbereder systemet för en ny period. Du måste köra Stäng årsslutsprocess för att förbereda systemet för ett nytt år. Varje organisation har olika processer och steg som utförs för en utgång. Här är några valfria åtgärder för avslutas:

-   Slutför alla uppgifter i alla andra moduler, som Kundreskontra, Leverantörsreskontra och Lager.
-   Kontrollera att alla journaler har bokförts.
-   Kör omräkningen i utländsk valuta för att skapa belopp för orealiserad vinst eller förlust.
-   Kvitta transaktioner för varje huvudbokskonto.
-   Behandla alla obligatorisk allokeringar.
-   Bokför periodslutsjusteringar manuellt.
-   Journalför transaktioner och granska rapporten **Redovisningsjournal**.
-   Utför en konsolidering genom att använda ett konsolideringsföretag eller en ekonomisk rapportering.
-   Generera bokslut för periodslutet genom att använda ekonomisk rapportering.
-   Ställ in redovisningsperioder på **Spärrad** så att ingen ytterligare bokföring sker. Du kan även begränsa en period till en viss användargrupp medan periodslutsaktiviteter sker för bättre kontroll. Det är inte bra att ange perioder som **permanent stängda**, eftersom du inte kan öppna en period som har stängts.

Finansiell period nära arbetsytan kan användas för att ordna och spåra aktiviteter som krävs för olika periodslut processer. Avser det [ekonomiska period nära arbetsytan](financial-period-close-workspace.md) och [årsslut nära](Year-end-close.md) avsnitt för mer information. 




