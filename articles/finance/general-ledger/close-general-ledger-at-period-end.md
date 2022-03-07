---
title: Stäng redovisningen vid periodslutet
description: Det här avsnittet beskriver de uppgifter som normalt slutförs vid en periodstängning av redovisningen.
author: aprilolson
manager: AnnBe
ms.date: 08/01/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerPeriodCloseWorkspace
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 14111
ms.assetid: cec9e039-c1a2-482c-bea6-e11d896eea9d
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5cabdce5e23704fbf12e631a138235174ebc5772
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/13/2020
ms.locfileid: "4448003"
---
# <a name="close-the-general-ledger-at-period-end"></a>Stäng redovisningen vid periodslutet

[!include [banner](../includes/banner.md)]

Det här avsnittet beskriver de uppgifter som normalt slutförs vid en periodstängning av redovisningen. 

I redovisningen kan du slutföra stängningsprocedurerna för en period eller ett år. Stängningsprocesser förbereder systemet för en ny period. För att förbereda systemet för ett nytt år måste du köra processen för årsslutet. Varje organisation har olika processer och steg som utförs i samband med ett periodslut. Här följer några valfria steg för periodslut:

-   Slutför alla uppgifter i alla andra moduler, som Kundreskontra, Leverantörsreskontra och Lager.
-   Kontrollera att alla journaler har bokförts.
-   Kör omräkningen i utländsk valuta för att skapa belopp för orealiserad vinst eller förlust.
-   Kvitta transaktioner för varje huvudbokskonto.
-   Behandla alla obligatorisk allokeringar.
-   Bokför periodslutsjusteringar manuellt.
-   Journalför transaktioner och granska rapporten **Redovisningsjournal**.
-   Utför en konsolidering genom att använda ett konsolideringsföretag eller en ekonomisk rapportering.
-   Generera bokslut för periodslutet genom att använda ekonomisk rapportering.
-   Ställ in redovisningsperioder på **Spärrad** så att ingen ytterligare bokföring sker. Du kan även begränsa en period till en viss användargrupp medan periodslutsaktiviteter sker för bättre kontroll. Det är ingen god idé att ange en period som **Permanent stängd**, detta eftersom du inte på nytt kan öppna en period som har stängts.

Arbetsytan för ett finansiellt periodslut kan användas för att organisera och spåra de aktiviteter som krävs för olika periodslutsprocesser. 


Mer information finns i följande avsnitt:
- [Arbetsyta för räkenskapsperiodens stängning](financial-period-close-workspace.md) 
- [Årsbokslut](Year-end-close.md)  
- [Masstäng räkenskapsperiod](tasks/mass-financial-period-close.md)




