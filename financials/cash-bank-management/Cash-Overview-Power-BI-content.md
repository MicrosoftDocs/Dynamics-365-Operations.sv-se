---
title: "Power BI-innehåll för kassaöversikt"
description: "Det här avsnittet beskriver Power BI-innehåll för översikt över översikt över kontanter Det förklarar hur du kommer åt rapporterna som är inkluderade i innehållspaketet, samt ger dig information om den datamodell och de enheter som användes för att skapa innehållspaketet."
author: saraschi2
manager: AnnBe
ms.date: 06/16/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: Human Translation
ms.sourcegitcommit: 63160b9473c7f45b0eb0ca7139f9ed47c8e1446f
ms.openlocfilehash: e969c2033463d565ce782c7dc8cfc4b458349289
ms.contentlocale: sv-se
ms.lasthandoff: 06/20/2017

---

# Power BI-innehåll för kassaöversikt
<a id="cash-overview-power-bi-content" class="xliff"></a>

[!include[banner](../includes/banner.md)]

Det här avsnittet beskriver **Översikt över kontanter** för Microsoft Power BI-innehåll. Det förklarar hur du kommer åt rapporterna som är inkluderade i innehållspaketet, samt ger dig information om den datamodell och de enheter som användes för att skapa innehållspaketet.

## Översikt
<a id="overview" class="xliff"></a>

Power BI-innehåll för **kassaöversikt** har skapats för personer som är ansvariga för kontanta betalningar i din organisation. Power BI-innehåll för **kassaöversikt** ger insyn i kassaflödet. Det innehåller även prognoser som kan hjälpa dig att fatta bättre beslut och därmed förbättra kassaflödet. Du kan analysera kontanter per juridisk person, valuta och bankkonto för att få en bättre förståelse för överskott och brister.

## Åtkomst till Power BI-innehåll
<a id="accessing-the-power-bi-content" class="xliff"></a>

Om du använder Microsoft Dynamics 365 for Finance and Operations, Enterprise edition juli 2017 - uppdatering visas rapporter från **Kassaöversikt** i arbetsytorna **Kassaöversikt** och **Bankhantering**.

## Rapporter som ingår i Power BI-innehållet
<a id="reports-that-are-included-in-the-power-bi-content" class="xliff"></a>
I följande tabell finns information om mått som finns på varje enskild rapportsida i Power BI-innehållet för **kassaöversikt**.

| Rapport                                | Innehåll |
|---------------------------------------|----------|
| Kassaöversikt - alla företag         | <ul><li>Kostnader och intäkter i systemvaluta</li><li>Prognostiserade valutasaldon</li><li>Totalt banksaldo i systemvaluta</li><li>Saldo per juridisk person</li><li>Aktuellt utfall kontra prognostiserat saldot i bankkontots valuta</li></ul> |
| Kassaöversikt - aktuellt företag       | <ul><li>Kostnader och intäkter i redovisningsvaluta</li><li>Prognostiserade valutasaldon</li><li>Totalt banksaldo i redovisningsvaluta</li><li>Aktuellt utfall kontra prognostiserat saldot i bankkontots valuta</li></ul> |
| Kassaflödesprognos - alla företag    | <ul><li>Kostnader och intäkter i systemvaluta</li><li>Daglig sammanfattningsprognos</li><li>Prognosdetaljer</li></ul> |
| Kassaflödesprognos- valutaföretag | <ul><li>Kostnader och intäkter i redovisningsvaluta</li><li>Daglig sammanfattningsprognos</li><li>Prognosdetaljer</li></ul> |
| Valutaprognos                     | <ul><li>Prognostiserade valutasaldon</li><li>Daglig sammanfattningsvaluta</li><li>Prognosdetaljer</li></ul> |
| Banksaldon                         | <ul><li>Totalt banksaldo i systemvaluta</li><li>Saldo per juridisk person</li><li>Aktuellt utfall kontra prognostiserat saldot i bankkontots valuta</li><li>Saldo per bankkonto</li><li>Saldo per valuta</li></ul> |

## Utöka Power BI-innehåll
<a id="extending-the-power-bi-content" class="xliff"></a>
Du kan ge utmärkt analys till de som inte loggar in Dynamics 365 genom att använda innehållspaketen tillgängliga i Lifecycle Services (LCS). Dessa innehållspaket kan ändras så att de innehåller andra rapporter och modeller och publicera till din Power BI.com-innehavare för analys. 

Du hittar Power BI-innehåll för **Kassaöversikt** i det delade resursbiblioteket i LCS. Mer information om hur du laddar ned innehållspaket och använder det i din organisation finns i [Power BI-innehåll i LCS från Microsoft och dina partner](/dynamics365/unified-operations/dev-itpro/analytics/power-bi-content-microsoft-partners). Om du vill se en demonstration som visar hur du implementerar Power BI-innehållet, se [Power BI-innehåll från Microsoft och dina samarbetspartners i Dynamics Lifecycle Services](https://mix.office.com/watch/9puyb1b2xs1w) Office mix.

## Förstå datamodellen och enheterna
<a id="understanding-the-data-model-and-entities" class="xliff"></a>

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

Dessa enheter används för att skapa beräknade mått i datamodellen. Beräknade åtgärder används sedan för att beräkna diagram och rapporter som används i Power BI-innehållspaketet för **Kassaöversikt**. Om du vill inkludera ytterligare beräkningar i rapporterna och instrumentpanelerna kan du ladda ned och ändra Power BI-filen från LCS. Filen är den standarddatamodell som använts för att skapa innehållet. +När du är klar med ändringarna kan du skapa ett innehållspaket för organisationen samt en instrumentpanel som innehåller den information som du har lagt till.


