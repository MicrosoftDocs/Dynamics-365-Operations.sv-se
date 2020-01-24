---
title: Dataintegrering nästan i realtid med Common Data Service
description: Det här avsnittet ger en översikt över integreringen av produktinformation mellan Finance and Operations-appar och Common Data Service.
author: RamaKrishnamoorthy
manager: AnnBe
ms.date: 07/15/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User, IT Pro
ms.reviewer: rhaertle
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: 072564446b74318ffc8e8e6ad4fd16f4421e7854
ms.sourcegitcommit: d0322d1ed6c798301058e44dae76227a0e1f49ac
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/26/2019
ms.locfileid: "2853916"
---
# <a name="near-real-time-data-integration-with-common-data-service"></a><span data-ttu-id="33852-103">Dataintegrering nästan i realtid med Common Data Service</span><span class="sxs-lookup"><span data-stu-id="33852-103">Near-real-time data integration with Common Data Service</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="33852-104">I den nuvarande digitala världen använder företags ekosystem Microsoft Dynamics 365-appar som helhet.</span><span class="sxs-lookup"><span data-stu-id="33852-104">In the current digital world, business ecosystems use Microsoft Dynamics 365 applications as a whole.</span></span> <span data-ttu-id="33852-105">Eftersom data från personer, kunder, åtgärder och sakernas Internet (IoT)-enheter flödar till en källa finns det en möjlighet för digitala feedbackloopar.</span><span class="sxs-lookup"><span data-stu-id="33852-105">Because data from people, customers, operations, and Internet of Things (IoT) devices flows into one source, there is an opportunity for digital feedback loops.</span></span> <span data-ttu-id="33852-106">För att uppnå den här upplevelsen är integration mellan Finance and Operations-appar och andra Dynamics 365-program viktigt.</span><span class="sxs-lookup"><span data-stu-id="33852-106">To achieve this experience, integration between Finance and Operations apps and other Dynamics 365 applications is essential.</span></span> <span data-ttu-id="33852-107">Vissa appar byggs ovanpå Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="33852-107">Some applications are built on top of Common Data Service.</span></span> <span data-ttu-id="33852-108">Integrering mellan Finance and Operations-appdata med Common Data Service låter andra program kommunicera konsekvent och flytande med Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="33852-108">Integration between Finance and Operations apps data with Common Data Service lets other applications communicate coherently and fluently with Finance and Operations.</span></span>

<span data-ttu-id="33852-109">Finance and Operations-appar och Common Data Service tillhandahåller datasynkronisering nästan i realtid mellan Finance and Operations-appar och andra Dynamics 365-program via ett ramverk med dubbelriktad skrivning.</span><span class="sxs-lookup"><span data-stu-id="33852-109">Finance and Operations apps and Common Data Service provide near-real-time data synchronization between Finance and Operations apps and other Dynamics 365 applications via a dual-write framework.</span></span> <span data-ttu-id="33852-110">Täckningen är bred och spänner över 28 ytområden av appen.</span><span class="sxs-lookup"><span data-stu-id="33852-110">The coverage is broad and spans 28 surface areas of the application.</span></span> <span data-ttu-id="33852-111">Målet är att ge användarupplevelsen "en Dynamics 365" genom sömlösa dataflöden som kopplar samman affärsprocesser mellan olika program.</span><span class="sxs-lookup"><span data-stu-id="33852-111">The goal is to provide a "One Dynamics 365" user experience through seamless data flows that connect business processes across applications.</span></span>

![Diagram över arkitekturöversikt](media/dual-write-overview.jpg)

<span data-ttu-id="33852-113">Följande värdepropositioner är tillgängliga:</span><span class="sxs-lookup"><span data-stu-id="33852-113">The following value propositions are available:</span></span>

+ [<span data-ttu-id="33852-114">Organisationshierarki i Common Data Service</span><span class="sxs-lookup"><span data-stu-id="33852-114">Organization hierarchy in Common Data Service</span></span>](dual-write-organization.md)
+ [<span data-ttu-id="33852-115">Företagskoncept i Common Data Service</span><span class="sxs-lookup"><span data-stu-id="33852-115">Company concept in Common Data Service</span></span>](dual-write-company.md)
+ [<span data-ttu-id="33852-116">Integrerat kundhuvud</span><span class="sxs-lookup"><span data-stu-id="33852-116">Integrated customer master</span></span>](dual-write-customer.md)
+ [<span data-ttu-id="33852-117">Integrerad redovisning</span><span class="sxs-lookup"><span data-stu-id="33852-117">Integrated ledger</span></span>](dual-write-ledger.md)
+ [<span data-ttu-id="33852-118">Enhetlig produktupplevelse</span><span class="sxs-lookup"><span data-stu-id="33852-118">Unified product experience</span></span>](dual-write-product.md)
+ [<span data-ttu-id="33852-119">Integrerat leverantörshuvud</span><span class="sxs-lookup"><span data-stu-id="33852-119">Integrated vendor master</span></span>](dual-write-vendor.md)
+ [<span data-ttu-id="33852-120">Integrerade platser och lagerställen</span><span class="sxs-lookup"><span data-stu-id="33852-120">Integrated sites and warehouses</span></span>](dual-write-sites-and-warehouses.md)
+ [<span data-ttu-id="33852-121">Integrerad huvudskatt</span><span class="sxs-lookup"><span data-stu-id="33852-121">Integrated tax master</span></span>](dual-write-tax.md)

## <a name="system-requirements"></a><span data-ttu-id="33852-122">Systemkrav</span><span class="sxs-lookup"><span data-stu-id="33852-122">System requirements</span></span>

<span data-ttu-id="33852-123">Synkrona, dubbelriktad, dataflöden nästan i realtid kräver följande versioner:</span><span class="sxs-lookup"><span data-stu-id="33852-123">Synchronous, bidirectional, near-real-time data flows require the following versions:</span></span>

+ <span data-ttu-id="33852-124">Microsoft Dynamics 365 for Finance and Operations version 10.0.4 (juli 2019) med plattformsuppdatering 28 eller senare</span><span class="sxs-lookup"><span data-stu-id="33852-124">Microsoft Dynamics 365 for Finance and Operations version 10.0.4 (July 2019) with Platform update 28, or later</span></span>
+ <span data-ttu-id="33852-125">Microsoft Dynamics 365 for Customer Engagement, plattform version 9.1 (4.2) eller senare</span><span class="sxs-lookup"><span data-stu-id="33852-125">Microsoft Dynamics 365 for Customer Engagement, Platform version 9.1 (4.2) or later</span></span>

## <a name="setup-instructions"></a><span data-ttu-id="33852-126">Installationsanvisningar</span><span class="sxs-lookup"><span data-stu-id="33852-126">Setup instructions</span></span>

<span data-ttu-id="33852-127">Följ dessa steg för att ställa in integrationen mellan med Finance and Operations-appar och Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="33852-127">Follow these steps to set up integration between Finance and Operations apps and Common Data Service.</span></span>
    
1. <span data-ttu-id="33852-128">För installationen av dubbelriktad skrivningssystemet, se [stegvis guiden](https://aka.ms/dualwrite-docs) om att tillkännage förhandsgranskning av dubbelriktad skrivning.</span><span class="sxs-lookup"><span data-stu-id="33852-128">For the setup of the dual-write system, see the [step-by-step guide](https://aka.ms/dualwrite-docs) on Announcing Dual Write Preview.</span></span>
2. <span data-ttu-id="33852-129">Ladda ned och installera lösningen från [Fin Ops och CD/CE-integration via dubbelriktad](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=66052096)Yammer-gruppen.</span><span class="sxs-lookup"><span data-stu-id="33852-129">Download and install the solution from the [Fin Ops and CDS/CE Integration via Dual-Write](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=66052096) Yammer group.</span></span> <span data-ttu-id="33852-130">Paketet innehåller fem lösningar:</span><span class="sxs-lookup"><span data-stu-id="33852-130">The package contains five solutions:</span></span>

    + <span data-ttu-id="33852-131">Dynamics365Company</span><span class="sxs-lookup"><span data-stu-id="33852-131">Dynamics365Company</span></span>
    + <span data-ttu-id="33852-132">CurrencyExchangeRates</span><span class="sxs-lookup"><span data-stu-id="33852-132">CurrencyExchangeRates</span></span>
    + <span data-ttu-id="33852-133">Dynamics365FinanceAndOperationsCommon</span><span class="sxs-lookup"><span data-stu-id="33852-133">Dynamics365FinanceAndOperationsCommon</span></span>
    + <span data-ttu-id="33852-134">Dynamics365FinanceCommon</span><span class="sxs-lookup"><span data-stu-id="33852-134">Dynamics365FinanceCommon</span></span>
    + <span data-ttu-id="33852-135">Dynamics365SupplyChainCommon</span><span class="sxs-lookup"><span data-stu-id="33852-135">Dynamics365SupplyChainCommon</span></span>

3. <span data-ttu-id="33852-136">Följ körningsordningen för att [synkronisera inledande referensdata](dual-write-initial.md).</span><span class="sxs-lookup"><span data-stu-id="33852-136">Follow the execution order for [synchronizing initial reference data](dual-write-initial.md).</span></span>
4. <span data-ttu-id="33852-137">Om du stöter på problem med synkronisering av dubbelriktad skrivning, se [felsökningsguiden för felsökningsguiden](dual-write-troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="33852-137">If you encounter dual-write synchronization issues, see the [Troubleshooting guide for data integration](dual-write-troubleshooting.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="33852-138">Du kan inte köra dubbelriktad skrivning och [potentiell kund till kontanter](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/accounts-template-mapping-direct) sida vid sida.</span><span class="sxs-lookup"><span data-stu-id="33852-138">You can’t run dual-write and [Prospect to cash](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/accounts-template-mapping-direct) side-by-side.</span></span> <span data-ttu-id="33852-139">Om du kör lösningen potentiell kund till kontanter måste du avinstallera den.</span><span class="sxs-lookup"><span data-stu-id="33852-139">If you're running the Prospect to cash solution, you must uninstall it.</span></span> <span data-ttu-id="33852-140">Du måste också inaktivera de mallar för dubbelriktad skrivning som ingår i lösningen potentiell kund till kontanter.</span><span class="sxs-lookup"><span data-stu-id="33852-140">You must also disable the customer and vendor dual-write templates that are part of the Prospect to cash solution.</span></span>
