---
title: "Power BI-innehåll för kassaöversikt"
description: "Det här avsnittet beskriver Power BI-innehåll för översikt över översikt över kontanter Det förklarar hur du kommer åt rapporterna som är inkluderade i innehållspaketet, samt ger dig information om den datamodell och de enheter som användes för att skapa innehållspaketet."
author: saraschi2
manager: AnnBe
ms.date: 12/19/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: BankTreasurerWorkspace
audience: Application User
ms.reviewer: sericks
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: cb43245afe578341251b140383a3b03ba2abd962
ms.openlocfilehash: 5d02a009ca988f91a212e467d4f9784248bbae76
ms.contentlocale: sv-se
ms.lasthandoff: 12/19/2017

---

# <a name="cash-overview-power-bi-content"></a>Power BI-innehåll för kassaöversikt

[!include[banner](../includes/banner.md)]

Det här avsnittet beskriver **Översikt över kontanter** för Microsoft Power BI-innehåll. Det förklarar hur du kommer åt rapporterna som är inkluderade i innehållspaketet, samt ger dig information om den datamodell och de enheter som användes för att skapa innehållspaketet.

## <a name="overview"></a>Översikt

Power BI-innehåll för **kassaöversikt** har skapats för personer som är ansvariga för kontanta betalningar i din organisation. Power BI-innehåll för **kassaöversikt** ger insyn i kassaflödet. Det innehåller även prognoser som kan hjälpa dig att fatta bättre beslut och därmed förbättra kassaflödet. Du kan analysera kontanter per juridisk person, valuta och bankkonto för att få en bättre förståelse för överskott och brister.

## <a name="accessing-the-power-bi-content"></a>Åtkomst till Power BI-innehåll

Rapporter från Power BI-innehållet **Kontantöversikt** visas i arbetsytorna **Kontantöversikt** och **Bankhantering**.

Om du vill visa kassaflödesprognoser med data måste du först köra prognosberäkningsprocessen genom att använda funktionen **beräkna kassaflödesprognoser** i området för kassa- och bankhantering.  Detta måste fyllas i för varje företag som ingår i prognosen.  Sedan måste du uppdatera det sammanlagda måttet LedgerCovLiquidityMeasurement på sidan **Enhetslagring**.  

I demonstrationssyfte kan du lägga till demodata för kassaflödesprognoser med sidan **generera data** från demodatamodulen.  Det här skriptet infogar data i kassaflödesprognostabeller för att snabbt fylla i information som behövs för rapporter.  Denna modul är endast tillgänglig om du använder en demodatapaketmodell i miljön. 

## <a name="reports-that-are-included-in-the-power-bi-content"></a>Rapporter som ingår i Power BI-innehållet
I följande tabell finns information om mått som finns på varje enskild rapportsida i Power BI-innehållet för **kassaöversikt**.

| Rapport                                | Innehåll |
|---------------------------------------|----------|
| Kassaöversikt - alla företag         | <ul><li>Kostnader och intäkter i systemvaluta</li><li>Prognostiserade valutasaldon</li><li>Totalt banksaldo i systemvaluta</li><li>Saldo per juridisk person</li><li>Aktuellt utfall kontra prognostiserat saldot i bankkontots valuta</li></ul> |
| Kassaöversikt - aktuellt företag       | <ul><li>Kostnader och intäkter i redovisningsvaluta</li><li>Prognostiserade valutasaldon</li><li>Totalt banksaldo i redovisningsvaluta</li><li>Aktuellt utfall kontra prognostiserat saldot i bankkontots valuta</li></ul> |
| Kassaflödesprognos - alla företag    | <ul><li>Kostnader och intäkter i systemvaluta</li><li>Daglig sammanfattningsprognos</li><li>Prognosdetaljer</li></ul> |
| Kassaflödesprognos- valutaföretag | <ul><li>Kostnader och intäkter i redovisningsvaluta</li><li>Daglig sammanfattningsprognos</li><li>Prognosdetaljer</li></ul> |
| Valutaprognos                     | <ul><li>Prognostiserade valutasaldon</li><li>Daglig sammanfattningsvaluta</li><li>Prognosdetaljer</li></ul> |
| Banksaldon                         | <ul><li>Totalt banksaldo i systemvaluta</li><li>Saldo per juridisk person</li><li>Aktuellt utfall kontra prognostiserat saldot i bankkontots valuta</li><li>Saldo per bankkonto</li><li>Saldo per valuta</li></ul> |


## <a name="understanding-the-data-model-and-entities"></a>Förstå datamodellen och enheterna

Följande tabell visar enheterna som Power BI-innehållspaketet **Kassaöversikt** baseras på.

| Enhet                                                                          | Innehåll |
|---------------------------------------------------------------------------------|----------|
| LedgerCovLiquidityMeasurement\_företag                                          | Företag att filtrera rapporter efter |
| LedgerCovLiquidityMeasurement\_datum                                             | Datum att filtrera rapporter efter |
| LedgerCovLiquidityMeasurement\_LedgerCovForecastActual                          | Aktuellt banksaldo kontra senaste prognostiserade banksaldo |
| LedgerCovLiquidityMeasurement\_LedgerCovLiquidity                               | Prognostiserade transaktionsdetaljer |
| LedgerCovLiquidityMeasurement\_LedgerCovLiquidityInflowOutflowBalanceCompany    | Summerade kassainflöden och kassautflöden och saldo med varje företag redovisningsvaluta |
| LedgerCovLiquidityMeasurement\_LedgerCovLiquidityInflowOutflowBalanceEnterprise | Summerade kassainflöden och kassautflöden och saldo som använder systemvaluta för alla företag |
| LedgerCovLiquidityMeasurement\_LedgerCovLiquidityTransactionCurrency            | Summerad nettotransaktionsbelopp och saldo av valutor med hjälp av transaktionsvalutan |



