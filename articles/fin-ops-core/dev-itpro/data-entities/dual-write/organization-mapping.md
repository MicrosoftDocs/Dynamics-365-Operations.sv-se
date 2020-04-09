---
title: Organisationshierarki i Common Data Service
description: I det här avsnittet beskrivs integreringen av organisationsinformation mellan Finance and Operations-appar och Common Data Service.
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
ms.openlocfilehash: fc5db8d04a2860df0c917816e2910c6fbda941ff
ms.sourcegitcommit: 68f1485de7d64a6c9eba1088af63bd07992d972d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/27/2020
ms.locfileid: "3173164"
---
# <a name="organization-hierarchy-in-common-data-service"></a><span data-ttu-id="9680a-103">Organisationshierarki i Common Data Service</span><span class="sxs-lookup"><span data-stu-id="9680a-103">Organization hierarchy in Common Data Service</span></span>

[!include [banner](../../includes/banner.md)]



<span data-ttu-id="9680a-104">Eftersom Dynamics 365 Finance är ett finansiellt system är *organisation* ett grundläggande begrepp och systeminställningarna börjar med konfigurationen av en organisationshierarki.</span><span class="sxs-lookup"><span data-stu-id="9680a-104">Because Dynamics 365 Finance is a financial system, *organization* is a core concept, and system setup starts with the configuration of an organization hierarchy.</span></span> <span data-ttu-id="9680a-105">Affärsekonomi kan sedan spåras på organisationsnivå och även på alla nivåer i organisationshierarkin.</span><span class="sxs-lookup"><span data-stu-id="9680a-105">Business financials can then be tracked at the organization level and also at any level in the organization hierarchy.</span></span>

<span data-ttu-id="9680a-106">Även om Common Data Service inte har begreppet av en organisationshierarki, har den några lösa begrepp, till exempel totala försäljningsintäkter.</span><span class="sxs-lookup"><span data-stu-id="9680a-106">Although Common Data Service doesn't have the concept of an organization hierarchy, it does have a few loose concepts, such as total sales revenue.</span></span> <span data-ttu-id="9680a-107">Som en del av Common Data Service-integrationen läggs organisationshierarkins datastruktur till i Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="9680a-107">As part of Common Data Service integration, the organization hierarchy data structure is added to Common Data Service.</span></span>

## <a name="data-flow"></a><span data-ttu-id="9680a-108">Dataflöde</span><span class="sxs-lookup"><span data-stu-id="9680a-108">Data flow</span></span>

<span data-ttu-id="9680a-109">Ett affärsekosystem som består av Finance and Operations-appar och Common Data Service kommer att fortsätta att ha en organisationshierarki.</span><span class="sxs-lookup"><span data-stu-id="9680a-109">A business ecosystem that consists of Finance and Operations apps and Common Data Service will continue to have an organization hierarchy.</span></span> <span data-ttu-id="9680a-110">Organisationshierarkin bygger på Finance and Operations-appar, men den exponeras i Common Data Service för information och utbyggbarhet.</span><span class="sxs-lookup"><span data-stu-id="9680a-110">This organization hierarchy is built on Finance and Operations apps, but it's exposed in Common Data Service for informational and extensibility purposes.</span></span> <span data-ttu-id="9680a-111">Följande illustration visar organisationshierarkiinformation som exponeras i Common Data Service som ett enkelriktat dataflöde från Finance and Operations-appar till Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="9680a-111">The following illustration shows the organization hierarchy information that is exposed in Common Data Service as a one-way data flow from Finance and Operations apps to Common Data Service.</span></span>

![Arkitekturbild](media/dual-write-data-flow.png)

## <a name="templates"></a><span data-ttu-id="9680a-113">Mallar</span><span class="sxs-lookup"><span data-stu-id="9680a-113">Templates</span></span>

<span data-ttu-id="9680a-114">Organisationshierarkin entitetskartor är tillgängliga för enkelriktad synkronisering av data från Finance and Operations-appar till Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="9680a-114">Organization hierarchy entity maps are available for one-way synchronization of data from Finance and Operations apps to Common Data Service.</span></span>

## <a name="templates"></a><span data-ttu-id="9680a-115">Mallar</span><span class="sxs-lookup"><span data-stu-id="9680a-115">Templates</span></span>

<span data-ttu-id="9680a-116">Produktinformationen innehåller all information som är relaterad till produkten och dess definition, t.ex. produktdimensioner eller spårnings- och lagringsdimensioner.</span><span class="sxs-lookup"><span data-stu-id="9680a-116">Product information contains all the information related to the product and its definition, such as the product dimensions or the tracking and storage dimensions.</span></span> <span data-ttu-id="9680a-117">Som framgår av följande tabell skapas en samling med enhetsmappningar för synkronisering av produkter och relaterad information.</span><span class="sxs-lookup"><span data-stu-id="9680a-117">As the following table shows, a collection of entity maps is created to sync products and related information.</span></span>

<span data-ttu-id="9680a-118">Finance and Operations-appar</span><span class="sxs-lookup"><span data-stu-id="9680a-118">Finance and Operations apps</span></span> | <span data-ttu-id="9680a-119">Andra Dynamics 365-appar</span><span class="sxs-lookup"><span data-stu-id="9680a-119">Other Dynamics 365 apps</span></span> | <span data-ttu-id="9680a-120">beskrivning</span><span class="sxs-lookup"><span data-stu-id="9680a-120">Description</span></span>
-----------------------|--------------------------------|---
<span data-ttu-id="9680a-121">Syften för organisationshierarki</span><span class="sxs-lookup"><span data-stu-id="9680a-121">Organization hierarchy purposes</span></span> | <span data-ttu-id="9680a-122">msdyn_internalorganizationhierarchypurposes</span><span class="sxs-lookup"><span data-stu-id="9680a-122">msdyn_internalorganizationhierarchypurposes</span></span> | <span data-ttu-id="9680a-123">Den här mallen innehåller en enkelriktad synkronisering av entiteten syfte för organisationshierarki.</span><span class="sxs-lookup"><span data-stu-id="9680a-123">This template provides one-way synchronization of the Organization Hierarchy Purpose entity.</span></span>
<span data-ttu-id="9680a-124">Typ av organisationshierarki</span><span class="sxs-lookup"><span data-stu-id="9680a-124">Organization hierarchy type</span></span> | <span data-ttu-id="9680a-125">msdyn_internalorganizationhierarchytypes</span><span class="sxs-lookup"><span data-stu-id="9680a-125">msdyn_internalorganizationhierarchytypes</span></span> | <span data-ttu-id="9680a-126">Den här mallen innehåller en enkelriktad synkronisering av entiteten typ för organisationshierarki.</span><span class="sxs-lookup"><span data-stu-id="9680a-126">This template provides one-way synchronization of the Organization Hierarchy Type entity.</span></span>
<span data-ttu-id="9680a-127">Organisationshierarki - publicerad</span><span class="sxs-lookup"><span data-stu-id="9680a-127">Organization hierarchy - published</span></span> | <span data-ttu-id="9680a-128">msdyn_internalorganizationhierarchies</span><span class="sxs-lookup"><span data-stu-id="9680a-128">msdyn_internalorganizationhierarchies</span></span> | <span data-ttu-id="9680a-129">Den här mallen innehåller en enkelriktad synkronisering av entiteten publicerad för organisationshierarki.</span><span class="sxs-lookup"><span data-stu-id="9680a-129">This template provides one-way synchronization of the Organization Hierarchy Published entity.</span></span>
<span data-ttu-id="9680a-130">Driftenhet</span><span class="sxs-lookup"><span data-stu-id="9680a-130">Operating unit</span></span> | <span data-ttu-id="9680a-131">msdyn_internalorganizations</span><span class="sxs-lookup"><span data-stu-id="9680a-131">msdyn_internalorganizations</span></span> | 
<span data-ttu-id="9680a-132">Juridiska personer</span><span class="sxs-lookup"><span data-stu-id="9680a-132">Legal entities</span></span> | <span data-ttu-id="9680a-133">msdyn_internalorganizations</span><span class="sxs-lookup"><span data-stu-id="9680a-133">msdyn_internalorganizations</span></span> | 
<span data-ttu-id="9680a-134">Juridiska personer</span><span class="sxs-lookup"><span data-stu-id="9680a-134">Legal entities</span></span> | <span data-ttu-id="9680a-135">cdm_companies</span><span class="sxs-lookup"><span data-stu-id="9680a-135">cdm_companies</span></span> | <span data-ttu-id="9680a-136">Tillhandahåller dubbelriktad synkronisering av information om den juridiska personen (företag).</span><span class="sxs-lookup"><span data-stu-id="9680a-136">Provides bidirectional synchronization of legal entity (company) information.</span></span>


[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Organization hierarchy purposes](includes/OrganizationHierarchyPurpose-msdyn-internalorganizationhierarchypurposes.md)]

[!include [Organization hierarchy type](includes/OrganizationHierarchyType-msdyn-internalorganizationhierarchytypes.md)]

[!include [Organization hierarchy - published](includes/OrganizationHierarchyPublished-msdyn-internalorganizationhierarchies.md)]

## <a name="internal-organization"></a><span data-ttu-id="9680a-137">Intern organisation</span><span class="sxs-lookup"><span data-stu-id="9680a-137">Internal Organization</span></span>

<span data-ttu-id="9680a-138">Intern organisationsinformation i Common Data Service kommer från två entiteter **driftenhet** och **juridiska personer**.</span><span class="sxs-lookup"><span data-stu-id="9680a-138">Internal organization information in Common Data Service comes from two entities, **operating unit** and **legal entities**.</span></span>

[!include [Operating unit](includes/OperatingUnit-msdyn-internalorganizations.md)]

[!include [Legal entities](includes/LegalEntities-msdyn-internalorganizations.md)]

[!include [Legal entities](includes/LegalEntities-Companies.md)]

