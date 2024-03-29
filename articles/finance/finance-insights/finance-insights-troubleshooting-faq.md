---
title: Felsöka problem med Finance Insights
description: Det här ämnet visar en lista med problem som kan inträffa när du använder Finance Insights. Här förklaras också hur du löser dessa problem.
author: panolte
ms.date: 02/11/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kfend
ms.custom:
- "14151"
- intro-internal
ms.assetid: 3d43ba40-780c-459a-a66f-9a01d556e674
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2021-08-20
ms.dyn365.ops.version: AX 10.0.20
ms.openlocfilehash: 331c714663d212471b72f1558e6183452ef7f394
ms.sourcegitcommit: adadbc6e355e2ad68a1f6af26a1be1f89dc8eec6
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/22/2022
ms.locfileid: "9573183"
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
  
    Kontrollera att programmet är registrerat Azure AD i listan **Alla program**. Mer information finns i [Visa företagsprogram](/azure/active-directory/manage-apps/view-applications-portal).
  
    Om programmet inte är registrerat i Azure AD kontaktar du support.

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

Modellutbildning för **kassaflödesprognos** kräver data som sträcker sig över mer än ett år och innehåller mer än 100 transaktioner. Vi rekommenderar att du har minst två års data med mer än 1 000 transaktioner.

Funktionen **Kundbetalningsförutsägelser** kräver mer än 100 transaktioner under de föregående sex till nio månaderna. Transaktionerna kan omfatta fritextfakturor, försäljningsorder och kundbetalningar. Dessa data måste sprids över inställningarna **I tid**, **Sent** och **Mycket sent** som har definierats på sidan **Konfiguration**.    

Funktionen för **budgetförslag** kräver minst tre års budget eller faktiska data. Lösningen använder tre till tio år data i prognoser. Mer än tre år ger bättre resultat. Själva data fungerar bäst när det finns variation i värdena. Om uppgifterna innehåller alla konstanta data, till exempel en leasingkostnad, kan utbildningen misslyckas eftersom bristen på variation inte kräver AI för att projicera beloppen.

## <a name="symptom-error-message-states-that-the-table-with-name-msdyn_paypredpredictionresultentities-does-not-exist-the-remote-server-returned-an-error-404-not-found"></a>Symptom: Felmeddelandet "Register med namn, msdyn_paypredpredictionresultentities" inte finns. Fjärrservern returnerade ett fel: (404) Hittade inte.

### <a name="resolution"></a>Lösning

Miljön har nått högsta registergräns för Data Lake Services. Mer information om gränsen finns i avsnittet **Aktivera ändringar av data i närtid i realtid** i avsnittet, översikten [Exportera översikt över Azure Data Lake](../../fin-ops-core/dev-itpro/data-entities/Azure-Data-Lake-GA-version-overview.md).
