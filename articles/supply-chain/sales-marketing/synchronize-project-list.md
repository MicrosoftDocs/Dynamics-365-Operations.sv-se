---
title: Synkronisera projektlista från Finance and Operations till Field Service
description: Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera projekt från Microsoft Dynamics 365 for Finance and Operations till Microsoft Dynamics 365 for Field Service.
author: ChristianRytt
manager: AnnBe
ms.date: 03/13/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: ea5c188891bb97ba73d2d022e86bbff50897381b
ms.sourcegitcommit: 2b890cd7a801055ab0ca24398efc8e4e777d4d8c
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/07/2019
ms.locfileid: "1525887"
---
# <a name="synchronize-project-list-from-finance-and-operations-to-field-service"></a>Synkronisera projektlista från Finance and Operations till Field Service

[!include[banner](../includes/banner.md)]

Det här avsnittet beskriver de mallar och underliggande uppgifter som används för att synkronisera projekt från Microsoft Dynamics 365 for Finance and Operations till Microsoft Dynamics 365 for Field Service.

[![Synkronisering av affärsprocesser mellan Finance and Operations och Field Service](./media/FSProjectOW.png)](./media/FSProjectOW.png)

## <a name="templates-and-tasks"></a>Mallar och uppgifter
Följande mall och underliggande uppgifter används för att köra synkronisering av projekt från Microsoft Dynamics 365 for Finance and Operations till Microsoft Dynamics 365 for Field Service.

**Mall i dataintegrering**
- Projekt (Fin and Ops till Field Service)

**Uppgift i dataintegreringsprojektet**
- Projekt

Följande synkroniseringsuppgifter krävs före synkronisering av projektlista kan uppstå:
- Konton (Sales till Fin and Ops) 

## <a name="entity-set"></a>Ange entiteten
| Field Service           | Finance and Operations  |
|-------------------------|-------------------------|
|msdynce_externalprojects | Projekt                |

## <a name="entity-flow"></a>Flöde för entitet
Projekt skapas i Finance and Operations. Projekt med **projekttyp** inställd på **tid och material** och **projektfas** inställd på **pågår** synkroniseras entiteten **externt projekt** i Field Service annat projektnummer, projektnamn, projektfas och kundkontoinformation. Listan över **externt projekt** används för att parkoppla Field Service-arbetsorder med Finance and Operations-projekt.

## <a name="field-service-crm-solution"></a>CRM-lösning för Field Service
Entitet **Externt projekt** får alla projekt från Finance and Operations. Fältet **Externt projekt** har lagts till entiteten **arbetsorder**. Detta fält är ett uppslagsfält så genom att märka din arbetsorder med ett projekt kommer försäljningsordern kopplas till ett projekt i Finance and Operations. Efter att **Systemstatus** ändras **Öppna – pågår (690 970 000)** till en högre status kommer fältet **Externt projekt** att låsas och du kan inte lägga till, ta bort eller ändra värdet.

## <a name="prerequisites-and-mapping-setup"></a>Ställa in mappning och förutsättningar
### <a name="finance-and-operations"></a>Finance and Operations
Aktivera ändringsspårning för dataentitetsprojekt

## <a name="template-mapping-in-data-integration"></a>Mallmappning i dataintegrering


### <a name="projects-fin-and-ops-to-field-service-projects"></a>Projekt (Fin and Ops till Field Service): projekt

[![Mallmappning i dataintegrering](./media/FSProject1.png)](./media/FSProject1.png)
