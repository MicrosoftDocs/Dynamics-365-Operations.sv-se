---
title: Ytterligare platszoner
description: Det här ämnet ger en översikt över de nya platszoner som har lagts till i Microsoft Dynamics 365 Supply Chain Management.
author: Mirzaab
manager: AnnBe
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations, Supply Chain Management
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 9727187ad555f9e3d09beed3f3447a22c29ed22a
ms.sourcegitcommit: a7a7303004620d2e9cef0642b16d89163911dbb4
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/01/2020
ms.locfileid: "3530177"
---
# <a name="additional-location-zones"></a><span data-ttu-id="b8f46-103">Ytterligare platszoner</span><span class="sxs-lookup"><span data-stu-id="b8f46-103">Additional location zones</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="b8f46-104">Tre nya zonfält finns tillgängliga i Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="b8f46-104">Three new zone fields are available in Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="b8f46-105">Lagerchefer kan använda dem för att definiera ytterligare lagerorganisationer eller layouter.</span><span class="sxs-lookup"><span data-stu-id="b8f46-105">Warehouse managers can use them to define additional warehouse organizations or layouts.</span></span> <span data-ttu-id="b8f46-106">De nya zonfälten kan ställas in antingen manuellt eller med hjälp guiden **platsinställning**.</span><span class="sxs-lookup"><span data-stu-id="b8f46-106">The new zone fields can be set either manually or by using the **Location setup** wizard.</span></span> <span data-ttu-id="b8f46-107">De kan användas i alla frågor eller filter som använder tabellen lagerställen.</span><span class="sxs-lookup"><span data-stu-id="b8f46-107">They can be used in any query or filtering that uses the Locations table.</span></span>

<span data-ttu-id="b8f46-108">Det krävs inga ytterligare inställningar för att använda zonfälten.</span><span class="sxs-lookup"><span data-stu-id="b8f46-108">No additional setup is required to use the zone fields.</span></span>

## <a name="turn-on-the-additional-location-zone-feature"></a><span data-ttu-id="b8f46-109">Aktivera funktionen ytterligare platszoner</span><span class="sxs-lookup"><span data-stu-id="b8f46-109">Turn on the Additional location zone feature</span></span>

<span data-ttu-id="b8f46-110">Innan du kan använda funktionen *Ytterligare platszon* den aktiveras i ditt system.</span><span class="sxs-lookup"><span data-stu-id="b8f46-110">Before you can use the *Additional location zone* feature, it must be turned on in your system.</span></span> <span data-ttu-id="b8f46-111">Administratörer kan använda inställningarna [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs.</span><span class="sxs-lookup"><span data-stu-id="b8f46-111">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="b8f46-112">I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="b8f46-112">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="b8f46-113">**Modul:** *Lagerstyrning*</span><span class="sxs-lookup"><span data-stu-id="b8f46-113">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="b8f46-114">**Funktionsnamn:** *Ytterligare platszon*</span><span class="sxs-lookup"><span data-stu-id="b8f46-114">**Feature name:** *Additional location zone*</span></span>

## <a name="use-location-zones"></a><span data-ttu-id="b8f46-115">Använda platszoner</span><span class="sxs-lookup"><span data-stu-id="b8f46-115">Use location zones</span></span>

1. <span data-ttu-id="b8f46-116">Gå till **Lagerstyrning \> Inställningar \> Lagerställe \> Guide för platsinställning**.</span><span class="sxs-lookup"><span data-stu-id="b8f46-116">Go to **Warehouse management \> Setup \> Warehouse \> Location setup wizard**.</span></span>
2. <span data-ttu-id="b8f46-117">Ange följande värden.</span><span class="sxs-lookup"><span data-stu-id="b8f46-117">Set the following values:</span></span>

    - <span data-ttu-id="b8f46-118">I fältet **Lagerställe**, välj _62_.</span><span class="sxs-lookup"><span data-stu-id="b8f46-118">In the **Warehouse** field, select _62_.</span></span>
    - <span data-ttu-id="b8f46-119">I fältet **Zon-ID** välj _FLOOR_.</span><span class="sxs-lookup"><span data-stu-id="b8f46-119">In the **Zone ID** field, select _FLOOR_.</span></span>
    - <span data-ttu-id="b8f46-120">I fältet **Ytterligare Zon 1** välj _PICKZONE1_.</span><span class="sxs-lookup"><span data-stu-id="b8f46-120">In the **Additional Zone 1** field, select _PICKZONE1_.</span></span>
    - <span data-ttu-id="b8f46-121">I fältet **Ytterligare Zon 2** välj _WEBSHOP1_.</span><span class="sxs-lookup"><span data-stu-id="b8f46-121">In the **Additional Zone 2** field, select _WEBSHOP1_.</span></span>
    - <span data-ttu-id="b8f46-122">I fältet **Platsprofil-ID**, välj _FLOOR_.</span><span class="sxs-lookup"><span data-stu-id="b8f46-122">In the **Location profile ID** field, select _FLOOR_.</span></span>

3. <span data-ttu-id="b8f46-123">Välj rad **Våning**.</span><span class="sxs-lookup"><span data-stu-id="b8f46-123">Select the **Floor** line.</span></span>
4. <span data-ttu-id="b8f46-124">I fältet **Från nummer**, ange _1_.</span><span class="sxs-lookup"><span data-stu-id="b8f46-124">In the **From number** field, enter _1_.</span></span> <span data-ttu-id="b8f46-125">I fältet **Till nummer**, ange _3_.</span><span class="sxs-lookup"><span data-stu-id="b8f46-125">In the **To number** field, enter _3_.</span></span>
5. <span data-ttu-id="b8f46-126">Välj rad **Gång**.</span><span class="sxs-lookup"><span data-stu-id="b8f46-126">Select the **Aisle** line.</span></span>
6. <span data-ttu-id="b8f46-127">I fältet **Från nummer**, ange _1_.</span><span class="sxs-lookup"><span data-stu-id="b8f46-127">In the **From number** field, enter _1_.</span></span> <span data-ttu-id="b8f46-128">I fältet **Till nummer**, ange _5_.</span><span class="sxs-lookup"><span data-stu-id="b8f46-128">In the **To number** field, enter _5_.</span></span>
7. <span data-ttu-id="b8f46-129">Markera **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="b8f46-129">Select **Create**.</span></span>
8. <span data-ttu-id="b8f46-130">Du får meddelanden om att nya platser har lagts till.</span><span class="sxs-lookup"><span data-stu-id="b8f46-130">You receive messages that state that new locations have been added.</span></span> <span data-ttu-id="b8f46-131">Välj knappen **Visa meddelanden** om du vill visa meddelandena.</span><span class="sxs-lookup"><span data-stu-id="b8f46-131">Select the **Show messages** button to view the messages.</span></span>
9. <span data-ttu-id="b8f46-132">Gå till **Lagerstyrning \> Inställningar \> Lagerställe \> Platser**.</span><span class="sxs-lookup"><span data-stu-id="b8f46-132">Go to **Warehouse management \> Setup \> Warehouse \> Locations**.</span></span> <span data-ttu-id="b8f46-133">De nya platserna visas i listan och alla zonfält är tillgängliga (det vill säga det befintliga zonfältet och de nya ytterligare zonfälten).</span><span class="sxs-lookup"><span data-stu-id="b8f46-133">The new locations appear in the list, and all zone fields are available (that is, the existing zone field and the new additional zone fields).</span></span>
