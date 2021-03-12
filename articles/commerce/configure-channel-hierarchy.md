---
title: Konfigurera en kanal för att använda en kanalnavigeringshierarki
description: I det här avsnittet beskrivs hur du konfigurerar en kanal för att använda en navigeringshierarki för kanal i Microsoft Dynamics 365 Commerce.
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
ms.openlocfilehash: 3dcba743e6557b1bd366ac79ecb49ead831dceb4
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "5001035"
---
# <a name="configure-a-channel-to-use-a-channel-navigation-hierarchy"></a><span data-ttu-id="43dc5-103">Konfigurera en kanal för att använda en kanalnavigeringshierarki</span><span class="sxs-lookup"><span data-stu-id="43dc5-103">Configure a channel to use a channel navigation hierarchy</span></span>


[!include [banner](includes/banner.md)]

<span data-ttu-id="43dc5-104">I det här avsnittet beskrivs hur du konfigurerar en kanal för att använda en navigeringshierarki för kanal i Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="43dc5-104">This topic describes how to configure a channel to use a channel navigation hierarchy in Microsoft Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="43dc5-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="43dc5-105">Overview</span></span>

<span data-ttu-id="43dc5-106">Navigeringshierarkier för kanal ordnar produkter till kategorier, så att du kan bläddra på en näthandelssajt i POS.</span><span class="sxs-lookup"><span data-stu-id="43dc5-106">Channel navigation hierarchies organize products into categories so that the products can be browsed on an e-Commerce site or at points of sale (POS).</span></span> <span data-ttu-id="43dc5-107">Butiks- och onlinekanaler måste konfigureras med hierarkier för kanalnavigering.</span><span class="sxs-lookup"><span data-stu-id="43dc5-107">Retail and online channels must be configured with channel navigation hierarchies.</span></span>

## <a name="configure-the-channel"></a><span data-ttu-id="43dc5-108">Konfigurera kanalen</span><span class="sxs-lookup"><span data-stu-id="43dc5-108">Configure the channel</span></span>

<span data-ttu-id="43dc5-109">Om du vill konfigurera en kanal till att använda en navigeringshierarki för kanal följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="43dc5-109">To configure a channel to use a channel navigation hierarchy, follow these steps.</span></span>

1. <span data-ttu-id="43dc5-110">I Navigeringsfönstret, gå till **Moduler \> Butik och handel \> Kanalinställningar \> Kanalkategorier och produktattribut**.</span><span class="sxs-lookup"><span data-stu-id="43dc5-110">In the navigation pane, go to **Modules \> Retail and commerce \> Channel setup \> Channel categories and product attributes**.</span></span>
1. <span data-ttu-id="43dc5-111">Välj kanal som ska konfigureras.</span><span class="sxs-lookup"><span data-stu-id="43dc5-111">Select the channel to configure.</span></span>
1. <span data-ttu-id="43dc5-112">I åtgärdsfönstret, välj **ange attributmetadata**.</span><span class="sxs-lookup"><span data-stu-id="43dc5-112">On the action pane, select **Set attribute metadata**.</span></span>
1. <span data-ttu-id="43dc5-113">I listrutan **kategorihierarki** väljer du lämplig hierarki för kanalnavigering.</span><span class="sxs-lookup"><span data-stu-id="43dc5-113">In the **Category hierarchy** drop-down list, select the appropriate channel navigation hierarchy.</span></span>
1. <span data-ttu-id="43dc5-114">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="43dc5-114">On the action pane, select **Save**.</span></span>
1. <span data-ttu-id="43dc5-115">Under **attributgrupper**, lägg till alla attributgrupper som kommer att vara globala attribut för alla noder.</span><span class="sxs-lookup"><span data-stu-id="43dc5-115">Under **Attribute group**, add any attribute groups that will be global attributes for all nodes.</span></span>

<span data-ttu-id="43dc5-116">Följande bild visar hur du konfigurerar en kanal till att använda en navigeringshierarki för kanal.</span><span class="sxs-lookup"><span data-stu-id="43dc5-116">The following image shows how to configure a channel to use a channel navigation hierarchy.</span></span>

![Exempel på kanalkonfiguration](media/configure-channel-hierarchy-1.png)

## <a name="set-attribute-metadata"></a><span data-ttu-id="43dc5-118">Ställ in attributmetadata</span><span class="sxs-lookup"><span data-stu-id="43dc5-118">Set attribute metadata</span></span>

<span data-ttu-id="43dc5-119">Om du anger metadata för attributet kan attributens konfiguration konfigureras på varje nod.</span><span class="sxs-lookup"><span data-stu-id="43dc5-119">Setting the attribute metadata will allow configuration of attributes on each node.</span></span>

<span data-ttu-id="43dc5-120">Följ dessa steg för att ställa in metadata för attribut.</span><span class="sxs-lookup"><span data-stu-id="43dc5-120">To set attribute metadata, follow these steps.</span></span>

1. <span data-ttu-id="43dc5-121">I åtgärdsfönstret, välj **ange attributmetadata**.</span><span class="sxs-lookup"><span data-stu-id="43dc5-121">On the action pane, select **Set attribute metadata**.</span></span>
1. <span data-ttu-id="43dc5-122">Välj **kanalproduktattribut** för varje nod.</span><span class="sxs-lookup"><span data-stu-id="43dc5-122">For each node select **Channel product attributes**.</span></span>
1. <span data-ttu-id="43dc5-123">Ange **Visa attribut för kanal** till **Ja** och **Kan förfinas** till **Ja** för att aktivera förfinare på den kanalen.</span><span class="sxs-lookup"><span data-stu-id="43dc5-123">Set **Show attribute on channel** to **Yes** and **Can be refined** to **Yes**, to enable refiners on that channel.</span></span>
1. <span data-ttu-id="43dc5-124">När du har konfigurerat varje nod som önskas, i **åtgärdsfönstret**, välj knappen **spara** för att spara.</span><span class="sxs-lookup"><span data-stu-id="43dc5-124">After configuring each node as desired, on the **Action pane**, select the **Save** button to save.</span></span>
1. <span data-ttu-id="43dc5-125">Välj **X** i det övre högra hörnet om du vill stänga fönstret på sidan **Kanalkategorier och produktattribut**.</span><span class="sxs-lookup"><span data-stu-id="43dc5-125">Select the **X** in the top right corner to exit this screen back to the **Channel categories and product attributes** page.</span></span>

<span data-ttu-id="43dc5-126">Följande bild visar ett exempel på en uppsättning kanalproduktattribut som konfigurerats på en kanalkategorinod.</span><span class="sxs-lookup"><span data-stu-id="43dc5-126">The following image shows an example set of channel product attributes configured on a channel category node.</span></span>

![Kanalvärdena för en kanalkategorinod](media/configure-channel-hierarchy-2.png)

## <a name="publish-changes"></a><span data-ttu-id="43dc5-128">Publicera ändringar</span><span class="sxs-lookup"><span data-stu-id="43dc5-128">Publish changes</span></span>

<span data-ttu-id="43dc5-129">För att ändringar ska träda i kraft måste du publicera ändringarna.</span><span class="sxs-lookup"><span data-stu-id="43dc5-129">For changes to take effect, you will need to publish the changes.</span></span>

<span data-ttu-id="43dc5-130">Gör så här om du vill publicera ändringarna.</span><span class="sxs-lookup"><span data-stu-id="43dc5-130">To publish changes, follow these steps.</span></span>

1. <span data-ttu-id="43dc5-131">I åtgärdsfönstret, välj **publicera kanaluppdateringar**.</span><span class="sxs-lookup"><span data-stu-id="43dc5-131">On the action pane, select **Publish channel updates**.</span></span>
1. <span data-ttu-id="43dc5-132">I fönstret **publicera kanaluppdateringar** välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="43dc5-132">In the **Publish channel updates** pane, select **OK**.</span></span>

<span data-ttu-id="43dc5-133">Följande bild visar hur du publicerar kanaluppdateringar.</span><span class="sxs-lookup"><span data-stu-id="43dc5-133">The following image shows how to publish channel updates.</span></span>

![Publicera kanaluppdateringar](media/configure-channel-hierarchy-3.png)

## <a name="additional-resources"></a><span data-ttu-id="43dc5-135">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="43dc5-135">Additional resources</span></span>

[<span data-ttu-id="43dc5-136">Skapa en navigeringshierarki för kanal</span><span class="sxs-lookup"><span data-stu-id="43dc5-136">Create a channel navigation hierarchy</span></span>](create-channel-hierarchy.md)


