---
title: Integrering med Microsoft Dynamics 365 for Field Service
description: "Det här ämnet innehåller en översikt över integrationen med Microsoft Dynamics 365 for Field Service."
author: ChristianRytt
manager: AnnBe
ms.date: 08/25/2018
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: 
audience: Application User, IT Pro
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 95031534c43dc0578e258bc3e5376c429d72b0ab
ms.openlocfilehash: 673ab2a101cee1a3dbbb1249f582d959cecc7f7f
ms.contentlocale: sv-se
ms.lasthandoff: 12/23/2018

---

# <a name="integration-with-microsoft-dynamics-365-for-field-service"></a>Integrering med Microsoft Dynamics 365 for Field Service

[!include[banner](../includes/banner.md)]

Microsoft Dynamics 365 for Finance and Operations aktiverar synkronisering av affärsprocesser mellan Finance and Operations och Microsoft Dynamics 365 for Field Service. Integrationsscenarierna konfigureras med hjälp av utbyggbara datamallar och Common Data Service (CDS) för att aktivera synkroniseringen av affärsprocesser.
Standardmallar kan användas för att skapa anpassade integrationsprojekt där ytterligare standardiserade och anpassade fält och även entiteter kan mappas för att justera integrationen och uppfylla affärsbehov. 

Integration av katalogtjänst i Field Service bygger vidare på befintliga funktioner för potentiell kund till pengar.

![Synkronisering av affärsprocesser mellan Finance and Operations och Field Service](./media/field-service-integration.png)

Den första fasen av integrationen mellan Field Service och Finance and Operations fokuserar på arbetsorder och avtal i Field Service som ska faktureras i Finance and Operations. Flödet som stöds startar i Field Service där information från arbetsorder synkroniseras till Finance and Operations som försäljningsorder. i Finance and Operations faktureras försäljningsorder för att generera fakturadokument. Dessutom synkroniseras informationen från avtalsfakturor för Field Service till Finance and Operations. Microsoft Dynamics 365-dataintegratören synkroniserar data med hjälp av anpassningsbara projekt. Standardmallar kan användas för att skapa anpassade integrationsprojekt där ytterligare standardiserade och anpassade fält och även entiteter kan mappas för att justera integrationen och uppfylla särskilda krav.

Den första fasen av integrationen mellan Field Service och Finance and Operation tillåter synkronisering av följande artiklar:

- [Produkter i Finance and Operations till produkter i Field Service som innehåller information om produkttyp](field-service-product.md)
- [Arbetsorder i Field Service till försäljningsorder i Finance and Operations](field-service-work-order.md)
- [Fakturor i Field Service till fritextfakturor i Finance and Operations](field-service-invoice.md)

Titta på den korta YouTube-videon om du vill se ett exempel på hur du synkroniserar en arbetsorder mellan Field Service och Finance and Operations [Så här synkroniserar du en arbetsorder med integration med Microsoft Dynamics 365](https://www.youtube.com/watch?v=46ylO7raZAo).

## <a name="system-requirements-for-finance-and-operations"></a>Systemkrav för Finance and Operations
Field Service-integration stöder följande versioner:

### <a name="dynamics-365-for-finance-and-operations-version-80-april-2018-or-later"></a>Dynamics 365 for Finance and Operations version 8.0 (april 2018) eller senare

- Dynamics 365 for Finance and Operations version 8.0 (april 2018) gavs ut i april 2018 och har programversionsnummer 8.0.30.8020 med plattformsuppdatering 15 (7.0.4841.35234). 

## <a name="system-requirements-for-field-service"></a>Systemkrav för Field Service
Om du vill använda integrationslösningen för Field Service måste du installera följande komponenter:

### <a name="microsoft-dynamics-365-for-field-service-90-or-later"></a>Microsoft Dynamics 365 for Field Service 9.0 eller senare

- Dynamics 365 for Field Service, version 1612 (9.0.1.733) (DB 9.0.1.733) online eller en senare version.
- Lösningen Potentiell kund till kontanter (P2C) för Dynamics 365, version 1.15.0.1 eller senare. Lösningen finns att hämta från [AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.c7a48b40-eed3-4d67-93ba-f2364281feb3).
- Integrationslösningen för Field Service för Dynamics 365, version 1.0.0.0 eller en senare version. Lösningen finns att hämta från [AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.p2cfieldserviceintegration).

# <a name="integration-with-microsoft-dynamics-365-for-field-service-including-inventory-and-project-information"></a>Integrering med Microsoft Dynamics 365 for Field Service, inklusive information om lager och projekt

Ytterligare funktioner i den här andra fasen fokuserar på att ge fälttekniker insikt om vilken lagerinformation som från Finance and Operations som tillåter dem att uppdatera lagernivåer och göra materialöverföringar. Dessutom får företag som utför installation och underhåll av sålda varor bättre kontroll och insyn i den fullständiga försäljnings- och serviceprocessen med integrering från projekt.

### <a name="functionality-includes-integration-of"></a>Funktionen inkluderar integrering av:
- Lagerställeinformation
- Information om lagerbehållning
- Lageröverföringar
- Lagerjusteringar
- Dynamics 365 for Finance and Operations-projekt som är kopplade till Dynamics 365 for Field Service arbetsorder
- Dynamics 365 for Field Service arbetsorder med en länk till Dynamics 365 for Finance and Operations projekt, tillämpa det här projektnumret till Dynamics 365 for Finance and Operations försäljningsorder för att kunna fakturera från projektet. 

![Synkronisering av affärsprocesser mellan Finance and Operations och Field Service](./media/FSv2overview.png)

### <a name="the-second-phase-of-the-integration-between-field-service-and-finance-and-operations-enables-synchronization-with-the-following-templates"></a>Den andra fasen av integrationen mellan Field Service och Finance and Operations tillåter synkronisering med följande mallar:
- Lagerställen (Fin and Ops till Field Service) - lagerställen från Finance and Operations till Field Service [avancerad fråga] 
- Produktlager (Fin and Ops till Field Service) - information om lagernivåer från Finance and Operations till Field Service [avancerad fråga] 
- Lagerjustering (Field Service till Fin and Ops) - lagerjusteringar från Field Service till Finance and Operations [avancerad fråga] 
- Lageröverföringar (Field Service till Fin and Ops) - Lageröverföringar från Field Service till Finance and Operations [avancerad fråga] 
- Projekt (Fin and Ops till Field Service) - projektlista från Finance and Operations till Field Service 
- Arbetsorder med projekt (Field Service till Fin and Ops) - arbetsorder i Field Service till försäljningsorder i Finance and Operations, med stöd för projekt [avancerad fråga] 
- Field Service-produkter med lagerenhet (Fin and Ops till Sales) - Finance and Operations "Säljbara frisläppta produkter" till Sales "produkter" för Field Service, inklusive lagerenhet 

## <a name="system-requirements-for-finance-and-operations"></a>Systemkrav för Finance and Operations
Field Service-integration stöder följande versioner:

- Dynamics 365 for Finance and Operations version 8.1.2 (december 2019) gavs ut i december 2019 och har programversionsnummer 8.1.195 med plattformsuppdatering 22 (7.0.5095). 

## <a name="system-requirements-for-field-service"></a>Systemkrav för Field Service
Om du vill använda integrationslösningen för Field Service måste du installera följande komponenter:

- Field Service for Dynamics 365 (version 8.2.0.286) eller en senare version för Dynamics 365 9.1.x - publicerad i november 2018
- Lösningen Potentiell kund till kontanter (P2C) för Dynamics 365, version 1.15.0.1 eller senare. Lösningen finns att hämta från [AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.c7a48b40-eed3-4d67-93ba-f2364281feb3).
- Lösningen "Field Service integrering, projekt och lager" för Dynamics 365, version 2.0.0.0 eller en senare version. Lösningen finns att hämta från [AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.p2cfieldserviceintegrationv2).

