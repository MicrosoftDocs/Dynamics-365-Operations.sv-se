---
title: Felsöka problem med Finance Insights
description: Det här ämnet visar en lista med problem som kan inträffa när du använder Finance Insights. Här förklaras också hur du löser dessa problem.
author: panolte
ms.date: 11/03/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: roschlom
ms.custom:
- "14151"
- intro-internal
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: shpandey
ms.search.validFrom: 2021-08-20
ms.dyn365.ops.version: AX 10.0.20
ms.openlocfilehash: f3cac30a66ff3a74a7f67c11dd9fa14af79d10af
ms.sourcegitcommit: 03fa7556840aa59f825697f6f9edeb58ea673fca
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/04/2021
ms.locfileid: "7752627"
---
# <a name="troubleshoot-finance-insights-setup-issues"></a>Felsöka problem med Finance Insights

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Det här ämnet visar en lista med problem som kan inträffa när du använder Finance Insights. Här förklaras också hur du löser dessa problem.

## <a name="symptom-why-cant-i-map-the-customer-payment-insights-data-integration-template-destination-column"></a>Symptom: Varför kan jag inte mappa målkolumnen Dataintegrationsmall för kundbetalning?

### <a name="resolution"></a>Lösning

Du kanske använder en mall för en tidigare version. Innan version 10.0.17 frisläpps måste kunderna förhandsgranskas i **Resultat av kundbetalningsinsikter (CDS till Fin och Ops)** dataintegreringsmall (DI) genom att använda entiteten **Resultat för betalningsprognos (förhandsgranskning)**. Efter en uppgradering till 10.0.17 och senare ska du använda **Resultat av kundbetalningsinsikter (CDS till Fin och Ops 10.0.17 och senare)** DI-mall för att slutföra mappningen. Du kanske inte kan mappa DI-mallens målkolumn förrän datahanteringslistan för entitet uppdateras och **resultat för betalningsprognos** visas i den. Om du vill uppdatera enhetslistan och visa resultatet av betalningsprognosen, utför du stegen i både Microsoft Dynamics 365 Finance och Dataverse (tidigare kallat Common Data Service \[CDS\] administratörsportal).

### <a name="in-finance"></a>I Finance

Följ dessa steg i Finance efter uppgraderingen.

1. Gå till **Systemadministration \> Arbetsytor \> Datahantering**.
2. I arbetsytan **Datahanteringen** välj panelen **Ramverksparametrar**.
3. På sidan **Ramverksparametrar för dataimport/export** välj **Entitetsinställningar** och välj **Uppdatera entitetslistan**.
4. Stäng sidan **Ramverksparametrar för dataimport/export**.
5. I arbetsytan **Datahanteringen** välj panelen **Dataentiteter**.
6. Sök efter "Resultat av betalningsprognoser." Kontrollera att entiteten **Resultat av betalningsprognoser** inte är förhandsgranskningsversionen. Namnet på förhandsgranskningsversionen slutar i "(förhandsgranskning)." Om det bara visas en förhandsgranskning av enheten kontaktar du Microsofts support.

### <a name="in-dataverse"></a>I Dataverse

Följ de här stegen i [Power Platform administratörscentret](https://admin.powerplatform.microsoft.com/environments) om du vill uppdatera dina dataintegrationsprojekt.

1. Om du använder en förhandsgranskningsversion av Finance Insights tar du bort det DI-projekt som är kopplat till mallen **Resultat av kundbetalningsinsikter (CDS till Fin och Ops)**. 
2. Följ anvisningarna i [Skapa ett projekt för dataintegrerare](create-data-integrate-project.md). Använd mallen **Resultat av kundbetalningsinsikter (CDS till Fin och Ops 10.0.17 och senare)**.

## <a name="symptom-when-i-try-to-open-ai-builder-by-using-the-links-on-the-customer-payment-predictions-setup-page-why-do-i-receive-the-following-error-message-sorry-theres-been-a-disconnect"></a>Symptom: När jag försöker öppna AI Builder med hjälp av länkarna på inställningssidan för kundbetalningsprognoser, varför visas följande felmeddelande: "Tyvärr har det skett en frånkoppling"?

### <a name="resolution"></a>Lösning

Dynamics 365 Finance-användare måste ha ett Microsoft Power Apps-användarkonto för miljön, och det användarkontot måste ha rollen Systemanpassare. Microsoft Power Apps-systemadministratören kan skapa användarkontot och tilldela rollen. Du kan sedan gå till <https://make.preview.powerapps.com/>, logga in med hjälp av det användarkontot och försöka med länkarna igen.

## <a name="symptom-why-doesnt-the-cash-forecast-tab-in-the-cash-flow-forecast-workspace-show-any-data"></a>Symptom: Varför visar inte fliken Kassaprognos i arbetsytan Kassaflödesprognos några data?

### <a name="resolution"></a>Lösning

Kassaflödesprognosfunktionen i kassa- och bankhantering och funktionen Kassaflödesprognoser i Finansinsikter måste konfigureras och aktiveras för att korrekt visa data i arbetsytan **Kassaflödesprognos**.

Först ställer du in och aktiverar kontona för kassaflödesprognos och likviditet. Mer information finns i [Kassaflödesprognoser](../cash-bank-management/cash-flow-forecasting.md). Om inställningen har slutförts men du inte ser de förväntade resultaten, kan du läsa mer i [Felsöka inställningar för kassaflödesprognoser](../cash-bank-management/cash-flow-forecasting-tsg.md).

Bekräfta sedan att funktionen Kassaflödesprognoser i Finance insights (**Hantering av kassa och bank \> Inställningar \> Finance Insights \> Kassaflödesprognoser**) har aktiverats och att utbildningen av AI-modellen har slutförts. Om utbildningen inte har slutförts väljer du **Prognos nu** för att starta modellutbildningsprocessen.
