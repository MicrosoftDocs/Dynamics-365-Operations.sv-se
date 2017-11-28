---
title: "Power BI-innehåll för kassaöversikt"
description: "Det här avsnittet beskriver Power BI-innehåll för översikt över översikt över kontanter Det förklarar hur du kommer åt rapporterna som är inkluderade i innehållspaketet, samt ger dig information om den datamodell och de enheter som användes för att skapa innehållspaketet."
author: saraschi2
manager: AnnBe
ms.date: 06/22/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: sericks
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2017-06-30
ms.dyn365.ops.version: July 2017 update
ms.translationtype: HT
ms.sourcegitcommit: 2771a31b5a4d418a27de0ebe1945d1fed2d8d6d6
ms.openlocfilehash: fdcd3083f475967ec2e5f94dad850a1bf98c864a
ms.contentlocale: sv-se
ms.lasthandoff: 11/03/2017

---

# <a name="cash-overview-power-bi-content"></a>Power BI-innehåll för kassaöversikt

[!include[banner](../includes/banner.md)]

Det här avsnittet beskriver **Översikt över kontanter** för Microsoft Power BI-innehåll. Det förklarar hur du kommer åt rapporterna som är inkluderade i innehållspaketet, samt ger dig information om den datamodell och de enheter som användes för att skapa innehållspaketet.

## <a name="overview"></a>Översikt

Power BI-innehåll för **kassaöversikt** har skapats för personer som är ansvariga för kontanta betalningar i din organisation. Power BI-innehåll för **kassaöversikt** ger insyn i kassaflödet. Det innehåller även prognoser som kan hjälpa dig att fatta bättre beslut och därmed förbättra kassaflödet. Du kan analysera kontanter per juridisk person, valuta och bankkonto för att få en bättre förståelse för överskott och brister.

## <a name="accessing-the-power-bi-content"></a>Åtkomst till Power BI-innehåll

Om du använder Dynamics 365 for Finance and Operations, Enterprise edition (juli-uppdateringen 2017) visas rapporter från Power BI-innehållet **Kassaöversikt** i arbetsytorna **Kassaöversikt** och **Bankhantering**.

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

## <a name="extending-the-power-bi-content"></a>Utöka Power BI-innehåll
Du kan ge utmärkt analys till de som inte loggar in Dynamics 365 genom att använda innehållspaketen tillgängliga i Lifecycle Services (LCS). Dessa innehållspaket kan ändras så att de innehåller andra rapporter och modeller och publicera till din Power BI.com-innehavare för analys. 

Du hittar Power BI-innehåll för **Kassaöversikt** i det delade resursbiblioteket i LCS. Mer information om hur du laddar ned innehållspaket och använder det i din organisation finns i [Power BI-innehåll i LCS från Microsoft och dina partner](../../dev-itpro/analytics/power-bi-content-microsoft-partners.md). Om du vill se en demonstration som visar hur du implementerar Power BI-innehållet, se [Power BI-innehåll från Microsoft och dina samarbetspartners i Dynamics Lifecycle Services](https://mix.office.com/watch/9puyb1b2xs1w) Office mix.

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

Dessa enheter används för att skapa beräknade mått i datamodellen. Beräknade åtgärder används sedan för att beräkna diagram och rapporter som används i Power BI-innehållspaketet för **Kassaöversikt**. Om du vill inkludera ytterligare beräkningar i rapporterna och instrumentpanelerna kan du ladda ned och ändra Power BI-filen från LCS. Filen är den standarddatamodell som använts för att skapa innehållet. +När du är klar med ändringarna kan du skapa ett innehållspaket för organisationen samt en instrumentpanel som innehåller den information som du har lagt till.


