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
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 2616e5275f9f59b962d4e456684073aea2c654ea
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/30/2019
ms.locfileid: "2249688"
---
# <a name="create-cost-objects"></a>Skapa kostnadsobjekt   

[!include [task guide banner](../../includes/task-guide-banner.md)]

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

