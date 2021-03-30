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
ms.openlocfilehash: a52a5ce2d789757a11c9e443c7f25058bd9d8a91
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5222345"
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



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]