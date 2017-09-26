---
title: "Importera historikdata för efterfrågeprognoser"
description: "För att få korrekta efterfrågeprognoser behöver du historiska efterfrågedata per artikel eller artikelallokeringsnyckel. Det här avsnittet beskriver hur du använder dataenheter för att importera historiska efterfrågedata från valfritt system, så att du får en längre historik över efterfrågeprognosdatan."
author: roxanadiaconu
manager: AnnBe
ms.date: 05/10/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Core, AX 7.0.0, Operations, UnifiedOperations
ms.assetid: 59c0d269-9db0-48e7-b8c7-9a388781a9ca
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: roxanad
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: Human Translation
ms.sourcegitcommit: 869151f2486b7a481e4694cfb6992d0ee2cfc008
ms.openlocfilehash: 957626a283b750645adefa5176480e68cc27e4f1
ms.contentlocale: sv-se
ms.lasthandoff: 06/13/2017

---

# <a name="import-historical-data-for-demand-forecasts"></a>Importera historikdata för efterfrågeprognoser

[!include[banner](../includes/banner.md)]

För att garantera att efterfrågeprognoserna blir korrekt måste du ha lika mycket historiska efterfrågeuppgifter som du kan för varje artikel eller artikelallokeringsnyckel. Om den historiska begärandedatan inte redan har importerats, använd då dataenheten **Historisk extern begäran** (ReqDemPlanHistoricalExternalDemandEntity) i Microsoft Dynamics 365 for Finance and Operations för att importera den.

I arbetsytan **Datahantering** kan du visa en översikt över alla fält i entiteten.

1. Öppna arbetsytan **Datahantering**.
2. Klicka på fliken **Dataenheter**.
3. Sök enhetslistan för **Historisk extern efterfrågan**.
4. Klicka på **Målfält**. Följande enhetsfält är obligatoriska: webbplats (**DeliveringSiteId**), datum (**DemandDate**), kvantitet (**DemandQuantity**) samt antingen artikelnummer (**ItemNumber**) eller artikelallokeringsnyckel (**ProductAllocationKeyId**).

Du måste ha en Microsoft Excel-fil eller kommaseparerade värden (CSV) som innehåller historiska efterfrågeuppgifter data om du vill använda dataenheten. I följande exempel visas hur du importerar data från en CSV-fil.

## <a name="example"></a>Exempel

Du kan använda följande fil som exempel. Hämta [HistoricalDemandData](https://mbs.microsoft.com/customersource/northamerica/AX/learning/documentation/how-to-articles/365OperationsDemandForecast). Denna fil innehåller historiska efterfrågedata för artikel D0001. Den innehåller endast följande obligatoriska fält: webbplats, kvantitet och efterfrågedatum.

1. Välj det företag som du vill importera de historiska efterfrågeuppgifterna till.
2. Öppna arbetsytan **Datahantering**.
3. Klicka på fliken **Importera**.
4. Namnge importprojektet, exempelvis **Importera historisk efterfrågan för artikeln D0001**.
5. I fältet **Källdataformat** väljer du filformat för den fil som du importerar. Om du vill importera filen HistoricalDemandData i det här exemplet väljer du **CSV**.
6. I fältet **Enhetsnamn** väljer du **Historisk extern efterfrågan**.
7. Spara filen på din dator och överför den sedan.
8. Klicka på **Importera**.
9. Sidan **Utförandesummering** öppnas automatiskt. Kontrollera den importerade informationen på sidan.

När du har importerat efterfrågehistoriken kan du skapa en efterfrågeprognos.

## <a name="see-also"></a>Se även

[Generera en statistisk baslinjeprognos](generate-statistical-baseline-forecast.md)
