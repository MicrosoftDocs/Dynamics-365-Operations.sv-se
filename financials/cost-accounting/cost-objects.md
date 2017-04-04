---
title: Kostnadsobjektdimensioner
description: "När du analyserar kostnader använder du kostnadselementdimensioner för att definiera var kostnader flödar. Du använder kostnadsobjektdimensioner för att fastställa var du bör tilldela kostnader. Det här ämnet innehåller information om kostnadsobjektdimensioner."
author: YuyuScheller
manager: AnnBe
ms.date: 04/04/2017
ms.topic: article
ms.prod: 
ms.service: Dynamics365Operations
ms.technology: 
ms.search.form: CAMDimensionMember
audience: Application User
ms.search.scope: Operations, Core
ms.custom: 223174
ms.assetid: 2a1cdd35-30cb-41e7-9506-67fd04a537c5
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
translationtype: Human Translation
ms.sourcegitcommit: 87c13e268ab8825e06095d24e03694cf0f271a63
ms.openlocfilehash: 6029fbc070c3d476bb0918b60f43c8c33e8e0bc6
ms.lasthandoff: 03/31/2017


---

# <a name="cost-object-dimensions"></a>Kostnadsobjektdimensioner

När du analyserar kostnader använder du kostnadselementdimensioner för att definiera var kostnader flödar. Du använder kostnadsobjektdimensioner för att fastställa var du bör tilldela kostnader. Det här ämnet innehåller information om kostnadsobjektdimensioner.

Ett kostnadsobjekt kan vara en typ av objekt som du vill beräkna, fördela kostnader till eller mäta direkt. Typiska kostnadsobjekt inkluderar produkter, projekt, resurser, avdelningar, kostnadsställen och geografiska regioner. Företagsledningen använder kostnadsobjekt till att kvantifiera kostnader och även till att köra lönsamhetsanalyser.

## <a name="cost-object-dimensions-and-cost-object-dimension-members"></a>Kostnadsobjektdimensioner och kostnadsobjektets dimensionsmedlemmar
Kostnadobjekt kallas för *Kostnadsobjektdimensioner* När du har bestämt dig vilken enhet som kostnadsobjektdimensionen ska hänsvisa till, måste du ange de enskilda dimensionsvärdena eller importera dem från andra källsystem till Kostnadsredovisning. Dessa enskilda dimensionsvärden kallas *Dimensionsmedlemmen för kostnadsobjekt*. Du kanske till exempel vill använda den ekonomiska dimension som Kostnadsställe som kostnadsobjektdimension. Om du vill se hur kostnader flödar till de enskilda kostnadsställena, måste du importera dimensionsmedlemmarna för kostnadsobjekt. I detta fall är dimensionsmedlemmarna för kostnadsobjekt de faktiska kostnadsställena, till exempel försäljning, produktion, administration och geografiska platser. Följande exempel visar en skärmdump av kostnadsställen som kostnadsobjektdimensionen med dess faktiska kostnadsställe som dimensionsmedlem för kostnadsobjekt. 

[![kostnad-objekt-dimensioner](./media/cost-object-dimensions.png)](./media/cost-object-dimensions.png)

## <a name="import-cost-object-dimension-members-through-data-connectors"></a>Importera dimensionsmedlemmar för kostnadsobjekt via datakopplingar
Om du vill förenkla importen av dimensionsmedlemmar för kostnadsobjekt, använder du datakopplingar för att hämta värden från de enheter som du vill använda som kostnadsobjektdimensioner. Du kan använda antingen föruppbyggda datakopplingar eller anpassade datakopplingar som du skapar.


