---
title: Bearbeta allokeringar
description: "Artikeln innehåller information om fördelning alternativen för att bearbeta dem i Microsoft Dynamics 365 för operationer och hur de kan användas vid budgetplanering av. Allokeringar används för att fördela belopp mellan flera redovisningskontokombinationer. De hjälper till att garantera att utgifter eller intäkter debiteras för rätt objekt i redovisningen."
author: twheeloc
manager: AnnBe
ms.date: 2017-04-04
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: AccountingDistribution, LedgerAllocationRule, MainAccount
audience: Application User
ms.reviewer: annbe
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 17361
ms.assetid: 04c8548a-0af9-492b-954b-946b4f8ca023
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 9f4d7fdd8cfa7a540fce219f6ae4792e57dfbe44
ms.openlocfilehash: 37f4df5d0b79208a8c565bc9101ddde193a6ef5b
ms.lasthandoff: 03/31/2017


---

# <a name="process-allocations"></a>Bearbeta allokeringar

Artikeln innehåller information om fördelning alternativen för att bearbeta dem i Microsoft Dynamics 365 för operationer och hur de kan användas vid budgetplanering av. Allokeringar används för att fördela belopp mellan flera redovisningskontokombinationer. De hjälper till att garantera att utgifter eller intäkter debiteras för rätt objekt i redovisningen.

Microsoft Dynamics 365 för operationer ger följande fördelar för detta:

-   Manuellt allokera transaktionsbeloppen med åtgärden uppdelade i redovisningsfördelningarna eller genom att använda standardmallar för ekonomisk dimension till ett dokument. Mer information finns i [redovisningsfördelningar.](\accounts-payable\accounting-distributions.md)
-   Fördela transaktionsbelopp automatiskt baserat på allokeringsvillkor som definieras för individuella huvudkonton. Allokeringskontoposter skapas för varje journal som baseras på procentsats och målhuvudbokskontot, när en redovisningspost uppfyller kriterierna som definieras som källhuvudbokskontot.
-   Fördela redovisningssaldon eller fasta belopp automatiskt baserat på redovisningsallokeringsregler. Redovisningsallokeringsreglerna bearbetas periodvis med hjälp av allokeringsjournaler. 

###  <a name="allocations-in-budget-planning"></a>Allokeringar i budgetplanering

Redovisningsallokeringsregler kan användas för budgetplaner. När du använder allokeringsregler för redovisning i budgetplanering kommer allokeringsreglerna att fungera på samma sätt som i redovisningen, men källdata och måldata kommer från budgetplanen. Du kan manuellt välja redovisningsallokeringsregler som ska användas för budgetplaner. Alternativt kan du använda ett allokeringsschema som körs som en del i en arbetsflödesprocess.

> [!NOTE]
> Du kan inte använda koncerninterna redovisningsallokeringsregler för budgetplanering.




