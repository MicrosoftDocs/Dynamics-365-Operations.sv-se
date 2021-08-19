---
title: Överför delredovisning till redovisningen
description: Det här ämnet beskriver funktionerna som rör överföringsprocessen för delredovisningen i redovisningen.
author: rcarlson
ms.date: 07/20/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 03c04a5eb8b544b582019ddd204382900b162d952842c901f69ed4a853bd8183
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6716655"
---
# <a name="subledger-transfer-to-the-general-ledger"></a>Överför delredovisning till redovisningen

[!include [banner](../includes/banner.md)]

I det här avsnittet beskrivs funktioner som är relaterade till reglerna för överföring av delredovisningsjournalposter.

I version 8.1 gjordes ändringar för att tillåta överföring av regler, vilket föråldrade alternativet **Synkront**. Mer information finns i [borttagna eller gamla funktioner för Finance and Operations](../../fin-ops-core/dev-itpro/migration-upgrade/deprecated-features.md?toc=%2fdynamics365%2ffinance%2ftoc.json#finance-and-operations-81-with-platform-update-20).

Följande alternativ är tillgängliga för överföring av delredovisningsbatchar:

- **Asynkron** – Överför av delredovisningstransaktionerna till redovisningen schemaläggs omedelbart. Redovisningsverifikationen registreras så snart resurser är fria att bearbeta denna begäran på servern.
- **Tidsplanerad batch** – Bokföringsposterna som måste överföras läggs till i behandlingskön i huvudbok. Posterna i kön bearbetas i den ordning de kommer in. Redovisningsverifikationen kommer att uppdatera kontona på den schemalagda tiden om resurser är fria att bearbeta detta batchjobb på servern.

I version 10.0.8 har förbättringar gjorts för att förbättra prestanda för alternativet **Asynkront**. Den här funktionen aktiveras under funktionsnamnet **Prestandaoptimering för överföring av delredovisning till redovisning**.

Funktionerna för asynkron överföring av redovisningsbatchar underlättar överföringen av data från redovisningen till redovisningen. Genom att gruppera uppsättningar med mindre transaktioner och överföra transaktioner i grupper, bearbetar funktionerna transaktionerna på ett mer effektivt sätt. När transaktioner grupperas används batchserverns resurser på ett effektivare sätt.

Asynkron överföring av underbearbetningsbatchar kräver att batchservern ställs in, är online och arbetar. Annars fungerar inte **Asynkrona** överföringsalternativet.

Effektivitetsändringen på batchnivå använder ett enda återkommande batchjobb för alla juridiska personer i systemet. Vid körning skapas ett nytt batchjobb för bearbetning av de obligatoriska poster som ännu inte har överförts. Fler inställningar kan kontrolleras från sidan **Processautomatisering** i systemadministration. På den sidan kan du ändra bakgrundsprocessen, ändra frekvensen och definiera en period.

Mer information om inställning av processautomatisering finns i [processautomatisering](../../fin-ops-core/dev-itpro/sysadmin/process-automation.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
