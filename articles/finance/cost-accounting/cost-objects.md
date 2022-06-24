---
title: Kostnadsobjektdimensioner
description: När du analyserar kostnader använder du kostnadselementdimensioner för att definiera var kostnader flödar. Du använder kostnadsobjektdimensioner för att fastställa var du bör tilldela kostnader. Det här ämnet innehåller information om kostnadsobjektdimensioner.
author: AndersGirke
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: CAMDimensionMember, CAMCostObject
audience: Application User
ms.reviewer: twheeloc
ms.custom: 223174
ms.assetid: 2a1cdd35-30cb-41e7-9506-67fd04a537c5
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: twheeloc
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.openlocfilehash: 3ee481b9dafe202e0a850a31b6ab036d52a20547
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8874650"
---
# <a name="cost-object-dimensions"></a>Kostnadsobjektsdimensioner

[!include [banner](../includes/banner.md)]

När du analyserar kostnader använder du kostnadselementdimensioner för att definiera var kostnader flödar. Du använder kostnadsobjektdimensioner för att fastställa var du bör tilldela kostnader. Det här ämnet innehåller information om kostnadsobjektdimensioner.

Ett kostnadsobjekt kan vara en typ av objekt som du vill beräkna, fördela kostnader till eller mäta direkt. Typiska kostnadsobjekt inkluderar produkter, projekt, resurser, avdelningar, kostnadsställen och geografiska regioner. Företagsledningen använder kostnadsobjekt till att kvantifiera kostnader och även till att köra lönsamhetsanalyser.

## <a name="cost-object-dimensions-and-cost-object-dimension-members"></a>Kostnadsobjektdimensioner och kostnadsobjektets dimensionsmedlemmar
Kostnadobjekt kallas för *Kostnadsobjektdimensioner* När du har bestämt dig vilken enhet som kostnadsobjektdimensionen ska hänsvisa till, måste du ange de enskilda dimensionsvärdena eller importera dem från andra källsystem till Kostnadsredovisning. Dessa enskilda dimensionsvärden kallas *Dimensionsmedlemmen för kostnadsobjekt*. Du kanske till exempel vill använda den ekonomiska dimension som Kostnadsställe som kostnadsobjektdimension. Om du vill se hur kostnader flödar till de enskilda kostnadsställena, måste du importera dimensionsmedlemmarna för kostnadsobjekt. I detta fall är dimensionsmedlemmarna för kostnadsobjekt de faktiska kostnadsställena, till exempel försäljning, produktion, administration och geografiska platser. Följande exempel visar en skärmdump av kostnadsställen som kostnadsobjektdimensionen med dess faktiska kostnadsställe som dimensionsmedlem för kostnadsobjekt. 

[![Skärmbild med kostnadsställen som dimension för kostnadsbärare.](./media/cost-object-dimensions.png)](./media/cost-object-dimensions.png)

## <a name="import-cost-object-dimension-members-through-data-connectors"></a>Importera dimensionsmedlemmar för kostnadsobjekt via datakopplingar
Om du vill förenkla importen av dimensionsmedlemmar för kostnadsobjekt, använder du datakopplingar för att hämta värden från de enheter som du vill använda som kostnadsobjektdimensioner. Du kan använda antingen föruppbyggda datakopplingar eller anpassade datakopplingar som du skapar.





[!INCLUDE[footer-include](../../includes/footer-banner.md)]
