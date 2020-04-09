---
title: Ange ett tillägg till en anläggningstillgång
description: I den här proceduren visas hur du lägger till ett tillägg till en befintlig anläggningstillgång.
author: saraschi2
manager: AnnBe
ms.date: 07/22/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: AssetTable, AssetAddition
audience: Application User
ms.reviewer: roschlom
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: dc1e13863ae13daaa641f52f7a55e01fc1353dc1
ms.sourcegitcommit: 57e1dafa186fec77ddd8ba9425d238e36e0f0998
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/18/2020
ms.locfileid: "3142764"
---
# <a name="enter-an-addition-to-a-fixed-asset"></a><span data-ttu-id="1f91c-103">Ange ett tillägg till en anläggningstillgång</span><span class="sxs-lookup"><span data-stu-id="1f91c-103">Enter an addition to a fixed asset</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="1f91c-104">I den här proceduren visas hur du lägger till ett tillägg till en befintlig anläggningstillgång.</span><span class="sxs-lookup"><span data-stu-id="1f91c-104">This procedure shows how to add an addition to an existing fixed asset.</span></span> <span data-ttu-id="1f91c-105">Syftet med tillägg till anläggningstillgång ska följa efter Artikeltillägg, underhåll eller förbättringar av en tillgång och är endast till för information.</span><span class="sxs-lookup"><span data-stu-id="1f91c-105">The purpose of Fixed asset additions is to track item additions, maintenance, or improvements for an asset, and is informational only.</span></span> <span data-ttu-id="1f91c-106">Ändringar i anläggningstillgångens värde eller tjänstelivstid ska göras separat.</span><span class="sxs-lookup"><span data-stu-id="1f91c-106">Any changes to the fixed asset value or service life must be made separately.</span></span>   

<span data-ttu-id="1f91c-107">Här används revisorrollen och demonstrationdata för den juridiska personen USMF.</span><span class="sxs-lookup"><span data-stu-id="1f91c-107">The procedure uses the Accountant role and demo data for the USMF legal entity.</span></span>

1. <span data-ttu-id="1f91c-108">I navigeringsfönstret går du till **Moduler > Anläggningstillgångar > Anläggningstillgångar > Anläggningstillgångar**.</span><span class="sxs-lookup"><span data-stu-id="1f91c-108">In the Navigation pane, go to **Modules > Fixed assets > Fixed assets > Fixed assets**.</span></span>
2. <span data-ttu-id="1f91c-109">Hitta och välj den anläggningstillgång som ska läggas till.</span><span class="sxs-lookup"><span data-stu-id="1f91c-109">In the list, find and select the fixed asset for the addition.</span></span>
3. <span data-ttu-id="1f91c-110">Klicka på länken på den valda raden i listan.</span><span class="sxs-lookup"><span data-stu-id="1f91c-110">In the list, click the link in the selected row.</span></span>
4. <span data-ttu-id="1f91c-111">Klicka på **Anläggningstillgång** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="1f91c-111">On the Action Pane, click **Fixed asset**.</span></span>
5. <span data-ttu-id="1f91c-112">Klicka på **Tillägg till anläggningstillgång**.</span><span class="sxs-lookup"><span data-stu-id="1f91c-112">Click **Fixed asset additions**.</span></span>
6. <span data-ttu-id="1f91c-113">Klicka på **Ny**.</span><span class="sxs-lookup"><span data-stu-id="1f91c-113">Click **New**.</span></span>
7. <span data-ttu-id="1f91c-114">Skriv ett värde i fältet **Namn**.</span><span class="sxs-lookup"><span data-stu-id="1f91c-114">In the **Name** field, type a value.</span></span>
8. <span data-ttu-id="1f91c-115">I fältet **anskaffningsdatum** anger du datumet för tilläggsinköpet eller tjänsten.</span><span class="sxs-lookup"><span data-stu-id="1f91c-115">In the **Acquisition date** field, set the date of the addition purchase or service.</span></span>
9. <span data-ttu-id="1f91c-116">I fältet **Enhetskostnad** anger du kostnaden för artikeln eller underhållet eller ange en annan förbättring för tillgången.</span><span class="sxs-lookup"><span data-stu-id="1f91c-116">In the **Unit cost** field, enter the cost of the item, maintenance, or other improvement for the asset.</span></span>
10. <span data-ttu-id="1f91c-117">Ange ett nummer i fältet **Kvantitet**.</span><span class="sxs-lookup"><span data-stu-id="1f91c-117">In the **Quantity** field, enter a number.</span></span> <span data-ttu-id="1f91c-118">Det totala kostnaden har ingen inverkan på värdet på anläggningstillgången och är för att följa och informationsändamål.</span><span class="sxs-lookup"><span data-stu-id="1f91c-118">The total cost will have no impact on the value of the fixed asset and is for tracking and informational purposes only.</span></span> <span data-ttu-id="1f91c-119">Om kostnaden ska vara skriven med versaler, måste en uppskrivning transaktion bokförs separat.</span><span class="sxs-lookup"><span data-stu-id="1f91c-119">If the cost will be capitalized, then a write-up adjustment transaction must be posted separately.</span></span>  
11. <span data-ttu-id="1f91c-120">Klicka på fliken **Allmänt**.</span><span class="sxs-lookup"><span data-stu-id="1f91c-120">Click the **General** tab.</span></span>

    * <span data-ttu-id="1f91c-121">Ange **Ökar tjänstelivstiden** till **Ja** om tillägget förlänger anläggningstillgångens tjänstelivstid.</span><span class="sxs-lookup"><span data-stu-id="1f91c-121">Set **Increases service life** to **Yes** if the addition increases the service life of the asset.</span></span>  
    * <span data-ttu-id="1f91c-122">Det här fältet är endast till för information.</span><span class="sxs-lookup"><span data-stu-id="1f91c-122">This field is informational only.</span></span> <span data-ttu-id="1f91c-123">Ändra tjänstelivstiden i värdemodellerna och avskrivningsreglerna för tillgången att öka tjänstelivstid.</span><span class="sxs-lookup"><span data-stu-id="1f91c-123">To increase the service life, modify the Service life on the Value models and/or Depreciation books for the asset.</span></span>  

