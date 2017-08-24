--- 
title: 'Skapa kostnadsobjekt  '
description: "I den här proceduren visas hur du skapar kostnadsobjekt, genom att importera den ekonomiska dimensionen för Dynamics 365 for Finance and Operations, Enterprise Edition-kostnadsställen till kostnadsredovisning via en datakoppling."
author: YuyuScheller
manager: AnnBe
ms.date: 10/25/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: 79cb18717c6b42ef0307f304d28902dd66f0f932
ms.contentlocale: sv-se
ms.lasthandoff: 07/27/2017

---
# <a name="create-cost-objects"></a>Skapa kostnadsobjekt   

[!include[task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren visas hur du skapar kostnadsobjekt, genom att importera den ekonomiska dimensionen för Dynamics 365 for Finance and Operations, Enterprise Edition-kostnadsställen till kostnadsredovisning via en datakoppling. Demonstrationsdataföretaget USMF har använts för att skapa denna procedur. Denna procedur är avsedd för en kostnadsredovisningsfunktion som lades till i Dynamics 365 for Operations, version 1611.


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


