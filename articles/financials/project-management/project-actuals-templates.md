---
title: "Synkronisera projektets faktiska värden från Project Service Automation direkt till projektets integrationsjournal för bokföring i Finance and Operations "
description: "Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera projektets faktiska värden direkt från Microsoft Dynamics 365 for Project Service Automation till Dynamics 365 for Finance and Operations."
author: KimANelson
manager: AnnBe
ms.date: 05/21/2018
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
ms.openlocfilehash: 85ff049852e0b00623f47a12fb66e2c9bb9c4151
ms.contentlocale: sv-se
ms.lasthandoff: 05/29/2018

---
# <a name="synchronize-project-actuals-from-project-service-automation-directly-to-the-project-integration-journal-for-posting-in-finance-and-operations"></a>Synkronisera projektets faktiska värden från Project Service Automation direkt till projektets integrationsjournal för bokföring i Finance and Operations 

Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera projektets faktiska värden direkt från Microsoft Dynamics 365 for Project Service Automation till Dynamics 365 for Finance and Operations.

Mallen synkroniserar transaktionerna från Project Service Automation till ett mellanlagringsregister i Finance and Operations. När synkroniseringen är klar måste du importera från mellanlagringsregistret till integrationsjournalen.

> [!NOTE]
> Integration av projektets verkliga värden finns i Dynamics 365 for Finance and Operations version 8.01.

> [!NOTE]
> Om du anger momsbelopp på tid eller utgifter i Project Service Automation, måste du installera Project Service Automation uppdatering 7. Om uppdateringen inte har installerats kommer skattemässiga värden inte att kopplas till associerad tid eller verklig kostnad och kommer inte att synkroniseras inte med Finance and Operations. Kontakta support för mer information.


## <a name="data-flow-for-project-service-automation-to-finance-and-operations"></a>Dataflöde för Project Service Automation till Finance and Operations

Automatisering av integrationslösningen Project Service Automation till Finance and Operations använder funktionen dataintegration för att synkronisera data mellan instanser av Project Service Automation och Finance and Operations. Integrationsmallen som är tillgänglig med dataintegrationsfunktionen möjliggör flödet av data om projektets faktiska värden från Project Service Automation till Finance and Operations.

Följande bild visar hur data synkroniseras mellan Project Service Automation och Finance and Operations.

[![Dataflöde för integration av Project Service Automation med Finance and Operations](./media/ProjectActualsFlow.jpg)](./media/ProjectActualsFlow.jpg)


## <a name="templates-and-tasks"></a>Mallar och uppgifter

För att få åtkomst till tillgängliga mallar, i Microsoft PowerApps administratörscenter, välj **projekt**, och i det övre högra hörnet väljer du **nytt projekt** för att välja offentliga mallar.

Följande mall och underliggande uppgift används för att synkronisera projektets verkliga värden från Project Service Automation till Finance and Operations:

-  **Namnet på mallen i dataintegrering:** projektets verkliga värden (PSA to Fin and Ops)

-  **Namn på aktiviteter i projektet:** 
    - Utfall 
    - Transaktionsanslutningar

## <a name="entity-set"></a>Ange entiteten

| Project Service Automation      | Finance and Operations                                      |
|---------------------------------|-------------------------------------------------------------|
| Utfall                         | Integrationsenhet för projektets faktiska värden                      |
| Transaktionsanslutningar         | Integrationsenhet för projektets transaktionsrelationer    |

## <a name="entity-flow"></a>Flöde för entitet

Projektets verkliga värden hanteras i Project Service Automation och de synkroniseras till Finance and Operations till projektets integrationsjournal. Redovisningen används utifrån ekonomiska standarddimensioner och bokföringsinställningarna.

## <a name="preconditions"></a>Förvillkor

Innan synkroniseringen av verkliga värden kan utföras måste Project Service Automation konfigurera integrationsparametrar och synkronisera projekt, projektuppgifter och kategorier för projektutgiftstransaktioner.

## <a name="power-query"></a>Power Query

Du måste använda Microsoft Power Query i mallen för projektets faktiska värden:
- Omvandla Project Service Automation **transaktionstyp** till rätt **transaktionstyp** i Finance and Operations. Mallen för projektets verkliga värden (PSA till Fin and Ops) har redan den här omvandlingen definierad.
- Omvandla Project Service Automation **faktureringstyp** till rätt **faktureringstyp** i Finance and Operations. Mallen för projektets verkliga värden (PSA till Fin and Ops) har redan den här omvandlingen definierad. Faktureringstypen mappas sedan till **radegenskap** baserat på konfigurationen i Dynamics 365 for Project Service Automation parameterformuläret för integration.
- Filter till specifika **resursorganisationsenheter** som ska synkroniseras med den här mallen.
- Om **koncernintern tid eller koncernintern verklig kostnad** kommer att synkroniseras till Finance and Operations måste du omvandla **kontraktorganisationsenhet** till rätt **juridisk person** i Finance and Operations. Mallen projektets verkliga värden (PSA till Fin and Ops) har villkorliga kolumn som är definierad utifrån demodata. Du måste uppdatera kolumnens sista infogade villkor till rätt juridiska personer. Om du inte gör detta kan det resultera i integrationsfel eller felaktiga faktiska transaktioner importeras till Finance and Operations.
- Om **koncernintern tid eller koncernintern verklig kostnad** kommer inte att synkroniseras till Finance and operations måste du ta bort den sista infogade kolumnen från mallen. Om du inte gör detta kan det resultera i integrationsfel eller felaktiga faktiska transaktioner importeras till Finance and Operations.

### <a name="contract-organizational-unit"></a>Kontraktorganisationsenhet
För att uppdatera den infogade kolumnen i mallen, klicka på pilen **Mappa** för att öppna mappningen. Välj för att öppna avancerad fråga och filtrering.
- Om du använder standardmallen Microsoft mallen projektets faktiska värden (PSA till Fin and Ops), välj den senaste **Infogat villkor** i avsnittet **Tillämpade steg**. I posten **funktion**, ersätt **USSI** med namnet på den **juridiska person** som ska användas med integrationen. Lägg till ytterligare villkor för posten **funktion** och uppdatera villkoret **annat** från **USMF** till rätt **juridisk person**.
- Om du skapar en ny mall måste du lägga till den här kolumnen för att ge stöd till koncernintern tid och utgifter. Välj **lägga till villkorlig kolumn** och ge kolumnen ett namn, till exempel LegalEntity. Ange villkor för kolumnen där om msdyn_contractorganizationalunitid.msdyn_name <organizational unit>, sedan <enter the Legal entity>; annars null.

## <a name="template-mapping-in-data-integration"></a>Mallmappning i dataintegrering

I följande illustration visas ett exempel på uppgiftsmallmappning i dataintegrering. Mappningen visar vilken fältinformation som kommer att synkroniseras från Project Service Automation till Finance and Operations.

[![Mallmappning](./media/ActualsMapping.jpg)](./media/ActualsMapping.jpg)

[![Mallmappning](./media/TransactionConnections.jpg)](./media/TransactionConnections.jpg)

## <a name="import-from-staging-table"></a>Importera från mellanlagringsregister

Importen från mellanlagringsregistrets periodiska process måste köras efter synkronisering av verkliga värden från Project Service Automation till Finance and Operations. Denna process importerar projekttransaktionerna från mellanlagringsregistret till Project Service Automation integrationsjournalen där redovisning används och importerade transaktioner kan bokföras. Det rekommenderas att köra den här processen i batchläge och kan eventuellt ställas in att köras som ett återkommande batchjobb.

## <a name="update-actuals"></a>Uppdatera verkliga värden

Följande mall och underliggande uppgift används för att synkronisera kupongnummer och försäljningsskatt för upplagda projekttransaktioner från Finance and Operations till Project Service Automation:

-  **Namnet på mallen i dataintegrering:** projektets verkliga värden (Fin Ops till PSA)
-  **Namn på aktiviteter i projektet:** 
     - Utfall 
     - Transaktionsanslutningar

## <a name="entity-set"></a>Ange entiteten

| Finance and Operations                                         | Project Service Automation        |
|----------------------------------------------------------------|-----------------------------------|
| Integrationsenhet för projektets faktiska värden                         | Utfall                           |
| Integrationsenhet för projektets transaktionsrelationer       | Transaktionsanslutningar           |

## <a name="entity-flow"></a>Flöde för entitet

Projektets verkliga värden hanteras i Project Service Automation och de synkroniseras till Finance and Operations till projektets integrationsjournal. När de är bokförda i Finance and Operations uppdateras verkliga värden i Project Service Automation med verifikationsnumret från Finance and Operations. Om moms har lagts till i Finance and Operations kommer nya verkliga värden för skatt att skapas i Project Service Automation.

## <a name="power-query"></a>Power Query

Du måste använda Microsoft Power Query i uppdateringsmallen för projektets faktiska värden:
- Omvandla Finance and Operations **transaktionstyp** till rätt **transaktionstyp** i Project Service Automation. Mallen för projektets verkliga värden (Fin Ops till PSA) har redan den här omvandlingen definierad.
- Omvandla Finance and Operations **faktureringstyp** till rätt **faktureringstyp** i Finance and Operations. Mallen för projektets verkliga värden (Fin Ops till PSA) har redan den här omvandlingen definierad.

## <a name="template-mapping-in-data-integration"></a>Mallmappning i dataintegrering

I följande illustrationer visas ett exempel på uppgiftsmallmappning i dataintegrering. Mappningen visar vilken fältinformation som kommer att synkroniseras från Finance and Operations till Project Service Automation.

[![Mallmappning](./media/ActualsUpdateMapping.jpg)](./media/ActualsUpdateMapping.jpg)

[![Mallmappning](./media/TransactionConnectionsUpdate.jpg)](./media/TransactionConnectionsUpdate.jpg)




