---
title: Ställa in organisationshierarkier
description: I det här avsnittet beskrivs hur du ställer in organisationshierarkier i Microsoft Dynamics 365 Commerce.
author: samjarawan
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 4238d1aa277bf2f1df30825ef20dbf3095d13ebc
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/31/2021
ms.locfileid: "5800577"
---
# <a name="set-up-organization-hierarchies"></a><span data-ttu-id="f2677-103">Ställa in organisationshierarkier</span><span class="sxs-lookup"><span data-stu-id="f2677-103">Set up organization hierarchies</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="f2677-104">I det här avsnittet beskrivs hur du ställer in organisationshierarkier i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="f2677-104">This topic describes how to set up organization hierarchies in Microsoft Dynamics 365 Commerce.</span></span>

<span data-ttu-id="f2677-105">Innan du skapar kanaler måste du se till att du har ställt in dina organisationshierarkier.</span><span class="sxs-lookup"><span data-stu-id="f2677-105">Before creating channels, you'll want to ensure you have set up your organization hierarchies.</span></span>

<span data-ttu-id="f2677-106">Du kan använda organisationshierarkier för att visa och skapa en rapport från olika perspektiv av din verksamhet.</span><span class="sxs-lookup"><span data-stu-id="f2677-106">You can use organization hierarchies to view and report on your business from various perspectives.</span></span> <span data-ttu-id="f2677-107">Du kan till exempel skapa en hierarki för momsrapportering, juridisk rapportering eller lagstadgad rapportering.</span><span class="sxs-lookup"><span data-stu-id="f2677-107">For example, you can set up one hierarchy for tax, legal, or statutory reporting.</span></span> <span data-ttu-id="f2677-108">Du kan ställa in en annan hierarki om du vill rapportera ekonomisk information som inte krävs lagligen, men som används för intern rapportering.</span><span class="sxs-lookup"><span data-stu-id="f2677-108">You can then set up another hierarchy to report financial information that is not legally required, but that is used for internal reporting.</span></span>

<span data-ttu-id="f2677-109">Innan du skapar en organisationshierarki måste du skapa organisationer.</span><span class="sxs-lookup"><span data-stu-id="f2677-109">Before you create an organization hierarchy, you must create organizations.</span></span> <span data-ttu-id="f2677-110">Mer information finns i [Skapa juridisk personer](channels-legal-entities.md) eller [Skapa driftenheter](../fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit.md?toc=/dynamics365/commerce/toc.json).</span><span class="sxs-lookup"><span data-stu-id="f2677-110">For more information, see [Create legal entities](channels-legal-entities.md) or [Create operating units](../fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit.md?toc=/dynamics365/commerce/toc.json).</span></span>


<span data-ttu-id="f2677-111">Mer information finns i följande avsnitt.</span><span class="sxs-lookup"><span data-stu-id="f2677-111">For more information, see the following topics.</span></span>
- [<span data-ttu-id="f2677-112">Organisationer och organisationshierarkier – översikt</span><span class="sxs-lookup"><span data-stu-id="f2677-112">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)
- [<span data-ttu-id="f2677-113">Planera en organisationshierarki</span><span class="sxs-lookup"><span data-stu-id="f2677-113">Plan your organization hierarchy</span></span>](../fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy.md?toc=/dynamics365/commerce/toc.json)
- [<span data-ttu-id="f2677-114">Skapa en organisationshierarki</span><span class="sxs-lookup"><span data-stu-id="f2677-114">Create an organization hierarchy</span></span>](../fin-ops-core/fin-ops/organization-administration/tasks/create-organization-hierarchy.md?toc=/dynamics365/commerce/toc.json)

## <a name="create-an-organizational-hierarchy"></a><span data-ttu-id="f2677-115">Skapa en organisationshierarki</span><span class="sxs-lookup"><span data-stu-id="f2677-115">Create an organizational hierarchy</span></span>

<span data-ttu-id="f2677-116">Följ stegen nedan om du vill skapa en organisationshierarki för kanaler.</span><span class="sxs-lookup"><span data-stu-id="f2677-116">To create an organizational hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="f2677-117">I Navigeringsfönstret, gå till **Moduler \> Butik och handel \> Kanalsinställning \> Organisationshierarkier**.</span><span class="sxs-lookup"><span data-stu-id="f2677-117">In the navigation pane, go to **Modules \> Retail and commerce \> Channel Setup \> Organization hierarchies**.</span></span>
1. <span data-ttu-id="f2677-118">Klicka på **Ny** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="f2677-118">On the action pane, select **New**.</span></span>
1. <span data-ttu-id="f2677-119">I fältet **Namn** anger du ett värde.</span><span class="sxs-lookup"><span data-stu-id="f2677-119">In the **Name** field, enter a value.</span></span>
1. <span data-ttu-id="f2677-120">I avsnittet **Syfte**, klicka på **Tilldela syfte**.</span><span class="sxs-lookup"><span data-stu-id="f2677-120">In the **Purpose** section, select **Assign purpose**.</span></span>
1. <span data-ttu-id="f2677-121">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="f2677-121">In the list, find and select the desired record.</span></span> <span data-ttu-id="f2677-122">Välj ett syfte att tilldela till din organisationshierarki.</span><span class="sxs-lookup"><span data-stu-id="f2677-122">Select a purpose to assign to your organization hierarchy.</span></span>
1. <span data-ttu-id="f2677-123">Klicka på **Lägg till** i avsnittet **Tilldelade hierarkier**.</span><span class="sxs-lookup"><span data-stu-id="f2677-123">In the **Assigned hierarchies** section, select **Add**.</span></span>
1. <span data-ttu-id="f2677-124">Markera vald rad i listan.</span><span class="sxs-lookup"><span data-stu-id="f2677-124">In the list, mark the selected row.</span></span> <span data-ttu-id="f2677-125">Hitta hierarki som du just skapat.</span><span class="sxs-lookup"><span data-stu-id="f2677-125">Find the hierarchy you just created.</span></span>
1. <span data-ttu-id="f2677-126">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="f2677-126">Select **OK**.</span></span>

<span data-ttu-id="f2677-127">Följande bild visar ett exempel på en organisationshierarki som skapats för en fiktiv "Adventure Works"-uppsättning butiker.</span><span class="sxs-lookup"><span data-stu-id="f2677-127">The following image shows an example organizational hierarchy created for a fictitious "Adventure Works" set of stores.</span></span>

![Exempel på organisationshierarki](media/organizational-hierarchies.png)

### <a name="add-organizations-to-a-hierarchy"></a><span data-ttu-id="f2677-129">Lägg till organisationer i hierarkin</span><span class="sxs-lookup"><span data-stu-id="f2677-129">Add organizations to a hierarchy</span></span>

<span data-ttu-id="f2677-130">Om du vill lägga till organisationer till en hierarki gör du följande.</span><span class="sxs-lookup"><span data-stu-id="f2677-130">To add organizations to a hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="f2677-131">Hitta och markera önskad post i listan.</span><span class="sxs-lookup"><span data-stu-id="f2677-131">In the list, find and select the desired record.</span></span> <span data-ttu-id="f2677-132">Välj hierarki.</span><span class="sxs-lookup"><span data-stu-id="f2677-132">Select your hierarchy.</span></span>
1. <span data-ttu-id="f2677-133">Klicka på **Visa** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="f2677-133">On the action pane, select **View**.</span></span>
1. <span data-ttu-id="f2677-134">Lägg till fler organisationer efter behov.</span><span class="sxs-lookup"><span data-stu-id="f2677-134">Add organizations, as necessary.</span></span>
1. <span data-ttu-id="f2677-135">Om du vill lägga till en organisation, välj **redigera** och sedan **infoga**.</span><span class="sxs-lookup"><span data-stu-id="f2677-135">To add an organization, select **Edit** and then select **Insert**.</span></span> <span data-ttu-id="f2677-136">När du är klar med ändringar, kan du spara ett utkast och publicera ändringarna.</span><span class="sxs-lookup"><span data-stu-id="f2677-136">When you are done making changes you can save a draft and publish the changes.</span></span>

<span data-ttu-id="f2677-137">Följande bild visar en juridisk person som lagts till i hierarkistrukturen med fyra kostnadsställen som har lagts till för kanalerna "köpcentrum", "outlet", "online" och "kundtjänst".</span><span class="sxs-lookup"><span data-stu-id="f2677-137">The following image shows a legal entity added at the hierarchy root with four cost centers added for "Mall", "Outlet", "Online" and "Call Center" channels.</span></span> <span data-ttu-id="f2677-138">Olika butiks-, kundtjänst- och onlinekanaler kan sedan läggas till i var och en.</span><span class="sxs-lookup"><span data-stu-id="f2677-138">Various retail, call center and online channels can then be added to each.</span></span>

![Exempel på hierarkidesigner](media/hierarchy-designer.png)

## <a name="additional-resources"></a><span data-ttu-id="f2677-140">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="f2677-140">Additional resources</span></span>

[<span data-ttu-id="f2677-141">Organisationer och organisationshierarkier – översikt</span><span class="sxs-lookup"><span data-stu-id="f2677-141">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="f2677-142">Planera en organisationshierarki</span><span class="sxs-lookup"><span data-stu-id="f2677-142">Plan your organizational hierarchy</span></span>](../fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="f2677-143">Skapa juridiska personer</span><span class="sxs-lookup"><span data-stu-id="f2677-143">Create legal entities</span></span>](channels-legal-entities.md)

[<span data-ttu-id="f2677-144">Skapa driftenheter</span><span class="sxs-lookup"><span data-stu-id="f2677-144">Create operating units</span></span>](../fin-ops-core/fin-ops/organization-administration/tasks/create-operating-unit.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="f2677-145">Översikt över kanaler</span><span class="sxs-lookup"><span data-stu-id="f2677-145">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="f2677-146">Förutsättningar för att ställa in kanaler</span><span class="sxs-lookup"><span data-stu-id="f2677-146">Channel setup prerequisites</span></span>](channels-prerequisites.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
