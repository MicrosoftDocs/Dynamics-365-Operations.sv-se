---
title: Indroppningsbaserat orderskapande för butikstransaktioner
description: Det här ämnet beskriver det indroppningsbaserade orderskapandet för butikstransaktioner i Microsoft Dynamics 365 Commerce.
author: josaw1
manager: AnnBe
ms.date: 06/08/2020
ms.topic: index-page
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
ms.author: josaw
ms.search.validFrom: 2019-09-30
ms.dyn365.ops.version: ''
ms.openlocfilehash: 6e097ead7cacb3f71452323656546a4be661457f
ms.sourcegitcommit: 7061a93f9f2b54aec4bc4bf0cc92691e86d383a6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/20/2020
ms.locfileid: "3710293"
---
# <a name="trickle-feed-based-order-creation-for-retail-store-transactions"></a>Indroppningsbaserat orderskapande för butikstransaktioner

[!include [banner](includes/banner.md)]

I Dynamics 365 Retail version 10.0.4 och tidigare utförs bokföring av utdrag i slutet av dagen och alla transaktioner bokförs i slutet av dagen. Stora transaktioner måste sedan bearbetas i ett begränsat tidsfönster, som ibland leder till låsningar och transaktionsbokföringsfel. Återförsäljare kan heller inte identifiera intäkter och betalningar i sin bokföring under dagen.

Med indroppningsbaserat orderskapande som introducerades i Retail version 10.0.5 bearbetas transaktioner under dagen, och endast den ekonomiska avstämningen av anbud och andra transaktioner för likviditetshantering bearbetas vid slutet av dagen. Den här funktionen delar upp belastningen av att skapa försäljningsorder, fakturor och betalningar under dagen, vilket ger bättre uppfattad prestanda och större möjlighet att känna igen intäkter och betalningar i bokföringen nära realtid. 


## <a name="how-to-use-trickle-feed-based-posting"></a>Så här använder du indroppningsbaserad bokföring
  
1. Om du vill aktivera indroppningsbaserad bokföring av transaktioner går du till **Systemadministration > Inställningar > Licenskonfiguration** och inaktiverar nyckeln **Utdrag**.

2. På samma sida aktiverar du licensnyckeln **Utdrag (indroppning) – förhandsgranskning**. När du aktiverar den här nyckeln måste du se till att det inte finns några utdrag som väntar på att bokföras. 

    > [!Important]
    > Innan du aktiverar licensnyckeln **Utdrag (indroppning) – förhandsgranskning** ser du till att inga utdrag väntar på att bokföras.

3. Det aktuella utdragsdokumentet delas upp i två olika typer: transaktionsutdrag och bokslut.

      - Transaktionsutdraget hämtar alla ej bokförda och validerade transaktioner och skapa försäljningsorder, försäljningsfakturor, betalnings- och rabattjournaler samt intäkts-utgiftstransaktioner i den takt du konfigurerar. Du bör konfigurera den här processen så att den körs med hög frekvens så att dokument skapas när butikstransaktionerna överförs till Headquarters via P-jobbet. När du använder utdragsdokumentet som redan skapar försäljningsorder och försäljningsfakturor behöver du inte konfigurera batchjobbet **Bokföring av lager**. Du kan dock fortfarande använda det för att uppfylla specifika affärsbehov som du kan ha.  
      
     - Bokslutet är utformat för att skapas i slutet av dagen och stöder bara stängningsmetoden **Skift.** Detta utdrag begränsas till den ekonomiska avstämningen och skapar endast journaler för avvikelsebeloppen mellan det räknade beloppet och transaktionsbeloppet för de olika anbuden, tillsammans med journaler för andra likviditetshanteringstransaktioner.   

4. Om du vill beräkna transaktionsutdraget klickar du på **Retail och Commerce > Retail och Commerce IT > Kassabokföring > Beräkna transaktionsutdrag i batch**. Om du vill bokföra transaktionsutdrag i batch klickar du på **Retail och Commerce > Retail och Commerce IT > Kassabokföring > Bokför transaktionsutdrag i batch**.

5. Om du vill beräkna bokslutet klickar du på **Retail och Commerce > Retail och Commerce IT > Kassabokföring > Beräkna bokslutet i batch**. Om du vill bokföra bokslutet i batch klickar du på **Retail och Commerce > Retail och Commerce IT > Kassabokföring > Bokför bokslutet i batch**.

> [!NOTE]
> Menyalternativen **Retail och Commerce > Retail och Commerce IT > Kassabokföring > Beräkna utdrag i batch** och **Retail och Commerce >Retail och Commerce IT > Kassabokföring > Bokför utdrag i batch** tas bort i den nya funktionen.

Alternativt kan transaktions- och bokslutstyper skapas manuellt. Gå till **Retail och Commerce > Kanaler > Butiker** och klicka på **Utdrag**. Klicka på **Ny** och välj sedan den typ av utdrag som du vill skapa. Fält på sidan **Utdrag** och åtgärder under **Utdragsgrupper** på sidan visar relevanta data och åtgärder baserade på den valda utdragstypen.
