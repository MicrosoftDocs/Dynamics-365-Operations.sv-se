---
title: Bearbeta journal för redovisningsallokering
description: I det här avsnittet beskrivs hur du bearbetar en begäran om tilldelning i Dynamics 365 Finance.
author: aprilolson
manager: AnnBe
ms.date: 07/26/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerAllocationRequest, LedgerJournalTable, LedgerJournalTransAllocation
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0a7e8c3ef6fa85daec2a191b433b1ec4ece441ee
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4968489"
---
# <a name="process-ledger-allocation-journal"></a>Bearbeta journal för redovisningsallokering

[!include [banner](../../includes/banner.md)]

I det här avsnittet beskrivs hur du bearbetar en begäran om tilldelning. Använd sidan Bearbeta allokeringsbegäran för att skapa en allokeringsjournal som kan granskas och godkännas före bokföringen, eller bokföras direkt i redovisningen. Innan du kan skapa en allokeringsjournal måste det finnas minst en aktiv redovisningsallokeringsregel. I den här uppgiften används demonstrationsföretaget USMF.

1. I navigeringsfönstret, gå till **Moduler > Redovisning > Allokeringar > Bearbeta allokeringsbegäran**.
2. I fältet **Regel** väljer du önskad post i listrutan.
3. Ange ett datum i fältet **Från och med (datum).**

    - **Från och med**-datumet är mycket viktigt när redovisningen är datakällan för regeln. Detta datum styr vilka redovisningssaldon som ska inkluderas för allokering.  
    - I fältet **Noll urspr.belopp** väljer du **Stoppa**. När du gör det stoppas allokeringsprocessen och ett meddelande visa som anger att ett nollbelopp har valts.  

4. Välj **Enbart förslag** i fältet **Förslagsalternativ**. Välj **Enbart förslag** för att granska och eventuellt godkänna resultatet i allokeringsjournalerna innan du bokför allokeringen i redovisningen.  
5. Ange ett datum i fältet Datum för bokföring i huvudbok.
6. Välj **OK**.
7. I navigeringsfönstret, gå till **Moduler > Redovisning > Allokeringar > Allokeringsjournaler**.
8. Markera **rader**
9. Vald **bokföring**
10. Vald **bokföring**

