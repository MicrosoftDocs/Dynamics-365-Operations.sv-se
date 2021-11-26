---
title: Aktivera kassaflödesprognoser
description: I det här ämnet beskrivs hur du aktiverar funktionen för kassaflödesprognoser i Finance-insikter.
author: ShivamPandey-msft
ms.date: 11/03/2021
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
ms.openlocfilehash: d968f28126cf205a487d84301aa28f1251713386
ms.sourcegitcommit: 03fa7556840aa59f825697f6f9edeb58ea673fca
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/04/2021
ms.locfileid: "7752698"
---
# <a name="enable-cash-flow-forecasting"></a>Aktivera kassaflödesprognoser

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

I detta ämne beskrivs hur du aktiverar funktionen för kassaflödesprognoser i Finance Insights.

> [!NOTE]
> Om du vill använda betalningsförutsägelser i kassaflödet måste du ställa in funktionen Prediktioner av kundbetalning enligt beskrivningen i [Aktivera prediktioner av kundbetalning](enable-cust-paymnt-prediction.md).
  
1. Öppna arbetsytan **Funktionshantering** och gör så här:

    1. Välj **Sök efter uppdateringar**.
    2. På fliken **Alla** söker du efter **Kassaflödesprognoser**. Om du inte hittar funktionen söker du efter **(förhandsversion) Kassaflödesprognoser**. 
    3. Aktivera funktionen.

2. Gå till **Kassa- och bankhantering \> Kassaflödesprognosinställningar** och lägg till likviditetskontona som ska inkluderas i prognoserna. Ställ också in likviditetskontot för betalningar på flikarna **Kundreskontra** och **Leverantörsreskontra**. Se till att beräkna om kassaflödesprognosen.

    > [!NOTE]
    > Om likviditetskonton inte har konfigurerats kan kassaflödet inte genereras.
    >
    > Mer information om hur du ställer in prognoser för kassaflöden finns i [Kassaflödesprognoser](../cash-bank-management/cash-flow-forecasting.md).

3. Gå till **Kassa- och bankhantering \> Konfigurera \> Finance-insikter (förhandsversion) \> Kassaflödesprognoser (förhandsversion)** och gör så här:

    1. På fliken **Kassaflödesprognos** väljer du **Aktivera funktion**.
    2. Välj **Skapa förutsägelsemodell**.

Mer information om funktionen för kassaflödesprognoser finns i [Kassaflödesprognoser](cash-flow-forecast-intro.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
