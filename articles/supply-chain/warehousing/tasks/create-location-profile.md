---
title: Skapa en platsprofil
description: Det här avsnittet innehåller information om hur du skapar en platsprofil i Dynamics 365 for Finance and Operations.
author: ShylaThompson
manager: AnnBe
ms.date: 07/29/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocationProfile
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Distribution
ms.author: mirzaab
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 46aa1001c21ae39c158062444303ca02c0f41a45
ms.sourcegitcommit: a368682f9cf3897347d155f1a2d4b33e555cc2c4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 08/08/2019
ms.locfileid: "1866989"
---
# <a name="create-a-location-profile"></a><span data-ttu-id="b4318-103">Skapa en platsprofil</span><span class="sxs-lookup"><span data-stu-id="b4318-103">Create a location profile</span></span>

[!include [task guide banner](../../includes/task-guide-banner.md)]

<span data-ttu-id="b4318-104">Det här avsnittet innehåller information om hur du skapar en platsprofil i Dynamics 365 for Finance and Operations.</span><span class="sxs-lookup"><span data-stu-id="b4318-104">This topic explains how to create a location profile in Dynamics 365 for Finance and Operations.</span></span> <span data-ttu-id="b4318-105">Varje plats på lagerstället måste ha en platsprofil associerad som beskriver egenskaperna för platsen, till exempel om blandade artiklar tillåts för platsen.</span><span class="sxs-lookup"><span data-stu-id="b4318-105">Every location in the warehouse needs to have a location profile associated with it that describes the properties of the location, for example, whether the location allows mixed items.</span></span> <span data-ttu-id="b4318-106">I den här proceduren skapar vi en profil för en plats som inte kräver kontroll av registreringsskylt.</span><span class="sxs-lookup"><span data-stu-id="b4318-106">In this procedure we’ll create a profile for a location that doesn’t require license plate control.</span></span> <span data-ttu-id="b4318-107">Vi ska aktivera blandade artiklar och blandad lagerstatus, samt tillåta rullande inventering.</span><span class="sxs-lookup"><span data-stu-id="b4318-107">We’ll enable mixed items, and mixed inventory statuses, and allow cycle counting.</span></span> <span data-ttu-id="b4318-108">Du kan använda den här proceduren i demonstrationsdataföretaget USMF.</span><span class="sxs-lookup"><span data-stu-id="b4318-108">You can use this procedure in the USMF demo data company.</span></span>


1. <span data-ttu-id="b4318-109">I navigeringsfönstret, gå till **Moduler > Lagerstyrning > Inställningar > Lagerställe > Platsprofiler**.</span><span class="sxs-lookup"><span data-stu-id="b4318-109">In the navigation pane, go to **Modules > Warehouse management > Setup > Warehouse > Location profiles**.</span></span>
2. <span data-ttu-id="b4318-110">Välj **Ny**.</span><span class="sxs-lookup"><span data-stu-id="b4318-110">Select **New**.</span></span>
3. <span data-ttu-id="b4318-111">Skriv ett värde i fältet **Platsprofil-ID.**</span><span class="sxs-lookup"><span data-stu-id="b4318-111">In the **Location profile ID** field, type a value.</span></span>
4. <span data-ttu-id="b4318-112">Skriv ett värde i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="b4318-112">In the **Name** field, type a value.</span></span>
5. <span data-ttu-id="b4318-113">Ange eller välj ett värde i fältet **Platsformat.**</span><span class="sxs-lookup"><span data-stu-id="b4318-113">In the **Location format** field, enter or select a value.</span></span>
6. <span data-ttu-id="b4318-114">Ange eller välj ett värde i fältet **Platstyp.**</span><span class="sxs-lookup"><span data-stu-id="b4318-114">In the **Location type** field, enter or select a value.</span></span>
7. <span data-ttu-id="b4318-115">Ange eller välj ett värde i fältet **ID för lastkajshanteringsprofil**.</span><span class="sxs-lookup"><span data-stu-id="b4318-115">In the **Dock management profile ID** field, enter or select a value.</span></span>
8. <span data-ttu-id="b4318-116">Välj **Ja** i fältet **Tillåt blandade artiklar**.</span><span class="sxs-lookup"><span data-stu-id="b4318-116">Select **Yes** in the **Allow mixed items** field.</span></span>
9. <span data-ttu-id="b4318-117">Välj **Ja** i fältet **Tillåt blandade lagerstatusar**.</span><span class="sxs-lookup"><span data-stu-id="b4318-117">Select **Yes** in the **Allow mixed inventory statuses** field.</span></span>
10. <span data-ttu-id="b4318-118">Välj **Ja** i fältet **Tillåt rullande inventering**.</span><span class="sxs-lookup"><span data-stu-id="b4318-118">Select **Yes** in the **Allow cycle counting** field.</span></span>
11. <span data-ttu-id="b4318-119">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="b4318-119">Select **Save**.</span></span>

