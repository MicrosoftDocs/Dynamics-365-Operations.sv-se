---
title: Använd externa data i kassaflödesprognoser (förhandsversion)
description: I det här ämnes beskrivs de konfigurationssteg som du måste utföra så att externa data kan anges i eller importeras till kassaflödesprognoser.
author: rcarlson
ms.date: 07/16/2021
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
ms.openlocfilehash: ff2a454b422cc4decc15339e6b328d99df85ccbc66ba3928f6c9e9f21b7b51a7
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/05/2021
ms.locfileid: "6768853"
---
# <a name="use-external-data-in-cash-flow-forecasts-preview"></a>Använd externa data i kassaflödesprognoser (förhandsversion)

[!include [banner](../includes/banner.md)]

Externa data kan anges i eller importeras till kassaflödesprognoser. I det här avsnittet beskrivs de konfigurationssteg som är specifika för användningen av externa data och som gör att externa data kan inkluderas i en kassaflödesprognos.

## <a name="external-data-setup"></a>Konfigurera externa data

Använd fliken **Extern källa** på sidan **Kassaflödesprognosinställningar** (**Kassa- och bankhantering \> Kassaflödeprognoser**) om du vill ange inställningar som stöder användning av externa data i kassaflödesprognoser.

Mer information om konfigurationen finns i [Kassaflödesprognoser](../cash-bank-management/cash-flow-forecasting.md).

Om du vill ange externa data för kassaflödesprognoser kan du använda Öppna i Excel-upplevelsen för att ange och ändra externa data. Välj knappen **Externa data** och välj sedan antingen **Lägg till externa data** eller **Redigera befintliga externa data**. När Microsoft Excel-filen öppnas kan du ange information i följande fält:

- **Åtkomst-ID**
- **Beskrivning** (valfritt)
- **Namn på extern källa** – Välj ett av de värden i listan som du definierade när du konfigurerade Finance-insikter.
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
