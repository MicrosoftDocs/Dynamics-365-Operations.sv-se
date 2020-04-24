---
title: Ansvariga underhållsarbetare
description: I det här avsnittet beskrivs hur du ställer in ansvariga underhållsarbetare i tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 07/26/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-07-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 0b5f83474e56c996a40bdbdf7d3a7c8d495429c6
ms.sourcegitcommit: 4f9912439ff78acf0c754d5bff972c4b85763093
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/02/2020
ms.locfileid: "3208948"
---
# <a name="responsible-maintenance-workers"></a><span data-ttu-id="7fb0e-103">Ansvariga underhållsarbetare</span><span class="sxs-lookup"><span data-stu-id="7fb0e-103">Responsible maintenance workers</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="7fb0e-104">Ansvariga underhållsarbetare kan relateras till tillgångstyper, tillgångar, funktionsplatser, kategorier för underhållsjobbtyper, underhållsjobbtyper, underhållsjobbtypvarianter och handel.</span><span class="sxs-lookup"><span data-stu-id="7fb0e-104">Responsible maintenance workers can be related to asset types, assets, functional locations, maintenance job type categories, maintenance job types, maintenance job type variants, and trades.</span></span> <span data-ttu-id="7fb0e-105">De kan användas på arbetsorder och underhållsbegäranden för att indikera en preferens för underhållsarbetare som ska ansvara för en arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="7fb0e-105">They can be used on work orders and maintenance requests to indicate a preference about the maintenance workers who should be responsible for a work order.</span></span> <span data-ttu-id="7fb0e-106">(Dessa underhållsarbetare är dock inte nödvändigtvis samma arbetstagare som är schemalagda för att utföra arbetsordern.) Användning av den här funktionen är valfri.</span><span class="sxs-lookup"><span data-stu-id="7fb0e-106">(However, those maintenance workers aren't necessarily the same workers who are scheduled to carry out the work order.) Use of this functionality is optional.</span></span> <span data-ttu-id="7fb0e-107">Det kan till exempel användas för att välja ansvariga arbetare eller arbetargrupper för specifika arbetstyper eller arbetsområden.</span><span class="sxs-lookup"><span data-stu-id="7fb0e-107">For example, it can be used to select responsible workers or worker groups for specific work types or work areas.</span></span>

<span data-ttu-id="7fb0e-108">Under en livscykel för arbetsorder eller en livscykel för underhållsbegäran, ansvarig underhållsarbetare  kan ändras eller uppdateras.</span><span class="sxs-lookup"><span data-stu-id="7fb0e-108">During a work order lifecycle or a maintenance request lifecycle, responsible maintenance workers can be changed or updated.</span></span> <span data-ttu-id="7fb0e-109">Den här ändringen eller uppdateringen kan vara relaterade till exempelvis en ändring i livscykeltillståndet för underhållbegäran eller livscykelstatus för arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="7fb0e-109">This change or update might be related to, for example, a change in the maintenance request lifecycle state or the work order lifecycle state.</span></span>

<span data-ttu-id="7fb0e-110">Inställningen på sidan **ansvariga underhållsarbetare** används *inte* vid schemaläggning av arbetsorder.</span><span class="sxs-lookup"><span data-stu-id="7fb0e-110">The setup on the **Responsible maintenance workers** page is *not* used during work order scheduling.</span></span>

> [!NOTE]
> <span data-ttu-id="7fb0e-111">I tillgångshantering kan du också ställa in *önskade* underhållsarbetare som kan allokeras till arbetsorder under arbetsorderplanering.</span><span class="sxs-lookup"><span data-stu-id="7fb0e-111">In Asset Management, you can also set up *preferred* maintenance workers who might be allocated to work orders during work order scheduling.</span></span>

<span data-ttu-id="7fb0e-112">Innan du kan ställa in ansvariga underhållsarbetare måste du ställa in arbetare och underhållsgrupper som ska vara tillgängliga för val.</span><span class="sxs-lookup"><span data-stu-id="7fb0e-112">Before you can set up responsible maintenance workers, you must set up the workers and maintenance worker groups that should be available for selection.</span></span> <span data-ttu-id="7fb0e-113">Information om hur du ställer in arbetare och underhållsarbetsgrupper finns i [Underhållsarbetare och arbetargrupper](../setup-for-objects/workers-and-worker-groups.md).</span><span class="sxs-lookup"><span data-stu-id="7fb0e-113">For information about how to set up workers and maintenance worker groups, see [Maintenance workers and worker groups](../setup-for-objects/workers-and-worker-groups.md).</span></span>

## <a name="set-up-responsible-maintenance-workers"></a><span data-ttu-id="7fb0e-114">Ställ in ansvariga underhållsarbetare</span><span class="sxs-lookup"><span data-stu-id="7fb0e-114">Set up responsible maintenance workers</span></span>

1. <span data-ttu-id="7fb0e-115">Välj **tillgångshantering** \> **inställning** \> **arbetare** \> **ansvariga underhållsarbetare**.</span><span class="sxs-lookup"><span data-stu-id="7fb0e-115">Select **Asset management** \> **Setup** \> **Workers** \> **Responsible maintenance workers**.</span></span>
2. <span data-ttu-id="7fb0e-116">Välj **Ny** för att skapa en post.</span><span class="sxs-lookup"><span data-stu-id="7fb0e-116">Select **New** to create a record.</span></span>
3. <span data-ttu-id="7fb0e-117">Skapa först en standardinställning för ansvarig underhållsarbetare eller ansvarig underhållsarbetsgrupp där du endast anger fältet **ansvarig underhållsarbetargrupp** och/eller **ansvarig arbetare**.</span><span class="sxs-lookup"><span data-stu-id="7fb0e-117">First create a default responsible maintenance worker or responsible maintenance worker group setup, where you set only the **Responsible maintenance worker group** field and/or the **Responsible worker** field.</span></span> <span data-ttu-id="7fb0e-118">Lämna de återstående fälten tomma.</span><span class="sxs-lookup"><span data-stu-id="7fb0e-118">Leave the remaining fields blank.</span></span> <span data-ttu-id="7fb0e-119">Den här standardinställningen kommer att användas vid schemaläggning av arbetsorder om ingen annan, mer specifik kombination matchar innehållet i arbetsordern.</span><span class="sxs-lookup"><span data-stu-id="7fb0e-119">This default setup will be used during work order scheduling if no other, more specific combination matches the contents of the work order.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7fb0e-120">När en underhållsbegäran skapas, när en ansvarig underhållsarbetare eller ansvarig underhållsarbetsgrupp görs tillgänglig för markering på sidan **alla underhållsbegäran**, går tillgångshantering igenom alla ansvariga underhållsarbetsposter för att söka efter en möjlig matchning.</span><span class="sxs-lookup"><span data-stu-id="7fb0e-120">During creation of a maintenance request, when a responsible maintenance worker or responsible maintenance worker group is made available for selection on the **All maintenance requests** page, Asset Management goes through all responsible maintenance worker records to check for a possible match.</span></span> <span data-ttu-id="7fb0e-121">Den kontrollerar alltid den mest specifika kombinationen först.</span><span class="sxs-lookup"><span data-stu-id="7fb0e-121">It always checks the most specific combination first.</span></span> <span data-ttu-id="7fb0e-122">Med andra ord söker tillgångshantering först efter en matchning för fältet **handel**.</span><span class="sxs-lookup"><span data-stu-id="7fb0e-122">In other words, Asset Management first checks for a match for the **Trade** field.</span></span> <span data-ttu-id="7fb0e-123">Om ingen matchning hittas söker den efter en matchning för fältet **underhållsjobbtypvariant** och så vidare.</span><span class="sxs-lookup"><span data-stu-id="7fb0e-123">If no match is found, it checks for a match for the **Maintenance job type variant** field.</span></span> <span data-ttu-id="7fb0e-124">Om ingen matchning hittas söker den efter en matchning för fältet **underhållsjobbtyp** och så vidare.</span><span class="sxs-lookup"><span data-stu-id="7fb0e-124">If no match is found, it checks for a match for the **Maintenance job type** field, and so on.</span></span> <span data-ttu-id="7fb0e-125">Som du kan se i layouten på sidan, innebär detta beteende att, för att hitta den mest specifika kombinationen, kontrollerar tillgångshanteraren varje post från höger till vänster för en match (första **handel**, sedan **underhållsjobbtypvariant**, sedan **underhållsjobbtyp**, sedan **kategori för underhållsjobbtyp**, sedan **sedan funktionsplats**,sedan **tillgång** och slutligen**tillgångstyp**).</span><span class="sxs-lookup"><span data-stu-id="7fb0e-125">As you can see in the layout of the page, this behavior means that, to find the most specific combination, Asset Management checks each record from right to left for a match (first **Trade**, then **Maintenance job type variant**, then **Maintenance job type**, then **Maintenance job type category**, then **Functional location**, then **Asset**, and finally **Asset type**).</span></span> <span data-ttu-id="7fb0e-126">Om ingen matchning hittas används den standardpost som inte har några val i dessa sju fält.</span><span class="sxs-lookup"><span data-stu-id="7fb0e-126">If no match is found, the default record that has no selections in those seven fields is used.</span></span>

<span data-ttu-id="7fb0e-127">Följande illustration visar ett exempel på sidan **Ansvariga underhållsarbetare**.</span><span class="sxs-lookup"><span data-stu-id="7fb0e-127">The following illustration shows an example of the **Responsible maintenance workers** page.</span></span>

![Sidan Ansvariga underhållsarbetare](media/08-setup-for-requests.png)
