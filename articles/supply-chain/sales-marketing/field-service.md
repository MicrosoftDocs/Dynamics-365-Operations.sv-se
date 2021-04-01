---
title: Integrering med Microsoft Dynamics 365 Field Service - översikt
description: Det här ämnet innehåller en översikt över integrering med Microsoft Dynamics 365 Field Service.
author: ChristianRytt
manager: tfehr
ms.date: 07/25/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.openlocfilehash: 9b0fafd46143979a734151b4011e537991347862
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5237904"
---
# <a name="integration-with-microsoft-dynamics-365-field-service-overview"></a>Integrering med Microsoft Dynamics 365 Field Service - översikt

[!include[banner](../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Supply Chain Management tillåter synkronisering av affärsprocesser mellan Dynamics 365 Supply Chain Management och Dynamics 365 Field Service. Integrationsscenarierna konfigureras med hjälp av utbyggbara datamallar och Microsoft Dataverse för att aktivera synkroniseringen av affärsprocesser.
Standardmallar kan användas för att skapa anpassade integrationsprojekt där ytterligare standardiserade och anpassade kolumner och tabeller kan mappas för att justera integrationen och uppfylla affärsbehov. 

Integration av katalogtjänst i Field Service bygger vidare på befintliga funktioner för potentiell kund till pengar.

![Synkronisering av affärsprocesser mellan Supply Chain Management och Field Service](./media/field-service-integration.png)

Den första fasen av integrationen mellan Field Service och Supply Chain Management fokuserar på arbetsorder och avtal i Field Service som ska faktureras i Supply Chain Management. Flödet som stöds startar i Field Service där information från arbetsorder synkroniseras till Supply Chain Management som försäljningsorder. I Supply Chain Management faktureras försäljningsorder för generering av fakturadokument. Dessutom synkroniseras informationen från avtalsfakturor för Field Service till Supply Chain Management. Microsoft Dynamics 365-dataintegratören synkroniserar data med hjälp av anpassningsbara projekt. Standardmallar kan användas för att skapa anpassade integrationsprojekt där ytterligare standardiserade och anpassade kolumner och tabeller kan mappas för att justera integrationen och uppfylla särskilda krav.

Den första fasen av integrationen mellan Field Service och Supply Chain Management tillåter synkronisering av följande artiklar:

- [Synkronisera produkter i Supply Chain Management till produkter i Field Service](field-service-product.md)
- [Synkronisera arbetsorder i Field Service till försäljningsorder i Supply Chain Management](field-service-work-order.md)
- [Synkronisera avtalsfakturor i Field Service till fritextfakturor i Supply Chain Management](field-service-invoice.md)

Titta på den korta YouTube-videon om du vill se ett exempel på hur du synkroniserar en arbetsorder mellan Field Service och Supply Chain Management [Så här synkroniserar du en arbetsorder med integration med Microsoft Dynamics 365](https://www.youtube.com/watch?v=46ylO7raZAo).

## <a name="integration-with-field-service-including-inventory-and-project-information"></a>Integration med Field Service, till exempel lager- och projektinformation

Ytterligare funktioner i den här andra fasen fokuserar på att ge fälttekniker insikt om vilken lagerinformation som från Supply Chain Management som tillåter dem att uppdatera lagernivåer och göra materialöverföringar. Dessutom får företag som utför installation och underhåll av sålda varor bättre kontroll och insyn i den fullständiga försäljnings- och serviceprocessen med integrering från projekt.

### <a name="functionality-includes-integration-of"></a>Funktionen inkluderar integrering av:
- Lagerställeinformation
- Information om lagerbehållning
- Lageröverföringar
- Lagerjusteringar
- Supply Chain Management-projekt kopplade till Dynamics 365 Field Service arbetsorder
- Dynamics 365 Field Service arbetsorder med länk till Supply Chain Management-projekt använder detta projektnummer för att försäljningsorder ska kunna fakturera från projektet. 

![Synkronisering av affärsprocesser mellan Supply Chain Management och Field Service](./media/FSv2overview.png)

### <a name="the-second-phase-of-the-integration-between-field-service-and-supply-chain-management-enables-synchronization-with-the-following-templates"></a>Den andra fasen av integrationen mellan Field Service och Supply Chain Management tillåter synkronisering med följande mallar:
- Lagerställen (Supply Chain Management till Field Service) - Lagerställen från Supply Chain Management till Field Service [avancerad fråga] 
- Produktlager (Supply Chain Management till Field Service) - Information om lagernivåer från Supply Chain Management till Field Service [avancerad fråga] 
- Lagerjustering (Field Service till Supply Chain Management) - Lagerjusteringar från Field Service till Supply Chain Management [avancerad fråga] 
- Lageröverföringar (Field Service till Supply Chain Management) - Lageröverföringar från Field Service till Supply Chain Management [avancerad fråga] 
- Projekt (Supply Chain Management till Field Service) - Projektlista från Supply Chain Management till Field Service 
- Arbetsorder med projekt (Field Service till Supply Chain Management) - arbetsorder i Field Service till försäljningsorder i Supply Chain Management, med stöd för projekt [avancerad fråga] 
- Field Service-produkter med lagerenhet (Supply Chain Management till Sales) - Supply Chain Management "Säljbara frisläppta produkter" till Sales "produkter" för Field Service, inklusive lagerenhet 

## <a name="system-requirements"></a>Systemkrav

### <a name="system-requirements-for-supply-chain-management"></a>System krav för hantering av Supply Chain Management
Field Service-integration stöder följande versioner:

- Dynamics 365 for Finance and Operations version 8.1.2 (december 2018) släpptes i december 2018 och har programversionsnummer 8.1.195 med plattformsuppdatering 22 (7.0.5095). 

### <a name="system-requirements-for-field-service"></a>Systemkrav för Field Service
Om du vill använda integrationslösningen för Field Service måste du installera följande komponenter:

- Field Service (version 8.2.0.286) eller en senare version på Dynamics 365 9.1.x - utgiven i november 2018
- Lösningen Potentiell kund till kontanter (P2C) för Dynamics 365, version 1.15.0.1 eller senare. Lösningen finns att hämta från [AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.c7a48b40-eed3-4d67-93ba-f2364281feb3).
- Lösningen "Field Service integrering, projekt och lager" för Dynamics 365, version 2.0.0.0 eller en senare version. Lösningen finns att hämta från [AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.p2cfieldserviceintegrationv2).


[!INCLUDE[footer-include](../../includes/footer-banner.md)]