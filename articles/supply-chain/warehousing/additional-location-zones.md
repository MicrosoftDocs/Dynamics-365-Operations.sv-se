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
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: perlynne
ms.search.validFrom: 2020-07-01
ms.dyn365.ops.version: 10.0.8
ms.openlocfilehash: 662725edf5bf8d95be038f7c989b73d8d05fa0df
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4996436"
---
# <a name="additional-location-zones"></a><span data-ttu-id="ecea7-103">Ytterligare platszoner</span><span class="sxs-lookup"><span data-stu-id="ecea7-103">Additional location zones</span></span>

[!include [banner](../includes/banner.md)]

<span data-ttu-id="ecea7-104">Tre nya zonfält finns tillgängliga i Microsoft Dynamics 365 Supply Chain Management.</span><span class="sxs-lookup"><span data-stu-id="ecea7-104">Three new zone fields are available in Microsoft Dynamics 365 Supply Chain Management.</span></span> <span data-ttu-id="ecea7-105">Lagerchefer kan använda dem för att definiera ytterligare lagerorganisationer eller layouter.</span><span class="sxs-lookup"><span data-stu-id="ecea7-105">Warehouse managers can use them to define additional warehouse organizations or layouts.</span></span> <span data-ttu-id="ecea7-106">De nya zonfälten kan ställas in antingen manuellt eller med hjälp guiden **platsinställning**.</span><span class="sxs-lookup"><span data-stu-id="ecea7-106">The new zone fields can be set either manually or by using the **Location setup** wizard.</span></span> <span data-ttu-id="ecea7-107">De kan användas i alla frågor eller filter som använder tabellen lagerställen.</span><span class="sxs-lookup"><span data-stu-id="ecea7-107">They can be used in any query or filtering that uses the Locations table.</span></span>

<span data-ttu-id="ecea7-108">Det krävs inga ytterligare inställningar för att använda zonfälten.</span><span class="sxs-lookup"><span data-stu-id="ecea7-108">No additional setup is required to use the zone fields.</span></span>

## <a name="turn-on-the-additional-location-zone-feature"></a><span data-ttu-id="ecea7-109">Aktivera funktionen ytterligare platszoner</span><span class="sxs-lookup"><span data-stu-id="ecea7-109">Turn on the Additional location zone feature</span></span>

<span data-ttu-id="ecea7-110">Innan du kan använda funktionen *Ytterligare platszon* den aktiveras i ditt system.</span><span class="sxs-lookup"><span data-stu-id="ecea7-110">Before you can use the *Additional location zone* feature, it must be turned on in your system.</span></span> <span data-ttu-id="ecea7-111">Administratörer kan använda inställningarna [funktionshantering](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) för att kontrollera funktionens status och aktivera den om det behövs.</span><span class="sxs-lookup"><span data-stu-id="ecea7-111">Admins can use the [feature management](../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) settings to check the status of the feature and turn it on if it's required.</span></span> <span data-ttu-id="ecea7-112">I arbetsytan **utgiftshantering** anges den här funktionen på följande sätt:</span><span class="sxs-lookup"><span data-stu-id="ecea7-112">In the **Feature management** workspace, the feature is listed in the following way:</span></span>

- <span data-ttu-id="ecea7-113">**Modul:** *Lagerstyrning*</span><span class="sxs-lookup"><span data-stu-id="ecea7-113">**Module:** *Warehouse management*</span></span>
- <span data-ttu-id="ecea7-114">**Funktionsnamn:** *Ytterligare platszon*</span><span class="sxs-lookup"><span data-stu-id="ecea7-114">**Feature name:** *Additional location zone*</span></span>

## <a name="use-location-zones"></a><span data-ttu-id="ecea7-115">Använda platszoner</span><span class="sxs-lookup"><span data-stu-id="ecea7-115">Use location zones</span></span>

1. <span data-ttu-id="ecea7-116">Gå till **Lagerstyrning \> Inställningar \> Lagerställe \> Guide för platsinställning**.</span><span class="sxs-lookup"><span data-stu-id="ecea7-116">Go to **Warehouse management \> Setup \> Warehouse \> Location setup wizard**.</span></span>
2. <span data-ttu-id="ecea7-117">Ange följande värden.</span><span class="sxs-lookup"><span data-stu-id="ecea7-117">Set the following values:</span></span>

    - <span data-ttu-id="ecea7-118">I fältet **Lagerställe**, välj _62_.</span><span class="sxs-lookup"><span data-stu-id="ecea7-118">In the **Warehouse** field, select _62_.</span></span>
    - <span data-ttu-id="ecea7-119">I fältet **Zon-ID** välj _FLOOR_.</span><span class="sxs-lookup"><span data-stu-id="ecea7-119">In the **Zone ID** field, select _FLOOR_.</span></span>
    - <span data-ttu-id="ecea7-120">I fältet **Ytterligare Zon 1** välj _PICKZONE1_.</span><span class="sxs-lookup"><span data-stu-id="ecea7-120">In the **Additional Zone 1** field, select _PICKZONE1_.</span></span>
    - <span data-ttu-id="ecea7-121">I fältet **Ytterligare Zon 2** välj _WEBSHOP1_.</span><span class="sxs-lookup"><span data-stu-id="ecea7-121">In the **Additional Zone 2** field, select _WEBSHOP1_.</span></span>
    - <span data-ttu-id="ecea7-122">I fältet **Platsprofil-ID**, välj _FLOOR_.</span><span class="sxs-lookup"><span data-stu-id="ecea7-122">In the **Location profile ID** field, select _FLOOR_.</span></span>

3. <span data-ttu-id="ecea7-123">Välj rad **Våning**.</span><span class="sxs-lookup"><span data-stu-id="ecea7-123">Select the **Floor** line.</span></span>
4. <span data-ttu-id="ecea7-124">I fältet **Från nummer**, ange _1_.</span><span class="sxs-lookup"><span data-stu-id="ecea7-124">In the **From number** field, enter _1_.</span></span> <span data-ttu-id="ecea7-125">I fältet **Till nummer**, ange _3_.</span><span class="sxs-lookup"><span data-stu-id="ecea7-125">In the **To number** field, enter _3_.</span></span>
5. <span data-ttu-id="ecea7-126">Välj rad **Gång**.</span><span class="sxs-lookup"><span data-stu-id="ecea7-126">Select the **Aisle** line.</span></span>
6. <span data-ttu-id="ecea7-127">I fältet **Från nummer**, ange _1_.</span><span class="sxs-lookup"><span data-stu-id="ecea7-127">In the **From number** field, enter _1_.</span></span> <span data-ttu-id="ecea7-128">I fältet **Till nummer**, ange _5_.</span><span class="sxs-lookup"><span data-stu-id="ecea7-128">In the **To number** field, enter _5_.</span></span>
7. <span data-ttu-id="ecea7-129">Markera **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="ecea7-129">Select **Create**.</span></span>
8. <span data-ttu-id="ecea7-130">Du får meddelanden om att nya platser har lagts till.</span><span class="sxs-lookup"><span data-stu-id="ecea7-130">You receive messages that state that new locations have been added.</span></span> <span data-ttu-id="ecea7-131">Välj knappen **Visa meddelanden** om du vill visa meddelandena.</span><span class="sxs-lookup"><span data-stu-id="ecea7-131">Select the **Show messages** button to view the messages.</span></span>
9. <span data-ttu-id="ecea7-132">Gå till **Lagerstyrning \> Inställningar \> Lagerställe \> Platser**.</span><span class="sxs-lookup"><span data-stu-id="ecea7-132">Go to **Warehouse management \> Setup \> Warehouse \> Locations**.</span></span> <span data-ttu-id="ecea7-133">De nya platserna visas i listan och alla zonfält är tillgängliga (det vill säga det befintliga zonfältet och de nya ytterligare zonfälten).</span><span class="sxs-lookup"><span data-stu-id="ecea7-133">The new locations appear in the list, and all zone fields are available (that is, the existing zone field and the new additional zone fields).</span></span>
