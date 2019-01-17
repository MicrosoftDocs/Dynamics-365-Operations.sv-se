---
title: "Synkronisera projektlista från Finance and Operations till Field Service"
description: "Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera projekt från Microsoft Dynamics 365 for Finance and Operations, till Microsoft Dynamics 365 for Field Service"
author: ChristianRytt
manager: AnnBe
ms.date: 12/20/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.translationtype: HT
ms.sourcegitcommit: 8c6cb481f1a3fe48d329c5936118d8df88a4175b
ms.openlocfilehash: adcb1c1b241ce2b073cd26cf2a8a8d64931c8b0f
ms.contentlocale: sv-se
ms.lasthandoff: 12/20/2018

---

# <a name="synchronize-project-list-from-finance-and-operations-to-field-service"></a>Synkronisera projektlista från Finance and Operations till Field Service

[!include[banner](../includes/banner.md)]

Det här avsnittet beskriver vilka mallar och underliggande uppgifter som används för att synkronisera projekt från Microsoft Dynamics 365 for Finance and Operations, till Microsoft Dynamics 365 for Field Service

[![Synkronisering av affärsprocesser mellan Finance and Operations och Field Service](./media/FSProjectOW.png)](./media/FSProjectOW.png)

## <a name="templates-and-tasks"></a>Mallar och uppgifter
Följande mall och underliggande uppgifter används för att synkronisera projekt från Microsoft Dynamics 365 for Finance and Operations, till Microsoft Dynamics 365 for Field Service

**Namnet på mallen i dataintegreringen**
- Projekt (Finance and Operations till Field Service)

**Namnen på uppgifterna i dataintegreringsprojektet:**
- Projekt

Följande synkroniseringsuppgifter krävs före synkronisering av projektlista kan uppstå:
- Konton (Sales till Finance and Operations) 

## <a name="entity-set"></a>Ange entiteten
Field Service   Finance and Operations

| Field Service           | Finance and Operations  |
|-------------------------|-------------------------|
|msdynce_externalprojects | Projekt                |

## <a name="entity-flow"></a>Flöde för entitet
Projekt skapas i Finance and Operations. Projekt med **projekttypen** tid och material och **projektfas** pågår synkroniseras till entiteten **externt projekt** i Field Service, bland annat projektnummer, projektnamn, projektfas och kundkontoinformation. Listan över **externt projekt** används för att parkoppla Field service-arbetsorder med Finance and Operations-projekt.
CRM-lösning för Field Service, Externt projekt är en ny entitet som hämtar alla projekt från Operations.
Fältet Externt projekt har lagts till entiteten arbetsorder. Detta fält är ett uppslag och genom att märka din arbetsorder med ett projekt kommer försäljningsordern sedan kopplas till ett projekt i Operations. När systemstatus ändras, öppen – pågår (690 970 000) till en högre status kommer fältet Externt projekt att låsas och du kan inte lägga till, ta bort eller ändra värdet.

## <a name="prerequisites-and-mapping-setup"></a>Ställa in mappning och förutsättningar
### <a name="in-finance-and-operations"></a>I Finance and Operations
Aktivera ändringsspårning för dataentitetsprojekt

## <a name="template-mapping-in-data-integration"></a>Mallmappning i dataintegrering


### <a name="projects-finance-and-operations-to-field-service-projects"></a>Projekt (Finance and Operations till Field Service): projekt

[![Mallmappning i dataintegrering](./media/FSProject1.png)](./media/FSProject1.png)

