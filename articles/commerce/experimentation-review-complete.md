---
title: Höja en variant och slutföra ett experiment
description: I denna artikel beskrivs hur du höjer upp en framgångsrik variant och slutför ett experiment i Dynamics 365 Commerce.
author: sushma-rao
ms.date: 06/07/2022
ms.topic: article
audience: Application User
ms.reviewer: josaw
ms.search.region: Global
ms.author: sushmar
ms.search.validFrom: 2020-09-30
ms.openlocfilehash: 3e9a978551622bbb14d9213f607d9dfabe42672a
ms.sourcegitcommit: ddcb62bb5fbf26a1178c2bb1aec45a3d2362339e
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/07/2022
ms.locfileid: "8942753"
---
# <a name="promote-a-variation-and-complete-an-experiment"></a>Höja en variant och slutföra ett experiment

I denna artikel beskrivs hur du höjer den variant som gav bäst resultat i experimentet och hur du slutför experimentet. I bilden nedan visas alla steg som ingår när du konfigurerar och kör ett experiment på en näthandelssajt i Dynamics 365 Commerce. Ytterligare steg beskrivs i separata artiklar.

[ ![Experimentets användarresa – granska och slutför.](./media/experimentation_review_complete.svg) ](./media/experimentation_review_complete.svg#lightbox)

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

För att ta bort ett slutfört experiment i Commerce-webbplatsverktyget, följ dessa steg.

1. Välj **experiment** i det vänstra navigeringsfönstret och välj sedan experimentet. 
    > [!NOTE]
    > Om experimentet fortfarande är aktivt, stoppar du experimentet i tredjepartstjänst innan du fortsätter.
1. I kommandofältet, välj **Upphäv publicering** om du vill ta bort variantinnehållet från den aktiva webbplatsen.
1. Välj **Ta bort** för att ta bort experimentet.

## <a name="previous-step"></a>Föregående steg
[Köra och övervaka ett experiment](experimentation-run-monitor.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
