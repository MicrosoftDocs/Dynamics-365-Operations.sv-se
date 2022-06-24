---
title: Bearbeta journal för redovisningsallokering
description: I den här artikeln beskrivs hur du bearbetar en begäran om tilldelning i Dynamics 365 Finance.
author: aprilolson
ms.date: 07/26/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerAllocationRequest, LedgerJournalTable, LedgerJournalTransAllocation
audience: Application User
ms.reviewer: twheeloc
ms.search.region: Global
ms.author: aolson
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b86f8f5d090d624e812d9e7e6c0bc0212e5e9716
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8902441"
---
# <a name="process-ledger-allocation-journal"></a>Bearbeta journal för redovisningsallokering

[!include [banner](../../includes/banner.md)]

I den här artikeln beskrivs hur du bearbetar en begäran om tilldelning. Använd sidan Bearbeta allokeringsbegäran för att skapa en allokeringsjournal som kan granskas och godkännas före bokföringen, eller bokföras direkt i redovisningen. Innan du kan skapa en allokeringsjournal måste det finnas minst en aktiv redovisningsallokeringsregel. I den här uppgiften används demonstrationsföretaget USMF.

1. I navigeringsfönstret, gå till **Redovisning > Allokeringar > Bearbeta allokeringsbegäran**.
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
