---
title: Globaliseringstjänster i Dynamics 365
description: Detta ämne ger en översikt över globaliseringstjänsterna i Microsoft Dynamics 365.
author: JaneA07
ms.date: 04/12/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: RCS, Regulatory Configuration Services, Localization, Electronic invoicing, Tax calculation
audience: Application User
ms.reviewer: kfend
ms.custom: 97423
ms.assetid: ''
ms.search.region: Global
ms.author: janeaug
ms.search.validFrom: 2020-02-01
ms.dyn365.ops.version: AX 10.0.9
ms.openlocfilehash: 2ef942f7f6dac2c321a51800ade0bf25f2162304
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6018817"
---
# <a name="dynamics-365-globalization-services"></a><span data-ttu-id="8e747-103">Globaliseringstjänster i Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="8e747-103">Dynamics 365 globalization services</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="8e747-104">Följande globaliseringstjänster kan konfigureras i syfte att utöka kapaciteten hos vissa Microsoft Dynamics 365-onlinetjänster:</span><span class="sxs-lookup"><span data-stu-id="8e747-104">The following globalization services can be configured to extend the capabilities that exist in some Microsoft Dynamics 365 online services:</span></span>

- <span data-ttu-id="8e747-105">**Regulatory Configuration Service (RCS)** stöder konfigurationen av olika typer av elektroniska dokument och rapporter.</span><span class="sxs-lookup"><span data-stu-id="8e747-105">**Regulatory Configuration Service (RCS)** supports the configuration of different types of electronic documents and reports.</span></span> <span data-ttu-id="8e747-106">RCS innehåller en förbättrad version av designern för elektronisk rapportering (ER) där konfigurationsdatabasen är en fristående tjänst.</span><span class="sxs-lookup"><span data-stu-id="8e747-106">RCS provides an enhanced version of the Electronic reporting (ER) designer where the configuration repository is a standalone service.</span></span> <span data-ttu-id="8e747-107">Mer information finns i [Regulatory Configuration Service](rcs-overview.md).</span><span class="sxs-lookup"><span data-stu-id="8e747-107">For more information, see [Regulatory Configuration Service](rcs-overview.md).</span></span>
- <span data-ttu-id="8e747-108">Vid **e-fakturering** samlas konfigurerbara format för omvandling, digitala signaturer och konfigurerbara integreringar för anslutning till externa webbtjänster, inklusive certifiering och svarshantering.</span><span class="sxs-lookup"><span data-stu-id="8e747-108">**Electronic Invoicing** brings together configurable formats for transformations, digital signatures, and configurable integrations for connectivity with external web services, including certification and response handling.</span></span> <span data-ttu-id="8e747-109">Mer information finns i [E-fakturering](e-invoicing-service-overview.md).</span><span class="sxs-lookup"><span data-stu-id="8e747-109">For more information, see [Electronic Invoicing](e-invoicing-service-overview.md).</span></span>
- <span data-ttu-id="8e747-110">**Skatteberäkning** ger ökad flexibilitet genom att stödja flera skatte-ID, bestämmande av skattekod, skatteberäkningsdesigner och en körtidsmotor för att följa komplexa skatteregler globalt.</span><span class="sxs-lookup"><span data-stu-id="8e747-110">**Tax Calculation** provides enhanced flexibility by supporting multiple tax IDs, tax code determination, the tax calculation designer, and a runtime engine to comply with complex tax regulations worldwide.</span></span> <span data-ttu-id="8e747-111">Mer information finns i [Skatteberäkning](global-tax-calcuation-service-overview.md).</span><span class="sxs-lookup"><span data-stu-id="8e747-111">For more information, see [Tax Calculation](global-tax-calcuation-service-overview.md).</span></span>

<span data-ttu-id="8e747-112">Dessa globaliseringstjänster tillhandahåller direktintegration med följande onlinetjänster i Dynamics 365:</span><span class="sxs-lookup"><span data-stu-id="8e747-112">These globalization services provide out-of-box integration with the following Dynamics 365 online services.</span></span>

| <span data-ttu-id="8e747-113">Onlinetjänster</span><span class="sxs-lookup"><span data-stu-id="8e747-113">Online service</span></span> | <span data-ttu-id="8e747-114">Lagstadgad konfigurationstjänst</span><span class="sxs-lookup"><span data-stu-id="8e747-114">RCS</span></span> | <span data-ttu-id="8e747-115">E-fakturering</span><span class="sxs-lookup"><span data-stu-id="8e747-115">Electronic Invoicing</span></span> | <span data-ttu-id="8e747-116">Skatteberäkning (förhandsversion)</span><span class="sxs-lookup"><span data-stu-id="8e747-116">Tax Calculation (Preview)</span></span> |
|----------------|-----|----------------------|---------------------------|
| <span data-ttu-id="8e747-117">Dynamics 365 Finance</span><span class="sxs-lookup"><span data-stu-id="8e747-117">Dynamics 365 Finance</span></span> | <span data-ttu-id="8e747-118">Ja</span><span class="sxs-lookup"><span data-stu-id="8e747-118">Yes</span></span> | <span data-ttu-id="8e747-119">Ja</span><span class="sxs-lookup"><span data-stu-id="8e747-119">Yes</span></span> | <span data-ttu-id="8e747-120">Ja</span><span class="sxs-lookup"><span data-stu-id="8e747-120">Yes</span></span> | 
| <span data-ttu-id="8e747-121">Dynamics 365 Supply Chain Management</span><span class="sxs-lookup"><span data-stu-id="8e747-121">Dynamics 365 Supply Chain Management</span></span> | <span data-ttu-id="8e747-122">Ja</span><span class="sxs-lookup"><span data-stu-id="8e747-122">Yes</span></span> | <span data-ttu-id="8e747-123">Ja</span><span class="sxs-lookup"><span data-stu-id="8e747-123">Yes</span></span> | <span data-ttu-id="8e747-124">Ja</span><span class="sxs-lookup"><span data-stu-id="8e747-124">Yes</span></span> | 
| <span data-ttu-id="8e747-125">Dynamics 365 Project Operations</span><span class="sxs-lookup"><span data-stu-id="8e747-125">Dynamics 365 Project Operations</span></span> | <span data-ttu-id="8e747-126">Ja</span><span class="sxs-lookup"><span data-stu-id="8e747-126">Yes</span></span> | <span data-ttu-id="8e747-127">Ja</span><span class="sxs-lookup"><span data-stu-id="8e747-127">Yes</span></span> | <span data-ttu-id="8e747-128">Inte aktuellt</span><span class="sxs-lookup"><span data-stu-id="8e747-128">Not applicable</span></span> | 
| <span data-ttu-id="8e747-129">Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="8e747-129">Dynamics 365 Commerce</span></span> | <span data-ttu-id="8e747-130">Ja</span><span class="sxs-lookup"><span data-stu-id="8e747-130">Yes</span></span> | <span data-ttu-id="8e747-131">Inte aktuellt</span><span class="sxs-lookup"><span data-stu-id="8e747-131">Not applicable</span></span> | <span data-ttu-id="8e747-132">Inte aktuellt</span><span class="sxs-lookup"><span data-stu-id="8e747-132">Not applicable</span></span> | 

> [!NOTE]
> <span data-ttu-id="8e747-133">På grund av skillnader i tillgängligheten för geografiska platser i Azure (geos) för RCS kan konfigurationen av den här tjänsten leda till att kunddata överförs utanför det område som valts för tillämplig Dynamics 365-onlinetjänst.</span><span class="sxs-lookup"><span data-stu-id="8e747-133">Because of differences in the availability of Azure geographic locations (geos) for RCS, configuration of this service might cause customer data to be transferred outside the geo that is selected for the applicable Dynamics 365 online service.</span></span> <span data-ttu-id="8e747-134">Mer information finns i [Dynamics 365 och Power Platform: Tillgänglighet, dataplats, språk och lokalisering](https://aka.ms/rcs/D365Productavailabilityguide).</span><span class="sxs-lookup"><span data-stu-id="8e747-134">For more information, see [Dynamics 365 and Power Platform: Availability, data location, language, and localization](https://aka.ms/rcs/D365Productavailabilityguide).</span></span>