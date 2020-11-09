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
ms.custom: ''
ms.assetid: ''
ms.search.region: global
ms.search.industry: ''
ms.author: ramasri
ms.dyn365.ops.version: ''
ms.search.validFrom: 2019-07-15
ms.openlocfilehash: f502519ba419cb8fa322eb1d22f06d2b805f5f05
ms.sourcegitcommit: afc43699c0edc4ff2be310cb37add2ab586b64c0
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/14/2020
ms.locfileid: "4000744"
---
# <a name="organization-hierarchy-in-common-data-service"></a><span data-ttu-id="90ee4-103">Organisationshierarki i Common Data Service</span><span class="sxs-lookup"><span data-stu-id="90ee4-103">Organization hierarchy in Common Data Service</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="90ee4-104">Eftersom Dynamics 365 Finance är ett finansiellt system är *organisation* ett grundläggande begrepp och systeminställningarna börjar med konfigurationen av en organisationshierarki.</span><span class="sxs-lookup"><span data-stu-id="90ee4-104">Because Dynamics 365 Finance is a financial system, *organization* is a core concept, and system setup starts with the configuration of an organization hierarchy.</span></span> <span data-ttu-id="90ee4-105">Affärsekonomi kan sedan spåras på organisationsnivå och även på alla nivåer i organisationshierarkin.</span><span class="sxs-lookup"><span data-stu-id="90ee4-105">Business financials can then be tracked at the organization level and also at any level in the organization hierarchy.</span></span>

<span data-ttu-id="90ee4-106">Även om Common Data Service inte har begreppet av en organisationshierarki, har den några lösa begrepp, till exempel totala försäljningsintäkter.</span><span class="sxs-lookup"><span data-stu-id="90ee4-106">Although Common Data Service doesn't have the concept of an organization hierarchy, it does have a few loose concepts, such as total sales revenue.</span></span> <span data-ttu-id="90ee4-107">Som en del av Common Data Service-integrationen läggs organisationshierarkins datastruktur till i Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="90ee4-107">As part of Common Data Service integration, the organization hierarchy data structure is added to Common Data Service.</span></span>

## <a name="data-flow"></a><span data-ttu-id="90ee4-108">Dataflöde</span><span class="sxs-lookup"><span data-stu-id="90ee4-108">Data flow</span></span>

<span data-ttu-id="90ee4-109">Ett affärsekosystem som består av Finance and Operations-appar och Common Data Service kommer att fortsätta att ha en organisationshierarki.</span><span class="sxs-lookup"><span data-stu-id="90ee4-109">A business ecosystem that consists of Finance and Operations apps and Common Data Service will continue to have an organization hierarchy.</span></span> <span data-ttu-id="90ee4-110">Organisationshierarkin bygger på Finance and Operations-appar, men den exponeras i Common Data Service för information och utbyggbarhet.</span><span class="sxs-lookup"><span data-stu-id="90ee4-110">This organization hierarchy is built on Finance and Operations apps, but it's exposed in Common Data Service for informational and extensibility purposes.</span></span> <span data-ttu-id="90ee4-111">Följande illustration visar organisationshierarkiinformation som exponeras i Common Data Service som ett enkelriktat dataflöde från Finance and Operations-appar till Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="90ee4-111">The following illustration shows the organization hierarchy information that is exposed in Common Data Service as a one-way data flow from Finance and Operations apps to Common Data Service.</span></span>

![Arkitekturbild](media/dual-write-data-flow.png)

<span data-ttu-id="90ee4-113">Organisationshierarkin entitetskartor är tillgängliga för enkelriktad synkronisering av data från Finance and Operations-appar till Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="90ee4-113">Organization hierarchy entity maps are available for one-way synchronization of data from Finance and Operations apps to Common Data Service.</span></span>

## <a name="templates"></a><span data-ttu-id="90ee4-114">Mallar</span><span class="sxs-lookup"><span data-stu-id="90ee4-114">Templates</span></span>

<span data-ttu-id="90ee4-115">Produktinformationen innehåller all information som är relaterad till produkten och dess definition, t.ex. produktdimensioner eller spårnings- och lagringsdimensioner.</span><span class="sxs-lookup"><span data-stu-id="90ee4-115">Product information contains all the information related to the product and its definition, such as the product dimensions or the tracking and storage dimensions.</span></span> <span data-ttu-id="90ee4-116">Som framgår av följande tabell skapas en samling med enhetsmappningar för synkronisering av produkter och relaterad information.</span><span class="sxs-lookup"><span data-stu-id="90ee4-116">As the following table shows, a collection of entity maps is created to sync products and related information.</span></span>

<span data-ttu-id="90ee4-117">Finance and Operations-appar</span><span class="sxs-lookup"><span data-stu-id="90ee4-117">Finance and Operations apps</span></span> | <span data-ttu-id="90ee4-118">Andra Dynamics 365-appar</span><span class="sxs-lookup"><span data-stu-id="90ee4-118">Other Dynamics 365 apps</span></span> | <span data-ttu-id="90ee4-119">beskrivning</span><span class="sxs-lookup"><span data-stu-id="90ee4-119">Description</span></span>
-----------------------|--------------------------------|---
<span data-ttu-id="90ee4-120">Syften för organisationshierarki</span><span class="sxs-lookup"><span data-stu-id="90ee4-120">Organization hierarchy purposes</span></span> | <span data-ttu-id="90ee4-121">msdyn_internalorganizationhierarchypurposes</span><span class="sxs-lookup"><span data-stu-id="90ee4-121">msdyn_internalorganizationhierarchypurposes</span></span> | <span data-ttu-id="90ee4-122">Den här mallen innehåller en enkelriktad synkronisering av entiteten syfte för organisationshierarki.</span><span class="sxs-lookup"><span data-stu-id="90ee4-122">This template provides one-way synchronization of the Organization Hierarchy Purpose entity.</span></span>
<span data-ttu-id="90ee4-123">Typ av organisationshierarki</span><span class="sxs-lookup"><span data-stu-id="90ee4-123">Organization hierarchy type</span></span> | <span data-ttu-id="90ee4-124">msdyn_internalorganizationhierarchytypes</span><span class="sxs-lookup"><span data-stu-id="90ee4-124">msdyn_internalorganizationhierarchytypes</span></span> | <span data-ttu-id="90ee4-125">Den här mallen innehåller en enkelriktad synkronisering av entiteten typ för organisationshierarki.</span><span class="sxs-lookup"><span data-stu-id="90ee4-125">This template provides one-way synchronization of the Organization Hierarchy Type entity.</span></span>
<span data-ttu-id="90ee4-126">Organisationshierarki - publicerad</span><span class="sxs-lookup"><span data-stu-id="90ee4-126">Organization hierarchy - published</span></span> | <span data-ttu-id="90ee4-127">msdyn_internalorganizationhierarchies</span><span class="sxs-lookup"><span data-stu-id="90ee4-127">msdyn_internalorganizationhierarchies</span></span> | <span data-ttu-id="90ee4-128">Den här mallen innehåller en enkelriktad synkronisering av entiteten publicerad för organisationshierarki.</span><span class="sxs-lookup"><span data-stu-id="90ee4-128">This template provides one-way synchronization of the Organization Hierarchy Published entity.</span></span>
<span data-ttu-id="90ee4-129">Driftenhet</span><span class="sxs-lookup"><span data-stu-id="90ee4-129">Operating unit</span></span> | <span data-ttu-id="90ee4-130">msdyn_internalorganizations</span><span class="sxs-lookup"><span data-stu-id="90ee4-130">msdyn_internalorganizations</span></span> |
<span data-ttu-id="90ee4-131">Juridiska personer</span><span class="sxs-lookup"><span data-stu-id="90ee4-131">Legal entities</span></span> | <span data-ttu-id="90ee4-132">msdyn_internalorganizations</span><span class="sxs-lookup"><span data-stu-id="90ee4-132">msdyn_internalorganizations</span></span> |
<span data-ttu-id="90ee4-133">Juridiska personer</span><span class="sxs-lookup"><span data-stu-id="90ee4-133">Legal entities</span></span> | <span data-ttu-id="90ee4-134">cdm_companies</span><span class="sxs-lookup"><span data-stu-id="90ee4-134">cdm_companies</span></span> | <span data-ttu-id="90ee4-135">Tillhandahåller dubbelriktad synkronisering av information om den juridiska personen (företag).</span><span class="sxs-lookup"><span data-stu-id="90ee4-135">Provides bidirectional synchronization of legal entity (company) information.</span></span>

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Organization hierarchy purposes](includes/OrganizationHierarchyPurpose-msdyn-internalorganizationhierarchypurposes.md)]

[!include [Organization hierarchy type](includes/OrganizationHierarchyType-msdyn-internalorganizationhierarchytypes.md)]

[!include [Organization hierarchy - published](includes/OrganizationHierarchyPublished-msdyn-internalorganizationhierarchies.md)]

## <a name="internal-organization"></a><span data-ttu-id="90ee4-136">Intern organisation</span><span class="sxs-lookup"><span data-stu-id="90ee4-136">Internal Organization</span></span>

<span data-ttu-id="90ee4-137">Intern organisationsinformation i Common Data Service kommer från två entiteter **driftenhet** och **juridiska personer**.</span><span class="sxs-lookup"><span data-stu-id="90ee4-137">Internal organization information in Common Data Service comes from two entities, **operating unit** and **legal entities**.</span></span>

[!include [Operating unit](includes/OperatingUnit-msdyn-internalorganizations.md)]

[!include [Legal entities](includes/LegalEntities-msdyn-internalorganizations.md)]

[!include [Legal entities](includes/LegalEntities-Companies.md)]
