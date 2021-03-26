---
title: Indroppningsbaserat orderskapande för butikstransaktioner
description: Det här ämnet beskriver det indroppningsbaserade orderskapandet för butikstransaktioner i Microsoft Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 09/04/2020
ms.topic: index-page
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: Retail
ms.author: josaw
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: 0fdb1f636183e8365729ab8947a50614a77eaeac
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5211055"
---
# <a name="trickle-feed-based-order-creation-for-retail-store-transactions"></a>Indroppningsbaserat orderskapande för butikstransaktioner

[!include [banner](includes/banner.md)]

I Dynamics 365 Retail version 10.0.4 och tidigare utförs bokföring av utdrag i slutet av dagen och alla transaktioner bokförs i slutet av dagen. Stora transaktioner måste sedan bearbetas i ett begränsat tidsfönster, som ibland leder till låsningar och transaktionsbokföringsfel. Återförsäljare kan heller inte identifiera intäkter och betalningar i sin bokföring under dagen.

Med indroppningsbaserat orderskapande som introducerades i Retail version 10.0.5 bearbetas transaktioner under dagen, och endast den ekonomiska avstämningen av anbud och andra transaktioner för likviditetshantering bearbetas vid slutet av dagen. Den här funktionen delar upp belastningen av att skapa försäljningsorder, fakturor och betalningar under dagen, vilket ger bättre uppfattad prestanda och större möjlighet att känna igen intäkter och betalningar i bokföringen nära realtid. 


## <a name="how-to-use-trickle-feed-based-posting"></a>Så här använder du indroppningsbaserad bokföring
  
1. Om du vill aktivera indroppningsbaserad bokföring av butikstransaktioner aktiverar du funktionen **Butiksutdrag – Indroppning** med hjälp av Funktionshantering.

    > [!IMPORTANT]
    > Innan du aktiverar den här funktionen måste du se till att det inte finns några utdrag som väntar på att bokföras.

2. Det aktuella utdragsdokumentet delas upp i två typer: transaktionsutdrag och bokslut.

      - Transaktionsutdraget hämtar alla ej bokförda och validerade transaktioner och skapa försäljningsorder, försäljningsfakturor, betalnings- och rabattjournaler samt intäkts-utgiftstransaktioner i den takt du konfigurerar. Du bör konfigurera den här processen så att den körs med hög frekvens så att dokument skapas när butikstransaktionerna överförs till Headquarters via P-jobbet. När du använder utdragsdokumentet som redan skapar försäljningsorder och försäljningsfakturor behöver du inte konfigurera batchjobbet **Bokföring av lager**. Du kan dock fortfarande använda det för att uppfylla specifika affärsbehov som du kan ha.  
      
     - Bokslutet är utformat för att skapas i slutet av dagen och stöder bara stängningsmetoden **Skift.** Detta utdrag begränsas till den ekonomiska avstämningen och skapar endast journaler för avvikelsebeloppen mellan det räknade beloppet och transaktionsbeloppet för de olika anbuden, tillsammans med journaler för andra likviditetshanteringstransaktioner.   

3. Om du vill beräkna transaktionsutdraget går du till **Retail och Commerce > Retail och Commerce IT > Kassabokföring > Beräkna transaktionsutdrag i batch**. Om du vill bokföra transaktionsutdrag i batch går du till **Retail och Commerce > Retail och Commerce IT > Kassabokföring > Bokför transaktionsutdrag i batch**.

4. Om du vill beräkna bokslutet går du till **Retail och Commerce > Retail och Commerce IT > Kassabokföring > Beräkna bokslutet i batch**. Om du vill bokföra bokslutet i batch går du till **Retail och Commerce > Retail och Commerce IT > Kassabokföring > Bokför bokslutet i batch**.

> [!NOTE]
> Menyalternativen **Retail och Commerce > Retail och Commerce IT > Kassabokföring > Beräkna utdrag i batch** och **Retail och Commerce >Retail och Commerce IT > Kassabokföring > Bokför utdrag i batch** tas bort i den nya funktionen.

Alternativt kan transaktions- och bokslutstyper skapas manuellt. Gå till **Retail och Commerce > Kanaler > Butiker** och klicka på **Utdrag**. Klicka på **Ny** och välj sedan den typ av utdrag som du vill skapa. Fält på sidan **Utdrag** och åtgärder under **Utdragsgrupper** på sidan visar relevanta data och åtgärder baserade på den valda utdragstypen.


[!INCLUDE[footer-include](../includes/footer-banner.md)]