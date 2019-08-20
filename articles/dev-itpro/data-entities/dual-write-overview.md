---
title: Dataintegrering nästan i realtid mellan Finance and Operations och Common Data Service.
description: Det här ämnet innehåller en översikt över integrering mellan Microsoft Dynamics 365 for Finance and Operations och Common Data Service .
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
ms.openlocfilehash: aa614c8e6a79a3f7a4f8f2f99f1f1bd1a67ac921
ms.sourcegitcommit: efcc0dee8bde5f8f93f6291e7f059ad426843e57
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/31/2019
ms.locfileid: "1797238"
---
# <a name="near-real-time-data-integration-between-finance-and-operations-and-common-data-service"></a><span data-ttu-id="ff763-103">Dataintegrering nästan i realtid mellan Finance and Operations och Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="ff763-103">Near-real-time data integration between Finance and Operations and Common Data Service</span></span>

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

<span data-ttu-id="ff763-104">I den nuvarande digitala världen använder företags ekosystem Microsoft Dynamics 365-sviten som helhet.</span><span class="sxs-lookup"><span data-stu-id="ff763-104">In the current digital world, business ecosystems use the Microsoft Dynamics 365 suite as a whole.</span></span> <span data-ttu-id="ff763-105">Eftersom data från personer, kunder, åtgärder och sakernas Internet (IoT)-enheter flödar till en källa finns det en möjlighet för digitala feedbackloopar.</span><span class="sxs-lookup"><span data-stu-id="ff763-105">Because data from people, customers, operations, and Internet of Things (IoT) devices flows into one source, there is an opportunity for digital feedback loops.</span></span> <span data-ttu-id="ff763-106">För att uppnå den här upplevelsen är integration mellan Dynamics 365 for Finance and Operations och Dynamics 365 for Customer Engagement-program viktigt.</span><span class="sxs-lookup"><span data-stu-id="ff763-106">To achieve this experience, integration between Dynamics 365 for Finance and Operations and Dynamics 365 for Customer Engagement applications is essential.</span></span> <span data-ttu-id="ff763-107">Customer Engagement-program byggs ovanpå Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="ff763-107">Customer Engagement applications are built on top of Common Data Service.</span></span> <span data-ttu-id="ff763-108">Integrering mellan Finance and Operations-data med Common Data Service låter Customer Engagement-program kommunicera konsekvent och flytande med Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ff763-108">Integration between Finance and Operations data with Common Data Service lets Customer Engagement applications communicate coherently and fluently with Finance and Operations.</span></span>

<span data-ttu-id="ff763-109">Finance and Operations och Common Data Service tillhandahåller datasynkronisering nästan i realtid mellan Finance and Operations och Customer Engagement-program via ett ramverk med dubbelriktad skrivning.</span><span class="sxs-lookup"><span data-stu-id="ff763-109">Finance and Operations and Common Data Service provide near-real-time data synchronization between Finance and Operations and Customer Engagement applications via a dual-write framework.</span></span> <span data-ttu-id="ff763-110">Täckningen är bred och spänner över 28 ytområden av Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="ff763-110">The coverage is broad and spans 28 surface areas of Finance and Operations.</span></span> <span data-ttu-id="ff763-111">Målet är att ge användarupplevelsen "en Dynamics 365" genom sömlösa dataflöden som kopplar samman affärsprocesser mellan olika program.</span><span class="sxs-lookup"><span data-stu-id="ff763-111">The goal is to provide a "One Dynamics 365" user experience through seamless data flows that connect business processes across applications.</span></span>

![Diagram över arkitekturöversikt](media/dual-write-overview.jpg)

<span data-ttu-id="ff763-113">Följande värdepropositioner är tillgängliga för kunder:</span><span class="sxs-lookup"><span data-stu-id="ff763-113">The following value propositions are available for customers:</span></span>

+ [<span data-ttu-id="ff763-114">Organisationshierarki i Common Data Service</span><span class="sxs-lookup"><span data-stu-id="ff763-114">Organization hierarchy in Common Data Service</span></span>](dual-write-organization.md)
+ [<span data-ttu-id="ff763-115">Företagskoncept i Common Data Service</span><span class="sxs-lookup"><span data-stu-id="ff763-115">Company concept in Common Data Service</span></span>](dual-write-company.md)
+ [<span data-ttu-id="ff763-116">Integrerat kundhuvud</span><span class="sxs-lookup"><span data-stu-id="ff763-116">Integrated customer master</span></span>](dual-write-customer.md)
+ [<span data-ttu-id="ff763-117">Integrerat leverantörshuvud</span><span class="sxs-lookup"><span data-stu-id="ff763-117">Integrated vendor master</span></span>](dual-write-vendor.md)
+ <span data-ttu-id="ff763-118">Enhetlig produktmall</span><span class="sxs-lookup"><span data-stu-id="ff763-118">Unified product master</span></span>

## <a name="system-requirements"></a><span data-ttu-id="ff763-119">Systemkrav</span><span class="sxs-lookup"><span data-stu-id="ff763-119">System requirements</span></span>

<span data-ttu-id="ff763-120">Synkrona, dubbelriktad, dataflöden nästan i realtid kräver följande versioner:</span><span class="sxs-lookup"><span data-stu-id="ff763-120">Synchronous, bidirectional, near-real-time data flows require the following versions:</span></span>

+ <span data-ttu-id="ff763-121">Microsoft Dynamics 365 for Finance and Operations version 10.0.4 (juli 2019) med plattformsuppdatering 28 eller senare</span><span class="sxs-lookup"><span data-stu-id="ff763-121">Microsoft Dynamics 365 for Finance and Operations version 10.0.4 (July 2019) with Platform update 28, or later</span></span>
+ <span data-ttu-id="ff763-122">Microsoft Dynamics 365 for Customer Engagement, plattform version 9.1 (4.2) eller senare</span><span class="sxs-lookup"><span data-stu-id="ff763-122">Microsoft Dynamics 365 for Customer Engagement, Platform version 9.1 (4.2) or later</span></span>

## <a name="setup-instructions"></a><span data-ttu-id="ff763-123">Installationsanvisningar</span><span class="sxs-lookup"><span data-stu-id="ff763-123">Setup instructions</span></span>

<span data-ttu-id="ff763-124">Följ dessa steg för att ställa in integrationen mellan med Finance and Operations och Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="ff763-124">Follow these steps to set up integration between Finance and Operations and Common Data Service.</span></span>
    
1. <span data-ttu-id="ff763-125">För installationen av dubbelriktad skrivningssystemet, se [stegvis guiden](https://aka.ms/dualwrite-docs) om att tillkännage förhandsgranskning av dubbelriktad skrivning.</span><span class="sxs-lookup"><span data-stu-id="ff763-125">For the setup of the dual-write system, see the [step-by-step guide](https://aka.ms/dualwrite-docs) on Announcing Dual Write Preview.</span></span>
2. <span data-ttu-id="ff763-126">Hämta och installera lösningen från gruppen [Finance and Operations, Common Data Service, och Customer Engagement-iIntegration](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=66052096) Yammer.</span><span class="sxs-lookup"><span data-stu-id="ff763-126">Download and install the solution from the [Finance and Operations, Common Data Service, and Customer Engagement Integration](https://www.yammer.com/dynamicsaxfeedbackprograms/#/threads/inGroup?type=in_group&feedId=66052096) Yammer group.</span></span> <span data-ttu-id="ff763-127">Paketet innehåller fem lösningar:</span><span class="sxs-lookup"><span data-stu-id="ff763-127">The package contains five solutions:</span></span>

    + <span data-ttu-id="ff763-128">Dynamics365Company</span><span class="sxs-lookup"><span data-stu-id="ff763-128">Dynamics365Company</span></span>
    + <span data-ttu-id="ff763-129">CurrencyExchangeRates</span><span class="sxs-lookup"><span data-stu-id="ff763-129">CurrencyExchangeRates</span></span>
    + <span data-ttu-id="ff763-130">Dynamics365FinanceAndOperationsCommon</span><span class="sxs-lookup"><span data-stu-id="ff763-130">Dynamics365FinanceAndOperationsCommon</span></span>
    + <span data-ttu-id="ff763-131">Dynamics365FinanceCommon</span><span class="sxs-lookup"><span data-stu-id="ff763-131">Dynamics365FinanceCommon</span></span>
    + <span data-ttu-id="ff763-132">Dynamics365SupplyChainCommon</span><span class="sxs-lookup"><span data-stu-id="ff763-132">Dynamics365SupplyChainCommon</span></span>

3. <span data-ttu-id="ff763-133">Följ körningsordningen för att [synkronisera inledande referensdata](dual-write-initial.md).</span><span class="sxs-lookup"><span data-stu-id="ff763-133">Follow the execution order for [synchronizing initial reference data](dual-write-initial.md).</span></span>
4. <span data-ttu-id="ff763-134">Om du stöter på problem med synkronisering av dubbelriktad skrivning, se [felsökningsguiden för felsökningsguiden](dual-write-troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="ff763-134">If you encounter dual-write synchronization issues, see the [Troubleshooting guide for data integration](dual-write-troubleshooting.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ff763-135">Du kan inte köra dubbelriktad skrivning och [potentiell kund till kontanter](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/accounts-template-mapping-direct) sida vid sida.</span><span class="sxs-lookup"><span data-stu-id="ff763-135">You can’t run dual-write and [Prospect to cash](https://docs.microsoft.com/dynamics365/unified-operations/supply-chain/sales-marketing/accounts-template-mapping-direct) side-by-side.</span></span> <span data-ttu-id="ff763-136">Om du kör lösningen potentiell kund till kontanter måste du avinstallera den.</span><span class="sxs-lookup"><span data-stu-id="ff763-136">If you're running the Prospect to cash solution, you must uninstall it.</span></span> <span data-ttu-id="ff763-137">Du måste också inaktivera de mallar för dubbelriktad skrivning som ingår i lösningen potentiell kund till kontanter.</span><span class="sxs-lookup"><span data-stu-id="ff763-137">You must also disable the customer and vendor dual-write templates that are part of the Prospect to cash solution.</span></span>
