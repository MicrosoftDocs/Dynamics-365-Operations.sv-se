---
title: Skapa och tilldela en kostnadsfördelningspolicy till en kostnadsstyrenhet
description: Kostnadsfördelningsregler används för att fördela kostnader som räknats ekonomiskt i ett samlat kostnadsställe.
author: ShylaThompson
ms.date: 06/27/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: CAMCostDistributionRule
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 9230410d7b8cd4c94fdab5465e542e16fd286c530a8189d5cd1eca825bb1faf4
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6772861"
---
# <a name="create-and-assign-a-cost-distribution-policy-to-a-cost-control-unit"></a>Skapa och tilldela en kostnadsfördelningspolicy till en kostnadsstyrenhet

[!include [banner](../../includes/banner.md)]

Kostnadsfördelningsregler används för att fördela kostnader som räknats ekonomiskt i ett samlat kostnadsställe. Kostnadsrevisorn säkerställer att kostnaderna fördelas till kostnadsställena utifrån det valda allokeringsunderlaget. En princip och motsvarande regler tilldelas en kostnadsstyrenhet. I den här uppgiftsguiden används ett exempel för att lära dig skapa en kostnadsfördelningspolicy och motsvarande regler.


## <a name="create-a-policy"></a>Skapa en policy
1. Gå till Kostnadsredovisning > Policyer > Kostnadsfördelningspolicyer.
2. Klicka på Ny.
3. Skriv ett värde i fältet Policynamn.
4. Ange ett värde i fältet Beskrivning.
5. Ange eller välj ett värde i fältet Dimensionshierarki för kostnadsobjekt.
    * Välj Organisation.  
6. Ange eller välj ett värde i fältet Dimensionshierarki för kostnadselement.
    * Välj CDS P/L.  
7. Ange eller välj ett värde i fältet Statistikdimension.
    * Välj Statistiska element.  
8. Klicka på Spara.

## <a name="create-rules-for-the-policy"></a>Skapa regler för policyn
1. Klicka på Ny.
2. Markera vald rad i listan.
3. Ange eller välj ett värde i fältet Dimensionshierarkinod för kostnadsobjekt.
    * Expandera hela hierarkin för att välja 094.  
4. Ange eller välj ett värde i fältet Dimensionshierarkinod för kostnadselement.
    * Välj Övriga driftkostnader och sedan 605110 Cleaning.  
5. Välj ett alternativ i fältet Kostnadsbeteende.
    * Välj Fast kostnad.  
6. Ange eller välj ett värde i fältet Allokeringsunderlag.
7. Klicka på Ny.
8. Markera vald rad i listan.
9. Ange eller välj ett värde i fältet Dimensionshierarkinod för kostnadsobjekt.
    * Expandera hela hierarkin för att välja 094.  
10. Ange eller välj ett värde i fältet Dimensionshierarkinod för kostnadselement.
    * Välj Övriga driftkostnader och sedan 605150 Rent.  
11. Välj ett alternativ i fältet Kostnadsbeteende.
    * Välj Fast kostnad.  
12. Ange eller välj ett värde i fältet Allokeringsunderlag.
13. Klicka på Spara.

## <a name="assign-rules-to-a-cost-control-unit"></a>Tilldela regler till en kostnadsstyrenhet
1. Klicka på Policytilldelningar för kostnadsstyrenhet.
2. Klicka på Ny.
3. Markera vald rad i listan.
4. Ange ett datum i fältet Gäller från redovisningsdatum.
    * Välj den 1 september som giltigt räkenskapsår.  
5. Ange eller välj ett värde i fältet Kostnadsstyrenhet.
6. Klicka på Spara.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]