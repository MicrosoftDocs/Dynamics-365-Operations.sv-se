---
title: Transportföretagsgrupper
description: I det här avsnittet beskrivs hur du ställer in data för transportföretagsgrupper.
author: Henrikan
manager: ''
ms.date: 10/30/2020
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: TMSCarrierGroup
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.search.industry: Distribution
ms.author: henrikan
ms.search.validFrom: 2020-10-30
ms.dyn365.ops.version: 10.0.15
ms.openlocfilehash: 95517153dda06cecf8e57b1f9b080aa07966c111
ms.sourcegitcommit: eaf330dbee1db96c20d5ac479f007747bea079eb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2021
ms.locfileid: "5247273"
---
# <a name="carrier-groups"></a><span data-ttu-id="5537f-103">Transportföretagsgrupper</span><span class="sxs-lookup"><span data-stu-id="5537f-103">Carrier groups</span></span>

<span data-ttu-id="5537f-104">En transportföretagsgrupp är en samling transportföretag och transportföretagstjänster.</span><span class="sxs-lookup"><span data-stu-id="5537f-104">A carrier group is a collection of shipping carriers and carrier services.</span></span> <span data-ttu-id="5537f-105">Varje transportföretagsgrupp anger den ordningsföljd för transportföretag och transportföretagstjänster som tillhör till den.</span><span class="sxs-lookup"><span data-stu-id="5537f-105">Each carrier group specifies the preferred sequence for the shipping carriers and carrier services that belong to it.</span></span>

<span data-ttu-id="5537f-106">Om det finns flera transportföretag och transportföretagstjänster för samma flödessegment kan du ange en transportföretagsgrupp i stället för ett specifikt transportföretag och transportföretagstjänst i färdplanen eller ruttguiden.</span><span class="sxs-lookup"><span data-stu-id="5537f-106">When multiple shipping carriers and carrier services exist for the same route segment, you can specify a carrier group instead of a specific shipping carrier and carrier service in the route plan or route guide.</span></span>

## <a name="create-a-carrier-group"></a><span data-ttu-id="5537f-107">Skapa en transportföretagsgrupp</span><span class="sxs-lookup"><span data-stu-id="5537f-107">Create a carrier group</span></span>

1. <span data-ttu-id="5537f-108">Gå till **Transporthantering &gt; Inställningar &gt; Transportföretag &gt; Transportföretagsgrupp**.</span><span class="sxs-lookup"><span data-stu-id="5537f-108">Go to **Transportation management &gt; Setup &gt; Carriers &gt; Carrier group**.</span></span>
1. <span data-ttu-id="5537f-109">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="5537f-109">Select **New**.</span></span>
1. <span data-ttu-id="5537f-110">I fältet **transportföretagsgrupp** anger du en unik identifierare (ID) för gruppen.</span><span class="sxs-lookup"><span data-stu-id="5537f-110">In the **Carrier group** field, enter a unique identifier (ID) for the group.</span></span>
1. <span data-ttu-id="5537f-111">I fältet **Namn** ange ett beskrivande namn för gruppen.</span><span class="sxs-lookup"><span data-stu-id="5537f-111">In the **Name** field, enter a descriptive name for the group.</span></span>
1. <span data-ttu-id="5537f-112">På snabbfliken **Detaljer** lägger du till en rad och väljer ett transportföretag och en transportföretagstjänst för det.</span><span class="sxs-lookup"><span data-stu-id="5537f-112">On the **Details** FastTab, add a row, and select a shipping carrier and a carrier service for it.</span></span> <span data-ttu-id="5537f-113">Upprepa det här steget tills du har lagt till så många transportföretag som behövs för gruppen.</span><span class="sxs-lookup"><span data-stu-id="5537f-113">Repeat this step until you've added as many carriers as you require for the group.</span></span>
1. <span data-ttu-id="5537f-114">Stäng sidan.</span><span class="sxs-lookup"><span data-stu-id="5537f-114">Close the page.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]