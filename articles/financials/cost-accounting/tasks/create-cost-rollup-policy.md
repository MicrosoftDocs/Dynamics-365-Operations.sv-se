---
title: Skapa en policy för samlade kostnader
description: Nedan beskrivs proceduren att skapa en policy för samlad kostnad och skapa regler för den policyn.
author: ShylaThompson
manager: AnnBe
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 5f1fa434061832bd306cef13afc46c7f3adab0c0
ms.sourcegitcommit: 0f530e5f72a40f383868957a6b5cb0e446e4c795
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/29/2019
ms.locfileid: "362612"
---
# <a name="create-a-cost-rollup-policy"></a>Skapa en policy för samlade kostnader

[!include [task guide banner](../../includes/task-guide-banner.md)]

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

