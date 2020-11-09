---
title: Ytterligare platszoner
description: Det här ämnet ger en översikt över de nya platszoner som har lagts till i Microsoft Dynamics 365 Supply Chain Management.
author: Mirzaab
manager: tfehr
ms.date: 07/01/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: WHSLocationBuild, WHSZone
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Core, Operations, Supply Chain Management
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 6cf81939989b8faffcda51bbbd5bc6b27aec7eea
ms.sourcegitcommit: a36a4f9915ae3eb36bf8220111cf1486387713d9
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/16/2020
ms.locfileid: "4016318"
---
# <a name="additional-location-zones"></a><span data-ttu-id="58150-103">Ytterligare platszoner</span><span class="sxs-lookup"><span data-stu-id="58150-103">Additional location zones</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="58150-104">Tre nya zonfält finns tillgängliga i Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="58150-104">Three new zone fields are available in Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="58150-105">Lagerchefer kan använda dem för att definiera ytterligare lagerorganisationer eller layouter.</span><span class="sxs-lookup"><span data-stu-id="58150-105">Warehouse managers can use them to define additional warehouse organizations or layouts.</span></span> <span data-ttu-id="58150-106">De nya zonfälten kan ställas in antingen manuellt eller med hjälp guiden **platsinställning**.</span><span class="sxs-lookup"><span data-stu-id="58150-106">The new zone fields can be set either manually or by using the **Location setup** wizard.</span></span> <span data-ttu-id="58150-107">De kan användas i alla frågor eller filter som använder tabellen lagerställen.</span><span class="sxs-lookup"><span data-stu-id="58150-107">They can be used in any query or filtering that uses the Locations table.</span></span>

<span data-ttu-id="58150-108">Det krävs inga ytterligare inställningar för att använda zonfälten.</span><span class="sxs-lookup"><span data-stu-id="58150-108">No additional setup is required to use the zone fields.</span></span>

## <a name="turn-on-the-additional-location-zone-feature"></a><span data-ttu-id="58150-109">Aktivera funktionen ytterligare platszoner</span><span class="sxs-lookup"><span data-stu-id="58150-109">Turn on the Additional location zone feature</span></span>

<span data-ttu-id="58150-110">Innan du kan använda funktionen *Ytterligare platszon* den aktiveras i ditt system.</span><span class="sxs-lookup"><span data-stu-id="58150-110">Before you can use the *Additional location zone* feature, it must be turned on in your system.</span></span> <span data-ttu-id="58150-111">Administratörer kan använda inställningarna [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs.</span><span class="sxs-lookup"><span data-stu-id="58150-111">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="58150-112">I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="58150-112">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="58150-113">**Modul:** *Lagerstyrning*</span><span class="sxs-lookup"><span data-stu-id="58150-113">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="58150-114">**Funktionsnamn:** *Ytterligare platszon*</span><span class="sxs-lookup"><span data-stu-id="58150-114">**Feature name:** *Additional location zone*</span></span>

## <a name="use-location-zones"></a><span data-ttu-id="58150-115">Använda platszoner</span><span class="sxs-lookup"><span data-stu-id="58150-115">Use location zones</span></span>

1. <span data-ttu-id="58150-116">Gå till **Lagerstyrning \> Inställningar \> Lagerställe \> Guide för platsinställning**.</span><span class="sxs-lookup"><span data-stu-id="58150-116">Go to **Warehouse management \> Setup \> Warehouse \> Location setup wizard**.</span></span>
2. <span data-ttu-id="58150-117">Ange följande värden.</span><span class="sxs-lookup"><span data-stu-id="58150-117">Set the following values:</span></span>

    - <span data-ttu-id="58150-118">I fältet **Lagerställe** , välj _62_.</span><span class="sxs-lookup"><span data-stu-id="58150-118">In the **Warehouse** field, select _62_.</span></span>
    - <span data-ttu-id="58150-119">I fältet **Zon-ID** välj _FLOOR_.</span><span class="sxs-lookup"><span data-stu-id="58150-119">In the **Zone ID** field, select _FLOOR_.</span></span>
    - <span data-ttu-id="58150-120">I fältet **Ytterligare Zon 1** välj _PICKZONE1_.</span><span class="sxs-lookup"><span data-stu-id="58150-120">In the **Additional Zone 1** field, select _PICKZONE1_.</span></span>
    - <span data-ttu-id="58150-121">I fältet **Ytterligare Zon 2** välj _WEBSHOP1_.</span><span class="sxs-lookup"><span data-stu-id="58150-121">In the **Additional Zone 2** field, select _WEBSHOP1_.</span></span>
    - <span data-ttu-id="58150-122">I fältet **Platsprofil-ID** , välj _FLOOR_.</span><span class="sxs-lookup"><span data-stu-id="58150-122">In the **Location profile ID** field, select _FLOOR_.</span></span>

3. <span data-ttu-id="58150-123">Välj rad **Våning**.</span><span class="sxs-lookup"><span data-stu-id="58150-123">Select the **Floor** line.</span></span>
4. <span data-ttu-id="58150-124">I fältet **Från nummer** , ange _1_.</span><span class="sxs-lookup"><span data-stu-id="58150-124">In the **From number** field, enter _1_.</span></span> <span data-ttu-id="58150-125">I fältet **Till nummer** , ange _3_.</span><span class="sxs-lookup"><span data-stu-id="58150-125">In the **To number** field, enter _3_.</span></span>
5. <span data-ttu-id="58150-126">Välj rad **Gång**.</span><span class="sxs-lookup"><span data-stu-id="58150-126">Select the **Aisle** line.</span></span>
6. <span data-ttu-id="58150-127">I fältet **Från nummer** , ange _1_.</span><span class="sxs-lookup"><span data-stu-id="58150-127">In the **From number** field, enter _1_.</span></span> <span data-ttu-id="58150-128">I fältet **Till nummer** , ange _5_.</span><span class="sxs-lookup"><span data-stu-id="58150-128">In the **To number** field, enter _5_.</span></span>
7. <span data-ttu-id="58150-129">Markera **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="58150-129">Select **Create**.</span></span>
8. <span data-ttu-id="58150-130">Du får meddelanden om att nya platser har lagts till.</span><span class="sxs-lookup"><span data-stu-id="58150-130">You receive messages that state that new locations have been added.</span></span> <span data-ttu-id="58150-131">Välj knappen **Visa meddelanden** om du vill visa meddelandena.</span><span class="sxs-lookup"><span data-stu-id="58150-131">Select the **Show messages** button to view the messages.</span></span>
9. <span data-ttu-id="58150-132">Gå till **Lagerstyrning \> Inställningar \> Lagerställe \> Platser**.</span><span class="sxs-lookup"><span data-stu-id="58150-132">Go to **Warehouse management \> Setup \> Warehouse \> Locations**.</span></span> <span data-ttu-id="58150-133">De nya platserna visas i listan och alla zonfält är tillgängliga (det vill säga det befintliga zonfältet och de nya ytterligare zonfälten).</span><span class="sxs-lookup"><span data-stu-id="58150-133">The new locations appear in the list, and all zone fields are available (that is, the existing zone field and the new additional zone fields).</span></span>
