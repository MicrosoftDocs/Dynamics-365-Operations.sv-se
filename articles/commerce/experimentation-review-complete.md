---
title: Höja en variant och slutföra ett experiment
description: I det här avsnittet beskrivs hur du höjer upp en framgångsrik variant och slutför ett experiment i Dynamics 365 Commerce.
author: sushma-rao
manager: AnnBe
ms.date: 10/21/2020
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
ms.openlocfilehash: c7da601323663d4c1ea76f7cad7bdab8e7632d1c
ms.sourcegitcommit: cd83f2bc0e52e13071ad306e07e4c255fc65cb03
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/22/2020
ms.locfileid: "4415975"
---
# <a name="promote-a-variation-and-complete-an-experiment"></a>Höja en variant och slutföra ett experiment

I det här avsnittet beskrivs hur du höjer den variant som gav bäst resultat i experimentet och hur du slutför experimentet. I bilden nedan visas alla steg som ingår när du ställer in och kör ett experiment på en näthandelswebbplats i Dynamics 365 Commerce. Ytterligare steg beskrivs i olika avsnitt.

[ ![Experimentets användarresa - granska och slutför](./media/experimentation_review_complete.svg) ](./media/experimentation_review_complete.svg#lightbox)

När du har [kört ditt experiment](experimentation-run-monitor.md) och samlat in tillräckligt med data för att avgöra vilken variant du vill använda på den aktiva platsen höjer du varianten och avslutar experimentet.

## <a name="promote-a-variation"></a>Höj en variant
Använd de data och den analys som är relaterade till experimentet i tredjepartstjänsten för att avgöra vilken variant som gav bäst resultat. Du kan sedan flytta upp det genom att ersätta det aktuella innehållet på den aktiva platsen med den vinnande varianten så att den är tillgänglig för alla användare av webbplatsen.

Gör så här för att befordra den vinnande variationen: 

1. I Commerce webbplatsskaparen, välj **experiment** i det vänstra navigeringsfönstret och välj sedan experimentet.
1. I kommandofältet, välj **slutför experimentet**.
1. I dialogrutan **Slutför experiment** välj **Granska status för ett experiment**. Tredjepartstjänsten öppnas där du kan validera mätvärdena och bestämma vilken variant som presterade bäst.
1. I dialogrutan **Slutför experiment**, välj vinnande variant och välj sedan **Nästa**.
1. Öppna tredjepartstjänsten och stoppa experimentet.
1. I webbplatsskaparen välj **Slutför** om du vill skriva över den ursprungliga publicerade sidan och publicera den vinnande varianten så att den blir tillgänglig för alla användare av webbplatsen. 

> [!NOTE]
> Om du väljer att behålla den aktuella publicerade sidan och inte publicera en variant väljer du **Publicera om den ursprungliga sidan**.

## <a name="delete-your-experiment"></a>Ta bort experimentet
Det är inte nödvändigt att du tar bort ett slutfört experiment i Commerce, men du kan välja att ta bort det för att spara utrymme eller rensa arbetsytan. 

För att ta bort ett experiment i Commerce webbplatsskaparen, följ dessa steg.

1. Välj **experiment** i det vänstra navigeringsfönstret och välj sedan experimentet. 
    > [!NOTE]
    > Om experimentet fortfarande är aktivt, stoppar du experimentet i tredjepartstjänst innan du fortsätter.
1. I kommandofältet, välj **Upphäv publicering** om du vill ta bort variantinnehållet från den aktiva webbplatsen.
1. Välj **Ta bort** för att ta bort experimentet.

## <a name="previous-step"></a>Föregående steg
[Köra och övervaka ett experiment](experimentation-run-monitor.md)
