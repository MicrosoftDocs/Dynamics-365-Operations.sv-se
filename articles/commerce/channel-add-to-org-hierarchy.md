---
title: Lägga till kanal till organisationshierarkin
description: I det här avsnittet beskrivs hur du lägger till kanal till en organisatorisk hierarki i Microsoft Dynamics 365 Commerce.
author: samjarawan
manager: annbe
ms.date: 01/27/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: samjar
ms.search.validFrom: 2020-01-20
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: 297bd34f9bde23d5cc7de266b8e8f49b1a752662
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993712"
---
# <a name="add-a-channel-to-an-organizational-hierarchy"></a><span data-ttu-id="c2ab4-103">Lägga till kanal till organisationshierarkin</span><span class="sxs-lookup"><span data-stu-id="c2ab4-103">Add a channel to an organizational hierarchy</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="c2ab4-104">I det här avsnittet beskrivs hur du lägger till kanal till en organisatorisk hierarki i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="c2ab4-104">This topic describes how to add a channel to an organizational hierarchy in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="c2ab4-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="c2ab4-105">Overview</span></span>

<span data-ttu-id="c2ab4-106">Kanaler måste vara kopplade till en eller flera organisatoriska hierarkier.</span><span class="sxs-lookup"><span data-stu-id="c2ab4-106">Channels need to be associated with one or more organizational hierarchies.</span></span> <span data-ttu-id="c2ab4-107">Innan du skapar kanaler måste du bekräfta att dina organisatoriska hierarkier har ställts in.</span><span class="sxs-lookup"><span data-stu-id="c2ab4-107">Before creating channels, you need to confirm that your organizational hierarchies have been set up.</span></span>  

<span data-ttu-id="c2ab4-108">Se [organisationshierarkier](channels-org-hierarchies.md) för mer information om hur du skapar organisationshierarkier.</span><span class="sxs-lookup"><span data-stu-id="c2ab4-108">See [Organizational hierarchies](channels-org-hierarchies.md) for more details on how to create organizational hierarchies.</span></span>

## <a name="select-a-hierarchy"></a><span data-ttu-id="c2ab4-109">Välj en hierarki</span><span class="sxs-lookup"><span data-stu-id="c2ab4-109">Select a hierarchy</span></span>

<span data-ttu-id="c2ab4-110">Gör så här för att välja en hierarki:</span><span class="sxs-lookup"><span data-stu-id="c2ab4-110">To select a hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="c2ab4-111">I Navigeringsfönstret, gå till **Moduler \> Butik och handel \> Kanalsinställning \> Organisationshierarkier**.</span><span class="sxs-lookup"><span data-stu-id="c2ab4-111">In the navigation pane, go to **Modules \> Retail and commerce \> Channel Setup \> Organization hierarchies**.</span></span>
1. <span data-ttu-id="c2ab4-112">I listan väljer du den organisationshierarki som du vill lägga till kanalen i.</span><span class="sxs-lookup"><span data-stu-id="c2ab4-112">From the list, select the organization hierarchy that you'll be adding the channel to.</span></span>
1. <span data-ttu-id="c2ab4-113">Välj **Visa** för att visa information om hierarkin i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="c2ab4-113">On the action pane, select **View** to view hierarchy details.</span></span>

<span data-ttu-id="c2ab4-114">Följande bild visar information om organisationshierarkin för den valda hierarkin.</span><span class="sxs-lookup"><span data-stu-id="c2ab4-114">The following image shows organizational hierarchy details for the selected hierarchy.</span></span>

![Information om organisationshierarkin för den valda hierarkin](media/channel-add-to-org-hierarchy-1.png)

## <a name="add-a-channel-to-a-hierachy-node"></a><span data-ttu-id="c2ab4-116">Lägga till en kanal i en hierarkinod</span><span class="sxs-lookup"><span data-stu-id="c2ab4-116">Add a channel to a hierachy node</span></span>

<span data-ttu-id="c2ab4-117">Om du vill lägga till en kanal till en hierarkinod gör du följande.</span><span class="sxs-lookup"><span data-stu-id="c2ab4-117">To add a channel to a hierachy node, follow these steps.</span></span>

1. <span data-ttu-id="c2ab4-118">Klicka på **Redigera** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="c2ab4-118">On the action pane, select **Edit**.</span></span>
1. <span data-ttu-id="c2ab4-119">Välj den hierarkinod som du vill lägga till kanalen i, välj sedan **Infoga** i listrutan och välj **butikskanal**.</span><span class="sxs-lookup"><span data-stu-id="c2ab4-119">Select the hierachy node you want the channel added to, then from the **Insert** drop-down list, select **Retail Channel**.</span></span> 
1. <span data-ttu-id="c2ab4-120">Välj kanal att lägga till och välj sedan **OK**-knappen.</span><span class="sxs-lookup"><span data-stu-id="c2ab4-120">Select the channel to add, then select the **OK** button.</span></span>
1. <span data-ttu-id="c2ab4-121">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="c2ab4-121">On the action pane, select **Save**.</span></span>
1. <span data-ttu-id="c2ab4-122">I åtgärdsfönstret, välj **publicera** och ange **giltighetsdatum** som har passerat för att den här åtgärden ska börja gälla direkt.</span><span class="sxs-lookup"><span data-stu-id="c2ab4-122">On the action pane, select **Publish** and provide an **Effective date** in the past to have this action go into effect immediately.</span></span>

<span data-ttu-id="c2ab4-123">Följande bild visar hur du väljer en kanal som ska läggas till i en hierarkinod.</span><span class="sxs-lookup"><span data-stu-id="c2ab4-123">The following image shows how to select a channel to add to a hierarchy node.</span></span>

![Välj en kanal för att lägga till en hierarkinod](media/channel-add-to-org-hierarchy-2.png)

<span data-ttu-id="c2ab4-125">Följande bild visar en hierarki med olika kanaler tillagda.</span><span class="sxs-lookup"><span data-stu-id="c2ab4-125">The following image shows a hierarchy with various channels added.</span></span>

![En hierarki med olika kanaler tillagda](media/channel-add-to-org-hierarchy-3.png)

## <a name="additional-resources"></a><span data-ttu-id="c2ab4-127">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="c2ab4-127">Additional resources</span></span>

[<span data-ttu-id="c2ab4-128">Översikt över kanaler</span><span class="sxs-lookup"><span data-stu-id="c2ab4-128">Channels overview</span></span>](channels-overview.md)

[<span data-ttu-id="c2ab4-129">Förutsättningar för att ställa in kanaler</span><span class="sxs-lookup"><span data-stu-id="c2ab4-129">Channel setup prerequisites</span></span>](channels-prerequisites.md)

[<span data-ttu-id="c2ab4-130">Organisationer och organisationshierarkier – översikt</span><span class="sxs-lookup"><span data-stu-id="c2ab4-130">Organizations and organizational hierarchies overview</span></span>](../fin-ops-core/fin-ops/organization-administration/organizations-organizational-hierarchies.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="c2ab4-131">Planera en organisationshierarki</span><span class="sxs-lookup"><span data-stu-id="c2ab4-131">Plan your organizational hierarchy</span></span>](../fin-ops-core/fin-ops/organization-administration/plan-organizational-hierarchy.md?toc=/dynamics365/commerce/toc.json)

[<span data-ttu-id="c2ab4-132">Organisationshierarkier</span><span class="sxs-lookup"><span data-stu-id="c2ab4-132">Organization hierarchies</span></span>](channels-org-hierarchies.md)

[<span data-ttu-id="c2ab4-133">Ställa in en butikskanal</span><span class="sxs-lookup"><span data-stu-id="c2ab4-133">Set up a retail channel</span></span>](channel-setup-retail.md)
    
[<span data-ttu-id="c2ab4-134">Ställ in en onlinekanal</span><span class="sxs-lookup"><span data-stu-id="c2ab4-134">Set up an online channel</span></span>](channel-setup-online.md)
