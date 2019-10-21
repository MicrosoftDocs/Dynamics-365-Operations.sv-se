---
title: Synkronisera projektets verkliga värden från Project Service Automation direkt till projektets integrationsjournal för bokföring i Finance and Operations
description: Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera projektets faktiska värden direkt från Dynamics 365 Project Service Automation till Finance and Operations.
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
ms.openlocfilehash: 0aeaa1ee4c35ca42a5382b3c7ff3519cba52996c
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/30/2019
ms.locfileid: "2250540"
---
# <a name="synchronize-project-actuals-directly-from-project-service-automation-to-the-project-integration-journal-for-posting-in-finance-and-operations"></a>Synkronisera projektets verkliga värden från Project Service Automation direkt till projektets integrationsjournal för bokföring i Finance and Operations

[!include[banner](../includes/banner.md)]

Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera projektets faktiska värden direkt från Dynamics 365 Project Service Automation till Dynamics 365 Finance.

Mallen synkroniserar transaktionerna från Project Service Automation till ett mellanlagringsregister i Finance. När synkroniseringen är klar **måste** du importera datan från mellanlagringsregistret till integrationsjournalen.

> [!NOTE]
> - Projektets verkliga integration finns med start i version 8.0.1.
> - Om du använder Enterprise edition 7.3.0, när du har installerat KB 4132657 och KB 4132660, kommer du att kunna använda mallarna för att integrera projektuppgifter, utgiftstransaktionskategorier, timuppskattningar, utgiftsuppskattningar och verkliga värden, och så här konfigurerar du funktionslåsning. Om du måste återställa redovisningsfördelningarna rekommenderar vi att du också installerar KB 4131710.
> - Om du använder version 7.3.0 och överför avgiftstransaktioner från Project Service Automation måste du installera KB 4345320 för att inkludera dessa avgifter på projektfakturan.
> - Om du anger momsbelopp för tids- eller utgiftstransaktioner i Project Service Automation, måste du installera Project Service Automation uppdatering 7. I annat fall kommer de faktiska momsvärdena inte att kopplas till faktiska associerade tids- eller utgiftsvärden, och kommer heller inte att associeras med Finance. Kontakta support för mer information.

## <a name="data-flow-for-project-service-automation-to-finance"></a>Dataflöde för Project Service Automation till Finance

Automatisering av integrationslösningen Project Service Automation till Finance-integrationslösningen använder funktionen dataintegration för att synkronisera data mellan instanser av Project Service Automation och Finance. Integrationsmallen som är tillgänglig med dataintegrationsfunktionen möjliggör flödet av data om projektets verkliga värden från Project Service Automation till Finance.

Följande bild visar hur data synkroniseras mellan Project Service Automation och Finance.

[![Dataflöde för integration av Project Service Automation med Finance and Operations](./media/ProjectActualsFlow.jpg)](./media/ProjectActualsFlow.jpg)

## <a name="project-actuals-from-project-service-automation"></a>Faktiska projektuppgifter från Project Service Automation

### <a name="template-and-tasks"></a>Mall och uppgifter

För att få åtkomst till tillgängliga mallar väljer du i administratörscentret för Microsoft PowerApps **Projekt** och sedan i det övre högra hörnet **Ny projekt** för att välja offentliga mallar.

Följande mall och underliggande uppgifter används för att synkronisera projektets faktiska värden från Project Service Automation till Finance:

- **Namnet på mallen i dataintegrering:** projektets verkliga värden (PSA till Fin och Ops)
- **Namn på aktiviteter i projektet:**

    - Utfall
    - Transaktionsanslutningar

### <a name="entity-set"></a>Ange entiteten

| Project Service Automation | Finansiellt                                   |
|----------------------------|----------------------------------------------------------|
| Utfall                    | Integrationsenhet för projektets faktiska värden                   |
| Transaktionsanslutningar    | Integrationsenhet för projektets transaktionsrelationer |

### <a name="entity-flow"></a>Flöde för entitet

Projektets verkliga värden hanteras i Project Service Automation, och de synkroniseras till projektets integrationsjournal i Finance. Redovisningen används utifrån ekonomiska standarddimensioner och bokföringsinställningarna.

### <a name="prerequisites"></a>Krav

Innan synkroniseringen av verkliga värden kan utföras måste Project Service Automation konfigurera integrationsparametrar och synkronisera projekt, projektuppgifter och kategorier för projektutgiftstransaktioner.

### <a name="power-query"></a>Power Query

Du måste använda Microsoft Power Query för Excel i uppskattningsmallen för projekt för att kunna slutföra följande uppgifter:

- Omvandla transaktionstypen i Project Service Automation till rätt transaktionstyp i Finance. Denna omvandling har redan definierats i mallen för faktiska projektvärden ("PSA till Fin och Ops").
- Omvandla faktureringstypen i Project Service Automation till rätt faktureringstyp i Finance. Denna omvandling har redan definierats i mallen för faktiska projektvärden ("PSA till Fin och Ops"). Faktureringstypen mappas sedan till radegenskapen, baserat på konfigurationen på sidan **Integreringsparametrar för Project Service Automation**.
- Filtrera till specifika resursorganisationsenheter som måste synkroniseras med den här mallen.
- Om koncernintern tid eller koncerninterna faktiska kostnader kommer att synkroniseras till Finance måste du omvandla kontraktorganisationsenhet till rätt juridisk person i Finance. I mallen för projektets verkliga värden ("PSA till Fin och Ops") definieras en villkorlig kolumn utifrån demodata. Du måste uppdatera den sista infogade villkorskolumnen till rätt juridiska personer. I annat fall kan antingen ett integrationsfel uppstå, eller också kan felaktiga faktiska transaktioner importeras till Finance.
- Om koncernintern tid eller koncerninterna verkliga kostnader inte synkroniseras till Finance måste du ta bort den sista infogade villkorskolumnen från mallen. I annat fall kan antingen ett integrationsfel uppstå, eller också kan felaktiga faktiska transaktioner importeras till Finance.

#### <a name="contract-organizational-unit"></a>Kontraktorganisationsenhet
För att uppdatera den infogade villkorskolumnen i mallen, klicka på pilen **Mappa** för att öppna mappningen. Markera länken **Avancerade frågor och filter** för att öppna Power Query.

- Om du använder standardmallen för faktiska projektvärden ("PSA till Fin och Ops"), välj då senaste **Infogat villkor** i avsnittet **Tillämpade steg** i Power Query. I posten **Funktion** ersätter du **USSI** med namnet på den juridiska person som ska användas med integrationen. Lägg till ytterligare villkor i posten **Funktion** efter behov och uppdatera villkoret **annars** från **USMF** till korrekt juridisk person.
- Om du skapar en ny mall måste du lägga till kolumnen för att ge stöd till koncernintern tid och utgifter. Markera **Lägg till villkorskolumn** och ange ett namn på kolumnen, exempelvis **Juridisk person**. Ange ett villkor för kolumnen där, om **msdyn\_contractorganizationalunitid.msdyn\_name** är \<organisationsenhet\>, så \<ange juridisk person\>; annars noll.

### <a name="template-mapping-in-data-integration"></a>Mallmappning i dataintegrering

I följande illustration visas ett exempel på uppgiftsmallmappning i dataintegrering. Mappningen visar vilken fältinformation som kommer att synkroniseras från Project Service Automation till Finance.

[![Mallmappning](./media/ActualsMapping.jpg)](./media/ActualsMapping.jpg)

[![Mallmappning](./media/TransactionConnections.jpg)](./media/TransactionConnections.jpg)

## <a name="import-from-staging-table-after-integration-from-project-service-automation"></a>Importera från mellanlagringstabell efter integration från Project Service Automation

Importen från mellanlagringsregistrets periodiska process måste köras efter synkronisering av verkliga värden från Project Service Automation till Finance. Denna process importerar projekttransaktionerna från mellanlagringsregistret till Project Service Automation integrationsjournalen där redovisning används och importerade transaktioner kan bokföras. Vi rekommenderar att du kör denna process i batchläge. Den kan eventuellt ställas in att köras som ett återkommande batchjobb.

## <a name="update-actuals-from-finance"></a>Uppdatera verkliga värden från Finance

### <a name="template-and-tasks"></a>Mall och uppgifter

Följande mall och underliggande uppgift används för att synkronisera kupongnummer och försäljningsmoms för upplagda projekttransaktioner från Finance till Project Service Automation:

- **Namnet på mallen i dataintegrering:** projektets verkliga värden (Fin Ops till PSA)
- **Namn på aktiviteter i projektet:**

    - Utfall 
    - Transaktionsanslutningar

### <a name="entity-set"></a>Ange entiteten

| Finansiellt                                                  | Project Service Automation |
|----------------------------------------------------------|----------------------------|
| Integrationsenhet för projektets faktiska värden                   | Utfall                    |
| Integrationsenhet för projektets transaktionsrelationer | Transaktionsanslutningar    |

### <a name="entity-flow"></a>Flöde för entitet

Projektets verkliga värden hanteras i Project Service Automation, och de synkroniseras till projektets integrationsjournal i Finance. När de verkliga värdena bokförs i Finance uppdateras de i Project Service Automation med verifikationsnumret från Finance. Om moms har lagts till i Finance kommer nya verkliga skatt att skapas i Project Service Automation.

### <a name="power-query"></a>Power Query

Du måste använda Power Query för Excel i uppskattningsmallen för projekt för att kunna slutföra följande uppgifter:

- Omvandla transaktionstypen i Finance till rätt transaktionstyp i Project Service Automation. Denna omvandling har redan definierats i mallen för faktiska projektvärden ("Fin Ops till PSA").
- Omvandla faktureringstypen i Finance till rätt faktureringstyp i Project Service Automation. Denna omvandling har redan definierats i mallen för faktiska projektvärden ("Fin Ops till PSA").

### <a name="template-mapping-in-data-integration"></a>Mallmappning i dataintegrering

I följande illustrationer visas ett exempel på uppgiftsmallmappning i dataintegrering. Mappningen visar vilken fältinformation som kommer att synkroniseras från Finance till Project Service Automation.

[![Mallmappning](./media/ActualsUpdateMapping.jpg)](./media/ActualsUpdateMapping.jpg)

[![Mallmappning](./media/TransactionConnectionsUpdate.jpg)](./media/TransactionConnectionsUpdate.jpg)
