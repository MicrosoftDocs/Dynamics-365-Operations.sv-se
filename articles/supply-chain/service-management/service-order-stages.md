---
title: Serviceorderfaser
description: Genom att definiera faser för en serviceorder och tilldela dem till arbetare kan du styra flödet för en serviceorder genom uppgifterna som olika personer utför i serviceorganisationen.
author: ShylaThompson
manager: tfehr
ms.date: 04/30/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: SMAServiceOrderTable, SMAStageTable
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 7eab1b10e8c8782306c1c2d892f965dc0795c69a
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5224415"
---
# <a name="service-order-stages"></a>Serviceorderfaser   

[!include [banner](../includes/banner.md)]


Du kan ställa in faser för en serviceorder ska definieras uppgifter, som måste utföras, ordern, som de är i, och arbetarna som är ansvarig för att slutföra dem. Genom att definiera faser för en serviceorder och tilldela dem till arbetare kan du styra flödet för en serviceorder genom uppgifterna som olika personer utför i serviceorganisationen. Sekvensen med faser måste omfatta en första fas.

Du kan också definiera de åtgärder som tillåts i varje fas. Om du exempelvis avmarkerar kryssrutan **Bokför** för alla utom den sista fasen förhindrar du att serviceordern bokförs innan den har gått igenom hela fassekvensen.

## <a name="branching-in-service-order-stages"></a>Branchning i serviceorderfaser

När du ställer in en servicefas, kan du skapa flera alternativ, eller förgreningar, att välja mellan för nästa servicefas. Alla avdelningar som du skapar kan väljas när den inledande fasen är slutförd. Du ställer till exempel in **Planering** som en ursprunglig fas. Du skapar två faser med namne **Pågår** och **Avbryt** och väljer sedan **Planering** som det överordnade objektet för dem. Du tilldelar **Planering** in fasen till försäljningsorder. När planeringsfasen för försäljningsordern är slutförd, kan du välja fasen **Pågår**, om försäljningsordern är klar att arbeta på, eller välja fasen **Avbryt**, om försäljningsordern är annullerad.

## <a name="see-also"></a>Se även

[Ställ in serviceorderfaser](set-up-service-order-stages.md)

[Ändra serviceorderfasen](change-service-order-stage.md)

  




[!INCLUDE[footer-include](../../includes/footer-banner.md)]