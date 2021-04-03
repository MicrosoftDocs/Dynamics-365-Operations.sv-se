---
title: Aktivera kassaflödesprognoser (förhandsversion)
description: I det här ämnet beskrivs hur du aktiverar funktionen för kassaflödesprognoser i Finance-insikter.
author: ShivamPandey-msft
manager: AnnBe
ms.date: 07/24/2020
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
ms.search.validFrom: 2020-07-24
ms.dyn365.ops.version: AX 10.0.13
ms.openlocfilehash: 2de75962f5b8a71c8f7138289078b5c669ae1daa
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5250588"
---
# <a name="enable-cash-flow-forecasting-preview"></a>Aktivera kassaflödesprognoser (förhandsversion)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

I det här ämnet beskrivs hur du aktiverar funktionen för kassaflödesprognoser i Finance-insikter.

> [!NOTE]
> Om du vill använda betalningsförutsägelser i kassaflödet måste du ställa in funktionen Prediktioner av kundbetalning enligt beskrivningen i [Aktivera prediktioner av kundbetalning](enable-cust-paymnt-prediction.md).

1. Använd information från miljösidan i Microsoft Dynamics Lifecycle Services (LCS) för att ansluta till den primära instansen av Azure SQL för den miljön. Kör följande Transact-SQL-kommando (T-SQL) för att aktivera förhandsversioner för sandbox-miljön. (Du kanske måste aktivera åtkomst för din IP-adress i LCS innan du kan fjärransluta till Application Object Server \[AOS\].)

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('CashflowInsightsFeature', 1)`

    > [!NOTE]
    > Om din distribution av Microsoft Dynamics 365 Finance är en Service Fabric-distribution kan du hoppa över det här steget. Teamet för Finance-insikter ska redan ha aktiverat förhandsversionen för dig. Om funktionerna inte visas på arbetsytan **Funktionshantering**, eller om det uppstår problem när du försöker att aktivera dem, kontaktar du <fiap@microsoft.com>.
  
2. Öppna arbetsytan **Funktionshantering** och gör så här:

    1. Välj **Sök efter uppdateringar**.
    2. Aktivera följande funktioner:

        - Ny rutnätskontroll
        - Gruppering i rutnät (förhandsversion) 
        - Kundbetalningsförutsägelser (förhandsversion)
        - Kassaflödesprognoser (förhandsversion)

3. Gå till **Kassa- och bankhantering \> Kassaflödesprognosinställningar** och lägg till likviditetskontona som ska inkluderas i prognoserna.

    > [!NOTE]
    > Om likviditetskonton inte har konfigurerats kan kassaflödet inte genereras.

4. Gå till **Kassa- och bankhantering \> Konfigurera \> Finance-insikter (förhandsversion) \> Kassaflödesprognoser (förhandsversion)** och gör så här:

    1. På fliken **Kassaflödesprognos** väljer du **Aktivera funktion**.
    2. Välj **Skapa förutsägelsemodell**.

Mer information om funktionen för kassaflödesprognoser finns i [Kassaflödesprognoser](cash-flow-forecast-intro.md).

## <a name="privacy-notice"></a>Sekretesspolicy

Förhandsversioner (1) kan använda färre sekretess- och säkerhetsfunktioner än Dynamics 365 Finance and Operations, (2) de ingår inte i serviceavtalet (SLA) för den här tjänsten, (3) bör inte användas för behandling av personuppgifter eller andra uppgifter som omfattas av lagar och andra efterlevnadskrav, samt (4) har begränsad support.


[!INCLUDE[footer-include](../../includes/footer-banner.md)]