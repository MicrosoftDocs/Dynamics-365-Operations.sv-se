---
title: Aktivera förutsägelser för kundbetalning
description: I det här ämnet beskrivs hur du aktiverar och konfigurerar funktionen för kundbetalningsförutsägelse i Finance Insights.
author: ShivamPandey-msft
ms.date: 02/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-29
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: f04ee9db5efe3595dea30d641c5097d6b90c0d77
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8898219"
---
# <a name="enable-customer-payment-predictions"></a>Aktivera förutsägelser för kundbetalning

[!include [banner](../includes/banner.md)]

I det här ämnet beskrivs hur du aktiverar och konfigurerar funktionen för kundbetalningsförutsägelse i Finance Insights. Du aktiverar funktionen på arbetsytan **Funktionshantering** och anger konfigurationsinställningar på sidan **Konfiguration för Finance Insights**. Den här artikeln innehåller också information som kan hjälpa dig att effektivt använda funktionen.

> [!NOTE]
> Innan du genomför följande steg måste du se till att slutföra de nödvändiga stegen i ämnet [Konfigurera för Finance Insights](configure-for-fin-insites.md).

1. Aktivera funktionen för kundbetalningsförutsägelser:

    1. Öppna arbetsytan **Funktionshantering**.
    2. Välj **Sök efter uppdateringar**.
    3. På fliken **Alla** letar du upp **Förutsägelser för kundbetalningar**. Om du inte hittar funktionen söker du efter **(förhandsversion) Förutsägelser för kundbetalningar**. 
    4. Aktivera funktionen.

    Funktionen för kundbetalningsförutsägelser är nu aktiverad och redo att konfigureras.

2. Konfigurera funktionen för kundbetalningsinsikter:

    1. Gå till **Kredit och inkasso \> Inställningar \> Finance Insights \> Kundbetalningsförutsägelser**.
    2. På sidan **Konfiguration för Finance Insights**, på fliken **Kundbetalningsförutsägelser**, väljer du länken **Visa de datafält som används i förutsägelsemodellen** för att öppna sidan **Datafält för förutsägelsemodell**. Där kan du visa standardlistan över fält som används för att skapa en AI-förutsägelsemodell för kundbetalningsförutsägelser.

        Om du vill använda standardlistan med fält för att skapa förutsägelsemodellen stänger du sidan **Datafält för förutsägelsemodell** och anger på sidan **Konfiguration för Finance Insights** sedan alternativet **Aktivera funktion** som **Ja**.
        
   > [!NOTE]
   > Funktionen **Kundbetalningsförutsägelser** kräver mer än 100 transaktioner under de föregående sex till nio månaderna. Transaktionerna kan omfatta fritextfakturor, försäljningsorder och kundbetalningar. Dessa data måste sprids över inställningarna **I tid**, **Sent** och **Mycket sent**.    
     

    3. Ange transaktionsperioden "mycket sent" för att definiera vad den förutsägelsebucketen **Mycket sent** innebär för din verksamhet.

        För varje öppen faktura förutsäger systemet sannolikheten för betalning i tre buckets: **i tid**, **sent** och **mycket sent**.

        - **I tid** – Denna bucket inkluderar betalningar som förutsägs betalas på eller före transaktionens förfallodatum.
        - **Sent** – Denna bucket inkluderar betalningar som förutsägs betalas efter transaktionens förfallodatum men innan transaktionsperioden "mycket sent" har startats.
        - **Mycket sent** – Denna bucket inkluderar betalningar som förutsägs betalas efter att transaktionsperioden "mycket sent" har startats.

        > [!NOTE]
        > Om du ändrar transaktionsperioden "mycket sent" och väljer **Ändra tröskel för Sent** efter att AI-förutsägelsemodellen för kundbetalningar har skapats tas den befintliga förutsägelsemodellen bort och en ny modell skapas. Den nya förutsägelsemodellen flyttar transaktionerna till perioden "mycket sent", baserat på de inställningar som angavs för att definiera den.

    4. När du har definierat transaktionsperioden "mycket sent" väljer **Skapa förutsägelsemodell** för att skapa förutsägelsemodellen. I avsnittet **Förutsägelsemodell** på sidan **Konfiguration för Finance Insights** visas statusen för förutsägelsemodellen.

        > [!NOTE]
        > Du kan när som helst medan förusägelsemodellen skapas välja **Återställ modellskapande** för att starta om processen.

    Funktionen har nu konfigurerats och är redo att användas.

När funktionen har aktiverats och konfigurerats, och om förutsägelsemodellen har skapats och fungerar, visar avsnittet **Förutsägelsemodell** på sidan **Parametrar för Finance Insights** hur noggrann modellen är.

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
