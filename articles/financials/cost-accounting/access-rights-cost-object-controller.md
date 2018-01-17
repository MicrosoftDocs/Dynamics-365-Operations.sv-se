---
title: "Definiera åtkomsträttigheter för kostnadsobjektcontroller"
description: "Det här avsnittet innehåller information om åtkomsträttigheter för kostnadsobjektcontroller."
author: AndersGirke
manager: AnnBe
ms.date: 06/24/2017
ms.topic: article
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: CAMCostControlWorkspace, CAMParameters
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations, Core
ms.custom: 
ms.assetid: 
ms.search.region: global
ms.search.industry: Manufacturing
ms.author: yuyus
ms.search.validFrom: 2016-11-30
ms.dyn365.ops.version: Version 1611
ms.translationtype: HT
ms.sourcegitcommit: 029511634e56aec7fdd91bad9441cd12951fbd8d
ms.openlocfilehash: d3489e4cc5c9cbf1f3ac89350a811fd99c7d8ce3
ms.contentlocale: sv-se
ms.lasthandoff: 01/17/2018

---

# <a name="access-rights-of-a-cost-object-controller"></a><span data-ttu-id="f4e99-103">Åtkomsträttigheter för en kostnadsobjektcontroller</span><span class="sxs-lookup"><span data-stu-id="f4e99-103">Access rights of a cost object controller</span></span>

[!include[banner](../includes/banner.md)]

<span data-ttu-id="f4e99-104">Arbetsytan **Kostnadskontroll** är en central plats där chefer kan visa prestanda för deras kostnadsobjekt.</span><span class="sxs-lookup"><span data-stu-id="f4e99-104">The **Cost control** workspace is a central point where managers can view the performance of their cost objects.</span></span> <span data-ttu-id="f4e99-105">Den här arbetsytan låter chefer använda kostnadsredovisningsdata även om de inte är kostnadsrevisorer.</span><span class="sxs-lookup"><span data-stu-id="f4e99-105">This workspace lets managers consume Cost accounting data even though they aren't cost accountants.</span></span> <span data-ttu-id="f4e99-106">Av säkerhetsskäl ska chefer endast tillåtas se kostnadsredovisningsdata som hör till ett visst kostnadsobjekt som de ansvarar för.</span><span class="sxs-lookup"><span data-stu-id="f4e99-106">For security reasons, managers should be allowed to see only the Cost accounting data that is related to the specific cost objects that they are responsible for.</span></span>

<span data-ttu-id="f4e99-107">Det finns fyra unika roller i kostnadsredovisning.</span><span class="sxs-lookup"><span data-stu-id="f4e99-107">There are four unique roles in Cost accounting.</span></span>

| <span data-ttu-id="f4e99-108">Rollnamn</span><span class="sxs-lookup"><span data-stu-id="f4e99-108">Role name</span></span>               | <span data-ttu-id="f4e99-109">Licens</span><span class="sxs-lookup"><span data-stu-id="f4e99-109">License</span></span>      |
|-------------------------|--------------|
| <span data-ttu-id="f4e99-110">Kostnadsredovisningschef</span><span class="sxs-lookup"><span data-stu-id="f4e99-110">Cost accounting manager</span></span> | <span data-ttu-id="f4e99-111">Aktivitet</span><span class="sxs-lookup"><span data-stu-id="f4e99-111">Activity</span></span>     |
| <span data-ttu-id="f4e99-112">Kostnadsredovisare</span><span class="sxs-lookup"><span data-stu-id="f4e99-112">Cost accountant</span></span>         | <span data-ttu-id="f4e99-113">Operations</span><span class="sxs-lookup"><span data-stu-id="f4e99-113">Operations</span></span>   |
| <span data-ttu-id="f4e99-114">Ansvarig kostnadsredovisare</span><span class="sxs-lookup"><span data-stu-id="f4e99-114">Cost accountant clerk</span></span>   | <span data-ttu-id="f4e99-115">Operations</span><span class="sxs-lookup"><span data-stu-id="f4e99-115">Operations</span></span>   |
| <span data-ttu-id="f4e99-116">Kostnadsobjektcontroller</span><span class="sxs-lookup"><span data-stu-id="f4e99-116">Cost object controller</span></span>  | <span data-ttu-id="f4e99-117">Teammedlemmar</span><span class="sxs-lookup"><span data-stu-id="f4e99-117">Team members</span></span> |

<span data-ttu-id="f4e99-118">Det här avsnittet beskriver hur du tilldelar rollen **kostnadsobjektcontroller** till en chef.</span><span class="sxs-lookup"><span data-stu-id="f4e99-118">This topic explains how to assign the **Cost object controller** role to a manager.</span></span>

<span data-ttu-id="f4e99-119">När rollen **kostnadsobjektcontroller** har tilldelats en chef kan denne utföra följande uppgifter:</span><span class="sxs-lookup"><span data-stu-id="f4e99-119">When the **Cost object controller** role is assigned to a manager, the manager can perform the following tasks:</span></span>

- <span data-ttu-id="f4e99-120">Åtkomst till arbetsytan **kostnadskontroll** (i klienten).</span><span class="sxs-lookup"><span data-stu-id="f4e99-120">Access the **Cost control** workspace (in the client).</span></span>

    - <span data-ttu-id="f4e99-121">Gå igenom och ha visningsåtkomst till sidorna som stöder detaljgranskningsupplevelsen.</span><span class="sxs-lookup"><span data-stu-id="f4e99-121">Drill through and have view access to the pages that support the drill-through experience.</span></span>

- <span data-ttu-id="f4e99-122">Åtkomst till arbetsytan **kostnadskontroll** (i mobilapplikationen).</span><span class="sxs-lookup"><span data-stu-id="f4e99-122">Access the **Cost control** workspace (in the mobile application).</span></span>

> [!NOTE]
> <span data-ttu-id="f4e99-123">Rollen **kostnadsobjektcontroller** styr inte vilka objekt som användaren kan komma åt och visa data för.</span><span class="sxs-lookup"><span data-stu-id="f4e99-123">The **Cost object controller** role doesn't control which cost objects the user can access and view data for.</span></span> <span data-ttu-id="f4e99-124">Säkerhet på radnivå tillhandahålls via dimensionshierarkier och i Hierarki för åtkomstlista.</span><span class="sxs-lookup"><span data-stu-id="f4e99-124">Row-level security is provided via dimension hierarchies and the Access list hierarchy.</span></span>

## <a name="grant-access-rights"></a><span data-ttu-id="f4e99-125">Bevilja åtkomstbehörighet</span><span class="sxs-lookup"><span data-stu-id="f4e99-125">Grant access rights</span></span>
<span data-ttu-id="f4e99-126">I följande exempel visas hur en dimensionshierarki kan se ut.</span><span class="sxs-lookup"><span data-stu-id="f4e99-126">The following example shows what a dimension hierarchy can look like.</span></span>

<span data-ttu-id="f4e99-127">**Detaljer om dimensionshierarki**</span><span class="sxs-lookup"><span data-stu-id="f4e99-127">**Dimension hierarchy details**</span></span>

| <span data-ttu-id="f4e99-128">Dimensionshierarkins namn</span><span class="sxs-lookup"><span data-stu-id="f4e99-128">Dimension hierarchy name</span></span> | <span data-ttu-id="f4e99-129">Dimension</span><span class="sxs-lookup"><span data-stu-id="f4e99-129">Dimension</span></span>    | <span data-ttu-id="f4e99-130">Namn på typ av dimensionshierarki</span><span class="sxs-lookup"><span data-stu-id="f4e99-130">Dimension hierarchy type name</span></span>      | <span data-ttu-id="f4e99-131">Hierarki för åtkomstlista</span><span class="sxs-lookup"><span data-stu-id="f4e99-131">Access list hierarchy</span></span> |
|--------------------------|--------------|------------------------------------|-----------------------|
| <span data-ttu-id="f4e99-132">Organisation</span><span class="sxs-lookup"><span data-stu-id="f4e99-132">Organization</span></span>             | <span data-ttu-id="f4e99-133">Kostnadsställen</span><span class="sxs-lookup"><span data-stu-id="f4e99-133">Cost centers</span></span> | <span data-ttu-id="f4e99-134">Hierarki för dimensionsklassificering</span><span class="sxs-lookup"><span data-stu-id="f4e99-134">Dimension classification hierarchy</span></span> | <span data-ttu-id="f4e99-135">**Ja**</span><span class="sxs-lookup"><span data-stu-id="f4e99-135">**Yes**</span></span>               |

<span data-ttu-id="f4e99-136">Du kan använda snabbfliken **användare** i hierarkidesignern för att infoga minst ett användar-ID på varje nod.</span><span class="sxs-lookup"><span data-stu-id="f4e99-136">You can use the **Users** FastTab in the hierarchy designer to insert one or more user IDs on each node.</span></span>

|                                   | <span data-ttu-id="f4e99-137">Användare</span><span class="sxs-lookup"><span data-stu-id="f4e99-137">Users</span></span>            | <span data-ttu-id="f4e99-138">Dimensionsmedlemsintervall</span><span class="sxs-lookup"><span data-stu-id="f4e99-138">Dimension member ranges</span></span>   |                         |
|-----------------------------------|------------------|---------------------------|-------------------------|
| <span data-ttu-id="f4e99-139">**Noder**</span><span class="sxs-lookup"><span data-stu-id="f4e99-139">**Nodes**</span></span>                         | <span data-ttu-id="f4e99-140">**Användar-ID**</span><span class="sxs-lookup"><span data-stu-id="f4e99-140">**User ID**</span></span>      | <span data-ttu-id="f4e99-141">**Från dimensionsmedlem**</span><span class="sxs-lookup"><span data-stu-id="f4e99-141">**From dimension member**</span></span> | <span data-ttu-id="f4e99-142">**Till dimensionsmedlem**</span><span class="sxs-lookup"><span data-stu-id="f4e99-142">**To dimension member**</span></span> |
| <span data-ttu-id="f4e99-143">Organisation</span><span class="sxs-lookup"><span data-stu-id="f4e99-143">Organization</span></span>                      | <span data-ttu-id="f4e99-144">Benjamin Claire</span><span class="sxs-lookup"><span data-stu-id="f4e99-144">Benjamin, Claire</span></span> |                           |                         |
| <span data-ttu-id="f4e99-145">&nbsp;&nbsp;Admin</span><span class="sxs-lookup"><span data-stu-id="f4e99-145">&nbsp;&nbsp;Admin</span></span>                 | <span data-ttu-id="f4e99-146">april</span><span class="sxs-lookup"><span data-stu-id="f4e99-146">April</span></span>            |                           |                         |
| <span data-ttu-id="f4e99-147">&nbsp;&nbsp;&nbsp;&nbsp;Finansiellt</span><span class="sxs-lookup"><span data-stu-id="f4e99-147">&nbsp;&nbsp;&nbsp;&nbsp;Finance</span></span>   | <span data-ttu-id="f4e99-148">Alicia</span><span class="sxs-lookup"><span data-stu-id="f4e99-148">Alicia</span></span>           | <span data-ttu-id="f4e99-149">CC002</span><span class="sxs-lookup"><span data-stu-id="f4e99-149">CC002</span></span>                     | <span data-ttu-id="f4e99-150">CC003</span><span class="sxs-lookup"><span data-stu-id="f4e99-150">CC003</span></span>                   |
|                                   |                  | <span data-ttu-id="f4e99-151">CC007</span><span class="sxs-lookup"><span data-stu-id="f4e99-151">CC007</span></span>                     | <span data-ttu-id="f4e99-152">CC007</span><span class="sxs-lookup"><span data-stu-id="f4e99-152">CC007</span></span>                   |
| <span data-ttu-id="f4e99-153">&nbsp;&nbsp;&nbsp;&nbsp;Personal</span><span class="sxs-lookup"><span data-stu-id="f4e99-153">&nbsp;&nbsp;&nbsp;&nbsp;HR</span></span>        | <span data-ttu-id="f4e99-154">Arnie</span><span class="sxs-lookup"><span data-stu-id="f4e99-154">Arnie</span></span>            | <span data-ttu-id="f4e99-155">CC001</span><span class="sxs-lookup"><span data-stu-id="f4e99-155">CC001</span></span>                     | <span data-ttu-id="f4e99-156">CC001</span><span class="sxs-lookup"><span data-stu-id="f4e99-156">CC001</span></span>                   |
| <span data-ttu-id="f4e99-157">&nbsp;&nbsp;Produktion</span><span class="sxs-lookup"><span data-stu-id="f4e99-157">&nbsp;&nbsp;Production</span></span>            | <span data-ttu-id="f4e99-158">David</span><span class="sxs-lookup"><span data-stu-id="f4e99-158">David</span></span>            |                           |                         |
| <span data-ttu-id="f4e99-159">&nbsp;&nbsp;&nbsp;&nbsp;Paketering</span><span class="sxs-lookup"><span data-stu-id="f4e99-159">&nbsp;&nbsp;&nbsp;&nbsp;Packaging</span></span> | <span data-ttu-id="f4e99-160">Ellen</span><span class="sxs-lookup"><span data-stu-id="f4e99-160">Ellen</span></span>            | <span data-ttu-id="f4e99-161">CC005</span><span class="sxs-lookup"><span data-stu-id="f4e99-161">CC005</span></span>                     | <span data-ttu-id="f4e99-162">CC005</span><span class="sxs-lookup"><span data-stu-id="f4e99-162">CC005</span></span>                   |
| <span data-ttu-id="f4e99-163">&nbsp;&nbsp;&nbsp;&nbsp;Sammansättning</span><span class="sxs-lookup"><span data-stu-id="f4e99-163">&nbsp;&nbsp;&nbsp;&nbsp;Assembly</span></span>  | <span data-ttu-id="f4e99-164">Chris</span><span class="sxs-lookup"><span data-stu-id="f4e99-164">Chris</span></span>            | <span data-ttu-id="f4e99-165">CC006</span><span class="sxs-lookup"><span data-stu-id="f4e99-165">CC006</span></span>                     | <span data-ttu-id="f4e99-166">CC006</span><span class="sxs-lookup"><span data-stu-id="f4e99-166">CC006</span></span>                   |

> [!NOTE]
> <span data-ttu-id="f4e99-167">Kostnadsrevisorerna ska tilldelas till den översta nivån i hierarkin, så att de kan se alla poster i kostnadsredovisningen.</span><span class="sxs-lookup"><span data-stu-id="f4e99-167">Cost accountants should be assigned to the top level of the hierarchy, so that they can see all entries in Cost accounting.</span></span>

<span data-ttu-id="f4e99-168">Innan Hierarki för åtkomstlista kan användas måste alternativet **Aktivera visningsåtkomst för kostnadsobjektets dimensionsmedlemmar** anges till **Ja** på fliken **Allmänt** på fliken **kostnadsredovisningsparametrar** på sidan (**kostnadsredovisning** > **inställningar** > **parametrar**).</span><span class="sxs-lookup"><span data-stu-id="f4e99-168">Before the Access list hierarchy and its security settings can be applied, the **Enable view access for cost object dimension members** option must be set to **Yes** on the **General** tab of the **Cost accounting parameters** page (**Cost accounting** > **Setup** > **Parameters**).</span></span>

<span data-ttu-id="f4e99-169">Inställningar för Hierarki för åtkomstlista används för att bestämma vilka data som visas i följande områden:</span><span class="sxs-lookup"><span data-stu-id="f4e99-169">The settings for the Access list hierarchy are used to control the data that is shown in following areas:</span></span>

- <span data-ttu-id="f4e99-170">Arbetsytan **kostnadskontroll** (i klienten):</span><span class="sxs-lookup"><span data-stu-id="f4e99-170">**Cost control** workspace (in the client):</span></span>

    - <span data-ttu-id="f4e99-171">Data på de sidor som används för detaljgranskning</span><span class="sxs-lookup"><span data-stu-id="f4e99-171">Data on the pages that are used for drill-through</span></span>

- <span data-ttu-id="f4e99-172">Arbetsytan **kostnadskontroll** (i mobilapplikationen):</span><span class="sxs-lookup"><span data-stu-id="f4e99-172">**Cost control** workspace (in the mobile application):</span></span>

    - <span data-ttu-id="f4e99-173">Saldon i kort</span><span class="sxs-lookup"><span data-stu-id="f4e99-173">Balances in cards</span></span>

- <span data-ttu-id="f4e99-174">Microsoft Power BI</span><span class="sxs-lookup"><span data-stu-id="f4e99-174">Microsoft Power BI:</span></span>

    - <span data-ttu-id="f4e99-175">Data som visas i Power BI-visualiseringar</span><span class="sxs-lookup"><span data-stu-id="f4e99-175">Data that is shown in Power BI visualizations</span></span>
    - <span data-ttu-id="f4e99-176">Data Power BI-visualiseringar som bäddas in i Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, klient</span><span class="sxs-lookup"><span data-stu-id="f4e99-176">Data Power BI visualizations that are embedded in the Microsoft Dynamics 365 for Finance and Operations, Enterprise edition, client</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="f4e99-177">Innan Hierarki för åtkomstlista kan påverka data i Power BI, måste hierarkiåtkomst och säkerhet på radnivå i Power BI anges.</span><span class="sxs-lookup"><span data-stu-id="f4e99-177">Before the Access list hierarchy can affect data in Power BI, the Access list hierarchy and row-level security in Power BI must be paired.</span></span> <span data-ttu-id="f4e99-178">Mer information finns i [ställa in säkerhet för kostnadsredovisningens innehållspaket](../../dev-itpro/analytics/setup-security-cost-accounting-content-pack.md).</span><span class="sxs-lookup"><span data-stu-id="f4e99-178">For more information, see [Set up security for Cost accounting content pack](../../dev-itpro/analytics/setup-security-cost-accounting-content-pack.md).</span></span>
> - <span data-ttu-id="f4e99-179">Det här avsnittet visar kraven som måste vara på plats innan du kan använda arbetsytan **kostnadskontroll**.</span><span class="sxs-lookup"><span data-stu-id="f4e99-179">This topic shows the prerequisites that must be in place before you can use the **Cost control** workspace.</span></span>

<span data-ttu-id="f4e99-180">Se även</span><span class="sxs-lookup"><span data-stu-id="f4e99-180">See also</span></span>

- [<span data-ttu-id="f4e99-181">Arbetsyta för kostnadskontroll</span><span class="sxs-lookup"><span data-stu-id="f4e99-181">Cost control workspace</span></span>](cost-control-workspace.md)
- [<span data-ttu-id="f4e99-182">Dimensionshierarki</span><span class="sxs-lookup"><span data-stu-id="f4e99-182">Dimension hierarchy</span></span>](dimension-hierarchy.md)
- [<span data-ttu-id="f4e99-183">Ställa in säkerhet för kostnadsredovisningsinnehållspaket</span><span class="sxs-lookup"><span data-stu-id="f4e99-183">Set up security for Cost accounting content pack</span></span>](../../dev-itpro/analytics/setup-security-cost-accounting-content-pack.md)

