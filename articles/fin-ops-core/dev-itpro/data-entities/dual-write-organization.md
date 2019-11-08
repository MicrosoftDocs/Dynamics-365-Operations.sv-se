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
ms.openlocfilehash: 9a12ab249129dce24cdca5e29d737fa9f68c0eac
ms.sourcegitcommit: 6e0909e95f38b7487a4b7f68cc62b723f8b59bd4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/10/2019
ms.locfileid: "2572459"
---
# <a name="organization-hierarchy-in-common-data-service"></a><span data-ttu-id="38ab7-103">Organisationshierarki i Common Data Service</span><span class="sxs-lookup"><span data-stu-id="38ab7-103">Organization hierarchy in Common Data Service</span></span>

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

<span data-ttu-id="38ab7-104">Eftersom Dynamics 365 Finance är ett finansiellt system är *organisation* ett grundläggande begrepp och systeminställningarna börjar med konfigurationen av en organisationshierarki.</span><span class="sxs-lookup"><span data-stu-id="38ab7-104">Because Dynamics 365 Finance is a financial system, *organization* is a core concept, and system setup starts with the configuration of an organization hierarchy.</span></span> <span data-ttu-id="38ab7-105">Affärsekonomi kan sedan spåras på organisationsnivå och även på alla nivåer i organisationshierarkin.</span><span class="sxs-lookup"><span data-stu-id="38ab7-105">Business financials can then be tracked at the organization level and also at any level in the organization hierarchy.</span></span>

<span data-ttu-id="38ab7-106">Även om Common Data Service inte har begreppet av en organisationshierarki, har den några lösa begrepp, till exempel totala försäljningsintäkter.</span><span class="sxs-lookup"><span data-stu-id="38ab7-106">Although Common Data Service doesn't have the concept of an organization hierarchy, it does have a few loose concepts, such as total sales revenue.</span></span> <span data-ttu-id="38ab7-107">Som en del av Common Data Service-integrationen läggs organisationshierarkins datastruktur till i Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="38ab7-107">As part of Common Data Service integration, the organization hierarchy data structure is added to Common Data Service.</span></span>

## <a name="data-flow"></a><span data-ttu-id="38ab7-108">Dataflöde</span><span class="sxs-lookup"><span data-stu-id="38ab7-108">Data flow</span></span>

<span data-ttu-id="38ab7-109">Ett affärsekosystem som består av Finance and Operations-appar och Common Data Service kommer att fortsätta att ha en organisationshierarki.</span><span class="sxs-lookup"><span data-stu-id="38ab7-109">A business ecosystem that consists of Finance and Operations apps and Common Data Service will continue to have an organization hierarchy.</span></span> <span data-ttu-id="38ab7-110">Organisationshierarkin bygger på Finance and Operations-appar, men den exponeras i Common Data Service för information och utbyggbarhet.</span><span class="sxs-lookup"><span data-stu-id="38ab7-110">This organization hierarchy is built on Finance and Operations apps, but it's exposed in Common Data Service for informational and extensibility purposes.</span></span> <span data-ttu-id="38ab7-111">Följande illustration visar organisationshierarkiinformation som exponeras i Common Data Service som ett enkelriktat dataflöde från Finance and Operations-appar till Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="38ab7-111">The following illustration shows the organization hierarchy information that is exposed in Common Data Service as a one-way data flow from Finance and Operations apps to Common Data Service.</span></span>

![Arkitekturbild](media/dual-write-data-flow.png)

## <a name="templates"></a><span data-ttu-id="38ab7-113">Mallar</span><span class="sxs-lookup"><span data-stu-id="38ab7-113">Templates</span></span>

<span data-ttu-id="38ab7-114">Organisationshierarkin entitetskartor är tillgängliga för enkelriktad synkronisering av data från Finance and Operations-appar till Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="38ab7-114">Organization hierarchy entity maps are available for one-way synchronization of data from Finance and Operations apps to Common Data Service.</span></span>

[!include [banner](../includes/dual-write-symbols.md)]

## <a name="internal-organization-hierarchy-purpose"></a><span data-ttu-id="38ab7-115">Internt syfte för organisationshierarki</span><span class="sxs-lookup"><span data-stu-id="38ab7-115">Internal Organization Hierarchy Purpose</span></span>

<span data-ttu-id="38ab7-116">Den här mallen ger enkelriktad synkronisering av organisationshierarkin syftesentitet från Finance and Operations till andra Dynamics 365-appar.</span><span class="sxs-lookup"><span data-stu-id="38ab7-116">This template provides one-way synchronization of the Organization Hierarchy Purpose entity from Finance and Operations to other Dynamics 365 apps.</span></span>

<!-- ![architecture image](media/dual-write-purpose.png) -->

<span data-ttu-id="38ab7-117">Källfält</span><span class="sxs-lookup"><span data-stu-id="38ab7-117">Source field</span></span> | <span data-ttu-id="38ab7-118">Mappningstyp</span><span class="sxs-lookup"><span data-stu-id="38ab7-118">Map type</span></span> | <span data-ttu-id="38ab7-119">Målfält</span><span class="sxs-lookup"><span data-stu-id="38ab7-119">Destination field</span></span>
---|---|---
<span data-ttu-id="38ab7-120">HIERARCHYTYPE</span><span class="sxs-lookup"><span data-stu-id="38ab7-120">HIERARCHYTYPE</span></span> | \> | <span data-ttu-id="38ab7-121">msdyn\_hierarchypurposetypename</span><span class="sxs-lookup"><span data-stu-id="38ab7-121">msdyn\_hierarchypurposetypename</span></span>
<span data-ttu-id="38ab7-122">HIERARCHYTYPE</span><span class="sxs-lookup"><span data-stu-id="38ab7-122">HIERARCHYTYPE</span></span> | \> | <span data-ttu-id="38ab7-123">msdyn\_hierarchytype.msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="38ab7-123">msdyn\_hierarchytype.msdyn\_name</span></span>
<span data-ttu-id="38ab7-124">HIERARCHYPURPOSE</span><span class="sxs-lookup"><span data-stu-id="38ab7-124">HIERARCHYPURPOSE</span></span> | \>\> | <span data-ttu-id="38ab7-125">msdyn\_hierarchypurpose</span><span class="sxs-lookup"><span data-stu-id="38ab7-125">msdyn\_hierarchypurpose</span></span>
<span data-ttu-id="38ab7-126">IMMUTABLE</span><span class="sxs-lookup"><span data-stu-id="38ab7-126">IMMUTABLE</span></span> | \>\> | <span data-ttu-id="38ab7-127">msdyn\_immutable</span><span class="sxs-lookup"><span data-stu-id="38ab7-127">msdyn\_immutable</span></span>
<span data-ttu-id="38ab7-128">SETASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="38ab7-128">SETASDEFAULT</span></span> | \>\> | <span data-ttu-id="38ab7-129">msdyn\_setasdefault</span><span class="sxs-lookup"><span data-stu-id="38ab7-129">msdyn\_setasdefault</span></span>

## <a name="internal-organization-hierarchy-type"></a><span data-ttu-id="38ab7-130">Intern typ av organisationshierarki</span><span class="sxs-lookup"><span data-stu-id="38ab7-130">Internal Organization Hierarchy Type</span></span>

<span data-ttu-id="38ab7-131">Den här mallen ger enkelriktad synkronisering av organisationshierarkin typentitet från Finance and Operations till andra Dynamics 365-appar.</span><span class="sxs-lookup"><span data-stu-id="38ab7-131">Tihs template provides one-way synchronization of the Organization Hierarchy Type entity from Finance and Operations to other Dynamics 365 apps.</span></span>

<!-- ![architecture image](media/dual-write-type.png) -->

<span data-ttu-id="38ab7-132">Källfält</span><span class="sxs-lookup"><span data-stu-id="38ab7-132">Source field</span></span> | <span data-ttu-id="38ab7-133">Mappningstyp</span><span class="sxs-lookup"><span data-stu-id="38ab7-133">Map type</span></span> | <span data-ttu-id="38ab7-134">Målfält</span><span class="sxs-lookup"><span data-stu-id="38ab7-134">Destination field</span></span>
---|---|---
<span data-ttu-id="38ab7-135">NAMN</span><span class="sxs-lookup"><span data-stu-id="38ab7-135">NAME</span></span> | \> | <span data-ttu-id="38ab7-136">msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="38ab7-136">msdyn\_name</span></span>

## <a name="internal-organization-hierarchy"></a><span data-ttu-id="38ab7-137">Intern organisationshierarki</span><span class="sxs-lookup"><span data-stu-id="38ab7-137">Internal Organization Hierarchy</span></span>

<span data-ttu-id="38ab7-138">Den här mallen ger enkelriktad synkronisering av organisationshierarkin publicerad entitet från Finance and Operations till andra Dynamics 365-appar.</span><span class="sxs-lookup"><span data-stu-id="38ab7-138">This template provides one-way synchronization of the Organization Hierarchy Published entity from Finance and Operations to other Dynamics 365 apps.</span></span>

<!-- ![architecture image](media/dual-write-organization.png) -->

<span data-ttu-id="38ab7-139">Källfält</span><span class="sxs-lookup"><span data-stu-id="38ab7-139">Source field</span></span> | <span data-ttu-id="38ab7-140">Mappningstyp</span><span class="sxs-lookup"><span data-stu-id="38ab7-140">Map type</span></span> | <span data-ttu-id="38ab7-141">Målfält</span><span class="sxs-lookup"><span data-stu-id="38ab7-141">Destination field</span></span>
---|---|---
<span data-ttu-id="38ab7-142">VALIDTO</span><span class="sxs-lookup"><span data-stu-id="38ab7-142">VALIDTO</span></span> | \> | <span data-ttu-id="38ab7-143">msdyn\_validto</span><span class="sxs-lookup"><span data-stu-id="38ab7-143">msdyn\_validto</span></span>
<span data-ttu-id="38ab7-144">VALIDFROM</span><span class="sxs-lookup"><span data-stu-id="38ab7-144">VALIDFROM</span></span> | \> | <span data-ttu-id="38ab7-145">msdyn\_validfrom</span><span class="sxs-lookup"><span data-stu-id="38ab7-145">msdyn\_validfrom</span></span>
<span data-ttu-id="38ab7-146">HIERARCHYTYPE</span><span class="sxs-lookup"><span data-stu-id="38ab7-146">HIERARCHYTYPE</span></span> | \> | <span data-ttu-id="38ab7-147">msdyn\_hierarchytypename</span><span class="sxs-lookup"><span data-stu-id="38ab7-147">msdyn\_hierarchytypename</span></span>
<span data-ttu-id="38ab7-148">PARENTORGANIZATIONPARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="38ab7-148">PARENTORGANIZATIONPARTYNUMBER</span></span> | \> | <span data-ttu-id="38ab7-149">msdyn\_parentpartyid</span><span class="sxs-lookup"><span data-stu-id="38ab7-149">msdyn\_parentpartyid</span></span>
<span data-ttu-id="38ab7-150">CHILDORGANIZATIONPARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="38ab7-150">CHILDORGANIZATIONPARTYNUMBER</span></span> | \> | <span data-ttu-id="38ab7-151">msdyn\_childpartyid</span><span class="sxs-lookup"><span data-stu-id="38ab7-151">msdyn\_childpartyid</span></span>
<span data-ttu-id="38ab7-152">HIERARCHYTYPE</span><span class="sxs-lookup"><span data-stu-id="38ab7-152">HIERARCHYTYPE</span></span> | \> | <span data-ttu-id="38ab7-153">msdyn\_hierarchytypeid.msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="38ab7-153">msdyn\_hierarchytypeid.msdyn\_name</span></span>
<span data-ttu-id="38ab7-154">CHILDORGANIZATIONPARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="38ab7-154">CHILDORGANIZATIONPARTYNUMBER</span></span> | \> | <span data-ttu-id="38ab7-155">msdyn\_childid.msdyn\_partynumber</span><span class="sxs-lookup"><span data-stu-id="38ab7-155">msdyn\_childid.msdyn\_partynumber</span></span>
<span data-ttu-id="38ab7-156">PARENTORGANIZATIONPARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="38ab7-156">PARENTORGANIZATIONPARTYNUMBER</span></span> | \> | <span data-ttu-id="38ab7-157">msdyn\_parentid.msdyn\_partynumber</span><span class="sxs-lookup"><span data-stu-id="38ab7-157">msdyn\_parentid.msdyn\_partynumber</span></span>

## <a name="internal-organization"></a><span data-ttu-id="38ab7-158">Intern organisation</span><span class="sxs-lookup"><span data-stu-id="38ab7-158">Internal Organization</span></span>

<span data-ttu-id="38ab7-159">Intern organisationsinformation i Common Data Service kommer från två entiteter **driftenhet** och **juridiska personer**.</span><span class="sxs-lookup"><span data-stu-id="38ab7-159">Internal organization information in Common Data Service comes from two entities, **operating unit** and **legal entities**.</span></span>

<!-- ![architecture image](media/dual-write-operating-unit.png) -->

<!-- ![architecture image](media/dual-write-legal-entities.png) -->

### <a name="operating-unit"></a><span data-ttu-id="38ab7-160">Driftenhet</span><span class="sxs-lookup"><span data-stu-id="38ab7-160">Operating unit</span></span>

<span data-ttu-id="38ab7-161">Källfält</span><span class="sxs-lookup"><span data-stu-id="38ab7-161">Source field</span></span> | <span data-ttu-id="38ab7-162">Mappningstyp</span><span class="sxs-lookup"><span data-stu-id="38ab7-162">Map type</span></span> | <span data-ttu-id="38ab7-163">Målfält</span><span class="sxs-lookup"><span data-stu-id="38ab7-163">Destination field</span></span>
---|---|---
<span data-ttu-id="38ab7-164">LANGUAGEID</span><span class="sxs-lookup"><span data-stu-id="38ab7-164">LANGUAGEID</span></span> | \> | <span data-ttu-id="38ab7-165">msdyn\_languageid</span><span class="sxs-lookup"><span data-stu-id="38ab7-165">msdyn\_languageid</span></span>
<span data-ttu-id="38ab7-166">NAMEALIAS</span><span class="sxs-lookup"><span data-stu-id="38ab7-166">NAMEALIAS</span></span> | \> | <span data-ttu-id="38ab7-167">msdyn\_namnalias</span><span class="sxs-lookup"><span data-stu-id="38ab7-167">msdyn\_namealias</span></span>
<span data-ttu-id="38ab7-168">NAMN</span><span class="sxs-lookup"><span data-stu-id="38ab7-168">NAME</span></span> | \> | <span data-ttu-id="38ab7-169">msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="38ab7-169">msdyn\_name</span></span>
<span data-ttu-id="38ab7-170">PARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="38ab7-170">PARTYNUMBER</span></span> | \> | <span data-ttu-id="38ab7-171">msdyn\_partynumber</span><span class="sxs-lookup"><span data-stu-id="38ab7-171">msdyn\_partynumber</span></span>
<span data-ttu-id="38ab7-172">OPERATINGUNITTYPE</span><span class="sxs-lookup"><span data-stu-id="38ab7-172">OPERATINGUNITTYPE</span></span> | \>\> | <span data-ttu-id="38ab7-173">msdyn\_type</span><span class="sxs-lookup"><span data-stu-id="38ab7-173">msdyn\_type</span></span>

### <a name="legal-entity"></a><span data-ttu-id="38ab7-174">Juridisk person</span><span class="sxs-lookup"><span data-stu-id="38ab7-174">Legal entity</span></span>

<span data-ttu-id="38ab7-175">Källfält</span><span class="sxs-lookup"><span data-stu-id="38ab7-175">Source field</span></span> | <span data-ttu-id="38ab7-176">Mappningstyp</span><span class="sxs-lookup"><span data-stu-id="38ab7-176">Map type</span></span> | <span data-ttu-id="38ab7-177">Målfält</span><span class="sxs-lookup"><span data-stu-id="38ab7-177">Destination field</span></span>
---|---|---
<span data-ttu-id="38ab7-178">NAMEALIAS</span><span class="sxs-lookup"><span data-stu-id="38ab7-178">NAMEALIAS</span></span> | \> | <span data-ttu-id="38ab7-179">msdyn\_namnalias</span><span class="sxs-lookup"><span data-stu-id="38ab7-179">msdyn\_namealias</span></span>
<span data-ttu-id="38ab7-180">LANGUAGEID</span><span class="sxs-lookup"><span data-stu-id="38ab7-180">LANGUAGEID</span></span> | \> | <span data-ttu-id="38ab7-181">msdyn\_languageid</span><span class="sxs-lookup"><span data-stu-id="38ab7-181">msdyn\_languageid</span></span>
<span data-ttu-id="38ab7-182">NAMN</span><span class="sxs-lookup"><span data-stu-id="38ab7-182">NAME</span></span> | \> | <span data-ttu-id="38ab7-183">msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="38ab7-183">msdyn\_name</span></span>
<span data-ttu-id="38ab7-184">PARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="38ab7-184">PARTYNUMBER</span></span> | \> | <span data-ttu-id="38ab7-185">msdyn\_partynumber</span><span class="sxs-lookup"><span data-stu-id="38ab7-185">msdyn\_partynumber</span></span>
<span data-ttu-id="38ab7-186">ingen</span><span class="sxs-lookup"><span data-stu-id="38ab7-186">none</span></span> | \>\> | <span data-ttu-id="38ab7-187">msdyn\_type</span><span class="sxs-lookup"><span data-stu-id="38ab7-187">msdyn\_type</span></span>
<span data-ttu-id="38ab7-188">LEGALENTITYID</span><span class="sxs-lookup"><span data-stu-id="38ab7-188">LEGALENTITYID</span></span> | \> | <span data-ttu-id="38ab7-189">msdyn\_companycode</span><span class="sxs-lookup"><span data-stu-id="38ab7-189">msdyn\_companycode</span></span>

## <a name="company"></a><span data-ttu-id="38ab7-190">Företag</span><span class="sxs-lookup"><span data-stu-id="38ab7-190">Company</span></span>

<span data-ttu-id="38ab7-191">Ger dubbelriktad synkronisering av information om juridisk person (företag) mellan Finance and Operations och andra Dynamics 365-appar.</span><span class="sxs-lookup"><span data-stu-id="38ab7-191">Provides bidirectional synchronization of legal entity (company) information between Finance and Operations and other Dynamics 365 apps.</span></span>

<!-- ![architecture image](media/dual-write-company.png) -->

<span data-ttu-id="38ab7-192">Källfält</span><span class="sxs-lookup"><span data-stu-id="38ab7-192">Source field</span></span> | <span data-ttu-id="38ab7-193">Mappningstyp</span><span class="sxs-lookup"><span data-stu-id="38ab7-193">Map type</span></span> | <span data-ttu-id="38ab7-194">Målfält</span><span class="sxs-lookup"><span data-stu-id="38ab7-194">Destination field</span></span>
---|---|---
<span data-ttu-id="38ab7-195">NAMN</span><span class="sxs-lookup"><span data-stu-id="38ab7-195">NAME</span></span> | = | <span data-ttu-id="38ab7-196">cdm\_name</span><span class="sxs-lookup"><span data-stu-id="38ab7-196">cdm\_name</span></span>
<span data-ttu-id="38ab7-197">LEGALENTITYID</span><span class="sxs-lookup"><span data-stu-id="38ab7-197">LEGALENTITYID</span></span> | = | <span data-ttu-id="38ab7-198">cdm\_companycode</span><span class="sxs-lookup"><span data-stu-id="38ab7-198">cdm\_companycode</span></span>
