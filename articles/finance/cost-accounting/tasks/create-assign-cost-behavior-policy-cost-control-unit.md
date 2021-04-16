---
title: Skapa och tilldela en kostnadsbeteendepolicy till en kostnadsstyrenhet
description: Kostnadsbeteende är klassificeringen av kostnader som fasta eller rörliga.
author: ShylaThompson
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CAMCostBehaviorRule
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 757e5a5be94e7190f4dbb51d667dc8adec4b824a
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5826333"
---
# <a name="create-and-assign-a-cost-behavior-policy-to-a-cost-control-unit"></a>Skapa och tilldela en kostnadsbeteendepolicy till en kostnadsstyrenhet

[!include [banner](../../includes/banner.md)]

Kostnadsbeteende är klassificeringen av kostnader som fasta eller rörliga. En policy och motsvarande regler måste tilldelas till en kostnadsstyrenhet för att policyn ska börja gälla. Använd den här proceduren när du vill skapa en policy och sedan tilldela den till en kostnadsstyrenhet.


## <a name="create-a-cost-behavior-hierarchy"></a>Skapa en hierarki för kostnadsbeteende
1. Gå till Kostnadsredovisning > Dimensioner > Dimensionshierarkier.
2. Klicka på Ny.
3. Klicka på Skapa.
4. Skriv "Cost behavior hierarchy" i fältet Dimensionshierarkins namn.
5. Ange eller välj ett värde i fältet Dimension.
    * Välj Kostnadselement.  
6. Klicka på Spara.
7. Klicka p Visa hierarki
8. Klicka på Ny.
9. Skriv ett värde i fältet för nodnamn.
    * Ange fast kostnad.  
10. Välj Cost behavior hierarchy i trädet.
11. Klicka på Ny.
12. Skriv ett värde i fältet för nodnamn.
    * Ange rörlig kostnad.  
13. Klicka på Spara.
14. Välj Cost behavior hierarchy\Fixed cost i trädet.
15. Klicka på Ny.
16. Markera vald rad i listan.
17. Ange eller välj ett värde i fältet Från dimensionsmedlem.
    * Intervallet med dimensionsmedlemmar får innehålla luckor men medlemmarna får inte överlappa.  
18. Ange eller välj ett värde i fältet Till dimensionsmedlem.
    * Intervallet med dimensionsmedlemmar får innehålla luckor men medlemmarna får inte överlappa.  
19. Välj Cost behavior hierarchy\Variable cost i trädet.
20. Klicka på Ny.
21. Markera vald rad i listan.
22. Ange eller välj ett värde i fältet Från dimensionsmedlem.
    * Intervallet med dimensionsmedlemmar får innehålla luckor men medlemmarna får inte överlappa.  
23. Ange eller välj ett värde i fältet Till dimensionsmedlem.
    * Intervallet med dimensionsmedlemmar får innehålla luckor men medlemmarna får inte överlappa.  
24. Klicka på Spara.

## <a name="create-the-policy-and-rules"></a>Skapa policyn och regler
1. Gå till Kostnadsredovisning > Policyer > Kostnadsbeteendepolicyer.
2. Klicka på Ny.
3. Skriv ett värde i fältet Policynamn.
4. Ange eller välj ett värde i fältet Dimensionshierarki för kostnadselement.
    * Välj policyhierarkin som du just har skapat.  
5. Ange eller välj ett värde i fältet Dimensionshierarki för kostnadsobjekt.
    * Välj Organisation.  
6. Klicka på Spara.
7. Klicka på Ny.
8. Markera vald rad i listan.
9. Ange eller välj ett värde i fältet Dimensionshierarkinod för kostnadselement.
    * Expandera hela hierarkin för att Rörlig kostnad.  
10. Ange eller välj ett värde i fältet Dimensionshierarkinod för kostnadsobjekt.
    * Som standard är den rörliga procentandelen 100 procent.  
11. Klicka på Policytilldelningar för kostnadsstyrenhet.
12. Klicka på Ny.
13. Markera vald rad i listan.
14. Ange ett datum i fältet Gäller från redovisningsdatum.
    * Reglerna gäller utifrån datum och en regel kan upphöra att gälla genom en användare eller systemet om en nyare version skapas.  
15. Ange eller välj ett värde i fältet Kostnadsstyrenhet.
16. Klicka på Spara.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]