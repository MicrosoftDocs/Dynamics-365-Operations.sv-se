---
title: Synkronisera projektlista från Supply Chain Management till Field Service
description: Denna artikel beskriver de mallar och underliggande uppgifter som används för att synkronisera projekt från Dynamics 365 Supply Chain Management till Dynamics 365 Field Service.
author: Henrikan
ms.date: 03/13/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: henrikan
ms.dyn365.ops.version: 8.1.3
ms.search.validFrom: 2018-12-01
ms.openlocfilehash: 71c0580953f01c2d29e99fa2928a0b4a3937d5c5
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/03/2022
ms.locfileid: "8899365"
---
# <a name="synchronize-project-list-from-supply-chain-management-to-field-service"></a>Synkronisera projektlista från Supply Chain Management till Field Service

[!include[banner](../includes/banner.md)]

Denna artikel beskriver de mallar och underliggande uppgifter som används för att synkronisera projekt från Dynamics 365 Supply Chain Management till Dynamics 365 Field Service.

[![Synkronisering av affärsprocesser mellan Supply Chain Management och Field Service.](./media/FSProjectOW.png)](./media/FSProjectOW.png)

## <a name="templates-and-tasks"></a>Mallar och uppgifter
Följande mall och underliggande uppgifter används för att köra synkronisering av projekt från Supply Chain Management till Field Service.

**Mall i dataintegrering**
- Projekt (Supply Chain Management till Field Service)

**Uppgift i dataintegreringsprojektet**
- Projekt

Följande synkroniseringsuppgifter krävs före synkronisering av projektlista kan uppstå:
- Konton (Sales till Supply Chain Management) 

## <a name="entity-set"></a>Ange entiteten
| Field Service           | Hantering av underleverantörer  |
|-------------------------|-------------------------|
|msdynce_externalprojects | Projekt                |

## <a name="entity-flow"></a>Flöde för entitet
Projekt skapas i Supply Chain Management. Projekt med **projekttyp** inställd på **tid och material** och **projektfas** inställd på **pågår** synkroniseras entiteten **externt projekt** i Field Service annat projektnummer, projektnamn, projektfas och kundkontoinformation. Listan över **externt projekt** används för att parkoppla Field Service-arbetsorder med Supply Chain Management-projekt.

## <a name="field-service-crm-solution"></a>CRM-lösning för Field Service
Entitet **Externt projekt** får alla projekt från Supply Chain Management. Fältet **Externt projekt** har lagts till entiteten **arbetsorder**. Detta fält är ett uppslagsfält så genom att märka din arbetsorder med ett projekt kommer försäljningsordern kopplas till ett projekt i Supply Chain Management. Efter att **Systemstatus** ändras **Öppna – pågår (690 970 000)** till en högre status kommer fältet **Externt projekt** att låsas och du kan inte lägga till, ta bort eller ändra värdet.

## <a name="prerequisites-and-mapping-setup"></a>Ställa in mappning och förutsättningar
### <a name="supply-chain-management"></a>Hantering av underleverantörer
Aktivera ändringsspårning för dataentitetsprojekt

## <a name="template-mapping-in-data-integration"></a>Mallmappning i dataintegrering


### <a name="projects-supply-chain-management-to-field-service-projects"></a>Projekt (Supply Chain Management till Field Service): projekt

[![Mallmappning i dataintegrering.](./media/FSProject1.png)](./media/FSProject1.png)


[!INCLUDE[footer-include](../../includes/footer-banner.md)]