---
title: Arbetsflödessystem – översikt
description: Det här ämnet beskriver arbetsflödessystemet.
author: ChrisGarty
manager: AnnBe
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User, IT Pro
ms.reviewer: sericks
ms.custom: 56381
ms.assetid: 20b78595-e1d9-439a-ae1c-a776a3438919
ms.search.region: Global
ms.author: cgarty
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 660e01618eea66bc611dd51818694d36993ba9ea
ms.sourcegitcommit: b112925c389a460a98c3401cc2c67df7091b066f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/19/2020
ms.locfileid: "4797006"
---
# <a name="workflow-system-overview"></a>Arbetsflödessystem – översikt

[!include [banner](../includes/banner.md)]

Det här ämnet beskriver arbetsflödessystemet.

## <a name="what-is-workflow"></a>Vad är ett arbetsflöde?

Begreppet *arbetsflöde* kan definieras på två sätt: som ett system och som en affärsprocess.

### <a name="workflow-is-a-system"></a>Arbetsflödet som ett system

Arbetsflöde är ett system som körs på programobjektservern (AOS). Arbetsflödessystemet innehåller funktioner som du kan använda när du vill skapa individuella arbetsflöden eller affärsprocesser.

### <a name="workflow-is-a-business-process"></a>Arbetsflödet som en affärsprocess

Ett arbetsflöde representerar en affärsprocess. Det definierar hur ett dokument flyttas genom systemet genom att visa vem som måste genomföra en uppgift, fatta ett beslut eller godkänna ett dokument. Till exempel visar följande bild ett arbetsflöde för utgiftsrapporter.

![Arbetsflöde med element som tilldelas till användare](./media/workflow_user.gif)

För att du ska få en bättre förståelse för det här arbetsflödet, anta att Sam skickar in en utgiftsrapport på 7 000 USD. I det här scenariot måste Ivan granska kvittona som Sam har skickat till honom. Sedan måste Frank och Sue godkänna utgiftsrapporten. Anta nu att Sam skickar en utgiftsrapport på 110 000 kronor. I det här scenariot måste Ivan granska kvittona och Frank, Sue och Ann måste godkänna utgiftsrapporten.

## <a name="benefits-of-using-the-workflow-system"></a> Fördelar med att använda arbetsflödessystemet

Det finns flera fördelar med att använda arbetsflödessystemet i organisationen:

- **Konsekventa processer** – Du kan definiera hur godkännandeprocessen för specifika dokument, till exempel inköpsrekvisitioner och utgiftsrapporter behandlas. Genom att använda arbetsflödessystemet ser du till att dokumenten bearbetas och godkänns på ett enhetligt och effektivt sätt.
- **Processerna blir synliga** – Du kan spåra status, historik och prestandamått för arbetsflödesinstanser. Det blir då enklare att ta reda på om du bör göra ändringar för att höja effektiviteten.
- **Centraliserad arbetslista** – Användarna kan ta fram en central arbetslista där de kan granska vilka uppgifter de har tilldelats i arbetsflödet.


## <a name="workflow-content"></a>Arbetsflödesinnehåll

+ [Arbetsflödessystemets arkitektur](workflow-system-architecture.md)
+ [Arbetsflödeselement](workflow-elements.md)
+ [Åtgärder i godkännandeprocesser i ett arbetsflöde](workflow-actions.md)
+ [Skapa arbetsflöden – översikt](create-workflow.md)
+ [Konfigurera arbetsflödesegenskaper](configure-workflow-properties.md)
+ [Konfigurera manuella uppgifter i ett arbetsflöde](configure-manual-task-workflow.md)
+ [Konfigurera automatiska uppgifter i ett arbetsflöde](configure-automated-task-workflow.md)
+ [Konfigurera godkännandeprocesser i ett arbetsflöde](configure-approval-process-workflow.md)
+ [Konfigurera godkännandesteg i ett arbetsflöde](configure-approval-step-workflow.md)
+ [Konfigurera manuella beslut i ett arbetsflöde](configure-manual-decision-workflow.md)
+ [Konfigurera villkorsbeslut i ett arbetsflöde](configure-conditional-decision-workflow.md)
+ [Konfigurera parallella aktiviteter i ett arbetsflöde](configure-parallel-activity-workflow.md)
+ [Konfigurera parallella grenar i ett arbetsflöde](configure-parallel-branch-workflow.md)
+ [Konfigurera arbetsflöden för radartiklar](configure-line-item-workflow.md)
+ [Vanliga frågor om arbetsflöde](workflow-FAQ.md)
