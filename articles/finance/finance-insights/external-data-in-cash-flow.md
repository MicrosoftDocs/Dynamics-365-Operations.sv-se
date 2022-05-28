---
title: Externa data i kassaflödesprognoser
description: I detta ämne beskrivs de konfigurationssteg som måste utföras för att externa data ska kunna anges i eller importeras till kassaflödesprognoser.
author: RyanCCarlson2
ms.date: 02/16/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: kfend
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: rcarlson
ms.search.validFrom: 2020-06-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: f7fac80b7ad0fde273fbd33aa5df146e569be46e
ms.sourcegitcommit: d1683d033fc74adbc4465dd26f7b0055e7639753
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/05/2022
ms.locfileid: "8713738"
---
# <a name="external-data-in-cash-flow-forecasts"></a>Externa data i kassaflödesprognoser

[!include [banner](../includes/banner.md)]

Externa data kan anges i eller importeras till kassaflödesprognoser. I det här avsnittet beskrivs de konfigurationssteg som är specifika för användningen av externa data och som gör att externa data kan inkluderas i en kassaflödesprognos.

## <a name="external-data-setup"></a>Konfigurera externa data

Använd fliken **Extern källa** på sidan **Konfiguration för kassaflödesprognos** (**Hantering av kontanter och bankärenden\> Kassaflödesprognos \> Konfiguration för kassaflödesprognos**) för att ange inställningar som stöder användning av externa data i kassaflödesprognoser.

Externa data kan anges i eller importeras till kassaflödesprognoser. Innan externa data anges eller importeras måste externa källor konfigureras. På fliken **Extern källa** konfigurerar du externa kassaflödeskategorier. En kategori kan vara antingen **Utgående** eller **Inkommande**. **Likviditet** bör väljas som bokföringstyp. I rutnätet **Inställningar för juridisk person** väljer du de juridiska personer och motsvarande huvudkonton som kategorierna för externt kassaflöde gäller för.

Mer information om hur du ställer in prognoser för kassaflöden finns i [Kassaflödesprognoser](../cash-bank-management/cash-flow-forecasting.md).

## <a name="enter-external-data"></a>Ange externa data

Du kan använda funktionen **Öppna i Excel** för att ange och ändra externa data för kassaflödesprognoser. Välj knappen **Externa data** på arbetsytan **Konfiguration för kassaflödesprognos** och välj sedan antingen **Lägg til externa data** eller **Redigera befintliga externa data**. När Microsoft Excel-filen öppnas kan du ange information i följande fält:

- **Åtkomst-ID** (unikt)
- **Beskrivning** (valfritt)
- **Namn på extern källa** – Välj ett av de värden i listan som du definierade när du konfigurerade Finance Insights.
- **Juridisk person**
- **Datum**
- **Belopp i transaktionsvaluta**
- **Valutakod**
- **Standarddimension** (valfritt)
- **Dokumentnummer** (valfritt)
- **Kontonummer** (valfritt)
- **Kontonamn** (valfritt)

## <a name="importing-external-data-by-using-the-data-management-framework"></a>Importera externa data med hjälp av datahanteringsramverket

Du kan importera externa data för kassaflödesprognoser genom att använda arbetsytan **Datahantering** och den entitet som har namnet **Extern källpost för kassaflödesprognos**.

Dessutom, om du måste flytta konfigurationsdata från en miljö till en annan, är följande entitetsområde tillgänglig för konfigurationstabellerna som krävs:

- Konfiguration av extern kassaflödesprognoskälla
- Konfiguration av extern källa för kassaflödesprognos – juridisk person

[!INCLUDE[footer-include](../../includes/footer-banner.md)]
