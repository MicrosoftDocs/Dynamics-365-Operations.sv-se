---
title: Kassaöversikt Power BI-innehåll
description: Det här avsnittet beskriver Power BI-innehåll för översikt över översikt över kontanter Det förklarar hur du kommer åt rapporterna som är inkluderade i innehållspaketet, samt ger dig information om den datamodell och de enheter som användes för att skapa innehållspaketet.
author: saraschi2
manager: AnnBe
ms.date: 07/16/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: BankTreasurerWorkspace
audience: Application User
ms.reviewer: roschlom
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.openlocfilehash: 0f10022ae4906972d08e08e3e5476630213468d6
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4985471"
---
# <a name="cash-overview-power-bi-content"></a>Kassaöversikt Power BI-innehåll

[!include [banner](../includes/banner.md)]

Det här avsnittet beskriver **Kassaöversikt** för Microsoft Power BI-innehåll. Det förklarar hur du kommer åt rapporterna som är inkluderade i innehållspaketet, samt ger dig information om den datamodell och de enheter som användes för att skapa innehållspaketet.

## <a name="overview"></a>Översikt

**Kassaöversikt** för Power BI-innehåll har skapats för personer som är ansvariga för kontanta betalningar i din organisation. **Kassaöversikt** Power BI-innehåll ger insyn i kassaflödet. Det innehåller även prognoser som kan hjälpa dig att fatta bättre beslut och därmed förbättra kassaflödet. Du kan analysera kontanter per juridisk person, valuta och bankkonto för att få en bättre förståelse för överskott och brister.

## <a name="setup-needed-to-view-power-bi-content"></a>Installationen som behövs för att visa Power BI-innehåll

Följande inställningar måste slutföras för att data ska kunna visas i **kassaöversikt** och **bankhantering** Power BI visuella element.

1. Gå till **systemadministrations > inställningar > systemparametrar** för att ställa in **Systemvaluta** och **Systemets valutakurs**.
2. Gå till **Redovisning > kalendrar > räkenskapskalendrar** om du vill validera räkenskapskalender datum som tilldelats den aktiva tidsperioden.
3. Gå till **redovisning > Inställningar > redovisning** om du vill ange **redovisningsvaluta** och **valutakurstyp**.
4. Definiera valutakurser mellan transaktionsvalutor och redovisningsvaluta, redovisningsvaluta och systemvaluta samt redovisningsvaluta och bankvalutor. Det gör du genom att gå till **redovisning > valutor > valutakurser**.
5. Konfigurera och kör kassaflödesprognoser. Mer information om hur du ställer in prognoser för kassaflöden finns i [Kassaflödesprognoser](https://docs.microsoft.com/dynamics365/finance/cash-bank-management/cash-flow-forecasting). 
6. Gå till **Systemadministration > Inställningar > Enhetslagring** för att uppdatera sammanlagda måtten **LedgerCovLiquidityMeasurement**.

## <a name="accessing-the-power-bi-content"></a>Komma åt Power BI-innehåll

Rapporter från **Kassaöversikt** Power BI-innehåll visas i arbetsytorna **Kassaöversikt** och **Bankhantering**.

Om du vill visa kassaflödesprognoser med data måste du först köra prognosberäkningsprocessen genom att använda funktionen **beräkna kassaflödesprognoser** i området för kassa- och bankhantering. Detta måste fyllas i för varje företag som ingår i prognosen.  Sedan måste du uppdatera det sammanlagda måttet LedgerCovLiquidityMeasurement på sidan **Enhetslagring**.  

I demonstrationssyfte kan du lägga till demodata för kassaflödesprognoser med sidan **generera data** från demodatamodulen.  Det här skriptet infogar data i kassaflödesprognostabeller för att snabbt fylla i information som behövs för rapporter.  Denna modul är endast tillgänglig om du använder en demodatapaketmodell i miljön. 

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Rapporter som ingår i Power BI-innehållet

I följande tabell finns information om mått som finns på varje enskild rapportsida i **kassaöversikt** Power BI-innehåll.

| Rapport                                | Innehåll |
|---------------------------------------|----------|
| Kassaöversikt – alla företag         | <ul><li>Kostnader och intäkter i systemvaluta</li><li>Prognostiserade valutasaldon</li><li>Totalt banksaldo i systemvaluta</li><li>Saldo per juridisk person</li><li>Aktuellt utfall kontra prognostiserat saldot i bankkontots valuta</li></ul> |
| Kassaöversikt – aktuellt företag       | <ul><li>Kostnader och intäkter i redovisningsvaluta</li><li>Prognostiserade valutasaldon</li><li>Totalt banksaldo i redovisningsvaluta</li><li>Aktuellt utfall kontra prognostiserat saldot i bankkontots valuta</li></ul> |
| Kassaflödesprognos – alla företag    | <ul><li>Kostnader och intäkter i systemvaluta</li><li>Daglig sammanfattningsprognos</li><li>Prognosdetaljer</li></ul> |
| Kassaflödesprognos- valutaföretag | <ul><li>Kostnader och intäkter i redovisningsvaluta</li><li>Daglig sammanfattningsprognos</li><li>Prognosdetaljer</li></ul> |
| Valutaprognos                     | <ul><li>Prognostiserade valutasaldon</li><li>Daglig sammanfattningsvaluta</li><li>Prognosdetaljer</li></ul> |
| Banksaldon                         | <ul><li>Totalt banksaldo i systemvaluta</li><li>Saldo per juridisk person</li><li>Aktuellt utfall kontra prognostiserat saldot i bankkontots valuta</li><li>Saldo per bankkonto</li><li>Saldo per valuta</li></ul> |


## <a name="understanding-the-data-model-and-entities"></a>Förstå datamodellen och enheterna

Följande tabell visar enheterna som **Kassaöversikt** Power BI-innehåll baseras på.

| Enhet                                                                          | Innehåll |
|---------------------------------------------------------------------------------|----------|
| LedgerCovLiquidityMeasurement\_företag                                          | Företag att filtrera rapporter efter |
| LedgerCovLiquidityMeasurement\_datum                                             | Datum att filtrera rapporter efter |
| LedgerCovLiquidityMeasurement\_LedgerCovForecastActual                          | Aktuellt banksaldo kontra senaste prognostiserade banksaldo |
| LedgerCovLiquidityMeasurement\_LedgerCovLiquidity                               | Prognostiserade transaktionsdetaljer |
| LedgerCovLiquidityMeasurement\_LedgerCovLiquidityInflowOutflowBalanceCompany    | Summerade kassainflöden och kassautflöden och saldo med varje företag redovisningsvaluta |
| LedgerCovLiquidityMeasurement\_LedgerCovLiquidityInflowOutflowBalanceEnterprise | Summerade kassainflöden och kassautflöden och saldo som använder systemvaluta för alla företag |
| LedgerCovLiquidityMeasurement\_LedgerCovLiquidityTransactionCurrency            | Summerad nettotransaktionsbelopp och saldo av valutor med hjälp av transaktionsvalutan |


[!INCLUDE[footer-include](../../includes/footer-banner.md)]