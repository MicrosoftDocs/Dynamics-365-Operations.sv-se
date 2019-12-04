---
title: Synkronisera projektuppskattningar från Project Service Automation direkt till Finance and Operations
description: Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera projektets timuppskattningar och projektets utgiftsuppskattningar direkt från Microsoft Dynamics 365 Project Service Automation till Dynamics 365 Finance.
author: KimANelson
manager: AnnBe
ms.date: 07/20/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2016-11-28
ms.dyn365.ops.version: AX 7.3.0
ms.openlocfilehash: ebf0fce60ad006e798aa4f404fbffcf10a0b31f9
ms.sourcegitcommit: fbc106af09bdadb860677f590464fb93223cbf65
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/06/2019
ms.locfileid: "2770299"
---
# <a name="synchronize-project-estimates-directly-from-project-service-automation-to-finance-and-operations"></a>Synkronisera projektuppskattningar från Project Service Automation direkt till Finance and Operations

[!include[banner](../includes/banner.md)]

Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera projektets timuppskattningar och projektets utgiftsuppskattningar direkt från Dynamics 365 Project Service Automation till Dynamics 365 Finance.

> [!NOTE]
> - Projektuppgiftsintegration, utgiftstransationskategorier, uppskattningar av timme, uppskattning av utgifter och funktionslåsning är tillgängliga i version 8.0.
> - Integrering av faktiska uppgifter finns i version 8.0.1 eller senare.

## <a name="data-flow-for-project-service-automation-to-finance"></a>Dataflöde för Project Service Automation till Finance

Automatisering av integrationslösningen Project Service Automation till Finance-integrationslösningen använder funktionen dataintegration för att synkronisera data mellan instanser av Project Service Automation och Finance. Integrationsmallarna som är tillgängliga med dataintegrationsfunktionen möjliggör flödet av data om projektets timuppskattningar och projektets utgiftsuppskattningar från Project Service Automation till Finance.

Följande bild visar hur data synkroniseras mellan Project Service Automation och Finance.

[![Dataflöde för integration av Project Service Automation med Finance](./media/ProjectEstimatesFlow.png)](./media/ProjectEstimatesFlow.png)

## <a name="project-hour-estimates"></a>Timuppskattningar för projekt

### <a name="template-and-tasks"></a>Mall och uppgifter

För att få åtkomst till tillgängliga mallar väljer du i administratörscentret för Microsoft Power Apps **Projekt** och sedan i det övre högra hörnet **Ny projekt** för att välja offentliga mallar.

Följande mall och underliggande uppgifter används för att synkronisera projektets timuppskattningar från Project Service Automation till Finance:

- **Namnet på mallen i dataintegrering:** projektets timuppskattningar (PSA till Fin och Ops)
- **Namn på aktiviteter i projektet:**

    - Transaktionsrelationer
    - Utgiftsuppskattning

### <a name="entity-set"></a>Ange entiteten

| Project Service Automation | Finansiellt                                       |
|----------------------------|-----------------------------------------------|
| Projektuppgifter              | Integrationsenhet för projektets timuppskattningar |

### <a name="entity-flow"></a>Flöde för entitet

Projektets timuppskattningar hanteras i Project Service Automation och de synkroniseras till Finance som timprognoser i projekt.

### <a name="prerequisites"></a>Förutsättningar

Innan synkroniseringen av projektets uppskattade timmar kan utföras måste du synkronisera projekt, projektuppgifter och transaktionskategorier för projektutgifter.

### <a name="power-query"></a>Power Query

Du måste använda Microsoft Power Query för Excel i uppskattningsmallen för projekttimmar för att kunna slutföra följande uppgifter:

- Ange det förvalda prognosmodell-ID som ska användas när integrationen skapar nya timprognoser.
- Filtrera bort alla resursspecifika poster i uppgiften som kommer att misslyckas med integrationen i timuppskattningar.
- Filtrera bort alla tomma transaktionskategorirader. Om denna uppgift inte utförs kan detta resultera i fel timprognoserna.

#### <a name="set-the-default-forecast-model-id"></a>Anger standard-ID för prognosmodell

För att uppdatera standardprognosmodell-ID i mallen, klicka på pilen **Mapp** för att öppna mappningen. Välj sedan länken **Avancerade frågor och filter**.

- Om du använder mallen för förvalda uppskattningar för projekttimmar ("PSA till Fin och Ops"), markera då **Infört tillstånd** i listan för **Tillämpade steg**. I posten **Funktion** byter du ut **O\_forecast** mot ID för den prognosmodell som ska användas för integreringen. Standardmallen har en prognosmodell från demonstrationsdata.
- Om du skapar en ny mall måste du lägga till den här kolumnen. I Power Query markerar du **Lägg till villkorskolumn** och anger ett namn för den nya kolumnen, till exempel **ModelID**. Ange villkoret för den nya kolumnen, där – om projektuppgiften inte är noll – \<ange prognosens modell-ID\>; annars noll.

#### <a name="filter-out-resource-specific-records"></a>Filtrera ut resursspecifika poster

Mallen för projektets timuppskattningar ("PSA till Fin och Ops") har ett standardfilter som tar bort alla resursspecifika poster. Om du skapar en egen mall måste du lägga till filtret. Markera länken **Avancerade frågor och filtrering** att filtrera kolumnen **msdyn\_islinetask** så att endast poster markerade **False** omfattas.

#### <a name="filter-out-empty-transaction-category-rows"></a>Filtrera bort alla tomma transaktionskategorirader.

Du måste lägga till ett filter för att ta bort alla rader som har tomma transaktionskategorier. Denna uppgift krävs oavsett om du använder standardmallen eller om du skapar en egen mall. Detta filter tar bort alla sammanfattningsrader från Project Service Automation som skulle kunna medföra att timprognoser i Finance blir felaktiga. Marker länken **Avancerade frågor och filter** för att filtrera ut nollposter i kolumnen **msdyn\_transactioncategory\_value**.

### <a name="template-mapping-in-data-integration"></a>Mallmappning i dataintegrering

I följande illustration visas ett exempel på uppgiftsmallmappning i dataintegrering. Mappningen visar vilken fältinformation som kommer att synkroniseras från Project Service Automation till Finance.

[![Mallmappning](./media/ProjectHourEstimatesMapping.jpg)](./media/ProjectHourEstimatesMapping.jpg)

## <a name="project-expense-estimates"></a>Uppskattningar av projektutgifter

### <a name="template-and-tasks"></a>Mall och uppgifter

Följande mall och underliggande uppgifter används för att synkronisera projektets utgiftsupppskattningar från Project Service Automation till Finance:

- **Namnet på mallen i dataintegrering:** projektets utgiftsuppskattningar (PSA till Fin och Ops)
- **Namn på aktiviteter i projektet:**

    - Transaktionsrelationer 
    - Utgiftsuppskattning

### <a name="entity-set"></a>Ange entiteten

| Project Service Automation | Finansiellt                                                  |
|----------------------------|----------------------------------------------------------|
| Transaktionsanslutningar    | Integrationsenhet för projektets transaktionsrelationer |
| Uppskattningsrader             | Integrationsenhet för projektets utgiftsuppskattningar         |

### <a name="entity-flow"></a>Flöde för entitet

Projektets utgiftsuppskattningar hanteras i Project Service Automation och de synkroniseras till Finance som utgiftsprognoser i projekt.

### <a name="prerequisites"></a>Förutsättningar

Innan synkroniseringen av projektets utgiftsuppskattningar kan utföras måste du synkronisera projekt, projektuppgifter och transaktionskategorier för projektutgifter.

### <a name="power-query"></a>Power Query

Du måste använda Power Query i mallen i projektets utgiftsuppskattningar för att slutföra följande uppgifter:

- Filtrera med endast uppskattade utgiftsradsposter.
- Ange det förvalda prognosmodell-ID som ska användas när integrationen skapar nya timprognoser.
- Omvandla faktureringstyper.
- Omvandla transaktionstyper.

#### <a name="filter-to-include-only-expense-estimate-lines"></a>Filtrera med endast uppskattade utgiftsposter

Mallen för projektets utgiftsupppskattningar ("PSA till Fin och Ops") har ett standardfilter som endast inkluderar utgiftsrader i integrationen. Om du skapar en egen mall måste du lägga till filtret. Markera uppgiften **Transaktionsrelationer** och klicka sedan på pilen **Mappa** för att öppna mappningen. Markera länken **Avancerade frågor och filter**. Filtrera kolumnen **msdyn\_transactiontype1** så att den endast omfattar **msdyn\_estimateline**.

#### <a name="set-the-default-forecast-model-id"></a>Anger standard-ID för prognosmodell

För att uppdatera förvalt ID för prognosmodell i mallen, markera uppgiften **Utgiftsuppskattningar**, och klicka sedan på pilen **Mappa** för att öppna mappningen. Markera länken **Avancerade frågor och filter**.

- Om du använder förvald standardmall för projektutgifter ("PSA till Fin och Ops") markerar du första **Infört tillstånd** från avsnittet **Tillämpade steg** i Power Query. I posten **Funktion** byter du ut **O\_forecast** mot ID för den prognosmodell som ska användas för integreringen. Standardmallen har en prognosmodell från demonstrationsdata.
- Om du skapar en ny mall måste du lägga till den här kolumnen. I Power Query markerar du **Lägg till villkorskolumn** och anger ett namn för den nya kolumnen, till exempel **ModelID**. Ange villkoret för kolumnen där - om ID för uppskattningsraden inte är noll - \<ange ID för prognosmodell\>; annars noll.

#### <a name="transform-the-billing-types"></a>Omvandla faktureringstyper.

Mallen för projektets utgiftsuppskattningar ("PSA till Fin och Ops") omfattar en villkorlig kolumn som används för att omvandla faktureringstyperna som tas emot från Project Service Automation under integreringen. Om du skapar en egen mall måste du lägga till denna villkorliga kolumn. Markera länken **Avancerade frågor och filter** och välj sedan **Lägg till villkorskolumn**. Ange ett namn för den nya kolumnen, till exempel **Faktureringstyp**. Ange sedan följande tillstånd:

Om **msdyn\_billingtype** = 192350000, så **Ej debiteringsbar**  
annars om **msdyn\_billingtype** = 192350001, så **Debiteringsbar**  
annars om **msdyn\_billingtype** = 192350002, så **Kostnadsfri**  
annars **Ej tillgänglig**

#### <a name="transform-the-transaction-types"></a>Omvandla transaktionstyper.

Mallen för projektets utgiftsuppskattningar ("PSA till Fin och Ops") omfattar en villkorlig kolumn som används för att omvandla transaktionstyperna som tas emot från Project Service Automation under integreringen. Om du skapar en egen mall måste du lägga till denna villkorliga kolumn. Markera länken **Avancerade frågor och filter** och välj sedan **Lägg till villkorskolumn**. Ange ett namn för den nya kolumnen, till exempel **Transaktionstyp**. Ange sedan följande tillstånd:

Om **msdyn\_transactiontypecode** = 192350000, så **Kostnad**  
annars om **msdyn\_transactiontypecode** = 192350005, så **Försäljning**  
annars **noll**

### <a name="template-mapping-in-data-integration"></a>Mallmappning i dataintegrering

I följande illustrationer visas ett exempel på uppgiftsmallmappning i dataintegrering. Mappningen visar vilken fältinformation som kommer att synkroniseras från Project Service Automation till Finance.

[![Mallmappning](./media/ExpenseEstimateTransactionRelationshipsMapping.jpg)](./media/ExpenseEstimateTransactionRelationshipsMapping.jpg)

[![Mallmappning](./media/ExpenseEstimatesMapping.jpg)](./media/ExpenseEstimatesMapping.jpg)
