---
title: "Översikt över arbetsflödessystem"
description: "Det här ämnet beskriver arbetsflödessystemet i Microsoft Dynamics 365 for Finance and Operations."
author: sericks007
manager: AnnBe
ms.date: 04/25/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 56381
ms.assetid: 20b78595-e1d9-439a-ae1c-a776a3438919
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 1dc7935bf92567d529d393abf3069935a387e388
ms.contentlocale: sv-se
ms.lasthandoff: 06/13/2017


---

# Översikt över arbetsflödessystem
<a id="workflow-system-overview" class="xliff"></a>

[!include[banner](../includes/banner.md)]


Det här ämnet beskriver arbetsflödessystemet i Microsoft Dynamics 365 for Finance and Operations.

Vad är ett arbetsflöde?
<a id="what-is-workflow" class="xliff"></a>
-----------------

Begreppet *arbetsflöde* kan definieras på två sätt: som ett system och som en affärsprocess.
### Arbetsflödet som ett system
<a id="workflow-is-a-system" class="xliff"></a>

Arbetsflödet är ett system som är installerat i Finance and Operations och som körs på Application Object Server (AOS). Arbetsflödessystemet innehåller funktioner som du kan använda när du vill skapa individuella arbetsflöden eller affärsprocesser.

### Arbetsflödet som en affärsprocess
<a id="workflow-is-a-business-process" class="xliff"></a>

Ett arbetsflöde representerar en affärsprocess. Det definierar hur ett dokument flyttas genom systemet genom att visa vem som måste genomföra en uppgift, fatta ett beslut eller godkänna ett dokument. Till exempel visar följande bild ett arbetsflöde för utgiftsrapporter. 

![Arbetsflöde med element som tilldelas till användare](./media/workflow_user.gif) 

För att du ska få en bättre förståelse för det här arbetsflödet, anta att Sam skickar in en utgiftsrapport på 7 000 USD. I det här scenariot måste Ivan granska kvittona som Sam har skickat till honom. Sedan måste Frank och Sue godkänna utgiftsrapporten. Anta nu att Sam skickar en utgiftsrapport på 110 000 kronor. I det här scenariot måste Ivan granska kvittona och Frank, Sue och Ann måste godkänna utgiftsrapporten.

##  Fördelar med att använda arbetsflödessystemet
<a id="benefits-of-using-the-workflow-system" class="xliff"></a>

Det finns flera fördelar med att använda arbetsflödessystemet i organisationen:
-   **Konsekventa processer** – Du kan definiera hur godkännandeprocessen för specifika dokument, till exempel inköpsrekvisitioner och utgiftsrapporter behandlas. Genom att använda arbetsflödessystemet ser du till att dokumenten bearbetas och godkänns på ett enhetligt och effektivt sätt.
-   **Processerna blir synliga** – Du kan spåra status, historik och prestandamått för arbetsflödesinstanser. Det blir då enklare att ta reda på om du bör göra ändringar för att höja effektiviteten.
-   **Centraliserad arbetslista** – Användarna kan ta fram en central arbetslista där de kan granska vilka uppgifter de har tilldelats i arbetsflödet.


## Arbetsflödesinnehåll
<a id="workflow-content" class="xliff"></a>

+ [Arbetsflödesarkitektur](workflow-system-architecture.md)
+ [Arbetsflödeselement](workflow-elements.md)
+ [Arbetsflödesåtgärder](workflow-actions.md)
+ [Skapa ett arbetsflöde](create-workflow.md)
+ [Konfigurera arbetsflödesegenskaper](configure-workflow-properties.md)
+ [Konfigurera en manuell uppgift i ett arbetsflöde](configure-manual-task-workflow.md)
+ [Konfigurera en automatisk uppgift i ett arbetsflöde](configure-automated-task-workflow.md)
+ [Konfigurera en godkännandeprocess i ett arbetsflöde](configure-approval-process-workflow.md)
+ [Konfigurera ett godkännandesteg i ett arbetsflöde](configure-approval-step-workflow.md)
+ [Konfigurera ett manuellt beslut i ett arbetsflöde](configure-manual-decision-workflow.md)
+ [Konfigurera ett villkorsbeslut i ett arbetsflöde](configure-conditional-decision-workflow.md)
+ [Konfigurera en parallell aktivitet i ett arbetsflöde](configure-parallel-activity-workflow.md)
+ [Konfigurera en parallell gren i ett arbetsflöde](configure-parallel-branch-workflow.md)
+ [Konfigurera ett arbetsflöde för radartiklar](configure-line-item-workflow.md)

