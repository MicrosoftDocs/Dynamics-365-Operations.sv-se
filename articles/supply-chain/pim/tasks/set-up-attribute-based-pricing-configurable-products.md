---
title: Ställ in attributbaserad prissättning för konfigurerbara produkter
description: I det här avsnittet visas hur du ställer in attributbaserad prissättning.
author: ShylaThompson
manager: tfehr
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCPriceModelList, PCPriceModel, PCConstraintEditor
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 7382cdfa11e89896bba9518f36eb6caab56b98f6
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3213065"
---
# <a name="set-up-attribute-based-pricing-for-configurable-products"></a>Ställ in attributbaserad prissättning för konfigurerbara produkter

[!include [banner](../../includes/banner.md)]

I det här avsnittet visas hur du ställer in attributbaserad prissättning. Som en förutsättning måste du ha en modell för produktkonfiguration som har en eller flera komponenter och attribut. Detta exempel använder produktmodellen High End Speaker i demonstrationsföretaget USMF. Vanligtvis använder en produktchef denna procedur.


## <a name="create-a-new-price-model"></a>Skapa en ny prismodell
1. Välj **Definition av produktvariantmodell** på startsidan.
2. Välj **Modeller för produktkonfiguration** i avsnitet **Länkar**.
3. Välj raden **High End Speaker** i listan, men välj inte länken för namn.
4. Klicka på **Modell** i åtgärdsfönstret.
5. Välj **Prismodeller**.
6. Välj **Ny**.
7. Ange ett värde i fältet **Prismodellnamn**. Använd ett namn som gör modellen enkel att identifiera.  
8. I fältet **Beskrivning** anger du ett värde.
9. Välj **Spara**.

## <a name="add-price-elements"></a>Lägg till priselement
1. Välj **Redigera**. Varje komponent i en produktmodell kan ha ett grundpriselement och ett valfritt antal prisuttrycksregler. Du kan också lägga till priser i olika valutor.  
2. Ange ett värde i fältet **Grundprisuttryck**. Ange till exempel 100. Ett grundprisuttryck kan utgöras av ett numeriskt värde eller bestå av en aritmetisk beräkning som gäller ett eller flera attribut.  
3. Markera **Lägg till**.
4. I fältet **Namn** skriver du `Rosewood`. Namnet för prisuttrycket hjälper till att identifiera det som priselementet representerar. I detta exempel skapar vi ett priselement för alternativet med rosenträfinish på högtalarkabinettet.  
5. Välj **Redigeringsvillkor**. Ett prisvillkor hjälper till att säkerställa att ett prisuttryckselement ingår i försäljningspriset endast om en specifik attributkombination förekommer.  
6. Ange `CabinetFinish=="Rosewood"` i fältet **ConstraintBody**.
7. Välj **OK**.
8. Ange ett värde i fältet **Uttryck**. Ange till exempel `50`. 
9. Stäng sidan.

