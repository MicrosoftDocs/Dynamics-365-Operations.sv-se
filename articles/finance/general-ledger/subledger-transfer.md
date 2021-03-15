---
title: Överför delredovisning till redovisningen
description: Det här ämnet beskriver funktionerna i Microsoft Dynamics 365 Finance som rör överföringsprocessen för delredovisningen i redovisningen.
author: roschlom
manager: AnnBe
ms.date: 09/09/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2020-01-18
ms.dyn365.ops.version: AX 10.0.8
ms.openlocfilehash: de9328f69938151c5558d41263d36b873d117e4b
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4975493"
---
# <a name="subledger-transfer-to-the-general-ledger"></a>Överför delredovisning till redovisningen

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs funktioner i Microsoft Dynamics 365 Finance som är relaterade till reglerna för överföring av delredovisningsjournalposter.

I version 8.1 gjordes ändringar för att tillåta överföring av regler, vilket föråldrade alternativet **Synkront**. Mer information finns i [borttagna eller gamla funktioner för Finance and Operations](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/migration-upgrade/deprecated-features?toc=/dynamics365/finance/toc.json#finance-and-operations-81-with-platform-update-20).

Följande alternativ är tillgängliga för överföring av delredovisningsbatchar. 

 - Asynkron – det här alternativet schemalägger omedelbart överföringen av delredovisningstransaktionerna till redovisningen. Redovisningsverifikationen registreras så snart resurser är fria att bearbeta denna begäran på servern. 

- Tidsplanerad batch – med det här alternativet läggs delredovisning poster för redovisningen till som överförs till bearbetningskön i redovisningen, där posterna kommer att bearbetas i inlevererade order. Redovisningsverifikationen registreras på den schemalagda tiden om resurser är fria att bearbeta detta batchjobb på servern. 
 
I version 10.0.8 har förbättringar gjorts för att förbättra prestanda för alternativet Asynkront. Den här funktionen aktiveras under funktionsnamnet **Prestandaoptimering för överföring av delredovisning till redovisning**. 
 
Den här funktionen gör det enklare att överföra data från delredovisningen till redovisningen. Det gör att processen blir effektivare och grupper av mindre transaktioner som kan överföras till varandra. På så sätt kan du använda batch-servern mer effektivt. Denna funktion kräver att batch-servern ställs in online och fungerar för att det asynkrona överföringsalternativet ska fungera. 


[!INCLUDE[footer-include](../../includes/footer-banner.md)]