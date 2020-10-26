---
title: Höja en variant och slutföra ett experiment
description: I det här avsnittet beskrivs hur du höjer upp en framgångsrik variant och slutför ett experiment i Dynamics 365 Commerce.
author: sushma-rao
manager: AnnBe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Retail
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 2e011f10e908d6a2efe2e928fc5e0abc7659cb8b
ms.sourcegitcommit: b6ab46f6e5ce60e2c3d70a348827eaf60c84cae2
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/01/2020
ms.locfileid: "3930288"
---
# <a name="promote-a-variation-and-complete-an-experiment"></a>Höja en variant och slutföra ett experiment

I det här avsnittet beskrivs hur du höjer den variant som gav bäst resultat i experimentet och hur du slutför experimentet. I bilden nedan visas alla steg som ingår när du ställer in och kör ett experiment på en e-handelswebbplats i Dynamics 365 Commerce. Ytterligare steg beskrivs i olika avsnitt.

[ ![Experimentets användarresa - granska och slutför](./media/experimentation_review_complete.svg) ](./media/experimentation_review_complete.svg#lightbox)

När du har [kört ditt experiment](experimentation-run-monitor.md) och samlat in tillräckligt med data för att avgöra vilken variant du vill använda på den aktiva platsen höjer du varianten och avslutar experimentet.

## <a name="promote-a-variation"></a>Höj en variant
Använd de data och den analys som är relaterade till experimentet i tredjepartstjänsten för att avgöra vilken variant som gav bäst resultat. Om du vill ersätta det aktuella innehållet på den aktiva platsen med den vinnande varianten så att den är tillgänglig för alla användare av webbplatsen gör du följande: 

1. Gå till fliken **experiment** i webbplatsskaparen och välj experimentet.
1. Välj **slutför experimentet** i den översta raden.
1. I dialogmenyn **Slutför experiment** välj **Granska status för ett experiment**. Tredjepartstjänsten öppnas där du kan validera mätvärdena och bestämma vilken variant som presterade bäst.
1. I dialogmenyn **Slutför experiment** i webbplatsskaparen, välj vinnande variant och välj sedan **Nästa**.
1. Öppna tredjepartstjänsten och stoppa experimentet.
1. I webbplatsskaparen välj **Slutför** om du vill skriva över den ursprungliga publicerade sidan och publicera den vinnande varianten så att den blir tillgänglig för alla användare av webbplatsen. 

> [!NOTE]
> Om du väljer att behålla den aktuella publicerade sidan och inte publicera en variant väljer du **Publicera om den ursprungliga sidan**.

## <a name="delete-your-experiment"></a>Ta bort experimentet
Det är inte nödvändigt att du tar bort ett slutfört experiment i Commerce, men du kan välja att ta bort det för att spara utrymme eller rensa arbetsytan. Om du vill ta bort ett experiment gör du följande.

1. Gå till fliken **experiment** i webbplatsskaparen och välj experimentet. 
    > [!NOTE]
    > Om experimentet fortfarande är aktivt, stoppar du experimentet i tredjepartstjänst innan du fortsätter.
1. Välj **Upphäv publicering** i kommandofältet om du vill ta bort variantsinnehållet från den aktiva webbplatsen.
1. Välj **Ta bort** i kommandofältet för att ta bort experimentet.

## <a name="previous-step"></a>Föregående steg
[Köra och övervaka ett experiment](experimentation-run-monitor.md)
