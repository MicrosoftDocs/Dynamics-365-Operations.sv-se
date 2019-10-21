---
title: Synkronisera projektkontrakt och projekt direkt från Project Service Automation till Finance and Operations
description: Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera projektkontrakt och projekt direkt från Microsoft Dynamics 365 Project Service Automation till Dynamics 365 Finance.
author: KimANelson
manager: AnnBe
ms.date: 09/09/2019
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
ms.search.validFrom: 2017-12-13
ms.dyn365.ops.version: AX 7.3.0
ms.openlocfilehash: 76c62f3a503ff2a8c93143390fc91ef81fbf7d0f
ms.sourcegitcommit: 2460d0da812c45fce67a061386db52e0ae46b0f3
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/30/2019
ms.locfileid: "2250471"
---
# <a name="synchronize-project-contracts-and-projects-directly-from-project-service-automation-to-finance-and-operations"></a>Synkronisera projektkontrakt och projekt direkt från Project Service Automation till Finance and Operations

[!include[banner](../includes/banner.md)]

Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera projektkontrakt och projekt direkt från Dynamics 365 Project Service Automation till Dynamics 365 Finance.

> [!NOTE] 
> Om du använder Enterprise edition 7.3.0, måste du installera KB 4074835.

## <a name="data-flow-for-project-service-automation-to-finance"></a>Dataflöde för Project Service Automation till Finance

> [!NOTE]
> Innan du kan använda integrationslösningen Project Service Automation till Finance bör du känna till Dynamics 365 dataintegrationsfunktionen.

Automatisering av integrationslösningen Project Service Automation till Finance-integrationslösningen använder funktionen dataintegration för att synkronisera data mellan instanser av Project Service Automation och Finance. Integrationsmallen som är tillgänglig med dataintegrationsfunktionen tillåter flöde av data om projektkontrakt, projekt, projektkontraktsrader och projektkontraktraders milstolpar från Project Service Automation till Finance.

Följande bild visar hur data synkroniseras mellan Project Service Automation och Finance.

[![Dataflöde för integration av Project Service Automation med Finance](./media/ProjectsAndContractsFlow.JPG)](./media/ProjectsAndContractsFlow.JPG)

## <a name="templates-and-tasks"></a>Mallar och uppgifter

För att få åtkomst till tillgängliga mallar väljer du i administratörscentret för Microsoft PowerApps **Projekt** och sedan i det övre högra hörnet **Ny projekt** för att välja offentliga mallar.

Följande mall och underliggande uppgift används för att synkronisera projektkontrakt och proojekt från Project Service Automation till Finance:

### <a name="integrating-with-dynamics-365-project-service-automation-v2x"></a>Integrera med Dynamics 365 Project Service Automation v2.x
- **Namnet på mallen i dataintegrering:** projektet och kontrakt (PSA till Fin och Ops)
- **Namn på aktiviteter i projektet:**

    - Projektkontrakt PSA till Fin och Ops
    - Projekt PSA till Fin och Ops
    - Projektkontraktrader PSA till Fin och Ops
    - Projektkontraktraders milstolpar PSA till Fin och Ops
  
### <a name="integrating-with-dynamics-365-project-service-automation-v3x"></a>Integrera med Dynamics 365 Project Service Automation v3.x
Det finns en schemaändring i Project Service Automation som påverkar mallen för milstolpe för projektkontraktsrad och användning av version v2 av mallen krävs för att kunna integrera Project Service Automation v3.x med Dynamics 365.

- **Namnet på mallen i dataintegrering:** projektet och kontrakt (PSA 3.x till Fin och Ops) - v2
- **Namn på aktiviteter i projektet:**

    - Projektkontrakt PSA till Fin och Ops
    - Projekt PSA till Fin och Ops
    - Projektkontraktrader PSA till Fin och Ops
    - Projektkontraktraders milstolpar PSA till Fin och Ops

Innan synkroniseringen av projektkontrakt och projekt kan utföras måste du synkronisera konton.

## <a name="entity-set"></a>Ange entiteten

| Project Service Automation       | Finansiellt                                                |
|----------------------------------|--------------------------------------------------------|
| Order                           | Integrationsenhet för projektkontrakt                |
| Projekt                         | Integrationsenhet för projekt                         |
| Orderrader                      | Integrationsenhet för projektkontraktsrad           |
| Milstolpar för projektkontraktsrad | Integrationsenhet för milstolpar för projektkontraktsrad |

## <a name="entity-flow"></a>Flöde för entitet

Projektkontrakt hanteras i Project Service Automation och de synkroniseras till Finance som projektkontrakt. Du kan ange integrationsmallen som del av integrationskällan i Finance för projektkontraktet.

Tids- och materialprojekt och fastprisprojekt hanteras i Project Service Automation, och dessa synkroniseras med Finance som projekt. Du kan ange integrationsmallen som del av integrationskällan i Finance för projektet.

Projektkontraktrader hanteras i Project Service Automation och de synkroniseras till Finance som faktureringsregler för projektkontrakt. Om faktureringsmetoden skiljer sig från förvald projekttyp kommer synkroniseringen att uppdatera projekttypen för kontraktradsprojekt och projektgrupp.

Milstolpar för projektkontraktsrad hanteras i Project Service Automation och de synkroniseras till Finance som milstolpar för faktureringsregler för projektkontrakt.

## <a name="project-service-automation-to-finance-integration-solution"></a>Integegrationslösning för Project Service Automation till Finance

Fältet **projektkontrakt-ID** är tillgängligt på sidan **projektkontrakt**. Detta fält har gjort en fysisk och en unik nyckel för att stödja integreringen.

När ett nytt projektkontrakt skapas om ett **Projektkontrakt-ID**-värde inte finns, skapas det automatiskt med hjälp av en nummerserie. Värdet består av **ORD** följt av en ökande nummerserie och sedan ett suffix på sex tecken. Här är ett exempel: **ORD-01022-Z4M9Q0**.

Fältet **Projektnummer** är tillgängligt på sidan **projekt**. Detta fält har gjort en fysisk och en unik nyckel för att stödja integreringen.

När ett nytt projekt skapas om ett **projektnummer**-värde inte finns, skapas det automatiskt med hjälp av en nummerserie. Värdet består av **PRJ** följt av en ökande nummerserie och sedan ett suffix på sex tecken. Här är ett exempel: **PRJ-01049-CCNID0**.

När integrationslösningen för Project Service Automation till Finance tillämpas, anger ett uppgraderingsskript fältet **projektkontrakt-ID** för befintliga projektkontrakt och **projektnummer** för befintliga projekt i Project Service Automation.

## <a name="prerequisites-and-mapping-setup"></a>Ställa in mappning och förutsättningar

- Innan synkroniseringen av projektkontrakt och projekt kan utföras måste du synkronisera konton.
- I din anslutningsuppsättning, lägg till en integrationsnyckelfältplanering för **msdyn\_organizationalunits** till **msdyn\_namn \[Namn\]**. Du kanske först måste lägga till ett projekt i anslutningsuppsättningen. Mer information finns i [integrera data i Common Data Service för appar](https://docs.microsoft.com/powerapps/administrator/data-integrator).
- I din anslutningsuppsättning, lägg till en integrationsnyckelfältplanering för **msdyn\_projekt** till **msdynce\_projektnummer \[Projektnummer\]**. Du kanske först måste lägga till ett projekt i anslutningsuppsättningen. Mer information finns i [integrera data i Common Data Service för appar](https://docs.microsoft.com/powerapps/administrator/data-integrator).
- **SourceDataID** för projektkontrakt och projekt kan uppdateras till ett annat värde eller tas bort från mappningen. Standardmallvärdet är **Project Service Automation**.
- Mappningen **PaymentTerms** måste uppdateras så att den motsvarar giltiga betalningsvillkor i Finance. Du kan också ta bort mappningen från projektuppgiften. Den standardinställda värdemappningen har standardvärden för demodata. Tabellen nedan visar värdena i Project Service Automation.

    | Värde | beskrivning   |
    |-------|---------------|
    | 1     | Netto 30        |
    | 2     | 2% 10, Netto 30 |
    | 3     | Netto 45        |
    | 4     | Netto 60        |

## <a name="power-query"></a>Power Query

Du måste använda Microsoft Power Query för Excel för att filtrera data om följande villkor uppfylls:

- Det finns försäljningsorder i Dynamics 365 Sales.
- Det finns flera organisationsenheter i Project Service Automation och organisationsenheterna mappas till flera juridiska personer i Finance.

Om du måste använda Power Query enligt riktlinjerna nedan:

- Mallen för projekt och kontrakt ("PSA till Fin och Ops") har ett standardfilter som endast inkluderar försäljningsorder av typen **Arbetsobjekt (msdyn\_ordertype = 192350001)**. Det här filtret hjälper till att garantera att projektkontrakt inte skapas för försäljningsorder i Finance. Om du skapar en egen mall måste du lägga till filtret.
- Du måste skapa ett Power Query-filtret som endast inkluderar kontraktorganisationer som ska synkroniseras mot den juridiska personen av integrationens anslutningsuppsättning. T.ex. ska projektkontrakt som du har med kontraktorganisationsenheten för Contoso US ska synkroniseras mot den juridiska personen USSI, men projektkontraktet som du har med kontraktorganisationsenhet för Contoso Global ska synkroniseras mot den juridiska personen för USMF. Om du inte lägger till det här filtret i din uppgiftsmappning kommer alla projektkontrakt att synkroniseras till den juridiska person som har definierats för anslutningen, oavsett kontraktorganisationsenhet.

## <a name="template-mapping-in-data-integration"></a>Mallmappning i dataintegrering

> [!NOTE] 
> Fälten **CustomerReference**, **AddressCity**, **AddressCountryRegionID**, **AddressDescription**, **AddressLine1**, **AddressLine2**, **AddressState** och **AddressZipCode** ingår inte i standardmappningen för projektkontrakt. Du kan lägga till mappningar om du vill att informationen ska synkroniseras för projektkontrakt.
>
> Fälten **beskrivning**, **ParentID**, **ProjectGroup**, **ProjectManagerPersonnelNumber**, och **ProjectType** ingår inte i standardmappning för projekt. Du kan lägga till mappningar om du vill att informationen ska synkroniseras för projekt.

I följande illustrationer visas ett exempel på uppgiftsmallmappning i dataintegrering. Mappningen visar vilken fältinformation som kommer att synkroniseras från Project Service Automation till Finance.

[![Mallmappning](./media/ProjectContractTemplateMapping.JPG)](./media/ProjectContractTemplateMapping.JPG)

[![Mallmappning](./media/ProjectTemplateMapping.JPG)](./media/ProjectTemplateMapping.JPG)

[![Mallmappning](./media/ProjectContractLinesMapping.JPG)](./media/ProjectContractLinesMapping.JPG)

[![Mallmappning](./media/ProjectContractLineMilestonesMapping.JPG)](./media/ProjectContractLineMilestonesMapping.JPG)

#### <a name="project-contract-line-milestone-mapping-in-the-projects-and-contracts-psa-3x-to-dynamics---v2-template"></a>Mappning av milstolpe för projektkontraktsrad i projekt och kontrakt (PSA 3.x till Dynamics) - v2-mall:

[![Mallmappning](./media/ProjectContractLineMilestoneMapping_v2.jpg)](./media/ProjectContractLineMilestoneMapping_v2.jpg)
