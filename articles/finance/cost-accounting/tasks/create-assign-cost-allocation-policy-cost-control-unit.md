---
title: Skapa och tilldela en kostnadsallokeringspolicy till en kostnadsstyrenhet
description: Använd den här proceduren när du vill skapa och tilldela en kostnadsallokeringspolicy och motsvarande regler för en kostnadsstyrenhet.
author: ShylaThompson
ms.date: 06/28/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CAMCostAccountingLedgerPolicyAssignment
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 1cff10132e8007be885e9c69d97cf96c30d69f50
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5822865"
---
# <a name="create-and-assign-a-cost-allocation-policy-to-a-cost-control-unit"></a>Skapa och tilldela en kostnadsallokeringspolicy till en kostnadsstyrenhet

[!include [banner](../../includes/banner.md)]

Använd den här proceduren när du vill skapa och tilldela en kostnadsallokeringspolicy och motsvarande regler för en kostnadsstyrenhet. I den här inspelningen används demonstrationsföretaget USP2.


## <a name="create-a-policy"></a>Skapa en policy
1. Gå till Kostnadsredovisning > Policyer > Kostnadsfördelningspolicyer.
2. Klicka på Ny.
3. Skriv ett värde i fältet Policynamn.
4. Ange eller välj ett värde i fältet Dimensionshierarki för kostnadsobjekt.
    * Välj Organisation.  
5. Ange eller välj ett värde i fältet Statistikdimension.
6. Klicka på Spara.

## <a name="create-allocation-rules"></a>Skapa allokeringsregler
1. Klicka på Ny.
2. Markera vald rad i listan.
3. Ange eller välj ett värde i fältet Dimensionshierarkinod för kostnadsobjekt.
4. Välj Summa i fältet Kostnadsbeteende.
5. Ange eller välj ett värde i fältet Allokeringsunderlag.
6. Klicka på Ny.
7. Markera vald rad i listan.
8. Ange eller välj ett värde i fältet Dimensionshierarkinod för kostnadsobjekt.
9. Välj Summa i fältet Kostnadsbeteende.
10. Ange eller välj ett värde i fältet Allokeringsunderlag.
11. Klicka på Ny.
12. Markera vald rad i listan.
13. Ange eller välj ett värde i fältet Dimensionshierarkinod för kostnadsobjekt.
14. Välj Summa i fältet Kostnadsbeteende.
15. Ange eller välj ett värde i fältet Allokeringsunderlag.
    * Fortsätt tills du har skapat alla regler.  
16. Klicka på Spara.

## <a name="assign-the-policy-to-a-cost-control-unit"></a>Tilldela policyn till en kostnadsstyrenhet
1. Klicka på Policytilldelningar för kostnadsstyrenhet.
2. Klicka på Ny.
3. Markera vald rad i listan.
4. Ange ett datum i fältet Gäller från redovisningsdatum.
    * Reglerna gäller utifrån datum. En användare eller systemet kan se till att reglerna upphör att gälla om det finns en nyare version.  
5. Ange eller välj ett värde i fältet Kostnadsstyrenhet.
6. Klicka på Spara.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]