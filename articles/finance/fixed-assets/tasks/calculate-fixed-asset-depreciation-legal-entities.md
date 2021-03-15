---
title: Beräkna avskrivning av anläggningstillgången över juridiska personer
description: Avskrivning av anläggningstillgångar kan köras över juridiska personer i ett enda steg.
author: saraschi2
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetParameters, AssetProposalDepreciation, DefaultDashboard, LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8b09bbe4d0143aa521ca0a4cf67e86b7165b0f4f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4968964"
---
# <a name="calculate-fixed-asset-depreciation-across-legal-entities"></a>Beräkna avskrivning av anläggningstillgången över juridiska personer

[!include [banner](../../includes/banner.md)]

Avskrivning av anläggningstillgångar kan köras över juridiska personer i ett enda steg. Den här proceduren visar hur du ställer in och kör processen för flera juridiska personer. Här används revisorrollen och demonstrationsdata för den juridiska USMF-personen.


## <a name="set-up-cross-company-depreciation-run-journals"></a>Ställ avskrivningsjournaler som körs mellan företag.
1. Gå till Anläggningstillgångar > Inställning > Parametrar för anläggningstillgångar.
2. Expandera avsnittet Förslag på anläggningstillgång.
3. Klicka på Lägg till.
4. Ange bokföringsskikt eller välj ett värde i bokföringsfältet.
5. Ange eller välj ett värde i fältet Journal name.
    * Upprepa journalinställningen på sidan Parametrar för anläggningstillgångar i respektive juridisk person.  

## <a name="depreciation-run"></a>Avskrivningskörning
1. Gå till Anläggningstillgångar > Journalposter > Skapa avskrivningsförslag.
2. Ange bokföringsskikt eller välj ett värde i bokföringsfältet.
    * Journalnamnet hämtas som standard från parametrar för anläggningstillgångar. Det kan ändras här för den aktuella juridiska personen.  
3. Ange ett datum i fältet Till datum.
    * Välj de juridiska personerna som ska inkluderas i avskrivningskörningen.  
    * Endast juridiska personer med journaler som är inställda för Förslag på anläggningstillgång på sidan Parametrar för anläggningstillgånga visas i listan.  
4. Välj Ja i fältet Bokför journaler.
    * Filtrering av fält inkluderar alla anläggningstillgångar, grupper och böcker för de juridiska personerna som valts för denna avskrivning.  
    * Alternativet Batchbearbetning aktiveras som standard. När detta alternativ är aktiverat körs skapande och bokföring av avskrivningjournal i bakgrunden.  
5. Kicka på Skapa journal.
6. Gå till Anläggningstillgångar > Journalposter > Journal för anläggningstillgångar.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]