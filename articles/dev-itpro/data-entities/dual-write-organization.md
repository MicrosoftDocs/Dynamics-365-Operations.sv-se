---
title: Organisationshierarki i Common Data Service
description: I det här avsnittet beskrivs integreringen av organisationsinformation mellan Finance and Operations och Common Data Service.
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
ms.openlocfilehash: ca2ac0f9dbb8544b12f23a271423a43b0e601272
ms.sourcegitcommit: 02c223b44ac7196df675afac61c6783f467d1983
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/24/2019
ms.locfileid: "1789248"
---
## <a name="organization-hierarchy-in-common-data-service"></a><span data-ttu-id="a4891-103">Organisationshierarki i Common Data Service</span><span class="sxs-lookup"><span data-stu-id="a4891-103">Organization hierarchy in Common Data Service</span></span>

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

<span data-ttu-id="a4891-104">Eftersom Microsoft Dynamics 365 for Finance and Operations är ett finansiellt system är *organisation* ett grundläggande begrepp och systeminställningarna börjar med konfigurationen av en organisationshierarki.</span><span class="sxs-lookup"><span data-stu-id="a4891-104">Because Microsoft Dynamics 365 for Finance and Operations is a financial system, *organization* is a core concept, and system setup starts with the configuration of an organization hierarchy.</span></span> <span data-ttu-id="a4891-105">Affärsekonomi och åtgärder kan sedan spåras på organisationsnivå och även på alla nivåer i organisationshierarkin.</span><span class="sxs-lookup"><span data-stu-id="a4891-105">Business financials and operations can then be tracked at the organization level and also at any level in the organization hierarchy.</span></span>

<span data-ttu-id="a4891-106">Även om Common Data Service inte har begreppet av en organisationshierarki, har den några lösa begrepp, till exempel totala försäljningsintäkter.</span><span class="sxs-lookup"><span data-stu-id="a4891-106">Although Common Data Service doesn't have the concept of an organization hierarchy, it does have a few loose concepts, such as total sales revenue.</span></span> <span data-ttu-id="a4891-107">Som en del av Common Data Service-integrationen läggs organisationshierarkins datastruktur till i Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="a4891-107">As part of Common Data Service integration, the organization hierarchy data structure is added to Common Data Service.</span></span>

## <a name="data-flow"></a><span data-ttu-id="a4891-108">Dataflöde</span><span class="sxs-lookup"><span data-stu-id="a4891-108">Data flow</span></span>

<span data-ttu-id="a4891-109">Ett affärsekosystem som består av Finance and Operations Common Data Service och kommer att fortsätta att ha en organisationshierarki.</span><span class="sxs-lookup"><span data-stu-id="a4891-109">A business ecosystem that consists of Finance and Operations and Common Data Service will continue to have an organization hierarchy.</span></span> <span data-ttu-id="a4891-110">Organisationshierarkin bygger på Finance and Operations, men den exponeras i Common Data Service för information och utbyggbarhet.</span><span class="sxs-lookup"><span data-stu-id="a4891-110">This organization hierarchy is built on Finance and Operations, but it's exposed in Common Data Service for informational and extensibility purposes.</span></span> <span data-ttu-id="a4891-111">Följande illustration visar organisationshierarkiinformation som exponeras i Common Data Service som ett enkelriktat dataflöde från Finance and Operations till Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="a4891-111">The following illustration shows the organization hierarchy information that is exposed in Common Data Service as a one-way data flow from Finance and Operations to Common Data Service.</span></span>

![Arkitekturbild](media/dual-write-data-flow.png)

## <a name="templates"></a><span data-ttu-id="a4891-113">Mallar</span><span class="sxs-lookup"><span data-stu-id="a4891-113">Templates</span></span>

<span data-ttu-id="a4891-114">Organisationshierarkin entitetskartor är tillgängliga för enkelriktad synkronisering av data från Finance and Operations till Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="a4891-114">Organization hierarchy entity maps are available for one-way synchronization of data from Finance and Operations to Common Data Service.</span></span>

[!include [banner](../includes/dual-write-symbols.md)]

## <a name="internal-organization-hierarchy-purpose"></a><span data-ttu-id="a4891-115">Internt syfte för organisationshierarki</span><span class="sxs-lookup"><span data-stu-id="a4891-115">Internal Organization Hierarchy Purpose</span></span>

<span data-ttu-id="a4891-116">Den här mallen ger enkelriktad synkronisering av organisationshierarkin syftesentitet från Finance and Operations till Dynamics 365 for Customer Engagement.</span><span class="sxs-lookup"><span data-stu-id="a4891-116">This template provides one-way synchronization of the Organization Hierarchy Purpose entity from Finance and Operations to Dynamics 365 for Customer Engagement.</span></span>

<!-- ![architecture image](media/dual-write-purpose.png) -->

<span data-ttu-id="a4891-117">Källfält</span><span class="sxs-lookup"><span data-stu-id="a4891-117">Source field</span></span> | <span data-ttu-id="a4891-118">Mappningstyp</span><span class="sxs-lookup"><span data-stu-id="a4891-118">Map type</span></span> | <span data-ttu-id="a4891-119">Målfält</span><span class="sxs-lookup"><span data-stu-id="a4891-119">Destination field</span></span>
---|---|---
<span data-ttu-id="a4891-120">HIERARCHYTYPE</span><span class="sxs-lookup"><span data-stu-id="a4891-120">HIERARCHYTYPE</span></span> | \> | <span data-ttu-id="a4891-121">msdyn\_hierarchypurposetypename</span><span class="sxs-lookup"><span data-stu-id="a4891-121">msdyn\_hierarchypurposetypename</span></span>
<span data-ttu-id="a4891-122">HIERARCHYTYPE</span><span class="sxs-lookup"><span data-stu-id="a4891-122">HIERARCHYTYPE</span></span> | \> | <span data-ttu-id="a4891-123">msdyn\_hierarchytype.msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="a4891-123">msdyn\_hierarchytype.msdyn\_name</span></span>
<span data-ttu-id="a4891-124">HIERARCHYPURPOSE</span><span class="sxs-lookup"><span data-stu-id="a4891-124">HIERARCHYPURPOSE</span></span> | \>\> | <span data-ttu-id="a4891-125">msdyn\_hierarchypurpose</span><span class="sxs-lookup"><span data-stu-id="a4891-125">msdyn\_hierarchypurpose</span></span>
<span data-ttu-id="a4891-126">IMMUTABLE</span><span class="sxs-lookup"><span data-stu-id="a4891-126">IMMUTABLE</span></span> | \>\> | <span data-ttu-id="a4891-127">msdyn\_immutable</span><span class="sxs-lookup"><span data-stu-id="a4891-127">msdyn\_immutable</span></span>
<span data-ttu-id="a4891-128">SETASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="a4891-128">SETASDEFAULT</span></span> | \>\> | <span data-ttu-id="a4891-129">msdyn\_setasdefault</span><span class="sxs-lookup"><span data-stu-id="a4891-129">msdyn\_setasdefault</span></span>

## <a name="internal-organization-hierarchy-type"></a><span data-ttu-id="a4891-130">Intern typ av organisationshierarki</span><span class="sxs-lookup"><span data-stu-id="a4891-130">Internal Organization Hierarchy Type</span></span>

<span data-ttu-id="a4891-131">Den här mallen ger enkelriktad synkronisering av organisationshierarkin typentitet från Finance and Operations till Customer Engagement.</span><span class="sxs-lookup"><span data-stu-id="a4891-131">Tihs template provides one-way synchronization of the Organization Hierarchy Type entity from Finance and Operations to Customer Engagement.</span></span>

<!-- ![architecture image](media/dual-write-type.png) -->

<span data-ttu-id="a4891-132">Källfält</span><span class="sxs-lookup"><span data-stu-id="a4891-132">Source field</span></span> | <span data-ttu-id="a4891-133">Mappningstyp</span><span class="sxs-lookup"><span data-stu-id="a4891-133">Map type</span></span> | <span data-ttu-id="a4891-134">Målfält</span><span class="sxs-lookup"><span data-stu-id="a4891-134">Destination field</span></span>
---|---|---
<span data-ttu-id="a4891-135">NAMN</span><span class="sxs-lookup"><span data-stu-id="a4891-135">NAME</span></span> | \> | <span data-ttu-id="a4891-136">msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="a4891-136">msdyn\_name</span></span>

## <a name="internal-organization-hierarchy"></a><span data-ttu-id="a4891-137">Intern organisationshierarki</span><span class="sxs-lookup"><span data-stu-id="a4891-137">Internal Organization Hierarchy</span></span>

<span data-ttu-id="a4891-138">Den här mallen ger enkelriktad synkronisering av organisationshierarkin publicerad entitet från Finance and Operations till Customer Engagement.</span><span class="sxs-lookup"><span data-stu-id="a4891-138">This template provides one-way synchronization of the Organization Hierarchy Published entity from Finance and Operations to Customer Engagement.</span></span>

<!-- ![architecture image](media/dual-write-organization.png) -->

<span data-ttu-id="a4891-139">Källfält</span><span class="sxs-lookup"><span data-stu-id="a4891-139">Source field</span></span> | <span data-ttu-id="a4891-140">Mappningstyp</span><span class="sxs-lookup"><span data-stu-id="a4891-140">Map type</span></span> | <span data-ttu-id="a4891-141">Målfält</span><span class="sxs-lookup"><span data-stu-id="a4891-141">Destination field</span></span>
---|---|---
<span data-ttu-id="a4891-142">VALIDTO</span><span class="sxs-lookup"><span data-stu-id="a4891-142">VALIDTO</span></span> | \> | <span data-ttu-id="a4891-143">msdyn\_validto</span><span class="sxs-lookup"><span data-stu-id="a4891-143">msdyn\_validto</span></span>
<span data-ttu-id="a4891-144">VALIDFROM</span><span class="sxs-lookup"><span data-stu-id="a4891-144">VALIDFROM</span></span> | \> | <span data-ttu-id="a4891-145">msdyn\_validfrom</span><span class="sxs-lookup"><span data-stu-id="a4891-145">msdyn\_validfrom</span></span>
<span data-ttu-id="a4891-146">HIERARCHYTYPE</span><span class="sxs-lookup"><span data-stu-id="a4891-146">HIERARCHYTYPE</span></span> | \> | <span data-ttu-id="a4891-147">msdyn\_hierarchytypename</span><span class="sxs-lookup"><span data-stu-id="a4891-147">msdyn\_hierarchytypename</span></span>
<span data-ttu-id="a4891-148">PARENTORGANIZATIONPARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="a4891-148">PARENTORGANIZATIONPARTYNUMBER</span></span> | \> | <span data-ttu-id="a4891-149">msdyn\_parentpartyid</span><span class="sxs-lookup"><span data-stu-id="a4891-149">msdyn\_parentpartyid</span></span>
<span data-ttu-id="a4891-150">CHILDORGANIZATIONPARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="a4891-150">CHILDORGANIZATIONPARTYNUMBER</span></span> | \> | <span data-ttu-id="a4891-151">msdyn\_childpartyid</span><span class="sxs-lookup"><span data-stu-id="a4891-151">msdyn\_childpartyid</span></span>
<span data-ttu-id="a4891-152">HIERARCHYTYPE</span><span class="sxs-lookup"><span data-stu-id="a4891-152">HIERARCHYTYPE</span></span> | \> | <span data-ttu-id="a4891-153">msdyn\_hierarchytypeid.msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="a4891-153">msdyn\_hierarchytypeid.msdyn\_name</span></span>
<span data-ttu-id="a4891-154">CHILDORGANIZATIONPARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="a4891-154">CHILDORGANIZATIONPARTYNUMBER</span></span> | \> | <span data-ttu-id="a4891-155">msdyn\_childid.msdyn\_partynumber</span><span class="sxs-lookup"><span data-stu-id="a4891-155">msdyn\_childid.msdyn\_partynumber</span></span>
<span data-ttu-id="a4891-156">PARENTORGANIZATIONPARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="a4891-156">PARENTORGANIZATIONPARTYNUMBER</span></span> | \> | <span data-ttu-id="a4891-157">msdyn\_parentid.msdyn\_partynumber</span><span class="sxs-lookup"><span data-stu-id="a4891-157">msdyn\_parentid.msdyn\_partynumber</span></span>

## <a name="internal-organization"></a><span data-ttu-id="a4891-158">Intern organisation</span><span class="sxs-lookup"><span data-stu-id="a4891-158">Internal Organization</span></span>

<span data-ttu-id="a4891-159">Intern organisationsinformation i Common Data Service kommer från två Finance and Operations-entiteter **driftenhet** och **juridiska personer**.</span><span class="sxs-lookup"><span data-stu-id="a4891-159">Internal organization information in Common Data Service comes from two Finance and Operations entities, **operating unit** and **legal entities**.</span></span>

<!-- ![architecture image](media/dual-write-operating-unit.png) -->

<!-- ![architecture image](media/dual-write-legal-entities.png) -->

### <a name="operating-unit"></a><span data-ttu-id="a4891-160">Driftenhet</span><span class="sxs-lookup"><span data-stu-id="a4891-160">Operating unit</span></span>

<span data-ttu-id="a4891-161">Källfält</span><span class="sxs-lookup"><span data-stu-id="a4891-161">Source field</span></span> | <span data-ttu-id="a4891-162">Mappningstyp</span><span class="sxs-lookup"><span data-stu-id="a4891-162">Map type</span></span> | <span data-ttu-id="a4891-163">Målfält</span><span class="sxs-lookup"><span data-stu-id="a4891-163">Destination field</span></span>
---|---|---
<span data-ttu-id="a4891-164">LANGUAGEID</span><span class="sxs-lookup"><span data-stu-id="a4891-164">LANGUAGEID</span></span> | \> | <span data-ttu-id="a4891-165">msdyn\_languageid</span><span class="sxs-lookup"><span data-stu-id="a4891-165">msdyn\_languageid</span></span>
<span data-ttu-id="a4891-166">NAMEALIAS</span><span class="sxs-lookup"><span data-stu-id="a4891-166">NAMEALIAS</span></span> | \> | <span data-ttu-id="a4891-167">msdyn\_namnalias</span><span class="sxs-lookup"><span data-stu-id="a4891-167">msdyn\_namealias</span></span>
<span data-ttu-id="a4891-168">NAMN</span><span class="sxs-lookup"><span data-stu-id="a4891-168">NAME</span></span> | \> | <span data-ttu-id="a4891-169">msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="a4891-169">msdyn\_name</span></span>
<span data-ttu-id="a4891-170">PARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="a4891-170">PARTYNUMBER</span></span> | \> | <span data-ttu-id="a4891-171">msdyn\_partynumber</span><span class="sxs-lookup"><span data-stu-id="a4891-171">msdyn\_partynumber</span></span>
<span data-ttu-id="a4891-172">OPERATINGUNITTYPE</span><span class="sxs-lookup"><span data-stu-id="a4891-172">OPERATINGUNITTYPE</span></span> | \>\> | <span data-ttu-id="a4891-173">msdyn\_type</span><span class="sxs-lookup"><span data-stu-id="a4891-173">msdyn\_type</span></span>

### <a name="legal-entity"></a><span data-ttu-id="a4891-174">Juridisk person</span><span class="sxs-lookup"><span data-stu-id="a4891-174">Legal entity</span></span>

<span data-ttu-id="a4891-175">Källfält</span><span class="sxs-lookup"><span data-stu-id="a4891-175">Source field</span></span> | <span data-ttu-id="a4891-176">Mappningstyp</span><span class="sxs-lookup"><span data-stu-id="a4891-176">Map type</span></span> | <span data-ttu-id="a4891-177">Målfält</span><span class="sxs-lookup"><span data-stu-id="a4891-177">Destination field</span></span>
---|---|---
<span data-ttu-id="a4891-178">NAMEALIAS</span><span class="sxs-lookup"><span data-stu-id="a4891-178">NAMEALIAS</span></span> | \> | <span data-ttu-id="a4891-179">msdyn\_namnalias</span><span class="sxs-lookup"><span data-stu-id="a4891-179">msdyn\_namealias</span></span>
<span data-ttu-id="a4891-180">LANGUAGEID</span><span class="sxs-lookup"><span data-stu-id="a4891-180">LANGUAGEID</span></span> | \> | <span data-ttu-id="a4891-181">msdyn\_languageid</span><span class="sxs-lookup"><span data-stu-id="a4891-181">msdyn\_languageid</span></span>
<span data-ttu-id="a4891-182">NAMN</span><span class="sxs-lookup"><span data-stu-id="a4891-182">NAME</span></span> | \> | <span data-ttu-id="a4891-183">msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="a4891-183">msdyn\_name</span></span>
<span data-ttu-id="a4891-184">PARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="a4891-184">PARTYNUMBER</span></span> | \> | <span data-ttu-id="a4891-185">msdyn\_partynumber</span><span class="sxs-lookup"><span data-stu-id="a4891-185">msdyn\_partynumber</span></span>
<span data-ttu-id="a4891-186">ingen</span><span class="sxs-lookup"><span data-stu-id="a4891-186">none</span></span> | \>\> | <span data-ttu-id="a4891-187">msdyn\_type</span><span class="sxs-lookup"><span data-stu-id="a4891-187">msdyn\_type</span></span>
<span data-ttu-id="a4891-188">LEGALENTITYID</span><span class="sxs-lookup"><span data-stu-id="a4891-188">LEGALENTITYID</span></span> | \> | <span data-ttu-id="a4891-189">msdyn\_companycode</span><span class="sxs-lookup"><span data-stu-id="a4891-189">msdyn\_companycode</span></span>

## <a name="company"></a><span data-ttu-id="a4891-190">Företag</span><span class="sxs-lookup"><span data-stu-id="a4891-190">Company</span></span>

<span data-ttu-id="a4891-191">Ger dubbelriktad synkronisering av information om juridisk person (företag) mellan Finance and Operations och Customer Engagement.</span><span class="sxs-lookup"><span data-stu-id="a4891-191">Provides bidirectional synchronization of legal entity (company) information between Finance and Operations and Customer Engagement.</span></span>

<!-- ![architecture image](media/dual-write-company.png) -->

<span data-ttu-id="a4891-192">Källfält</span><span class="sxs-lookup"><span data-stu-id="a4891-192">Source field</span></span> | <span data-ttu-id="a4891-193">Mappningstyp</span><span class="sxs-lookup"><span data-stu-id="a4891-193">Map type</span></span> | <span data-ttu-id="a4891-194">Målfält</span><span class="sxs-lookup"><span data-stu-id="a4891-194">Destination field</span></span>
---|---|---
<span data-ttu-id="a4891-195">NAMN</span><span class="sxs-lookup"><span data-stu-id="a4891-195">NAME</span></span> | = | <span data-ttu-id="a4891-196">cdm\_name</span><span class="sxs-lookup"><span data-stu-id="a4891-196">cdm\_name</span></span>
<span data-ttu-id="a4891-197">LEGALENTITYID</span><span class="sxs-lookup"><span data-stu-id="a4891-197">LEGALENTITYID</span></span> | = | <span data-ttu-id="a4891-198">cdm\_companycode</span><span class="sxs-lookup"><span data-stu-id="a4891-198">cdm\_companycode</span></span>
