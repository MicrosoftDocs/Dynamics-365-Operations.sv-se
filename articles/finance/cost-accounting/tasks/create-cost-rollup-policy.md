---
title: Skapa en policy för samlade kostnader
description: Nedan beskrivs proceduren att skapa en policy för samlad kostnad och skapa regler för den policyn.
author: ShylaThompson
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 50a50dc359dc4c2741ac4d280a9f97c6a7f2c259
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5810030"
---
# <a name="create-a-cost-rollup-policy"></a>Skapa en policy för samlade kostnader

[!include [banner](../../includes/banner.md)]

Nedan beskrivs proceduren att skapa en policy för samlad kostnad och skapa regler för den policyn. De demonstrationsdata som används för att skapa den här proceduren är USP2.


## <a name="create-a-policy"></a>Skapa en policy
1. Gå till Kostnadsredovisning > Policyer > redovisningPolicyer för samlade kostnader.
2. Klicka på Ny.
3. Skriv ett värde i fältet Policynamn.
4. Ange ett värde i fältet Beskrivning.
5. Ange eller välj ett värde i fältet Dimensionshierarki för kostnadsobjekt.
    * Välj Samlade kostnader CC.  
6. Ange eller välj ett värde i fältet Dimensionshierarki för kostnadselement.
    * Välj Samlade kostnader CC.  
7. Klicka på Spara.

## <a name="create-rules-for-the-cost-rollup-policy"></a>Skapa regler för policyn för samlad kostnad
1. Klicka på Ny.
2. Markera vald rad i listan.
3. Ange eller välj ett värde i fältet Dimensionshierarkinod för kostnadsobjekt.
    * Välj 007.  
4. Ange eller välj ett värde i fältet Dimensionshierarkinod för kostnadselement.
    * Välj Samlade kostnader CE.  
5. Ange eller välj ett värde i fältet Sekundärt kostnadselement.
    * I det här exemplet ska du mappa det sekundära kostnadselementet CC-007 till kostnadsstället.  
6. Klicka på Ny.
7. Markera vald rad i listan.
8. Ange eller välj ett värde i fältet Dimensionshierarkinod för kostnadsobjekt.
    * Välj 008.  
9. Ange eller välj ett värde i fältet Dimensionshierarkinod för kostnadselement.
    * Välj Samlade kostnader CE.  
10. Ange eller välj ett värde i fältet Sekundärt kostnadselement.
    * I det här exemplet ska du mappa det sekundära kostnadselementet CC-008 till kostnadsstället.  
11. Klicka på Ny.
12. Markera vald rad i listan.
13. Ange eller välj ett värde i fältet Dimensionshierarkinod för kostnadsobjekt.
    * Välj 009.  
14. Ange eller välj ett värde i fältet Dimensionshierarkinod för kostnadselement.
    * Välj Samlade kostnader CE.  
15. Ange eller välj ett värde i fältet Sekundärt kostnadselement.
    * I det här exemplet ska du mappa det sekundära kostnadselementet CC-009 till kostnadsstället.  
    * Fortsätt tills alla kostnadsställen har mappats till deras motsvarande sekundära kostnadselement.  
16. Klicka på Spara.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]