---
title: Bearbeta allokeringar
description: Det här avsnittet innehåller information om allokeringar, alternativen för att bearbeta dem i Microsoft Dynamics 365 Finance och hur de kan användas vid budgetplanering. Allokeringar används för att fördela belopp mellan flera redovisningskontokombinationer. De hjälper till att garantera att utgifter eller intäkter debiteras för rätt objekt i redovisningen.
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
ms.custom: 17361
ms.assetid: 04c8548a-0af9-492b-954b-946b4f8ca023
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 2a715fe2ae0cb32e523248ffb15bdde4b36bd01d
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4990224"
---
# <a name="process-allocations"></a>Bearbeta allokeringar

[!include [banner](../includes/banner.md)]

Det här avsnittet innehåller information om allokeringar, alternativen för att bearbeta dem och hur de kan användas vid budgetplanering. Allokeringar används för att fördela belopp mellan flera redovisningskontokombinationer. De hjälper till att garantera att utgifter eller intäkter debiteras för rätt objekt i redovisningen.

Följande funktioner stöder den här processen:

-   Fördela transaktionsbelopp manuellt genom att använda uppdelningsåtgärden i redovisningsfördelningarna eller genom att använda standardmallarna för ekonomiska dimensioner. Mer information finns i [Redovisningsfördelningar](../accounts-payable/accounting-distributions.md).
-   Fördela transaktionsbelopp automatiskt baserat på allokeringsvillkor som definieras för individuella huvudkonton. Allokeringskontoposter skapas för varje journal som baseras på procentsats och målhuvudbokskontot, när en redovisningspost uppfyller kriterierna som definieras som källhuvudbokskontot. Mer information finns i [allokeringsvillkor för huvudkonto](../general-ledger/main-account-allocation-terms.md)
-   Fördela redovisningssaldon eller fasta belopp automatiskt baserat på redovisningsallokeringsregler. Redovisningsallokeringsreglerna bearbetas periodvis med hjälp av allokeringsjournaler. Mer information finns i [Allokeringsregler](../general-ledger/ledger-allocation-rules.md).

###  <a name="allocations-in-budget-planning"></a>Allokeringar i budgetplanering

Redovisningsallokeringsregler kan användas för budgetplaner. När du använder allokeringsregler för redovisning i budgetplanering kommer allokeringsreglerna att fungera på samma sätt som i redovisningen, men källdata och måldata kommer från budgetplanen. Du kan manuellt välja redovisningsallokeringsregler som ska användas för budgetplaner. Alternativt kan du använda ett allokeringsschema som körs som en del i en arbetsflödesprocess.

> [!NOTE]
> Du kan inte använda koncerninterna redovisningsallokeringsregler för budgetplanering.



[!INCLUDE[footer-include](../../includes/footer-banner.md)]