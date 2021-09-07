---
title: Aktivera kassaflödesprognoser
description: I det här ämnet beskrivs hur du aktiverar funktionen för kassaflödesprognoser i Finance-insikter.
author: ShivamPandey-msft
ms.date: 07/16/2021
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: b5e54772b132b4098df8259e954a484a0838ee38
ms.sourcegitcommit: 822aea26c5da259efe11ff3b3dc4cf1598425689
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/16/2021
ms.locfileid: "7386721"
---
# <a name="enable-cash-flow-forecasting"></a>Aktivera kassaflödesprognoser

[!include [banner](../includes/banner.md)]

I det här ämnet beskrivs hur du aktiverar funktionen för kassaflödesprognoser i Finance-insikter.

> [!NOTE]
> Om du vill använda betalningsförutsägelser i kassaflödet måste du ställa in funktionen Prediktioner av kundbetalning enligt beskrivningen i [Aktivera prediktioner av kundbetalning](enable-cust-paymnt-prediction.md).

1. Använd information från miljösidan i Microsoft Dynamics Lifecycle Services (LCS) för att ansluta till den primära instansen av Azure SQL för den miljön. Kör följande Transact-SQL-kommando (T-SQL) för att aktivera förhandsversioner för sandbox-miljön. (Du kanske måste aktivera åtkomst för din IP-adress i LCS innan du kan fjärransluta till Application Object Server \[AOS\].)

    `INSERT INTO SYSFLIGHTING (FLIGHTNAME, ENABLED) VALUES ('CashflowInsightsFeature', 1)`

    > [!NOTE]
    > Hoppa över det här steget om du använder version 10.0.20 eller senare, eller om du använder en Service Fabric-distribution. Teamet för ekonomiinsikter ska redan ha aktiverat förhandsversionen för dig. Om funktionen inte visas på arbetsytan **Funktionshantering**, eller om det uppstår problem när du försöker att aktivera den, kontaktar du <fiap@microsoft.com>.
  
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

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
