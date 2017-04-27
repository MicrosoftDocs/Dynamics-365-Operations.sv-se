---
title: "Avskrivning av anläggningstillgång"
description: "Den här artikeln ger en översikt över avskrivning för anläggningstillgångar."
author: twheeloc
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: AssetBonus, AssetBookTable
audience: Application User
ms.search.scope: AX 7.0.0, Operations, Core
ms.custom: 3121
ms.assetid: 98ff891f-e0e2-4184-b618-28107a50851f
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
translationtype: Human Translation
ms.sourcegitcommit: 8e89a57dda8f2d392483ed13c686ea97b74926b0
ms.openlocfilehash: a16df710cfba4836cbc3531e09ca6eca933500c8
ms.lasthandoff: 03/31/2017


---

# <a name="fixed-asset-depreciation"></a>Avskrivning av anläggningstillgång

[!include[banner](../includes/banner.md)]


Den här artikeln ger en översikt över avskrivning för anläggningstillgångar.

Avskrivning är en periodisk transaktion som normalt minskar anläggningstillgångens värde i balansräkningen och debiteras som en utgift på ett resultatkonto. Därför används vanligtvis ett huvudkonto för att kreditera den periodiska avskrivningen i balansräkningen. Ett motkonto är ett konto i kontoplanens resultatdel.

## <a name="depreciation-adjustment"></a>Avskrivningsjustering
Vanligtvis bokförs bara en korrigering av en redan bokförd avskrivningstransaktion som en avskrivningsjustering. Därför ställs både huvudkontot och motkontot in på samma sätt som kontona för avskrivning. En avskrivningsjustering kan vara antingen ett positivt eller negativt belopp, men funktionen för huvudkontot (som balansräkningskonto) och motkontot (vanligtvis som ett resultatkonto) förblir oförändrad.

## <a name="extraordinary-depreciation"></a>Extraordinär avskrivning
En extraordinär avskrivning fungerar som en grundläggande avskrivning. Därför används ett huvudkonto används för att kreditera avskrivningsbeloppet till balansräkningen och minska värdet på anläggningstillgången. En motkonto är ett resultatkonto där avskrivningen som beräknas för räkenskapsperioden, debiteras som en utgift. 

Extraordinär avskrivning fungerar oberoende av den grundläggande avskrivningen. Genom att ha extraordinär avskrivning som en separat transaktionstyp kan du bokföra och rapportera den extraordinära avskrivningen separat från den grundläggande avskrivningen.

## <a name="special-depreciation-allowance"></a>Särskild avskrivning
Du kan använda särskilda avskrivningar för att ta extra- eller bonusavskrivningsbelopp under det första året som en tillgång tas i drift och skrivs av. Särskilda avskrivningar måste göras före andra avskrivningsberäkningar. Eftersom särskilda avskrivningar ofta är okända förrän senare under tjänstelivstiden för anläggningstillgången, är det bästa att använda den här typen av avskrivning med en bok som inte bokför i redovisningen. Du kan använda den periodiska funktionen Delete transactions not posted to general ledger för att radera transaktionshistoriken för dessa böcker. Du kan sedan ta bort avskrivninghistoriken för anläggningstillgångsboken, bokföra den särskilda avskrivningen när denna är känd, och sedan bokföra årets återstående avskrivningstransaktioner. 

Du kan skapa ett obegränsat antal poster för särskild avdragsavskrivning. När du har tilldelat dessa poster till en räkenskapsbok, appliceras dessa på tillgångsboken. 

En särskild avskrivning anges antingen som en procentsats eller som ett fast belopp. När du bokför avskrivningsförslag bokförs särskilda avskrivningar till boken som transaktioner som är separata från avskrivningstransaktionerna.

## <a name="depreciation-calendars"></a>Kalender för avskrivning
Varje bok har en kalender som används när du skriver av anläggningstillgångar. Boken använder redovisningskalendern som standard om du inte anger en kalender för boken. Du måste välja en räkenskapskalender för en bok när räkenskapsbokens associerade avskrivningsprofil använder ett räkenskapsår. 

Du kan skapa delade kalendrar genom att använda sidan **Fiscal calendars** i redovisningen.

Mer information finns i [Avskrivningsmetoder och avskrivningspraxis](depreciation-methods-conventions.md).




