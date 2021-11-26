---
title: Använd externa data i kassaflödesprognoser
description: I detta ämne beskrivs de konfigurationssteg som måste utföras för att externa data ska kunna anges i eller importeras till kassaflödesprognoser.
author: rcarlson
ms.date: 11/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2020-06-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: dbfa04228cf63c0874a7d69af4e2b932544c0d7f
ms.sourcegitcommit: 03fa7556840aa59f825697f6f9edeb58ea673fca
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/04/2021
ms.locfileid: "7753012"
---
# <a name="use-external-data-in-cash-flow-forecasts"></a>Använd externa data i kassaflödesprognoser

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Externa data kan anges i eller importeras till kassaflödesprognoser. I det här avsnittet beskrivs de konfigurationssteg som är specifika för användningen av externa data och som gör att externa data kan inkluderas i en kassaflödesprognos.

## <a name="external-data-setup"></a>Konfigurera externa data

Använd fliken **Extern källa** på sidan **Konfiguration för kassaflödesprognos** (**Hantering av kontanter och bankärenden\> Kassaflödesprognos \> Konfiguration för kassaflödesprognos**) för att ange inställningar som stöder användning av externa data i kassaflödesprognoser.

Externa data kan anges i eller importeras till kassaflödesprognoser. Innan externa data anges eller importeras måste externa källor konfigureras. På fliken **Extern källa** konfigurerar du externa kassaflödeskategorier. En kategori kan vara antingen **Utgående** eller **Inkommande**. **Likviditet** bör väljas som bokföringstyp. I rutnätet **Inställningar för juridisk person** väljer du de juridiska personer och motsvarande huvudkonton som kategorierna för externt kassaflöde gäller för.

Mer information om hur du ställer in prognoser för kassaflöden finns i [Kassaflödesprognoser](../cash-bank-management/cash-flow-forecasting.md).

## <a name="enter-external-data"></a>Ange externa data

Du kan använda funktionen **Öppna i Excel** för att ange och ändra externa data för kassaflödesprognoser. Välj knappen **Externa data** på sidan **Konfiguration för kassaflödesprognos** och välj sedan antingen **Lägg til externa data** eller **Redigera befintliga externa data**. När Microsoft Excel-filen öppnas kan du ange information i följande fält:

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
