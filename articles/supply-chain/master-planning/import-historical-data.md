---
title: Importera historikdata för efterfrågeprognoser
description: För att få korrekta efterfrågeprognoser behöver du historiska efterfrågedata per artikel eller artikelallokeringsnyckel. Det här avsnittet beskriver hur du använder dataenheter för att importera historiska efterfrågedata från valfritt system, så att du får en längre historik över efterfrågeprognosdatan.
author: roxanadiaconu
ms.date: 05/10/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ReqDemPlanCreateForecastDialog
audience: Application User
ms.reviewer: kamaybac
ms.assetid: 59c0d269-9db0-48e7-b8c7-9a388781a9ca
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: kamaybac
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0b04ee246d4c28e934407ccb92d792692cc4347d
ms.sourcegitcommit: cbbb35c71ab4ff1ae08fa4f7cc97019b207246be
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/23/2021
ms.locfileid: "6301660"
---
# <a name="import-historical-data-for-demand-forecasts"></a>Importera historikdata för efterfrågeprognoser

[!include [banner](../includes/banner.md)]

För att garantera att efterfrågeprognoserna blir korrekt måste du ha lika mycket historiska efterfrågeuppgifter som du kan för varje artikel eller artikelallokeringsnyckel. Om den historiska efterfrågedatan inte redan har importerats, använd då dataenheten **Historisk extern efterfrågan** (ReqDemPlanHistoricalExternalDemandEntity) i Dynamics 365 Supply Chain Management för att importera den.

I arbetsytan **Datahantering** kan du visa en översikt över alla fält i entiteten.

1. Öppna arbetsytan **Datahantering**.
2. Klicka på fliken **Dataenheter**.
3. Sök enhetslistan för **Historisk extern efterfrågan**.
4. Välj **målfält**. Följande enhetsfält är obligatoriska: webbplats (**DeliveringSiteId**), datum (**DemandDate**), kvantitet (**DemandQuantity**) samt antingen artikelnummer (**ItemNumber**) eller artikelallokeringsnyckel (**ProductAllocationKeyId**).

Du måste ha en Microsoft Excel-fil eller kommaseparerade värden (CSV) som innehåller historiska efterfrågeuppgifter data om du vill använda dataenheten. I följande exempel visas hur du importerar data från en CSV-fil.

Mer information om hur du importerar data, bland annat hur du rensar data efter en import, finns i [Översikt över dataimport- och exportjobb](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md) samt relaterade ämnen.

Se [Generera en statistisk baslinjeprognos](generate-statistical-baseline-forecast.md).

[!INCLUDE[footer-include](../../includes/footer-banner.md)]