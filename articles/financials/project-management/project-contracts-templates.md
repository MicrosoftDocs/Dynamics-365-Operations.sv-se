---
title: "Synkronisera projektkontrakt och projekt direkt från Project Service Automation till Finance and Operations"
description: "Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera projektprojektkontrakt och projekt direkt från Microsoft Dynamics 365 for Project Service Automation till Microsoft Dynamics 365 for Finance and Operations."
author: KimANelson
manager: AnnBe
ms.date: 10/25/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 87983
ms.assetid: b454ad57-2fd6-46c9-a77e-646de4153067
ms.search.region: Global
ms.author: knelson
ms.search.validFrom: 2017-12-13
ms.dyn365.ops.version: AX 7.3.0
ms.translationtype: HT
ms.sourcegitcommit: 0450326dce0ba6be99aede4ebc871dc58c8039ab
ms.openlocfilehash: 0889bc233674cb80dd056ac77edb5c936c6633a7
ms.contentlocale: sv-se
ms.lasthandoff: 11/01/2018

---

# <a name="synchronize-project-contracts-and-projects-directly-from-project-service-automation-to-finance-and-operations"></a>Synkronisera projektkontrakt och projekt direkt från Project Service Automation till Finance and Operations

[!include[banner](../includes/banner.md)]

Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera projektprojektkontrakt och projekt direkt från Microsoft Dynamics 365 for Project Service Automation till Microsoft Dynamics 365 for Finance and Operations.

> [!NOTE] 
> Om du använder Microsoft Dynamics 365 for Finance and Operations, Enterprise Edition, 7.3.0, måste du installera KB 4074835.

## <a name="data-flow-for-project-service-automation-to-finance-and-operations"></a>Dataflöde för Project Service Automation till Finance and Operations

> [!NOTE]
> Innan du kan använda integrationslösningen Project Service Automation till Finance and Operations bör du känna till dataintegrationsfunktionen för Microsoft Dynamics 365.

Automatisering av integrationslösningen Project Service Automation till Finance and Operations använder funktionen dataintegration för att synkronisera data mellan instanser av Project Service Automation och Finance and Operations. Integrationsmallen som är tillgänglig med dataintegrationsfunktionen tillåter flöde av data om projektkontrakt, projekt, projektkontraktsrader och projektkontraktraders milstolpar från Project Service Automation till Finance and Operations.

Följande bild visar hur data synkroniseras mellan Project Service Automation och Finance and Operations.

[![Dataflöde för integration av Project Service Automation med Finance and Operations](./media/ProjectsAndContractsFlow.JPG)](./media/ProjectsAndContractsFlow.JPG)

## <a name="templates-and-tasks"></a>Mallar och uppgifter

För att få åtkomst till tillgängliga mallar väljer du **Projekt** i administratörscentret för Microsoft PowerApps, och i det övre högra hörnet väljer du **Nytt projekt** för att välja offentliga mallar.

Följande mall och underliggande uppgift används för att synkronisera projektkontrakt och proojekt från Project Service Automation till Finance and Operations:

- **Namnet på mallen i dataintegrering:** projektet och kontrakt (PSA till Fin och Ops)
- **Namn på aktiviteter i projektet:**

    - Projektkontrakt PSA till Fin och Ops
    - Projekt PSA till Fin och Ops
    - Projektkontraktrader PSA till Fin och Ops
    - Projektkontraktraders milstolpar PSA till Fin och Ops

Innan synkroniseringen av projektkontrakt och projekt kan utföras måste du synkronisera konton.

## <a name="entity-set"></a>Ange entiteten

| Project Service Automation       | Finance and Operations                                 |
|----------------------------------|--------------------------------------------------------|
| Order                           | Integrationsenhet för projektkontrakt                |
| Projekt                         | Integrationsenhet för projekt                         |
| Orderrader                      | Integrationsenhet för projektkontraktsrad           |
| Milstolpar för projektkontraktsrad | Integrationsenhet för milstolpar för projektkontraktsrad |

## <a name="entity-flow"></a>Flöde för entitet

Projektkontrakt hanteras i Project Service Automation och de synkroniseras till Finance and Operations som projektkontrakt. Du kan ange integrationsmallen som del av integrationskällan i Finance and Operations för projektkontraktet.

Tids- och materialprojekt och fastprisprojekt hanteras i Project Service Automation, och dessa synkroniseras med Finance and Operations som projekt. Du kan ange integrationsmallen som del av integrationskällan i Finance and Operations för projektet.

Projektkontraktrader hanteras i Project Service Automation och de synkroniseras till Finance and Operations som faktureringsregler för projektkontrakt. Om faktureringsmetoden skiljer sig från förvald projekttyp kommer synkroniseringen att uppdatera projekttypen för kontraktradsprojekt och projektgrupp.

Milstolpar för projektkontraktsrad hanteras i Project Service Automation och de synkroniseras till Finance and Operations som milstolpar för faktureringsregler för projektkontrakt.

## <a name="project-service-automation-to-finance-and-operations-integration-solution"></a>Integegrationslösning för Project Service Automation till Finance and Operations

Fältet **projektkontrakt-ID** är tillgängligt på sidan **projektkontrakt**. Detta fält har gjort en fysisk och en unik nyckel för att stödja integreringen.

När ett nytt projektkontrakt skapas om ett **Projektkontrakt-ID**-värde inte finns, skapas det automatiskt med hjälp av en nummerserie. Värdet består av **ORD** följt av en ökande nummerserie och sedan ett suffix på sex tecken. Här är ett exempel: **ORD-01022-Z4M9Q0**.

Fältet **Projektnummer** är tillgängligt på sidan **projekt**. Detta fält har gjort en fysisk och en unik nyckel för att stödja integreringen.

När ett nytt projekt skapas om ett **projektnummer**-värde inte finns, skapas det automatiskt med hjälp av en nummerserie. Värdet består av **PRJ** följt av en ökande nummerserie och sedan ett suffix på sex tecken. Här är ett exempel: **PRJ-01049-CCNID0**.

När integrationslösningen för Project Service Automation till Finance and Operations tillämpas<TO DO: link in the top level document link where we will be adding the instructions for applying the PSA solution>, anger ett uppgraderingsskript fältet **projektkontrakt-ID** för befintliga projektkontrakt och **projektnummer** för befintliga projekt i Project Service Automation.

## <a name="prerequisites-and-mapping-setup"></a>Ställa in mappning och förutsättningar

- Innan synkroniseringen av projektkontrakt och projekt kan utföras måste du synkronisera konton.
- I din anslutningsuppsättning, lägg till en integrationsnyckelfältplanering för **msdyn\_organizationalunits** till **msdyn\_namn \[Namn\]**. Du kanske först måste lägga till ett projekt i anslutningsuppsättningen. Mer information finns i [integrera data i Common Data Service för appar](https://docs.microsoft.com/en-us/powerapps/administrator/data-integrator).
- I din anslutningsuppsättning, lägg till en integrationsnyckelfältplanering för **msdyn\_projekt** till **msdynce\_projektnummer \[Projektnummer\]**. Du kanske först måste lägga till ett projekt i anslutningsuppsättningen. Mer information finns i [integrera data i Common Data Service för appar](https://docs.microsoft.com/en-us/powerapps/administrator/data-integrator).
- **SourceDataID** för projektkontrakt och projekt kan uppdateras till ett annat värde eller tas bort från mappningen. Standardmallvärdet är **Project Service Automation**.
- Mappningen **PaymentTerms** måste uppdateras så att den motsvarar giltiga betalningsvillkor i Finance and Operations. Du kan också ta bort mappningen från projektuppgiften. Den standardinställda värdemappningen har standardvärden för demodata. Tabellen nedan visar värdena i Project Service Automation.

    | Värde | beskrivning   |
    |-------|---------------|
    | 1     | Netto 30        |
    | 2     | 2%10, Netto 30 |
    | 3     | Netto 45        |
    | 4     | Netto 60        |

## <a name="power-query"></a>Power Query

Du måste använda Microsoft Power Query för Excel för att filtrera data om följande villkor uppfylls:

- Det finns försäljningsorder i Microsoft Dynamics 365 for Sales.
- Det finns flera organisationsenheter i Project Service Automation och organisationsenheterna mappas till flera juridiska personer i Finance and Operations.

Om du måste använda Power Query enligt riktlinjerna nedan:

- Mallen för projekt och kontrakt ("PSA till Fin och Ops") har ett standardfilter som endast inkluderar försäljningsorder av typen **Arbetsobjekt (msdyn\_ordertype = 192350001)**. Det här filtret hjälper till att garantera att projektkontrakt inte skapas för försäljningsorder i Finance and Operations. Om du skapar en egen mall måste du lägga till filtret.
- Du måste skapa ett Power Query-filtret som endast inkluderar kontraktorganisationer som ska synkroniseras mot den juridiska personen av integrationens anslutningsuppsättning. T.ex. ska projektkontrakt som du har med kontraktorganisationsenheten för Contoso US ska synkroniseras mot den juridiska personen USSI, men projektkontraktet som du har med kontraktorganisationsenhet för Contoso Global ska synkroniseras mot den juridiska personen för USMF. Om du inte lägger till det här filtret i din uppgiftsmappning kommer alla projektkontrakt att synkroniseras till den juridiska person som har definierats för anslutningen, oavsett kontraktorganisationsenhet.

## <a name="template-mapping-in-data-integration"></a>Mallmappning i dataintegrering

> [!NOTE] 
> Fälten **CustomerReference**, **AddressCity**, **AddressCountryRegionID**, **AddressDescription**, **AddressLine1**, **AddressLine2**, **AddressState** och **AddressZipCode** ingår inte i standardmappningen för projektkontrakt. Du kan lägga till mappningar om du vill att informationen ska synkroniseras för projektkontrakt.
>
> Fälten **beskrivning**, **ParentID**, **ProjectGroup**, **ProjectManagerPersonnelNumber**, och **ProjectType** ingår inte i standardmappning för projekt. Du kan lägga till mappningar om du vill att informationen ska synkroniseras för projekt.

I följande illustrationer visas ett exempel på uppgiftsmallmappning i dataintegrering. Mappningen visar vilken fältinformation som kommer att synkroniseras från Project Service Automation till Finance and Operations.

[![Mallmappning](./media/ProjectContractTemplateMapping.JPG)](./media/ProjectContractTemplateMapping.JPG)

[![Mallmappning](./media/ProjectTemplateMapping.JPG)](./media/ProjectTemplateMapping.JPG)

[![Mallmappning](./media/ProjectContractLinesMapping.JPG)](./media/ProjectContractLinesMapping.JPG)

[![Mallmappning](./media/ProjectContractLineMilestonesMapping.JPG)](./media/ProjectContractLineMilestonesMapping.JPG)

