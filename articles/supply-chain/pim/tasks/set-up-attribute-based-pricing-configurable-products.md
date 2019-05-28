---
title: Ställ in attributbaserad prissättning för konfigurerbara produkter
description: I den här proceduren visas hur du ställer in attributbaserad prissättning.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCPriceModelList, PCPriceModel, PCConstraintEditor
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8568b5f4933ae58bc2d55a169c798668e03bed2a
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/15/2019
ms.locfileid: "1573290"
---
# <a name="set-up-attribute-based-pricing-for-configurable-products"></a>Ställ in attributbaserad prissättning för konfigurerbara produkter

[!include [task guide banner](../../includes/task-guide-banner.md)]

I den här proceduren visas hur du ställer in attributbaserad prissättning. Som en förutsättning måste du ha en modell för produktkonfiguration som har en eller flera komponenter och attribut. Detta exempel använder produktmodellen High End Speaker i demonstrationsföretaget USMF. Vanligtvis använder en produktchef denna procedur.


## <a name="create-a-new-price-model"></a>Skapa en ny prismodell
1. Klicka på Definition av produktvariantmodell.
2. Klicka på Modeller för produktkonfiguration.
3. Välj raden High End Speaker i listan, men inte klicka på länken för namn.
4. Klicka på Modell i åtgärdsfönstret.
5. Klicka på Price models.
6. Klicka på Ny.
7. Ange ett värde i fältet Price model name.
    * Använd ett namn som gör modellen enkel att identifiera.  
8. Ange ett värde i fältet Beskrivning.
9. Klicka på Spara.

## <a name="add-price-elements"></a>Lägg till priselement
1. Klicka på Redigera.
    * Varje komponent i en produktmodell kan ha ett grundpriselement och ett valfritt antal prisuttrycksregler. Du kan också lägga till priser i olika valutor.  
2. Ange ett värde i fältet Base price expression.
    * Ange till exempel 100.   Ett grundprisuttryck kan utgöras av ett numeriskt värde eller bestå av en aritmetisk beräkning som gäller ett eller flera attribut.  
3. Klicka på Lägg till.
4. Ange "Rosewood" i namnfältet.
    * Namnet för prisuttrycket hjälper till att identifiera det som priselementet representerar. I detta exempel skapar vi ett priselement för alternativet med rosenträfinish på högtalarkabinettet.  
5. Klicka på Edit condition.
    * Ett prisvillkor hjälper till att säkerställa att ett prisuttryckselement ingår i försäljningspriset endast om en specifik attributkombination förekommer.  
6. I fältet ConstraintBody anger du "CabinetFinish=="Rosewood"".
7. Klicka på OK.
8. Ange ett värde i fältet Expression.
    * Ange till exempel 50.  
9. Stäng sidan.
10. Stäng sidan.

