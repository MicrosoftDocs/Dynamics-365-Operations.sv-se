---
title: Bearbeta allokeringar
description: Det här avsnittet innehåller information om allokeringar, alternativen för att bearbeta dem i Microsoft Dynamics 365 for Finance and Operations och hur de kan användas vid budgetplanering. Allokeringar används för att fördela belopp mellan flera redovisningskontokombinationer. De hjälper till att garantera att utgifter eller intäkter debiteras för rätt objekt i redovisningen.
author: ShylaThompson
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AccountingDistribution, LedgerAllocationRule, MainAccount
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 17361
ms.assetid: 04c8548a-0af9-492b-954b-946b4f8ca023
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9a1946875460e9dfafb481b288a6d6a10ba8931d
ms.sourcegitcommit: 8b4b6a9226d4e5f66498ab2a5b4160e26dd112af
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/01/2019
ms.locfileid: "1846809"
---
# <a name="process-allocations"></a>Bearbeta allokeringar

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller information om allokeringar, alternativen för att bearbeta dem i Microsoft Dynamics 365 for Finance and Operations och hur de kan användas vid budgetplanering. Allokeringar används för att fördela belopp mellan flera redovisningskontokombinationer. De hjälper till att garantera att utgifter eller intäkter debiteras för rätt objekt i redovisningen.

Microsoft Dynamics 365 for Finance and Operations finns följande funktioner för den här processen:

-   Fördela transaktionsbelopp manuellt genom att använda uppdelningsåtgärden i redovisningsfördelningarna eller genom att använda standardmallarna för ekonomiska dimensioner. Mer information finns i [Redovisningsfördelningar](../accounts-payable/accounting-distributions.md).
-   Fördela transaktionsbelopp automatiskt baserat på allokeringsvillkor som definieras för individuella huvudkonton. Allokeringskontoposter skapas för varje journal som baseras på procentsats och målhuvudbokskontot, när en redovisningspost uppfyller kriterierna som definieras som källhuvudbokskontot.
-   Fördela redovisningssaldon eller fasta belopp automatiskt baserat på redovisningsallokeringsregler. Redovisningsallokeringsreglerna bearbetas periodvis med hjälp av allokeringsjournaler. 

###  <a name="allocations-in-budget-planning"></a>Allokeringar i budgetplanering

Redovisningsallokeringsregler kan användas för budgetplaner. När du använder allokeringsregler för redovisning i budgetplanering kommer allokeringsreglerna att fungera på samma sätt som i redovisningen, men källdata och måldata kommer från budgetplanen. Du kan manuellt välja redovisningsallokeringsregler som ska användas för budgetplaner. Alternativt kan du använda ett allokeringsschema som körs som en del i en arbetsflödesprocess.

> [!NOTE]
> Du kan inte använda koncerninterna redovisningsallokeringsregler för budgetplanering.





