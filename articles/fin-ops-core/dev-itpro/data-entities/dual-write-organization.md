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
ms.openlocfilehash: fd159b38f69305dcaecb364ba0ccb3befabb3582
ms.sourcegitcommit: 3ba95d50b8262fa0f43d4faad76adac4d05eb3ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/27/2019
ms.locfileid: "2182035"
---
## <a name="organization-hierarchy-in-common-data-service"></a><span data-ttu-id="6ddaf-103">Organisationshierarki i Common Data Service</span><span class="sxs-lookup"><span data-stu-id="6ddaf-103">Organization hierarchy in Common Data Service</span></span>

[!include [banner](../includes/banner.md)]

[!include [preview](../includes/preview-banner.md)]

<span data-ttu-id="6ddaf-104">Eftersom Dynamics 365 Finance är ett finansiellt system är *organisation* ett grundläggande begrepp och systeminställningarna börjar med konfigurationen av en organisationshierarki.</span><span class="sxs-lookup"><span data-stu-id="6ddaf-104">Because Dynamics 365 Finance is a financial system, *organization* is a core concept, and system setup starts with the configuration of an organization hierarchy.</span></span> <span data-ttu-id="6ddaf-105">Affärsekonomi kan sedan spåras på organisationsnivå och även på alla nivåer i organisationshierarkin.</span><span class="sxs-lookup"><span data-stu-id="6ddaf-105">Business financials can then be tracked at the organization level and also at any level in the organization hierarchy.</span></span>

<span data-ttu-id="6ddaf-106">Även om Common Data Service inte har begreppet av en organisationshierarki, har den några lösa begrepp, till exempel totala försäljningsintäkter.</span><span class="sxs-lookup"><span data-stu-id="6ddaf-106">Although Common Data Service doesn't have the concept of an organization hierarchy, it does have a few loose concepts, such as total sales revenue.</span></span> <span data-ttu-id="6ddaf-107">Som en del av Common Data Service-integrationen läggs organisationshierarkins datastruktur till i Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="6ddaf-107">As part of Common Data Service integration, the organization hierarchy data structure is added to Common Data Service.</span></span>

## <a name="data-flow"></a><span data-ttu-id="6ddaf-108">Dataflöde</span><span class="sxs-lookup"><span data-stu-id="6ddaf-108">Data flow</span></span>

<span data-ttu-id="6ddaf-109">Ett affärsekosystem som består av Finance and Operations-appar och Common Data Service kommer att fortsätta att ha en organisationshierarki.</span><span class="sxs-lookup"><span data-stu-id="6ddaf-109">A business ecosystem that consists of Finance and Operations apps and Common Data Service will continue to have an organization hierarchy.</span></span> <span data-ttu-id="6ddaf-110">Organisationshierarkin bygger på Finance and Operations-appar, men den exponeras i Common Data Service för information och utbyggbarhet.</span><span class="sxs-lookup"><span data-stu-id="6ddaf-110">This organization hierarchy is built on Finance and Operations apps, but it's exposed in Common Data Service for informational and extensibility purposes.</span></span> <span data-ttu-id="6ddaf-111">Följande illustration visar organisationshierarkiinformation som exponeras i Common Data Service som ett enkelriktat dataflöde från Finance and Operations-appar till Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="6ddaf-111">The following illustration shows the organization hierarchy information that is exposed in Common Data Service as a one-way data flow from Finance and Operations apps to Common Data Service.</span></span>

![Arkitekturbild](media/dual-write-data-flow.png)

## <a name="templates"></a><span data-ttu-id="6ddaf-113">Mallar</span><span class="sxs-lookup"><span data-stu-id="6ddaf-113">Templates</span></span>

<span data-ttu-id="6ddaf-114">Organisationshierarkin entitetskartor är tillgängliga för enkelriktad synkronisering av data från Finance and Operations-appar till Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="6ddaf-114">Organization hierarchy entity maps are available for one-way synchronization of data from Finance and Operations apps to Common Data Service.</span></span>

[!include [banner](../includes/dual-write-symbols.md)]

## <a name="internal-organization-hierarchy-purpose"></a><span data-ttu-id="6ddaf-115">Internt syfte för organisationshierarki</span><span class="sxs-lookup"><span data-stu-id="6ddaf-115">Internal Organization Hierarchy Purpose</span></span>

<span data-ttu-id="6ddaf-116">Den här mallen ger enkelriktad synkronisering av organisationshierarkin syftesentitet från Finance and Operations till andra Dynamics 365-appar.</span><span class="sxs-lookup"><span data-stu-id="6ddaf-116">This template provides one-way synchronization of the Organization Hierarchy Purpose entity from Finance and Operations to other Dynamics 365 apps.</span></span>

<!-- ![architecture image](media/dual-write-purpose.png) -->

<span data-ttu-id="6ddaf-117">Källfält</span><span class="sxs-lookup"><span data-stu-id="6ddaf-117">Source field</span></span> | <span data-ttu-id="6ddaf-118">Mappningstyp</span><span class="sxs-lookup"><span data-stu-id="6ddaf-118">Map type</span></span> | <span data-ttu-id="6ddaf-119">Målfält</span><span class="sxs-lookup"><span data-stu-id="6ddaf-119">Destination field</span></span>
---|---|---
<span data-ttu-id="6ddaf-120">HIERARCHYTYPE</span><span class="sxs-lookup"><span data-stu-id="6ddaf-120">HIERARCHYTYPE</span></span> | \> | <span data-ttu-id="6ddaf-121">msdyn\_hierarchypurposetypename</span><span class="sxs-lookup"><span data-stu-id="6ddaf-121">msdyn\_hierarchypurposetypename</span></span>
<span data-ttu-id="6ddaf-122">HIERARCHYTYPE</span><span class="sxs-lookup"><span data-stu-id="6ddaf-122">HIERARCHYTYPE</span></span> | \> | <span data-ttu-id="6ddaf-123">msdyn\_hierarchytype.msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="6ddaf-123">msdyn\_hierarchytype.msdyn\_name</span></span>
<span data-ttu-id="6ddaf-124">HIERARCHYPURPOSE</span><span class="sxs-lookup"><span data-stu-id="6ddaf-124">HIERARCHYPURPOSE</span></span> | \>\> | <span data-ttu-id="6ddaf-125">msdyn\_hierarchypurpose</span><span class="sxs-lookup"><span data-stu-id="6ddaf-125">msdyn\_hierarchypurpose</span></span>
<span data-ttu-id="6ddaf-126">IMMUTABLE</span><span class="sxs-lookup"><span data-stu-id="6ddaf-126">IMMUTABLE</span></span> | \>\> | <span data-ttu-id="6ddaf-127">msdyn\_immutable</span><span class="sxs-lookup"><span data-stu-id="6ddaf-127">msdyn\_immutable</span></span>
<span data-ttu-id="6ddaf-128">SETASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="6ddaf-128">SETASDEFAULT</span></span> | \>\> | <span data-ttu-id="6ddaf-129">msdyn\_setasdefault</span><span class="sxs-lookup"><span data-stu-id="6ddaf-129">msdyn\_setasdefault</span></span>

## <a name="internal-organization-hierarchy-type"></a><span data-ttu-id="6ddaf-130">Intern typ av organisationshierarki</span><span class="sxs-lookup"><span data-stu-id="6ddaf-130">Internal Organization Hierarchy Type</span></span>

<span data-ttu-id="6ddaf-131">Den här mallen ger enkelriktad synkronisering av organisationshierarkin typentitet från Finance and Operations till andra Dynamics 365-appar.</span><span class="sxs-lookup"><span data-stu-id="6ddaf-131">Tihs template provides one-way synchronization of the Organization Hierarchy Type entity from Finance and Operations to other Dynamics 365 apps.</span></span>

<!-- ![architecture image](media/dual-write-type.png) -->

<span data-ttu-id="6ddaf-132">Källfält</span><span class="sxs-lookup"><span data-stu-id="6ddaf-132">Source field</span></span> | <span data-ttu-id="6ddaf-133">Mappningstyp</span><span class="sxs-lookup"><span data-stu-id="6ddaf-133">Map type</span></span> | <span data-ttu-id="6ddaf-134">Målfält</span><span class="sxs-lookup"><span data-stu-id="6ddaf-134">Destination field</span></span>
---|---|---
<span data-ttu-id="6ddaf-135">NAMN</span><span class="sxs-lookup"><span data-stu-id="6ddaf-135">NAME</span></span> | \> | <span data-ttu-id="6ddaf-136">msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="6ddaf-136">msdyn\_name</span></span>

## <a name="internal-organization-hierarchy"></a><span data-ttu-id="6ddaf-137">Intern organisationshierarki</span><span class="sxs-lookup"><span data-stu-id="6ddaf-137">Internal Organization Hierarchy</span></span>

<span data-ttu-id="6ddaf-138">Den här mallen ger enkelriktad synkronisering av organisationshierarkin publicerad entitet från Finance and Operations till andra Dynamics 365-appar.</span><span class="sxs-lookup"><span data-stu-id="6ddaf-138">This template provides one-way synchronization of the Organization Hierarchy Published entity from Finance and Operations to other Dynamics 365 apps.</span></span>

<!-- ![architecture image](media/dual-write-organization.png) -->

<span data-ttu-id="6ddaf-139">Källfält</span><span class="sxs-lookup"><span data-stu-id="6ddaf-139">Source field</span></span> | <span data-ttu-id="6ddaf-140">Mappningstyp</span><span class="sxs-lookup"><span data-stu-id="6ddaf-140">Map type</span></span> | <span data-ttu-id="6ddaf-141">Målfält</span><span class="sxs-lookup"><span data-stu-id="6ddaf-141">Destination field</span></span>
---|---|---
<span data-ttu-id="6ddaf-142">VALIDTO</span><span class="sxs-lookup"><span data-stu-id="6ddaf-142">VALIDTO</span></span> | \> | <span data-ttu-id="6ddaf-143">msdyn\_validto</span><span class="sxs-lookup"><span data-stu-id="6ddaf-143">msdyn\_validto</span></span>
<span data-ttu-id="6ddaf-144">VALIDFROM</span><span class="sxs-lookup"><span data-stu-id="6ddaf-144">VALIDFROM</span></span> | \> | <span data-ttu-id="6ddaf-145">msdyn\_validfrom</span><span class="sxs-lookup"><span data-stu-id="6ddaf-145">msdyn\_validfrom</span></span>
<span data-ttu-id="6ddaf-146">HIERARCHYTYPE</span><span class="sxs-lookup"><span data-stu-id="6ddaf-146">HIERARCHYTYPE</span></span> | \> | <span data-ttu-id="6ddaf-147">msdyn\_hierarchytypename</span><span class="sxs-lookup"><span data-stu-id="6ddaf-147">msdyn\_hierarchytypename</span></span>
<span data-ttu-id="6ddaf-148">PARENTORGANIZATIONPARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="6ddaf-148">PARENTORGANIZATIONPARTYNUMBER</span></span> | \> | <span data-ttu-id="6ddaf-149">msdyn\_parentpartyid</span><span class="sxs-lookup"><span data-stu-id="6ddaf-149">msdyn\_parentpartyid</span></span>
<span data-ttu-id="6ddaf-150">CHILDORGANIZATIONPARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="6ddaf-150">CHILDORGANIZATIONPARTYNUMBER</span></span> | \> | <span data-ttu-id="6ddaf-151">msdyn\_childpartyid</span><span class="sxs-lookup"><span data-stu-id="6ddaf-151">msdyn\_childpartyid</span></span>
<span data-ttu-id="6ddaf-152">HIERARCHYTYPE</span><span class="sxs-lookup"><span data-stu-id="6ddaf-152">HIERARCHYTYPE</span></span> | \> | <span data-ttu-id="6ddaf-153">msdyn\_hierarchytypeid.msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="6ddaf-153">msdyn\_hierarchytypeid.msdyn\_name</span></span>
<span data-ttu-id="6ddaf-154">CHILDORGANIZATIONPARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="6ddaf-154">CHILDORGANIZATIONPARTYNUMBER</span></span> | \> | <span data-ttu-id="6ddaf-155">msdyn\_childid.msdyn\_partynumber</span><span class="sxs-lookup"><span data-stu-id="6ddaf-155">msdyn\_childid.msdyn\_partynumber</span></span>
<span data-ttu-id="6ddaf-156">PARENTORGANIZATIONPARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="6ddaf-156">PARENTORGANIZATIONPARTYNUMBER</span></span> | \> | <span data-ttu-id="6ddaf-157">msdyn\_parentid.msdyn\_partynumber</span><span class="sxs-lookup"><span data-stu-id="6ddaf-157">msdyn\_parentid.msdyn\_partynumber</span></span>

## <a name="internal-organization"></a><span data-ttu-id="6ddaf-158">Intern organisation</span><span class="sxs-lookup"><span data-stu-id="6ddaf-158">Internal Organization</span></span>

<span data-ttu-id="6ddaf-159">Intern organisationsinformation i Common Data Service kommer från två entiteter **driftenhet** och **juridiska personer**.</span><span class="sxs-lookup"><span data-stu-id="6ddaf-159">Internal organization information in Common Data Service comes from two entities, **operating unit** and **legal entities**.</span></span>

<!-- ![architecture image](media/dual-write-operating-unit.png) -->

<!-- ![architecture image](media/dual-write-legal-entities.png) -->

### <a name="operating-unit"></a><span data-ttu-id="6ddaf-160">Driftenhet</span><span class="sxs-lookup"><span data-stu-id="6ddaf-160">Operating unit</span></span>

<span data-ttu-id="6ddaf-161">Källfält</span><span class="sxs-lookup"><span data-stu-id="6ddaf-161">Source field</span></span> | <span data-ttu-id="6ddaf-162">Mappningstyp</span><span class="sxs-lookup"><span data-stu-id="6ddaf-162">Map type</span></span> | <span data-ttu-id="6ddaf-163">Målfält</span><span class="sxs-lookup"><span data-stu-id="6ddaf-163">Destination field</span></span>
---|---|---
<span data-ttu-id="6ddaf-164">LANGUAGEID</span><span class="sxs-lookup"><span data-stu-id="6ddaf-164">LANGUAGEID</span></span> | \> | <span data-ttu-id="6ddaf-165">msdyn\_languageid</span><span class="sxs-lookup"><span data-stu-id="6ddaf-165">msdyn\_languageid</span></span>
<span data-ttu-id="6ddaf-166">NAMEALIAS</span><span class="sxs-lookup"><span data-stu-id="6ddaf-166">NAMEALIAS</span></span> | \> | <span data-ttu-id="6ddaf-167">msdyn\_namnalias</span><span class="sxs-lookup"><span data-stu-id="6ddaf-167">msdyn\_namealias</span></span>
<span data-ttu-id="6ddaf-168">NAMN</span><span class="sxs-lookup"><span data-stu-id="6ddaf-168">NAME</span></span> | \> | <span data-ttu-id="6ddaf-169">msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="6ddaf-169">msdyn\_name</span></span>
<span data-ttu-id="6ddaf-170">PARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="6ddaf-170">PARTYNUMBER</span></span> | \> | <span data-ttu-id="6ddaf-171">msdyn\_partynumber</span><span class="sxs-lookup"><span data-stu-id="6ddaf-171">msdyn\_partynumber</span></span>
<span data-ttu-id="6ddaf-172">OPERATINGUNITTYPE</span><span class="sxs-lookup"><span data-stu-id="6ddaf-172">OPERATINGUNITTYPE</span></span> | \>\> | <span data-ttu-id="6ddaf-173">msdyn\_type</span><span class="sxs-lookup"><span data-stu-id="6ddaf-173">msdyn\_type</span></span>

### <a name="legal-entity"></a><span data-ttu-id="6ddaf-174">Juridisk person</span><span class="sxs-lookup"><span data-stu-id="6ddaf-174">Legal entity</span></span>

<span data-ttu-id="6ddaf-175">Källfält</span><span class="sxs-lookup"><span data-stu-id="6ddaf-175">Source field</span></span> | <span data-ttu-id="6ddaf-176">Mappningstyp</span><span class="sxs-lookup"><span data-stu-id="6ddaf-176">Map type</span></span> | <span data-ttu-id="6ddaf-177">Målfält</span><span class="sxs-lookup"><span data-stu-id="6ddaf-177">Destination field</span></span>
---|---|---
<span data-ttu-id="6ddaf-178">NAMEALIAS</span><span class="sxs-lookup"><span data-stu-id="6ddaf-178">NAMEALIAS</span></span> | \> | <span data-ttu-id="6ddaf-179">msdyn\_namnalias</span><span class="sxs-lookup"><span data-stu-id="6ddaf-179">msdyn\_namealias</span></span>
<span data-ttu-id="6ddaf-180">LANGUAGEID</span><span class="sxs-lookup"><span data-stu-id="6ddaf-180">LANGUAGEID</span></span> | \> | <span data-ttu-id="6ddaf-181">msdyn\_languageid</span><span class="sxs-lookup"><span data-stu-id="6ddaf-181">msdyn\_languageid</span></span>
<span data-ttu-id="6ddaf-182">NAMN</span><span class="sxs-lookup"><span data-stu-id="6ddaf-182">NAME</span></span> | \> | <span data-ttu-id="6ddaf-183">msdyn\_name</span><span class="sxs-lookup"><span data-stu-id="6ddaf-183">msdyn\_name</span></span>
<span data-ttu-id="6ddaf-184">PARTYNUMBER</span><span class="sxs-lookup"><span data-stu-id="6ddaf-184">PARTYNUMBER</span></span> | \> | <span data-ttu-id="6ddaf-185">msdyn\_partynumber</span><span class="sxs-lookup"><span data-stu-id="6ddaf-185">msdyn\_partynumber</span></span>
<span data-ttu-id="6ddaf-186">ingen</span><span class="sxs-lookup"><span data-stu-id="6ddaf-186">none</span></span> | \>\> | <span data-ttu-id="6ddaf-187">msdyn\_type</span><span class="sxs-lookup"><span data-stu-id="6ddaf-187">msdyn\_type</span></span>
<span data-ttu-id="6ddaf-188">LEGALENTITYID</span><span class="sxs-lookup"><span data-stu-id="6ddaf-188">LEGALENTITYID</span></span> | \> | <span data-ttu-id="6ddaf-189">msdyn\_companycode</span><span class="sxs-lookup"><span data-stu-id="6ddaf-189">msdyn\_companycode</span></span>

## <a name="company"></a><span data-ttu-id="6ddaf-190">Företag</span><span class="sxs-lookup"><span data-stu-id="6ddaf-190">Company</span></span>

<span data-ttu-id="6ddaf-191">Ger dubbelriktad synkronisering av information om juridisk person (företag) mellan Finance and Operations och andra Dynamics 365-appar.</span><span class="sxs-lookup"><span data-stu-id="6ddaf-191">Provides bidirectional synchronization of legal entity (company) information between Finance and Operations and other Dynamics 365 apps.</span></span>

<!-- ![architecture image](media/dual-write-company.png) -->

<span data-ttu-id="6ddaf-192">Källfält</span><span class="sxs-lookup"><span data-stu-id="6ddaf-192">Source field</span></span> | <span data-ttu-id="6ddaf-193">Mappningstyp</span><span class="sxs-lookup"><span data-stu-id="6ddaf-193">Map type</span></span> | <span data-ttu-id="6ddaf-194">Målfält</span><span class="sxs-lookup"><span data-stu-id="6ddaf-194">Destination field</span></span>
---|---|---
<span data-ttu-id="6ddaf-195">NAMN</span><span class="sxs-lookup"><span data-stu-id="6ddaf-195">NAME</span></span> | = | <span data-ttu-id="6ddaf-196">cdm\_name</span><span class="sxs-lookup"><span data-stu-id="6ddaf-196">cdm\_name</span></span>
<span data-ttu-id="6ddaf-197">LEGALENTITYID</span><span class="sxs-lookup"><span data-stu-id="6ddaf-197">LEGALENTITYID</span></span> | = | <span data-ttu-id="6ddaf-198">cdm\_companycode</span><span class="sxs-lookup"><span data-stu-id="6ddaf-198">cdm\_companycode</span></span>
