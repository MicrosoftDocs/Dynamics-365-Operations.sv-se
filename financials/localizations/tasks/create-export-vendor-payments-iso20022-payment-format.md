--- 
title: "Skapa och exportera leverantörbetalningar med ett ISO20022-betalningsformat"
description: "Den här proceduren visar hur du kan skapa betalningsrader i leverantörbetalningsjournalen och generera en leverantörbetalningsfil med ett ISO2022-kreditöverföringsexempel."
author: mrolecki
manager: AnnBe
ms.date: 10/24/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: mrolecki
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 16c2af862a73047a2e6ebdc056275392fa8a0d93
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---
# <a name="create-and-export-vendor-payments-using-iso20022-payment-format"></a>Skapa och exportera leverantörbetalningar med ett ISO20022-betalningsformat

[!include[task guide banner](../../includes/task-guide-banner.md)]

Den här proceduren visar hur du kan skapa betalningsrader i leverantörbetalningsjournalen och generera en leverantörbetalningsfil med ett ISO2022-kreditöverföringsexempel. 

Det demonstrationsdataföretag som används för att skapa den här proceduren är DEMF.

Detta är den femte proceduren av fem som illustrerar leverantörbetalningsprocessen med hjälp av elektroniska rapporteringskonfigurationer. Denna procedur är avsedd för en funktion som lades till i Dynamics 365 for Operations version 1611.


## <a name="create-payment-lines"></a>Skapa betalningsrader
1. Gå till Leverantörsreskontra > Betalningar > Betalningsjournal.
2. Klicka på Ny.
3. Markera vald rad i listan.
4. Ange eller välj ett värde i fältet Namn.
5. Klicka på Rader.
6. Klicka på Betalningsförslag.
7. Klicka på Skapa betalningsförslag.
8. Expandera avsnittet Poster som ska ingå.
9. Klicka på Filter.
10. I listan markerar du raden för leverantörsregister och fältet för leverantörskonto.
11. Ange eller välj ett värde i fältet Kriterier.
    * Du kan använda vissa kriterier för urval av leverantörstransaktioner för betalning ‒ för detta exempel, använd DE-001 som leverantörskonto.  
12. Klicka på OK.
13. Klicka på OK.
14. Klicka på Skapa betalningar.

## <a name="generate-an-iso20022-payment-file"></a>Skapa en ISO20022-betalningsfil


