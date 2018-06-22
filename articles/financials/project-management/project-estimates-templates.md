---
title: "Synkronisera projektuppskattningar från Project Service Automation direkt till projektprognoser i Finance and Operations"
description: "Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera projektets timuppskattningar och projektets utgiftsupppskattningar från Microsoft Dynamics 365 for Project Service Automation till Dynamics 365 for Finance and Operations."
author: KimANelson
manager: AnnBe
ms.date: 04/02/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.3.0
ms.translationtype: HT
ms.sourcegitcommit: bd8feff598cf80ca675c7d2b5dda636799b19e29
ms.openlocfilehash: 90501f40da0fdc66ad087b3bd746c908cc25711b
ms.contentlocale: sv-se
ms.lasthandoff: 05/29/2018

---
# <a name="synchronize-project-estimates-from-project-service-automation-directly-to-project-forecasts-in-finance-and-operations"></a>Synkronisera projektuppskattningar från Project Service Automation direkt till projektprognoser i Finance and Operations

Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera projektets timuppskattningar och projektets utgiftsupppskattningar från Microsoft Dynamics 365 for Project Service Automation till Dynamics 365 for Finance and Operations.

> [!NOTE]
> Projektuppgiftsintegration, utgiftstransationskategorier, uppskattningar av timme, uppskattning av utgifter och funktionslåsning är tillgängliga i Dynamics 365 for Finance and Operations version 8.0.


## <a name="data-flow-for-project-service-automation-to-finance-and-operations"></a>Dataflöde för Project Service Automation till Finance and Operations

Automatisering av integrationslösningen Project Service Automation till Finance and Operations använder funktionen dataintegration för att synkronisera data mellan instanser av Project Service Automation och Finance and Operations. Integrationsmallarna som är tillgängliga med dataintegrationsfunktionen möjliggör flödet av data om projektets timuppskattningar och projektets utgiftsupppskattningar från Project Service Automation till Finance and Operations.

Följande bild visar hur data synkroniseras mellan Project Service Automation och Finance and Operations.

[![Dataflöde för integration av Project Service Automation med Finance and Operations](./media/ProjectEstimatesFlow.png)](./media/ProjectEstimatesFlow.png)


## <a name="templates-and-tasks"></a>Mallar och uppgifter

För att få åtkomst till tillgängliga mallar, i Microsoft PowerApps administratörscenter, välj **projekt**, och i det övre högra hörnet väljer du **nytt projekt** för att välja offentliga mallar.

Följande mall och underliggande uppgifter används för att synkronisera projektets timuppskattningar från Project Service Automation till Finance and Operations:

-  **Namnet på mallen i dataintegrering:** projektets timuppskattningar (PSA to Fin and Ops)

-  **Namn på aktiviteter i projektet:** 
    - Transaktionsrelationer 
    - Utgiftsuppskattning

## <a name="entity-set"></a>Ange entiteten

| Project Service Automation      | Finance and Operations                          |
|---------------------------------|-------------------------------------------------|
| Projektuppgifter                   | Integrationsenhet för projektets timuppskattningar   |

## <a name="entity-flow"></a>Flöde för entitet

Projektets timuppskattningar hanteras i Project Service Automation och de synkroniseras till Finance and Operations som timprognoser i projekt.

## <a name="preconditions"></a>Förvillkor

Innan synkroniseringen av projektets uppskattade timmar kan utföras måste du synkronisera projekt, projektuppgifter och transaktionskategorier för projektutgifter.

## <a name="power-query"></a>Power Query

Du måste använda Microsoft Power Query i mallen för projektets timuppskattningar:
- Ange det **Prognosmodell-ID** som ska användas när integrationen skapar nya timprognoser.
- Filtrera bort alla resursspecifika poster i uppgiften som misslyckas med integrationen i timuppskattningar
- Filtrera bort alla tomma transaktionskategorirader. Om du inte gör detta kan det resultera i fel timprognoser.

### <a name="forecast-model-id"></a>Prognosmodell-ID
För att uppdatera standardprognosmodell-ID i mallen, klicka på pilen **Mapp** för att öppna mappningen. Välj för att öppna avancerad fråga och filtrering.
- Om du använder standardmallen Microsoft mallen timuppskattningar (PSA till Fin and Ops), välj **Infogat villkor** i avsnittet **Tillämpade steg**. I posten **funktion**, ersätt **O_forecast** med namnet på den **Prognosmodell-ID** som ska användas med integrationen. Standardmallen har en prognosmodell från demonstrationsdata.
- Om du skapar en ny mall måste du lägga till den här kolumnen. Välj **lägga till villkorlig kolumn** och ge kolumnen ett namn, till exempel ModelID. Ange villkor för kolumnen där om projectuppgiften inte null <enter the forecast model ID>; annars null.

### <a name="filter-out-resource-specific-records"></a>Filtrera ut resursspecifika poster
Mallen för projektets timuppskattningar (PSA till Fin and Ops) har ett standardfilter som tar bort alla resursspecifika poster. Om du skapar en egen mall måste du lägga till filtret. I formuläret för avancerad fråga och filtrering, välj filter på kolumnen **msdyn_islinetask** för att endast inkludera posterna **falsk**.

### <a name="filter-out-empty-transaction-category-rows"></a>Filtrera bort alla tomma transaktionskategorirader.
Du måste lägga till ett filter för att ta bort alla rader med tomma transaktionskategorier. Det behövs oavsett om du använder standardmallen eller om du skapar en egen mall. Detta filter tar bort alla sammanfattningsrader från Project Service Automation som kan medföra att timprognoser i Finance and Operations är felaktiga. I formuläret avancerad sökning och filtrering väljer du att filtrera bort nullposterna i kolumnen **msdyn_transactioncategory_value**.

## <a name="template-mapping-in-data-integration"></a>Mallmappning i dataintegrering

I följande illustration visas ett exempel på uppgiftsmallmappning i dataintegrering. Mappningen visar vilken fältinformation som kommer att synkroniseras från Project Service Automation till Finance and Operations.

[![Mallmappning](./media/ProjectHourEstimatesMapping.jpg)](./media/ProjectHourEstimatesMapping.jpg)

Följande mall och underliggande uppgift används för att synkronisera projektets utgiftsuppskattningar från Project Service Automation till Finance and Operations:

-  **Namnet på mallen i dataintegrering:** projektets utgiftsupppskattningar (PSA to Fin and Ops)
-  **Namn på aktiviteter i projektet:** 
     - Transaktionsrelationer 
     - Utgiftsuppskattning

## <a name="entity-set"></a>Ange entiteten

| Project Service Automation      | Finance and Operations                                     |
|---------------------------------|------------------------------------------------------------|
| Transaktionsanslutningar         | Integrationsenhet för projektets transaktionsrelationer   |
| Uppskattningsrader                  | Integrationsenhet för projektets utgiftsupppskattningar           |

## <a name="entity-flow"></a>Flöde för entitet

Projektets utgiftsupppskattningar hanteras i Project Service Automation och de synkroniseras till Finance and Operations som utgiftsprognoser i projekt.

## <a name="prerequisites"></a>Krav

Innan synkroniseringen av projektets utgiftsupppskattningar kan utföras måste du synkronisera projekt, projektuppgifter och transaktionskategorier för projektutgifter.

## <a name="power-query"></a>Power Query

Du måste använda Microsoft Power Query i mallen för projektets utgiftsupppskattningar:
- Filtrera med endast uppskattade utgiftsradsposter
- Ange det **Prognosmodell-ID** som ska användas när integrationen skapar nya timprognoser.
- Omvandla faktureringstyper.
- Omvandla transaktionstyper.

### <a name="filter-to-include-only-expense-estimate-lines"></a>Filtrera med endast uppskattade utgiftsposter
Mallen för projektets utgiftsupppskattningar (PSA till Fin and Ops) har ett standardfilter som endast inkluderar endast utgiftsrader i integrationen. Om du skapar en egen mall måste du lägga till filtret. Markera uppgifter för transaktionsrelationer och klicka på pilen **Mapp**. Välj **Avancerad fråga och filtrering** Filtrera kolumnen **msdyn_transactiontype1** så att den endast innehåller **msdyn_estimateline**.

### <a name="forecast-model-id"></a>Prognosmodell-ID
För att uppdatera standardprognosmodell-ID i mallen, för uppgiften utgiftsuppskattningar, klicka på pilen **Mapp** för att öppna mappningen. Välj för att öppna avancerad fråga och filtrering.
- Om du använder standardmallen Microsoft mallen utgiftsuppskattningar (PSA till Fin and Ops), välj först **Infogat villkor** i avsnittet **Tillämpade steg**. I posten **funktion**, ersätt **O_forecast** med namnet på den **Prognosmodell-ID** som ska användas med integrationen. Standardmallen har en prognosmodell från demonstrationsdata.
- Om du skapar en ny mall måste du lägga till den här kolumnen. Välj **lägga till villkorlig kolumn** och ge kolumnen ett namn, till exempel ModelID. Ange villkor för kolumnen däruppskattningsrad-ID inte är null och < Ange prognosmodell-ID >; annars null.

### <a name="transform-the-billing-types"></a>Omvandla faktureringstyper.
Mallen för projektets utgiftsupppskattningar (PSA till Fin and Ops) har en villkorlig kolumn tillagd för att omvandla faktureringstyperna som tas emot från Project Service Automation under integreringen.
- Om du skapar en egen mall måste du lägga till denna villkorliga kolumn. Välj i formuläret avancerad fråga och filtrering, lägg till **lägga till villkorliga kolumnen**. Namnge den nya kolumnen, till exempel BillingType. Villkoret att ange är följande:

    Om **msdyn_billingtype** = 192350000, sedan **NonChargeable** annars om **msdyn_billingtype** = 192350001, sedan **Chargeable** annars om **msdyn_billingtype** = 192350002, sedan **Complimentary** annars **NotAvailable**

### <a name="transform-the-transaction-types"></a>Omvandla transaktionstyper.
Mallen för projektets utgiftsupppskattningar (PSA till Fin and Ops) har en villkorlig kolumn tillagd för att omvandla transaktionstyperna som tas emot från Project Service Automation under integreringen.
- Om du skapar en egen mall måste du lägga till denna villkorliga kolumn. Välj i formuläret avancerad fråga och filtrering, lägg till **lägga till villkorliga kolumnen**. Namnge den nya kolumnen, till exempel TransactionType. Villkoret som ska anges är följande: om **msdyn_transactiontypecode** = 192350000, sedan **kostnad** annars om **msdyn_transactiontypecode** = 192350005, sedan **försäljning** annars **null**

## <a name="template-mapping-in-data-integration"></a>Mallmappning i dataintegrering

I följande illustrationer visas ett exempel på uppgiftsmallmappning i dataintegrering. Mappningen visar vilken fältinformation som kommer att synkroniseras från Project Service Automation till Finance and Operations.

[![Mallmappning](./media/ExpenseEstimateTransactionRelationshipsMapping.jpg)](./media/ExpenseEstimateTransactionRelationshipsMapping.jpg)

[![Mallmappning](./media/ExpenseEstimatesMapping.jpg)](./media/ExpenseEstimatesMapping.jpg)




