---
title: Aktivera kassaflödesprognoser
description: I det här ämnet beskrivs hur du aktiverar funktionen för kassaflödesprognoser i Finance-insikter.
author: ShivamPandey-msft
ms.date: 02/11/2022
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
ms.openlocfilehash: 763818f70095964d77ff82cf02178367d05eaf23
ms.sourcegitcommit: 3105642fca2392edef574b60b4748a82cda0a386
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/12/2022
ms.locfileid: "8109589"
---
# <a name="enable-cash-flow-forecasting"></a>Aktivera kassaflödesprognoser

[!include [banner](../includes/banner.md)]

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

> [!NOTE]
> Modellutbildning för **kassaflödesprognos** kräver data som sträcker sig över mer än ett år och innehåller mer än 100 transaktioner. Vi rekommenderar att du har minst två års data med mer än 1 000 transaktioner.

Mer information om funktionen för kassaflödesprognoser finns i [Kassaflödesprognoser](cash-flow-forecast-intro.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
