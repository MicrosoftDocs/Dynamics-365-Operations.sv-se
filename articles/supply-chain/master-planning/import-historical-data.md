---
title: Importera historikdata för efterfrågeprognoser
description: För att få korrekta efterfrågeprognoser behöver du historiska efterfrågedata per artikel eller artikelallokeringsnyckel. Det här avsnittet beskriver hur du använder dataenheter för att importera historiska efterfrågedata från valfritt system, så att du får en längre historik över efterfrågeprognosdatan.
author: roxanadiaconu
manager: tfehr
ms.date: 05/10/2017
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
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
ms.openlocfilehash: d6ba2e1a3a884d29bff491f914aa2d5f9ece2b84
ms.sourcegitcommit: 79621e667cd7f48ba3bdbf2731f6f33d8e9f57f6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/10/2021
ms.locfileid: "5154237"
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

## <a name="example"></a>Exempel

Du kan använda följande fil som exempel. Hämta [HistoricalDemandData](https://docs.microsoft.com/dynamics/s-e/). Denna fil innehåller historiska efterfrågedata för artikel D0001. Den innehåller endast följande obligatoriska fält: webbplats, kvantitet och efterfrågedatum.

1. Välj det företag som du vill importera de historiska efterfrågeuppgifterna till.
2. Öppna arbetsytan **Datahantering**.
3. Välj panelen **Import**.
4. Namnge importprojektet, exempelvis **Importera historisk efterfrågan för artikeln D0001**.
5. I fältet **Källdataformat** väljer du filformat för den fil som du importerar. Om du vill importera filen HistoricalDemandData i det här exemplet väljer du **CSV**.
6. I fältet **Enhetsnamn** väljer du **Historisk extern efterfrågan**.
7. Spara filen på din dator och överför den sedan.
8. Välj **Importera**.
9. Sidan **Utförandesummering** öppnas automatiskt. Kontrollera den importerade informationen på sidan.

När du har importerat efterfrågehistoriken kan du skapa en efterfrågeprognos.

## <a name="additional-resources"></a>Ytterligare resurser

[Generera en statistisk baslinjeprognos](generate-statistical-baseline-forecast.md)  
[Översikt över jobb för import och export av data](../../fin-ops-core/dev-itpro/data-entities/data-import-export-job.md)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]