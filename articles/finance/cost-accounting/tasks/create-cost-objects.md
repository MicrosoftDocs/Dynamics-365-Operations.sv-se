---
title: 'Skapa kostnadsobjekt  '
description: I den här proceduren visas hur du skapar kostnadsobjekt, genom att importera den ekonomiska dimensionen för -kostnadsställen till kostnadsredovisning via en datakoppling.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: CAMDimension, CAMAXFinancialDimensionMemberProviderConfiguration, CAMDimensionMember
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: roschlom
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 91c25c52a2c6dc7f096a494577b361ff30406e9c
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5236804"
---
# <a name="create-cost-objects"></a>Skapa kostnadsobjekt   

[!include [banner](../../includes/banner.md)]

I den här proceduren visas hur du skapar kostnadsobjekt, genom att importera den ekonomiska dimensionen för -kostnadsställen till kostnadsredovisning via en datakoppling. Demonstrationsdataföretaget USMF har använts för att skapa denna procedur. 


## <a name="create-new-cost-objects"></a>Skapa nya kostnadsobjekt
1. Gå till Kostnadsredovisning > Dimensioner > Kostnadsobjektdimensioner.
2. Klicka på Ny.
3. Skriv ett värde i fältet Namn.
4. Ange eller välj ett värde i fältet Data connector for dimension members.
5. Ange ett värde i fältet Beskrivning.
6. Klicka på Spara.

## <a name="configure-the-data-connector"></a>Konfigurera datakopplingen
1. Klicka på Configure dimension member provider.
    * Välj CostCenter för att importera CostCenter-dimensionen till kostnadsredovisningen.  
2. Välj Cost center i fältet Dimension name.
3. Klicka på OK.

## <a name="import-cost-centers"></a>Importera kostnadsställen
1. Klicka på Import dimension members.
2. Klicka på OK.

## <a name="view-the-imported-cost-centers"></a>Visa de importerade kostnadsställena
1. Klicka på View dimension members.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]