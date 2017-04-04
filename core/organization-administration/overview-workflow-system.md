---
title: "Arbetsflöde: översikt"
description: "Den här artikeln beskrivs arbetsflödessystemet i Microsoft Dynamics 365 för operationer."
author: sericks007
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
audience: Application User, IT Pro
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 56381
ms.assetid: 20b78595-e1d9-439a-ae1c-a776a3438919
ms.search.region: Global
ms.author: tjvass
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 0c6a7bdc4ba82dd57ab3e395e6dfb0ae4de31fc4
ms.openlocfilehash: 08c36f02f88fef7508730b6c01a1c99a0f77fb0c
ms.lasthandoff: 03/31/2017


---

# <a name="workflow-system-overview"></a>Arbetsflöde: översikt

Den här artikeln beskrivs arbetsflödessystemet i Microsoft Dynamics 365 för operationer.

<a name="what-is-workflow"></a>Vad är ett arbetsflöde?
-----------------

Begreppet *arbetsflöde* kan definieras på två sätt: som ett system och som en affärsprocess.
### <a name="workflow-is-a-system"></a>Arbetsflödet som ett system

Arbetsflöde är ett system som installeras med Dynamics 365 för operationer och som körs på den programobjektserver (AOS). Arbetsflödessystemet innehåller funktioner som du kan använda när du vill skapa individuella arbetsflöden eller affärsprocesser.

### <a name="workflow-is-a-business-process"></a>Arbetsflödet som en affärsprocess

Ett arbetsflöde representerar en affärsprocess. Det definierar hur ett dokument flyttas genom systemet genom att visa vem som måste genomföra en uppgift, fatta ett beslut eller godkänna ett dokument. Till exempel visar följande bild ett arbetsflöde för utgiftsrapporter. ![Arbetsflöde med element som är tilldelade användare ](./media/workflow_user.gif)För att bättre förstå detta arbetsflöde, antar vi att Sam skickar in en utgiftsrapport på 70 000 kronor. I det här scenariot måste Ivan granska kvittona som Sam har skickat till honom. Sedan måste Frank och Sue godkänna utgiftsrapporten. Anta nu att Sam skickar en utgiftsrapport på 110 000 kronor. I det här scenariot måste Ivan granska kvittona och Frank, Sue och Ann måste godkänna utgiftsrapporten.
 Fördelar med att använda arbetsflödessystemet
-------------------------------------

Det finns flera fördelar med att använda arbetsflödessystemet i organisationen:
-   **Konsekventa processer** – Du kan definiera hur godkännandeprocessen för specifika dokument, till exempel inköpsrekvisitioner och utgiftsrapporter behandlas. Genom att använda arbetsflödessystemet ser du till att dokumenten bearbetas och godkänns på ett enhetligt och effektivt sätt.
-   **Processerna blir synliga** – Du kan spåra status, historik och prestandamått för arbetsflödesinstanser. Det blir då enklare att ta reda på om du bör göra ändringar för att höja effektiviteten.
-   **Centraliserad arbetslista** – Användarna kan ta fram en central arbetslista där de kan granska vilka uppgifter de har tilldelats i arbetsflödet.




