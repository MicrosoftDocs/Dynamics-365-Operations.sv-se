---
title: Arbetsyta för leverantörsbetalningar
description: Det här avsnittet innehåller information om arbetsytan för leverantörsbetalningar. Arbetsyta för leverantörsbetalningar visar information kopplad till behandling av leverantörsbetalningar.
author: abruer
manager: AnnBe
ms.date: 06/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: VendPaymentWorkspace
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.assetid: ''
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 89ba0d68bd52413328dd583e87b09b01fd523d6f
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2180044"
---
# <a name="vendor-payments-workspace"></a>Arbetsyta för leverantörsbetalningar

[!include [banner](../includes/banner.md)]

Arbetsytan **Leverantörsbetalningar** visar information kopplad till behandling av leverantörsbetalningar. Den här arbetsytan innehåller vyn **Mitt arbete** och sidan **Analyser**. Vyn **Mitt arbete** visar sammanfattningsrutor, rutnät för leverantörstransaktioner och relaterad leverantörsinformation. Sidan **Analyser** använder funktionerna i Microsoft Power BI för att visa modeller relaterade till leverantörsbetalningar.

## <a name="setup-needed-to-view-power-bi-content"></a>Installationen som behövs för att visa Power BI-innehåll

Följande inställningar måste slutföras för att data ska visas i **Leverantörsbetalningar**Power BI-visualiseringar.
1. Gå till **systemadministrations > inställningar > systemparametrar** för att ställa in **Systemvaluta** och **Systemets valutakurs**.
2. Gå till **redovisning > Inställningar > redovisning** om du vill ange **redovisningsvaluta** och **valutakurstyp**. 
2. Definiera valutakurser mellan transaktionsvalutor och redovisningsvaluta, redovisningsvaluta och systemvaluta. Det gör du genom att gå till **redovisning > valutor > valutakurser**.
3. Gå till **Systemadministration > Inställningar > Enhetslagring** för att uppdatera sammanlagda måtten **VendPaymentBIMeasure**. 

## <a name="my-work-view"></a>Vyn Mitt arbete

### <a name="summary-tiles"></a>Sammanfattningsrutor

Rutorna i avsnittet **Sammanfattning** ger en översikt över statusen på din betalningsinformation. Du kan se betalningsjournaler som ännu inte har bokförts, fakturor som har passerat förfallodatum, alla leverantörer och spärrade leverantörer. Från avsnittet **Sammanfattning** kan du skapa en ny betalningskörning.

Informationen i avsnittet **Sammanfattning** är avsett för det företag du är inloggat på.

### <a name="vendor-transactions-grids"></a>Rutnät för leverantörstransaktioner

Avsnittet **Leverantörstransaktioner** innehåller rutnät som visar fakturor som har förfallit till betalning och betalningar som inte har kvittats. Från rutnätet **Förfallna fakturor** kan du visa kvittningshistoriken för en vald faktura. Från rutnätet **Förfallna betalningar** kan du visa kvittningshistoriken för en vald faktura och kvitta en faktura.

Ansvariga för centraliserade kundreskontrabetalningar kan använda ett filter som visas överst i varje rutnät för att välja ett företag. Sedan filtreras rutnätet så att det bara visar företag som definieras i organisationshierarkin för centraliserad betalning som den ansvarige för centraliserade kundreskontrabetalningar har behörighet att visa.

Under fliken **Sök transaktioner** i avsnittet **Leverantörstransaktioner** kan du söka efter en leverantörstransaktion.

### <a name="related-information"></a>Relaterad information

Du kan visa rapporterna **Åldersrapport för leverantörer** och **Betalningar per datum** genom att använda länkarna i avsnittet **Relaterad information** på arbetsytan.

## <a name="analytics-page"></a>Analyssida

På sidan **Analyser** finns viktiga mätvärden såsom leverantörsfakturor som har förfallit till betalning och leverantörsfakturor som förfaller i framtiden. Denna sida innehåller nio rapportsidor. En sida ger en översikt och de andra åtta sidorna ger information om statistik över leverantörsreskontrabetalning.

Följande tabell visar de visulaiseringar som är tillgängliga på varje rappportsida.


|            Rapportsida            |                                                                                                                                                                                Visualisering                                                                                                                                                                                |
|-----------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     Översikt över leverantörsbetalningar      | <ul><li>Förfallna fakturor</li><li>Fakturor som förfaller idag</li><li>Rabatter vid förlorade rabatter</li><li>Fakturor med kassarabattdatum som förfaller i framtiden</li><li>Fakturor med förfallodatum i framtiden</li><li>Fakturor som betalats sent till fakturor som betalats i tid</li><li>Tilldelning av arbetsflöde för betalning</li><li>Kund till leverantörssaldo</li><li>Öppna fakturor med betalningsspärr</li></ul> |
|         Förfallna fakturor         |                                                                                             <ul><li>Förfallna fakturor</li><li>Information om förfallna fakturor</li><li>Totalt antal öppna fakturor</li><li>Förfallna fakturor per leverantörsgrupp</li><li>Förfallna fakturor per företag</li></ul>                                                                                              |
|        Fakturor som förfaller idag         |                                                                                                         <ul><li>Fakturor som förfaller idag</li><li>Information om fakturor som förfaller idag</li><li>Fakturor som förfaller idag per företag</li><li>Fakturor som förfaller idag per leverantörsgrupp</li></ul>                                                                                                          |
| Rabatter vid förlorade rabatter |                                                                             <ul><li>Rabatter vid förlorade rabatter</li><li>Information om rabatter vid förlorade rabatter</li><li>Rabatter vid förlorade rabatter per företag</li><li>Rabatter vid förlorade rabatter per leverantörsgrupp</li></ul>                                                                              |
|      Fakturor som förfaller i framtiden       |                                                 <ul><li>Fakturor som förfaller i framtiden</li><li>Information om fakturor som förfaller i framtiden</li><li>Fakturor som förfaller i framtiden per företag</li><li>Fakturor som förfaller i framtiden per leverantörsgrupp</li><li>Fakturor med kassarabattdatum som förfaller i framtiden</li><li>Fakturor med förfallodatum i framtiden</li></ul>                                                  |
|        Fakturor som betalats sent         |                                                         <ul><li>Fakturor som betalats efter förfallodatum</li><li>Information om fakturor som betalats efter förfallodatum</li><li>Fakturor som betalats efter förfallodatum per företag</li><li>Fakturor som betalats efter förfallodatum per leverantörsgrupp</li><li>Fakturor som betalats sent mot fakturor som betalats i tid</li></ul>                                                          |
|         Arbetsflöde för betalning          |                                                                                <ul><li>Instanser av arbetsflöde för betalning</li><li>Instanser av arbetsflöde för betalning per godkännare</li><li>Instanser av arbetsflöde för betalning per företag</li><li>Genomsnittligt antal dagar i arbetsflödet per godkännare</li></ul>                                                                                |
|    Kund till leverantörssaldo     |                                                                                                                   <ul><li>Kund till leverantörssaldo</li><li>Kund till leverantörssaldo per företag</li><li>Information om kund till leverantörssaldo</li></ul>                                                                                                                    |
|    Fakturor med betalningsspärr     |                                                                                         <ul><li>Fakturor med betalningsspärr</li><li>Information om fakturor med betalningsspärr</li><li>Fakturor med betalningsspärr per företag</li><li>Fakturor med betalningsspärr per leverantörsgrupp</li></ul>                                                                                          |

