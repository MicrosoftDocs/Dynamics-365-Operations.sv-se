---
title: Felsöka problem med Finance Insights
description: Det här ämnet visar en lista med problem som kan inträffa när du använder Finance Insights. Här förklaras också hur du löser dessa problem.
author: panolte
ms.date: 01/29/2022
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
ms.openlocfilehash: f77cddfdab22bef8af7f62d49723e330c4f13261
ms.sourcegitcommit: 3a7f1fe72ac08e62dda1045e0fb97f7174b69a25
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/31/2022
ms.locfileid: "8064876"
---
# <a name="troubleshoot-finance-insights-setup-issues"></a>Felsöka problem med Finance Insights

[!include [banner](../includes/banner.md)]

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

## <a name="symptom-why-isnt-the-install-a-new-add-in-button-visible-in-microsoft-dynamics-lifecycle-services"></a>Symptom: Varför visas inte knappen Installera ett nytt tillägg i Microsoft Dynamics Lifecycle Services?

### <a name="resolution"></a>Lösning

Kontrollera att rollen **Miljöchefen** eller **Projektägare** tilldelas den inloggade användaren i fältet **Projektsäkerhetsroll** i Microsoft Dynamics Lifecycle Services (LCS). Installationen av de nya tilläggen kräver en av dessa projektsäkerhetsroller.

Om du har tilldelats rätt projektsäkerhetsroll kanske du måste uppdatera webbläsaren för att kunna visa knappen **Installera nytt tillägg**.

## <a name="symptom-the-finance-insights-add-in-doesnt-seem-to-be-installing-why-is-that"></a>Symptom: tillägget Finance Insights verkar inte vara installerat. Varför är det?

### <a name="resolution"></a>Lösning

Följande steg bör ha genomförts.

- Verifiera att du har åtkomst **systemadministratörer** och **Systemanpassare** i administrationscentret för Power Portal.
- Verifiera att en Dynamics 365 Finance eller motsvarande licens tillämpas på den användare som installerar tillägget.
- Kontrollera att följande Azure AD app är registrerat i Azure AD: 

  | Ansökning                  | App-ID           |
  | ---------------------------- | ---------------- |
  | Microsoft Dynamics ERP Microservices CDS | 703e2651-d3fc-48f5-942c-74274233dba8 | 
  
## <a name="symptom-error-we-didnt-find-any-data-for-the-selected-filter-range-please-select-a-different-filter-range-and-try-again"></a>Symptom: Fel, "Vi hittade inga data för det valda filterintervallet. Välj ett annat filterintervall och försök igen." 

### <a name="resolution"></a>Lösning

Kontrollera inställningarna för dataintegrerare för att validera att det fungerar som förväntat och ställa in data från AI Builder tillbaka till Ekonomi.  
Mer information finns i [Skapa ett dataintegrationsprojekt](../finance-insights/create-data-integrate-project.md).

## <a name="symptom-customer-payment-prediction-training-failed-and-the-ai-builder-error-states-prediction-should-have-only-2-distinct-outcome-values-to-train-the-model-map-to-two-outcomes-and-retrain-training-report-issue-isnotminrequireddistinctnonnullvalues"></a>Symptom: Utbildning av kundbetalningsförutsägelser misslyckades och AI Builder felvärdena, "Förutsägelse ska bara ha 2 olika resultatvärden för att utbilda modellen. Mappa till två resultat och redisponera", "Utbildningsrapportproblem: IsNotMinRequiredDistinctNonNullValues".

### <a name="resolution"></a>Lösning

Det här felet indikerar att det inte finns tillräckligt många historiska transaktioner under det senaste året som representerar varje kategori som beskrivs i kategorierna **I tid**, **Sent** och **Mycket sent**. Du löser det här felet genom att justera transaktionsperioden **Mycket sent**. Om justering av transaktionsperioden **Mycket sent** korrigerar inte felet, **Kundbetalningsförutsägelser** är inte den bästa lösningen att använda eftersom den behöver data i varje kategori för utbildningsändamål.

Mer information om hur du justerar kategorierna **I tid**, **Sent** och **Mycket sent**, se [Aktivera förutsägelser för kundbetalning](../finance-insights/enable-cust-paymnt-prediction.md).

## <a name="symptom-model-training-failed"></a>Symptom: Modellutbildningen misslyckades

### <a name="resolution"></a>Lösning

Modellutbildning för **kassaflödesprognos** kräver data som sträcker sig över mer än ett år och innehåller mer än 100 transaktioner. Dessa transaktioner måste påverka likviditetskonton som är inkluderade i inställningen av kassaflödesprognosen.

**Kundbetalningsförutsägelser** kräver minst 100 kundfaktura- och betalningstransaktioner de senaste sex till nio månaderna för att det ska gå att skapa förutsägelser.  
