---
title: Använd externa data i kassaflödesprognoser (förhandsversion)
description: I det här ämnes beskrivs de konfigurationssteg som du måste utföra så att externa data kan anges i eller importeras till kassaflödesprognoser.
author: rcarlson
manager: AnnBe
ms.date: 05/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: LedgerJournalSetup, LedgerJournalTable
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.custom: 15721
ms.assetid: b4b406fa-b772-44ec-8dd8-8eb818a921ef
ms.search.region: Global
ms.author: peakerbl
ms.search.validFrom: 2020-06-08
ms.dyn365.ops.version: AX 10.0.12
ms.openlocfilehash: 801327dc54f6d4cfef7a9f062395e29846783e8f
ms.sourcegitcommit: deb711c92251ed48cdf20ea514d03461c26a2262
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644955"
---
# <a name="use-external-data-in-cash-flow-forecasts-preview"></a>Använd externa data i kassaflödesprognoser (förhandsversion)

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Externa data kan anges i eller importeras till kassaflödesprognoser. I det här avsnittet beskrivs de konfigurationssteg som är specifika för användningen av externa data och som gör att externa data kan inkluderas i en kassaflödesprognos.

## <a name="external-data-setup"></a>Konfigurera externa data

Använd fliken **Extern källa** på sidan **Kassaflödesprognosinställningar** (**Kassa- och bankhantering \> Kassaflödeprognoser**) om du vill ange inställningar som stöder användning av externa data i kassaflödesprognoser.

Mer information om konfigurationen finns i [Kassaflödesprognoser](https://docs.microsoft.com/dynamics365/finance/cash-bank-management/cash-flow-forecasting).

Om du vill ange externa data för kassaflödesprognoser kan du använda Öppna i Excel-upplevelsen för att ange och ändra externa data. Välj knappen **Externa data** och välj sedan antingen **Lägg till externa data** eller **Redigera befintliga externa data**. När Microsoft Excel-filen öppnas kan du ange information i följande fält:

- **Åtkomst-ID**
- **Beskrivning** (valfritt)
- **Namn på extern källa** – Välj ett av de värden i listan som du definierade när du konfigurerade Ekonomiinsikter.
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

#### <a name="privacy-notice"></a>Sekretesspolicy
Förhandsversioner (1) kan använda färre sekretess- och säkerhetsfunktioner än Dynamics 365 Finance and Operations, (2) de ingår inte i serviceavtalet (SLA) för den här tjänsten, (3) bör inte användas för behandling av personuppgifter eller andra uppgifter som omfattas av lagar och andra efterlevnadskrav, samt (4) har begränsad support.
