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
ms.reviewer: yuyus
ms.search.scope: Core, Operations
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: 
ms.author: crytt
ms.dyn365.ops.version: July 2017 update
ms.search.validFrom: 2017-07-8
ms.translationtype: HT
ms.sourcegitcommit: 03a932652cdd93b2a5917d0fca72809d1648b678
ms.openlocfilehash: b1acf0b64914a3199fcf44f8377e32b26f0af99e
ms.contentlocale: sv-se
ms.lasthandoff: 04/25/2018

---


# <a name="integration-with-microsoft-dynamics-365-for-field-service"></a><span data-ttu-id="c90a7-103">Integrering med Microsoft Dynamics 365 for Field Service</span><span class="sxs-lookup"><span data-stu-id="c90a7-103">Integration with Microsoft Dynamics 365 for Field Service</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="c90a7-104">Microsoft Dynamics 365 for Finance and Operations aktiverar synkronisering av affärsprocesser mellan Finance and Operations och Microsoft Dynamics 365 for Field Service.</span><span class="sxs-lookup"><span data-stu-id="c90a7-104">Microsoft Dynamics 365 for Finance and Operations enables synchronization of business processes between Finance and Operations and Microsoft Dynamics 365 for Field Service.</span></span> <span data-ttu-id="c90a7-105">Integrationsscenarierna konfigureras med hjälp av utbyggbara datamallar och Common Data Service (CDS) för att aktivera synkroniseringen av affärsprocesser.</span><span class="sxs-lookup"><span data-stu-id="c90a7-105">The integration scenarios are configured by using extensible Data integrator templates and the Common Data Service (CDS) to enable the synchronization of business processes.</span></span>

<span data-ttu-id="c90a7-106">[![Synkronisering av affärsprocesser mellan Finance and Operations och Field Service](./media/field-service-integration.png)](./media/field-service-integration.png)</span><span class="sxs-lookup"><span data-stu-id="c90a7-106">[![Synchronization of business processes between Finance and Operations and Field Service](./media/field-service-integration.png)](./media/field-service-integration.png)</span></span>

<span data-ttu-id="c90a7-107">Den första fasen av integrationen mellan Field Service och Finance and Operations fokuserar på arbetsorder och avtal i Field Service som ska faktureras i Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c90a7-107">The first phase  of the integration between Field Service and Finance and Operations is focused on enabling work orders and agreements in Field Service to be invoiced in Finance and Operations.</span></span> <span data-ttu-id="c90a7-108">Flödet som stöds startar i Field Service där information från arbetsorder synkroniseras till Finance and Operations som försäljningsorder.</span><span class="sxs-lookup"><span data-stu-id="c90a7-108">The supported flow starts in Field Service, where information from work orders is synchronized to Finance and Operations as sales orders.</span></span> <span data-ttu-id="c90a7-109">i Finance and Operations faktureras försäljningsorder för att generera fakturadokument.</span><span class="sxs-lookup"><span data-stu-id="c90a7-109">In Finance and Operations, the sales orders are invoiced to generate invoice documents.</span></span> <span data-ttu-id="c90a7-110">Dessutom synkroniseras informationen från avtalsfakturor för Field Service till Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="c90a7-110">In addition, the information from Field Service agreement invoices is synchronized to Finance and Operations.</span></span> <span data-ttu-id="c90a7-111">Microsoft Dynamics 365-dataintegratören synkroniserar data med hjälp av anpassningsbara projekt.</span><span class="sxs-lookup"><span data-stu-id="c90a7-111">The Microsoft Dynamics 365 Data integrator synchronizes data by using customizable projects.</span></span> <span data-ttu-id="c90a7-112">Standardmallar kan användas för att skapa anpassade integrationsprojekt där ytterligare standardiserade och anpassade fält och även entiteter kan mappas för att justera integrationen och uppfylla särskilda krav.</span><span class="sxs-lookup"><span data-stu-id="c90a7-112">Standard templates can be used to create custom integration projects where additional standard and custom fields, and also entities, can be mapped to adjust the integration and meet specific requirements.</span></span>

<span data-ttu-id="c90a7-113">Den första fasen av integrationen mellan Field Service och Finance and Operation tillåter synkronisering av följande artiklar:</span><span class="sxs-lookup"><span data-stu-id="c90a7-113">The first phase of the integration between Field Service and Finance and Operations enables synchronization of the following items:</span></span>

- [<span data-ttu-id="c90a7-114">Produkter i Finance and Operations till produkter i Field Service som innehåller information om produkttyp</span><span class="sxs-lookup"><span data-stu-id="c90a7-114">Products in Finance and Operations to products in Field Service that include Product Type information</span></span>](field-service-product.md)
- [<span data-ttu-id="c90a7-115">Arbetsorder i Field Service till försäljningsorder i Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="c90a7-115">Work orders in Field Service to sales orders in Finance and Operations</span></span>](field-service-work-order.md)
- [<span data-ttu-id="c90a7-116">Fakturor i Field Service till fritextfakturor i Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="c90a7-116">Invoices in Field Service to free text invoices in Finance and Operations</span></span>](field-service-invoice.md)

<span data-ttu-id="c90a7-117">Om du vill se ett exempel på hur du synkroniserar en arbetsorder mellan Field Service och Finance and Operations titta på kort YouTube videon:</span><span class="sxs-lookup"><span data-stu-id="c90a7-117">To see an example of how you can synchronize a work order between Field Service and Finance and Operations, watch the short YouTube video:</span></span>

> [!Video https://www.youtube.com/embed/hAB4TDVMjxU]

[<span data-ttu-id="c90a7-118">Synkronisera en arbetsorder mellan Field Service och Finance and Operations (YouTube video)</span><span class="sxs-lookup"><span data-stu-id="c90a7-118">Synchronize a work order between Field Service and Finance and Operations (YouTube video)</span></span>](https://youtu.be/hAB4TDVMjxU)

## <a name="system-requirements-for-finance-and-operations"></a><span data-ttu-id="c90a7-119">Systemkrav för Finance and Operations</span><span class="sxs-lookup"><span data-stu-id="c90a7-119">System requirements for Finance and Operations</span></span>
<span data-ttu-id="c90a7-120">Field Service-integration stöder följande versioner:</span><span class="sxs-lookup"><span data-stu-id="c90a7-120">Field Service integration supports the following versions:</span></span>

### <a name="dynamics-365-for-finance-and-operations-version-80-april-2018-or-later"></a><span data-ttu-id="c90a7-121">Dynamics 365 for Finance and Operations version 8.0 (april 2018) eller senare</span><span class="sxs-lookup"><span data-stu-id="c90a7-121">Dynamics 365 for Finance and Operations version 8.0 (April 2018) or later</span></span>

- <span data-ttu-id="c90a7-122">Dynamics 365 for Finance and Operations version 8.0 (april 2018) gavs ut i april 2018 och har programversionsnummer 8.0.30.8020 med plattformsuppdatering 15 (7.0.4841.35234).</span><span class="sxs-lookup"><span data-stu-id="c90a7-122">Dynamics 365 for Finance and Operations version 8.0 (April 2018) was released in April 2018 and has an application build number 8.0.30.8020 with Platform Update 15 (7.0.4841.35234).</span></span> 

## <a name="system-requirements-for-field-service"></a><span data-ttu-id="c90a7-123">Systemkrav för Field Service</span><span class="sxs-lookup"><span data-stu-id="c90a7-123">System requirements for Field Service</span></span>
<span data-ttu-id="c90a7-124">Om du vill använda integrationslösningen för Field Service måste du installera följande komponenter:</span><span class="sxs-lookup"><span data-stu-id="c90a7-124">To use the Field Service integration solution, you must install the following components:</span></span>

### <a name="microsoft-dynamics-365-for-field-service-90-or-later"></a><span data-ttu-id="c90a7-125">Microsoft Dynamics 365 for Field Service 9.0 eller senare</span><span class="sxs-lookup"><span data-stu-id="c90a7-125">Microsoft Dynamics 365 for Field Service 9.0 or later</span></span>

- <span data-ttu-id="c90a7-126">Dynamics 365 for Field Service, version 1612 (9.0.1.733) (DB 9.0.1.733) online eller en senare version.</span><span class="sxs-lookup"><span data-stu-id="c90a7-126">Dynamics 365 for Field Service version 1612 (9.0.1.733) (DB 9.0.1.733) online or a later version.</span></span>
- <span data-ttu-id="c90a7-127">Lösningen Potentiell kund till kontanter (P2C) för Dynamics 365, version 1.15.0.1 eller senare.</span><span class="sxs-lookup"><span data-stu-id="c90a7-127">Prospect to Cash (P2C) solution for Dynamics 365, version 1.15.0.1 or a later version.</span></span> <span data-ttu-id="c90a7-128">Lösningen finns att hämta från [AppSource](https://appsource.microsoft.com/en-us/product/dynamics-365/mscrm.c7a48b40-eed3-4d67-93ba-f2364281feb3).</span><span class="sxs-lookup"><span data-stu-id="c90a7-128">The solution is available for download from [AppSource](https://appsource.microsoft.com/en-us/product/dynamics-365/mscrm.c7a48b40-eed3-4d67-93ba-f2364281feb3).</span></span>
- <span data-ttu-id="c90a7-129">Integrationslösningen för Field Service för Dynamics 365, version 1.0.0.0 eller en senare version.</span><span class="sxs-lookup"><span data-stu-id="c90a7-129">Field Service integration solution for Dynamics 365, version 1.0.0.0 or a later version.</span></span> <span data-ttu-id="c90a7-130">Lösningen finns att hämta från [AppSource](https://appsource.microsoft.com/en-us/product/dynamics-365/mscrm.p2cfieldserviceintegration).</span><span class="sxs-lookup"><span data-stu-id="c90a7-130">The solution is available for download from [AppSource](https://appsource.microsoft.com/en-us/product/dynamics-365/mscrm.p2cfieldserviceintegration).</span></span>

