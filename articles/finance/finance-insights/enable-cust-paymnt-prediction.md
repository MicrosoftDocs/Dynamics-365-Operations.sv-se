---
title: Aktivera prediktioner av kundbetalning (förhandsversion)
description: I det här ämnet beskrivs hur du aktiverar och konfigurerar funktionen för kundbetalningsförutsägelse i Finance-insikter.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 05/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom: 14151
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2020-05-29
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 584c1af5f9252a4b8c88a8866a64184bd0595b2e
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "5009428"
---
# <a name="enable-customer-payment-predictions-preview"></a>Aktivera prediktioner av kundbetalning (förhandsversion)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

I det här ämnet beskrivs hur du aktiverar och konfigurerar funktionen för kundbetalningsförutsägelse i Finance-insikter. Du aktiverar funktionen på arbetsytan **Funktionshantering** och anger konfigurationsinställningar på sidan **Parametrar för ekonomiinsikter**. Det här avsnittet innehåller också information som kan hjälpa dig att effektivt använda funktionen.

> [!NOTE]
> Innan du genomför följande steg måste du se till att slutföra de nödvändiga stegen i ämnet [Konfigurera för Finance-insikter](configure-for-fin-insites.md).

1. Använd information från miljösidan i Microsoft Dynamics Lifecycle Services (LCS) för att ansluta till den primära instansen av Azure SQL för den miljön. Kör följande Transact-SQL-kommando (T-SQL) för att aktivera förhandsversioner för sandbox-miljön. (Du kanske måste aktivera åtkomst för din IP-adress i LCS innan du kan fjärransluta till Application Object Server \[AOS\].)

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED, PARTITION) VALUES ('PayPredEnableFeature', 1, 5637144576)`

    > [!NOTE]
    > Om din distribution av Microsoft Dynamics 365 Finance är en Service Fabric-distribution kan du hoppa över det här steget. Teamet för ekonomiinsikter ska redan ha aktiverat förhandsversionen för dig. Om funktionen inte visas på arbetsytan **Funktionshantering**, eller om det uppstår problem när du försöker att aktivera den, kontaktar du <fiap@microsoft.com>.

2. Aktivera funktionen för kundbetalningsinsikter:

    1. Gå till **Systemadministration \> Arbetsytor \> Funktionshantering**.
    2. Hitta funktionen med namnet **Kundbetalningsinsikter (förhandsversion)**.
    3. Välj **Aktivera nu**.

    Funktionen för kundbetalningsinsikter är nu aktiverad och kan konfigureras.

3. Konfigurera funktionen för kundbetalningsinsikter:

    1. Gå till **Kredit och inkasso \> Konfigurera \> Finance-insikter \> Parametrar för ekonomiinsikter**.

        [![Sidan med parametrar för ekonomiinsikter innan funktionen har konfigurerats](./media/finance-insights-parameters.png)](./media/finance-insights-parameters.png)

    2. På sidan **Parametrar för ekonomiinsikter**, på fliken **Kundbetalningsinsikter**, väljer du länken **Visa de datafält som används i förutsägelsemodellen** för att öppna sidan **Datafält för förutsägelsemodell**. Där kan du visa standardlistan över fält som används för att skapa en AI-förutsägelsemodell för kundbetalningsförutsägelser.

        Om du vill använda standardlistan med fält för att skapa förutsägelsemodellen stänger du sidan **Datafält för förutsägelsemodell** och väljer sedan **Ja** för alternativet **Aktivera funktion** på sidan **Parametrar för ekonomiinsikter**.

    3. Ange transaktionsperioden "mycket sent" för att definiera vad den förutsägelsebucketen **Mycket sent** innebär för din verksamhet.

        För varje öppen faktura förutsäger systemet sannolikheten för betalning i tre buckets: **i tid**, **sent** och **mycket sent**.

        - **I tid** – Denna bucket inkluderar betalningar som förutsägs betalas på eller före transaktionens förfallodatum.
        - **Sent** – Denna bucket inkluderar betalningar som förutsägs betalas efter transaktionens förfallodatum men innan transaktionsperioden "mycket sent" har startats.
        - **Mycket sent** – Denna bucket inkluderar betalningar som förutsägs betalas efter att transaktionsperioden "mycket sent" har startats.

        > [!NOTE]
        > Om du ändrar transaktionsperioden "mycket sent" och väljer **Ändra tröskel för Sent** efter att AI-förutsägelsemodellen för kundbetalningar har skapats tas den befintliga förutsägelsemodellen bort och en ny modell skapas. Den nya förutsägelsemodellen flyttar transaktionerna till perioden "mycket sent", baserat på de inställningar som angavs för att definiera den.

    4. När du har definierat transaktionsperioden "mycket sent" väljer **Skapa förutsägelsemodell** för att skapa förutsägelsemodellen. I avsnittet **Förutsägelsemodell** på sidan **Parametrar för ekonomiinsikter** visas status för förutsägelsemodellen.

        > [!NOTE]
        > Du kan när som helst medan förusägelsemodellen skapas välja **Återställ modellskapande** för att starta om processen.

    Funktionen har nu konfigurerats och är redo att användas.

När funktionen har aktiverats och konfigurerats, och om förutsägelsemodellen har skapats och fungerar, visar avsnittet **Förutsägelsemodell** på sidan **Parametrar för ekonomiinsikter** hur noggrann modellen är, vilket visas i bilden nedan.

[![Noggrannhet för förutsägelsemodellen på sidan Parametrar för ekonomiinsikter](./media/finance-insights-parameters-accuracy.png)](./media/finance-insights-parameters-accuracy.png)

## <a name="release-details"></a>Frisläppningsinformation

Den allmänt tillgängliga förhandsversionen av Finance-insikter finns tillgänglig för bedömningsdistribution i USA, Europa och Storbritannien. Microsoft lägger stegvis till support för fler regioner.

Funktionerna för allmänt tillgänglig förhandsversion kan och ska bara aktiveras i nivå-2-sandbox-miljöer. Konfiguration och AI-modeller som skapas i en sandbox-miljö kan inte migreras till en produktionsmiljö. Mer information finns i [Tilläggsavtal för Microsoft Dynamics 365 förhandsversioner](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/public-preview-terms).

## <a name="privacy-notice"></a>Sekretesspolicy

Förhandsversioner (1) kan använda färre sekretess- och säkerhetsfunktioner än Dynamics 365 Finance and Operations, (2) de ingår inte i serviceavtalet (SLA) för den här tjänsten, (3) bör inte användas för behandling av personuppgifter eller andra uppgifter som omfattas av lagar och andra efterlevnadskrav, samt (4) har begränsad support.
