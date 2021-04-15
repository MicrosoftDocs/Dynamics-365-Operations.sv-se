---
title: Organisationshierarki i Dataverse
description: I det här avsnittet beskrivs integreringen av organisationsinformation mellan Finance and Operations-appar och Dataverse.
author: RamaKrishnamoorthy
ms.date: 07/15/2019
ms.topic: article
ms.prod: ''
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
ms.openlocfilehash: 8b147c27b9309b1b3597f1194c415fbb2e2b7ad2
ms.sourcegitcommit: 074b6e212d19dd5d84881d1cdd096611a18c207f
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5750822"
---
# <a name="organization-hierarchy-in-dataverse"></a><span data-ttu-id="4f498-103">Organisationshierarki i Dataverse</span><span class="sxs-lookup"><span data-stu-id="4f498-103">Organization hierarchy in Dataverse</span></span>

[!include [banner](../../includes/banner.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

<span data-ttu-id="4f498-104">Eftersom Dynamics 365 Finance är ett finansiellt system är *organisation* ett grundläggande begrepp och systeminställningarna börjar med konfigurationen av en organisationshierarki.</span><span class="sxs-lookup"><span data-stu-id="4f498-104">Because Dynamics 365 Finance is a financial system, *organization* is a core concept, and system setup starts with the configuration of an organization hierarchy.</span></span> <span data-ttu-id="4f498-105">Affärsekonomi kan sedan spåras på organisationsnivå och även på alla nivåer i organisationshierarkin.</span><span class="sxs-lookup"><span data-stu-id="4f498-105">Business financials can then be tracked at the organization level and also at any level in the organization hierarchy.</span></span>

<span data-ttu-id="4f498-106">Även om Dataverse inte har begreppet av en organisationshierarki, har den några lösa begrepp, till exempel totala försäljningsintäkter.</span><span class="sxs-lookup"><span data-stu-id="4f498-106">Although Dataverse doesn't have the concept of an organization hierarchy, it does have a few loose concepts, such as total sales revenue.</span></span> <span data-ttu-id="4f498-107">Som en del av Dataverse-integrationen läggs organisationshierarkins datastruktur till i Dataverse.</span><span class="sxs-lookup"><span data-stu-id="4f498-107">As part of Dataverse integration, the organization hierarchy data structure is added to Dataverse.</span></span>

## <a name="data-flow"></a><span data-ttu-id="4f498-108">Dataflöde</span><span class="sxs-lookup"><span data-stu-id="4f498-108">Data flow</span></span>

<span data-ttu-id="4f498-109">Ett affärsekosystem som består av Finance and Operations-appar och Dataverse kommer att fortsätta att ha en organisationshierarki.</span><span class="sxs-lookup"><span data-stu-id="4f498-109">A business ecosystem that consists of Finance and Operations apps and Dataverse will continue to have an organization hierarchy.</span></span> <span data-ttu-id="4f498-110">Organisationshierarkin bygger på Finance and Operations-appar, men den exponeras i Dataverse för information och utbyggbarhet.</span><span class="sxs-lookup"><span data-stu-id="4f498-110">This organization hierarchy is built on Finance and Operations apps, but it's exposed in Dataverse for informational and extensibility purposes.</span></span> <span data-ttu-id="4f498-111">Följande illustration visar organisationshierarkiinformation som exponeras i Dataverse som ett enkelriktat dataflöde från Finance and Operations-appar till Dataverse.</span><span class="sxs-lookup"><span data-stu-id="4f498-111">The following illustration shows the organization hierarchy information that is exposed in Dataverse as a one-way data flow from Finance and Operations apps to Dataverse.</span></span>

![Arkitekturbild](media/dual-write-data-flow.png)

<span data-ttu-id="4f498-113">Organisationshierarkins tabellmappningar är tillgängliga för enkelriktad synkronisering av data från Finance and Operations-appar till Dataverse.</span><span class="sxs-lookup"><span data-stu-id="4f498-113">Organization hierarchy table maps are available for one-way synchronization of data from Finance and Operations apps to Dataverse.</span></span>

## <a name="templates"></a><span data-ttu-id="4f498-114">Mallar</span><span class="sxs-lookup"><span data-stu-id="4f498-114">Templates</span></span>

<span data-ttu-id="4f498-115">Produktinformationen innehåller all information som är relaterad till produkten och dess definition, t.ex. produktdimensioner eller spårnings- och lagringsdimensioner.</span><span class="sxs-lookup"><span data-stu-id="4f498-115">Product information contains all the information related to the product and its definition, such as the product dimensions or the tracking and storage dimensions.</span></span> <span data-ttu-id="4f498-116">Som framgår av följande tabell skapas en samling med tabellmappningar för synkronisering av produkter och relaterad information.</span><span class="sxs-lookup"><span data-stu-id="4f498-116">As the following table shows, a collection of table maps is created to sync products and related information.</span></span>

<span data-ttu-id="4f498-117">Finance and Operations-appar</span><span class="sxs-lookup"><span data-stu-id="4f498-117">Finance and Operations apps</span></span> | <span data-ttu-id="4f498-118">Andra Dynamics 365-appar</span><span class="sxs-lookup"><span data-stu-id="4f498-118">Other Dynamics 365 apps</span></span> | <span data-ttu-id="4f498-119">beskrivning</span><span class="sxs-lookup"><span data-stu-id="4f498-119">Description</span></span>
-----------------------|--------------------------------|---
<span data-ttu-id="4f498-120">Syften för organisationshierarki</span><span class="sxs-lookup"><span data-stu-id="4f498-120">Organization hierarchy purposes</span></span> | <span data-ttu-id="4f498-121">msdyn_internalorganizationhierarchypurposes</span><span class="sxs-lookup"><span data-stu-id="4f498-121">msdyn_internalorganizationhierarchypurposes</span></span> | <span data-ttu-id="4f498-122">Den här mallen innehåller en enkelriktad synkronisering av tabellen syfte för organisationshierarki.</span><span class="sxs-lookup"><span data-stu-id="4f498-122">This template provides one-way synchronization of the Organization Hierarchy Purpose table.</span></span>
<span data-ttu-id="4f498-123">Typ av organisationshierarki</span><span class="sxs-lookup"><span data-stu-id="4f498-123">Organization hierarchy type</span></span> | <span data-ttu-id="4f498-124">msdyn_internalorganizationhierarchytypes</span><span class="sxs-lookup"><span data-stu-id="4f498-124">msdyn_internalorganizationhierarchytypes</span></span> | <span data-ttu-id="4f498-125">Den här mallen innehåller en enkelriktad synkronisering av tabellen typ för organisationshierarki.</span><span class="sxs-lookup"><span data-stu-id="4f498-125">This template provides one-way synchronization of the Organization Hierarchy Type table.</span></span>
<span data-ttu-id="4f498-126">Organisationshierarki - publicerad</span><span class="sxs-lookup"><span data-stu-id="4f498-126">Organization hierarchy - published</span></span> | <span data-ttu-id="4f498-127">msdyn_internalorganizationhierarchies</span><span class="sxs-lookup"><span data-stu-id="4f498-127">msdyn_internalorganizationhierarchies</span></span> | <span data-ttu-id="4f498-128">Den här mallen innehåller en enkelriktad synkronisering av tabellen publicerad för organisationshierarki.</span><span class="sxs-lookup"><span data-stu-id="4f498-128">This template provides one-way synchronization of the Organization Hierarchy Published table.</span></span>
<span data-ttu-id="4f498-129">Driftenhet</span><span class="sxs-lookup"><span data-stu-id="4f498-129">Operating unit</span></span> | <span data-ttu-id="4f498-130">msdyn_internalorganizations</span><span class="sxs-lookup"><span data-stu-id="4f498-130">msdyn_internalorganizations</span></span> |
<span data-ttu-id="4f498-131">Juridiska personer</span><span class="sxs-lookup"><span data-stu-id="4f498-131">Legal entities</span></span> | <span data-ttu-id="4f498-132">msdyn_internalorganizations</span><span class="sxs-lookup"><span data-stu-id="4f498-132">msdyn_internalorganizations</span></span> |
<span data-ttu-id="4f498-133">Juridiska personer</span><span class="sxs-lookup"><span data-stu-id="4f498-133">Legal entities</span></span> | <span data-ttu-id="4f498-134">cdm_companies</span><span class="sxs-lookup"><span data-stu-id="4f498-134">cdm_companies</span></span> | <span data-ttu-id="4f498-135">Tillhandahåller dubbelriktad synkronisering av information om den juridiska personen (företag).</span><span class="sxs-lookup"><span data-stu-id="4f498-135">Provides bidirectional synchronization of legal entity (company) information.</span></span>

[!include [banner](../../includes/dual-write-symbols.md)]

[!include [Organization hierarchy purposes](includes/OrganizationHierarchyPurpose-msdyn-internalorganizationhierarchypurposes.md)]

[!include [Organization hierarchy type](includes/OrganizationHierarchyType-msdyn-internalorganizationhierarchytypes.md)]

[!include [Organization hierarchy - published](includes/OrganizationHierarchyPublished-msdyn-internalorganizationhierarchies.md)]

## <a name="internal-organization"></a><span data-ttu-id="4f498-136">Intern organisation</span><span class="sxs-lookup"><span data-stu-id="4f498-136">Internal Organization</span></span>

<span data-ttu-id="4f498-137">Intern organisationsinformation i Dataverse kommer från två tabeller **driftenhet** och **juridiska personer**.</span><span class="sxs-lookup"><span data-stu-id="4f498-137">Internal organization information in Dataverse comes from two tables, **operating unit** and **legal entities**.</span></span>

[!include [Operating unit](includes/OperatingUnit-msdyn-internalorganizations.md)]

[!include [Legal entities](includes/LegalEntities-msdyn-internalorganizations.md)]

[!include [Legal entities](includes/LegalEntities-Companies.md)]


[!INCLUDE[footer-include](../../../../includes/footer-banner.md)]