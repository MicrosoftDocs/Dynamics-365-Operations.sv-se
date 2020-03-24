---
title: Ställa in organisationshierarkier
description: I det här avsnittet beskrivs hur du ställer in organisationshierarkier i Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 29d4b686cbb66715196fca06e4642fbb8a337ace
ms.sourcegitcommit: 141e0239b6310ab4a6a775bc0997120c31634f79
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/10/2020
ms.locfileid: "3113861"
---
# <a name="set-up-organization-hierarchies"></a><span data-ttu-id="0c030-103">Ställa in organisationshierarkier</span><span class="sxs-lookup"><span data-stu-id="0c030-103">Set up organization hierarchies</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="0c030-104">I det här avsnittet beskrivs hur du ställer in organisationshierarkier i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="0c030-104">This topic describes how to set up organization hierarchies in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="0c030-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="0c030-105">Overview</span></span>

<span data-ttu-id="0c030-106">Innan du skapar kanaler måste du se till att du har ställt in dina organisationshierarkier.</span><span class="sxs-lookup"><span data-stu-id="0c030-106">Before creating channels, you'll want to ensure you have set up your organization hierarchies.</span></span>

<span data-ttu-id="0c030-107">Du kan använda organisationshierarkier för att visa och skapa en rapport från olika perspektiv av din verksamhet.</span><span class="sxs-lookup"><span data-stu-id="0c030-107">You can use organization hierarchies to view and report on your business from various perspectives.</span></span> <span data-ttu-id="0c030-108">Du kan till exempel skapa en hierarki för momsrapportering, juridisk rapportering eller lagstadgad rapportering.</span><span class="sxs-lookup"><span data-stu-id="0c030-108">For example, you can set up one hierarchy for tax, legal, or statutory reporting.</span></span> <span data-ttu-id="0c030-109">Du kan ställa in en annan hierarki om du vill rapportera ekonomisk information som inte krävs lagligen, men som används för intern rapportering.</span><span class="sxs-lookup"><span data-stu-id="0c030-109">You can then set up another hierarchy to report financial information that is not legally required, but that is used for internal reporting.</span></span>

<span data-ttu-id="0c030-110">Innan du skapar en organisationshierarki måste du skapa organisationer.</span><span class="sxs-lookup"><span data-stu-id="0c030-110">Before you create an organization hierarchy, you must create organizations.</span></span> <span data-ttu-id="0c030-111">Mer information finns i [Skapa juridisk personer](channels-legal-entities.md) eller [Skapa driftenheter](../fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit.md?toc=/dynamics365/commerce/toc.json).</span><span class="sxs-lookup"><span data-stu-id="0c030-111">For more information, see [Create legal entities](channels-legal-entities.md) or [Create operating units](../fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit.md?toc=/dynamics365/commerce/toc.json).</span></span>


<span data-ttu-id="0c030-112">Mer information finns i följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="0c030-112">For more information, see the following topics.</span></span>
- [<span data-ttu-id="0c030-113">Organisationer och organisationshierarkier – översikt</span><span class="sxs-lookup"><span data-stu-id="0c030-113">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)
- [<span data-ttu-id="0c030-114">Planera en organisationshierarki</span><span class="sxs-lookup"><span data-stu-id="0c030-114">Plan your organization hierarchy</span></span>](../fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy.md?toc=/dynamics365/commerce/toc.json)
- [<span data-ttu-id="0c030-115">Skapa en organisationshierarki</span><span class="sxs-lookup"><span data-stu-id="0c030-115">Create an organization hierarchy</span></span>](../fin-ops-core/fin-ops/organization-administration/tasks/create-organization-hierarchy.md?toc=/dynamics365/commerce/toc.json)

## <a name="create-an-organizational-hierarchy"></a><span data-ttu-id="0c030-116">Skapa en organisationshierarki</span><span class="sxs-lookup"><span data-stu-id="0c030-116">Create an organizational hierarchy</span></span>

<span data-ttu-id="0c030-117">Följ stegen nedan om du vill skapa en organisationshierarki för kanaler.</span><span class="sxs-lookup"><span data-stu-id="0c030-117">To create an organizational hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="0c030-118">I Navigeringsfönstret, gå till **Moduler \> Butik och handel \> Kanalsinställning \> Organisationshierarkier**.</span><span class="sxs-lookup"><span data-stu-id="0c030-118">In the navigation pane, go to **Modules \> Retail and commerce \> Channel Setup \> Organization hierarchies**.</span></span>
1. <span data-ttu-id="0c030-119">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="0c030-119">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="0c030-120">I fältet **Namn** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="0c030-120">In the **Name** field, enter a value.</span></span>
1. <span data-ttu-id="0c030-121">I avsnittet **Syfte**, klicka på **Tilldela syfte**.</span><span class="sxs-lookup"><span data-stu-id="0c030-121">In the **Purpose** section, select **Assign purpose**.</span></span>
1. <span data-ttu-id="0c030-122">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="0c030-122">In the list, find and select the desired record.</span></span> <span data-ttu-id="0c030-123">Välj ett syfte att tilldela till din organisationshierarki.</span><span class="sxs-lookup"><span data-stu-id="0c030-123">Select a purpose to assign to your organization hierarchy.</span></span>
1. <span data-ttu-id="0c030-124">Klicka på **Lägg till** i avsnittet **Tilldelade hierarkier**.</span><span class="sxs-lookup"><span data-stu-id="0c030-124">In the **Assigned hierarchies** section, select **Add**.</span></span>
1. <span data-ttu-id="0c030-125">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="0c030-125">In the list, mark the selected row.</span></span> <span data-ttu-id="0c030-126">Hitta hierarki som du just skapat.</span><span class="sxs-lookup"><span data-stu-id="0c030-126">Find the hierarchy you just created.</span></span>
1. <span data-ttu-id="0c030-127">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="0c030-127">Select **OK**.</span></span>

<span data-ttu-id="0c030-128">Följande bild visar ett exempel på en organisationshierarki som skapats för en fiktiv "Adventure Works"-uppsättning butiker.</span><span class="sxs-lookup"><span data-stu-id="0c030-128">The following image shows an example organizational hierarchy created for a fictitious "Adventure Works" set of stores.</span></span>

![Exempel på organisationshierarki](media/organizational-hierarchies.png)

### <a name="add-organizations-to-a-hierarchy"></a><span data-ttu-id="0c030-130">Lägg till organisationer i hierarkin</span><span class="sxs-lookup"><span data-stu-id="0c030-130">Add organizations to a hierarchy</span></span>

<span data-ttu-id="0c030-131">Om du vill lägga till organisationer till en hierarki gör du följande.</span><span class="sxs-lookup"><span data-stu-id="0c030-131">To add organizations to a hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="0c030-132">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="0c030-132">In the list, find and select the desired record.</span></span> <span data-ttu-id="0c030-133">Välj hierarki.</span><span class="sxs-lookup"><span data-stu-id="0c030-133">Select your hierarchy.</span></span>
1. <span data-ttu-id="0c030-134">Klicka på **Visa** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="0c030-134">On the action pane, select **View**.</span></span>
1. <span data-ttu-id="0c030-135">Lägg till fler organisationer efter behov.</span><span class="sxs-lookup"><span data-stu-id="0c030-135">Add organizations, as necessary.</span></span>
1. <span data-ttu-id="0c030-136">Om du vill lägga till en organisation, välj **redigera** och sedan **infoga**.</span><span class="sxs-lookup"><span data-stu-id="0c030-136">To add an organization, select **Edit** and then select **Insert**.</span></span> <span data-ttu-id="0c030-137">När du är klar med ändringar, kan du spara ett utkast och publicera ändringarna.</span><span class="sxs-lookup"><span data-stu-id="0c030-137">When you are done making changes you can save a draft and publish the changes.</span></span>

<span data-ttu-id="0c030-138">Följande bild visar en juridisk person som lagts till i hierarkistrukturen med fyra kostnadsställen som har lagts till för kanalerna "köpcentrum", "outlet", "online" och "kundtjänst".</span><span class="sxs-lookup"><span data-stu-id="0c030-138">The following image shows a legal entity added at the hierarchy root with four cost centers added for "Mall", "Outlet", "Online" and "Call Center" channels.</span></span> <span data-ttu-id="0c030-139">Olika butiks-, kundtjänst- och onlinekanaler kan sedan läggas till i var och en.</span><span class="sxs-lookup"><span data-stu-id="0c030-139">Various retail, call center and online channels can then be added to each.</span></span>

![Exempel på hierarkidesigner](media/hierarchy-designer.png)

## <a name="additional-resources"></a><span data-ttu-id="0c030-141">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="0c030-141">Additional resources</span></span>

[<span data-ttu-id="0c030-142">Organisationer och organisationshierarkier – översikt</span><span class="sxs-lookup"><span data-stu-id="0c030-142">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="0c030-143">Planera en organisationshierarki</span><span class="sxs-lookup"><span data-stu-id="0c030-143">Plan your organizational hierarchy</span></span>](../fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="0c030-144">Skapa juridiska personer</span><span class="sxs-lookup"><span data-stu-id="0c030-144">Create legal entities</span></span>](channels-legal-entities.md)

[<span data-ttu-id="0c030-145">Skapa driftenheter</span><span class="sxs-lookup"><span data-stu-id="0c030-145">Create operating units</span></span>](../fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="0c030-146">Översikt över kanaler</span><span class="sxs-lookup"><span data-stu-id="0c030-146">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="0c030-147">Förutsättningar för att ställa in kanaler</span><span class="sxs-lookup"><span data-stu-id="0c030-147">Channel setup prerequisites</span></span>](channels-prerequisites.md)
