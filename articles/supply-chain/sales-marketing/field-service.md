---
title: Integrering med Microsoft Dynamics 365 for Field Service
description: "Det här ämnet innehåller en översikt över integrationen med Microsoft Dynamics 365 for Field Service."
author: ChristianRytt
manager: AnnBe
ms.date: 04/25/2018
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
ms.sourcegitcommit: a57e23691a6b4d48c6b8dd6d1f61fc9730365b39
ms.openlocfilehash: 0c1268d2fddcf7b28ecfc3197f21e9d30a5a5855
ms.contentlocale: sv-se
ms.lasthandoff: 05/31/2018

---


# <a name="integration-with-microsoft-dynamics-365-for-field-service"></a>Integrering med Microsoft Dynamics 365 for Field Service

[!include[banner](../includes/banner.md)]

Microsoft Dynamics 365 for Finance and Operations aktiverar synkronisering av affärsprocesser mellan Finance and Operations och Microsoft Dynamics 365 for Field Service. Integrationsscenarierna konfigureras med hjälp av utbyggbara datamallar och Common Data Service (CDS) för att aktivera synkroniseringen av affärsprocesser.

[![Synkronisering av affärsprocesser mellan Finance and Operations och Field Service](./media/field-service-integration.png)](./media/field-service-integration.png)

Den första fasen av integrationen mellan Field Service och Finance and Operations fokuserar på arbetsorder och avtal i Field Service som ska faktureras i Finance and Operations. Flödet som stöds startar i Field Service där information från arbetsorder synkroniseras till Finance and Operations som försäljningsorder. i Finance and Operations faktureras försäljningsorder för att generera fakturadokument. Dessutom synkroniseras informationen från avtalsfakturor för Field Service till Finance and Operations. Microsoft Dynamics 365-dataintegratören synkroniserar data med hjälp av anpassningsbara projekt. Standardmallar kan användas för att skapa anpassade integrationsprojekt där ytterligare standardiserade och anpassade fält och även entiteter kan mappas för att justera integrationen och uppfylla särskilda krav.

Den första fasen av integrationen mellan Field Service och Finance and Operation tillåter synkronisering av följande artiklar:

- [Produkter i Finance and Operations till produkter i Field Service som innehåller information om produkttyp](field-service-product.md)
- [Arbetsorder i Field Service till försäljningsorder i Finance and Operations](field-service-work-order.md)
- [Fakturor i Field Service till fritextfakturor i Finance and Operations](field-service-invoice.md)

Titta på den korta YouTube-videon om du vill se ett exempel på hur du synkroniserar en arbetsorder mellan Field Service och Finance and Operations [synkronisera en arbetsorder mellan Dynamics 365 for Field Service och Finance and Operations](https://www.youtube.com/watch?v=hAB4TDVMjxU).

## <a name="system-requirements-for-finance-and-operations"></a>Systemkrav för Finance and Operations
Field Service-integration stöder följande versioner:

### <a name="dynamics-365-for-finance-and-operations-version-80-april-2018-or-later"></a>Dynamics 365 for Finance and Operations version 8.0 (april 2018) eller senare

- Dynamics 365 for Finance and Operations version 8.0 (april 2018) gavs ut i april 2018 och har programversionsnummer 8.0.30.8020 med plattformsuppdatering 15 (7.0.4841.35234). 

## <a name="system-requirements-for-field-service"></a>Systemkrav för Field Service
Om du vill använda integrationslösningen för Field Service måste du installera följande komponenter:

### <a name="microsoft-dynamics-365-for-field-service-90-or-later"></a>Microsoft Dynamics 365 for Field Service 9.0 eller senare

- Dynamics 365 for Field Service, version 1612 (9.0.1.733) (DB 9.0.1.733) online eller en senare version.
- Lösningen Potentiell kund till kontanter (P2C) för Dynamics 365, version 1.15.0.1 eller senare. Lösningen finns att hämta från [AppSource](https://appsource.microsoft.com/en-us/product/dynamics-365/mscrm.c7a48b40-eed3-4d67-93ba-f2364281feb3).
- Integrationslösningen för Field Service för Dynamics 365, version 1.0.0.0 eller en senare version. Lösningen finns att hämta från [AppSource](https://appsource.microsoft.com/en-us/product/dynamics-365/mscrm.p2cfieldserviceintegration).

