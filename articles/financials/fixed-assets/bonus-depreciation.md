---
title: Bonusavskrivning
description: "Det här avsnittet innehåller en översikt över funktionen för bonusavskrivning."
author: twheeloc
manager: AnnBe
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: AssetBonus
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.custom: 3621
ms.assetid: 835ec594-744e-461c-a676-1b9abc094173
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: d421b161216d700f7819f1da8c0ca8ad089b5670
ms.openlocfilehash: 414440332d313cfef72ce65ac3cd842d19390aad
ms.contentlocale: sv-se
ms.lasthandoff: 05/25/2017


---

# <a name="bonus-depreciation"></a>Bonusavskrivning

[!include[banner](../includes/banner.md)]


Det här avsnittet innehåller en översikt över funktionen för bonusavskrivning.

För bonusavskrivning kan du ta extra- eller bonusavskrivningsbelopp under det första året som tillgången tas i drift och skrivs av. Bonusavskrivning måste göras före andra avskrivningsberäkningar. Därför är det bäst att använda bonusavskrivning med böcker där funktionen Bokför i huvudboken har inaktiverats. Du kan använda alternativet **Radera transaktioner som inte har bokförts i redovisning** för att radera historiska transaktioner för böcker som inte bokförs i redovisningen. Du kan sedan tillgodose bonusavskrivningen senare i tillgångens livscykel genom att ta bort avskrivningstransaktioner som tidigare bokförts. 

Du kan beräkna bonusavskrivning med förslagsprocessen eller skapa manuella transaktioner för bonusavskrivningar. Du kan inte skapa transaktioner för bonusavskrivning om det finns transaktioner för avskrivning eller avskrivningsjustering för den tillgångsförteckningen.

När du använder förslagsprocessen för att beräkna bonusavskrivning tas alla befintliga bonustransaktioner med i beräkningen av basen. Beräkningen innefattar också eventuella tidigare bonusavskrivningar som du manuellt har angett för tillgången. 

Om mer än en bonusavskrivning ska göras för en tillgång tas hänsyn till prioriteten. Varje bonus reducerar tillgångsunderlaget för nästa bonus. Skrotvärdet räknas inte in i tillgångsunderlaget för beräkningar av bonusavskrivning, och avskrivningspraxis gäller inte för bonusavskrivningar. 

I USA räknas för närvarande viss egendom som paragraf 179-egendom. Genom att använda avdrag enligt paragraf 179 kan du skriva av hela eller en del av kostnaden för viss egendom, upp till en viss gräns. Du kan skriva av kostnaden genom att dra av den under det år då egendomen tas i drift.

## <a name="example"></a>Exempel
Följande bonusavskrivningar är associerade med en tillgångsförteckning:

-   **Paragraf 179:** 1 000,00, Prioritet 1
-   **Frihetszon:** 30 procent, Prioritet 2

Anskaffningskostnaden för tillgången är 5 000,00 $. När bonusavskrivningen beräknas blir det första bonusavskrivningsbeloppet 1 000,00 $ för paragraf 179-avskrivningen. 

Nästa bonusavskrivningsbelopp – för Liberty Zone-avskrivningen – beräknas enligt följande: 

Anskaffningskostnad – 1 000 (paragraf 179-avskrivning) x 30 % = 1 200 

Om bonusavskrivningsbeloppet överstiger resterande anskaffningskostnad, blir bonusavskrivningsbeloppet antingen resultatet av den beräknade bonusavskrivning eller den återstående anskaffningskostnaden (det lägre beloppet av dessa). 

Om resterande anskaffningskostnad är noll eller lägre kan bonusavskrivningstransaktionerna inte genereras. 

När bonusavskrivning beräknas med förslagsprocessen skapas en transaktion för bonusavskrivning för alla tillämpliga bonusavskrivningsposter som är associerade med tillgångsförteckningen. 

Du kan skapa ett obegränsat antal bonusavskrivningsposter. När du har tilldelat dessa poster till en räkenskapsbok, appliceras de på tillgångsförteckningen. 

Bonusavskrivning anges i procent eller som ett fast belopp. När du bokför avskrivningsförslag, bokförs transaktioner för bonusavskrivning till boken som transaktioner som är skilda från avskrivningstransaktionerna.



