---
title: Ställ in lagerställen för överföringsorder
description: Det här avsnittet beskriver hur du ställer in lagerställen för överföringsorder.
author: Mirzaab
manager: tfehr
ms.date: 01/18/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: InventLocation,CustVendTransportPoint2Point
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: mirzaab
ms.search.validFrom: 2018-4-30
ms.dyn365.ops.version: 8
ms.openlocfilehash: 7dfb215683b4ee5d186626492bd90116d1a06a1d
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4976848"
---
# <a name="set-up-warehouses-for-transfer-orders"></a><span data-ttu-id="895fb-103">Ställ in lagerställen för överföringsorder</span><span class="sxs-lookup"><span data-stu-id="895fb-103">Set up warehouses for transfer orders</span></span> 

[!include [banner](../includes/banner.md)]

<span data-ttu-id="895fb-104">Lagerställenivåer kan användas för att skapa en hierarki som stöder överföringsorder mellan lagerställen.</span><span class="sxs-lookup"><span data-stu-id="895fb-104">You can use warehouse levels to create a hierarchy that supports transfer orders between warehouses.</span></span> <span data-ttu-id="895fb-105">Med dessa inställningar beräknar huvudplaneringen artikelbehoven vid den individuella lagerställenivån och genererar planerade överföringsorder från ett tilldelat källagerställe för att uppfylla dem.</span><span class="sxs-lookup"><span data-stu-id="895fb-105">Based on this setup, master scheduling calculates item requirements at the individual warehouse level and generates planned transfer orders from an assigned source warehouse to fulfill them.</span></span>

1.  <span data-ttu-id="895fb-106">Klicka på **Lagerhantering > Inställningar > Lagerindelning > Lagerställen**.</span><span class="sxs-lookup"><span data-stu-id="895fb-106">Click **Inventory management > Setup > Inventory breakdown > Warehouses**.</span></span>

2.  <span data-ttu-id="895fb-107">Välj det lagerställe som ska fyllas på.</span><span class="sxs-lookup"><span data-stu-id="895fb-107">Select the warehouse that you want to refill.</span></span>

3.  <span data-ttu-id="895fb-108">På snabbfliken **huvudplanering** markerar du kryssrutan **påfyllning**.</span><span class="sxs-lookup"><span data-stu-id="895fb-108">On the **Master planning** FastTab, select the **Refilling** check box.</span></span>

4.  <span data-ttu-id="895fb-109">I fältet **Huvudlagerställe** väljer du det lagerställe som du vill ange som påfyllningslagerstället.</span><span class="sxs-lookup"><span data-stu-id="895fb-109">In the **Main warehouse** field, select the warehouse that you want to assign as the refilling warehouse.</span></span> <span data-ttu-id="895fb-110">Huvuplaneringen beräknar ett överföringsbehov för det valda lagerstället och genererar en planerad överföringsorder från angivet **Huvudlagerställe**.</span><span class="sxs-lookup"><span data-stu-id="895fb-110">Master scheduling calculates a transfer requirement for the selected warehouse and generates a planned transfer order from the assigned **Main warehouse**.</span></span>
   
    > [!NOTE]
    > <P><span data-ttu-id="895fb-111">Om du avmarkerar kryssrutan <STRONG>Påfyllning</STRONG> tilldelas det markerade lagerstället en lagerställenivå i relation till <STRONG>Huvudlagerställe</STRONG>, men <STRONG>Huvudlagerställe</STRONG> ställs inte in som ett påfyllningslagerställe.</span><span class="sxs-lookup"><span data-stu-id="895fb-111">If you clear the <STRONG>Refilling</STRONG> check box, the selected warehouse is assigned a warehouse level in regard to the <STRONG>Main warehouse</STRONG>, but the <STRONG>Main warehouse</STRONG> is not set up as a refilling warehouse.</span></span></P>

5.  <span data-ttu-id="895fb-112">Tillämpa de nya inställningarna genom att stänga sidan.</span><span class="sxs-lookup"><span data-stu-id="895fb-112">Close the page to apply the new setup.</span></span>


> [!TIP]
> <P><span data-ttu-id="895fb-113">Om du vill tilldela ett lagerställe för påfyllning, måste du först ställa in lagerstället som en lagerdimension i formuläret <STRONG>Lagringsdimensionsgrupper</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="895fb-113">If you want to assign a warehouse for refilling, you must first set up the warehouse as a storage dimension on the <STRONG>Storage dimension groups</STRONG> page.</span></span> <span data-ttu-id="895fb-114">På den här sidan väljer du fältet <STRONG>Aktiv</STRONG> och fältet <STRONG>Disponera per dimension</STRONG> för lagerstället.</span><span class="sxs-lookup"><span data-stu-id="895fb-114">On this page, select the <STRONG>Active</STRONG> field and the <STRONG>Coverage plan by dimension</STRONG> field for the warehouse.</span></span></P>

## <a name="set-up-transport-lead-time"></a><span data-ttu-id="895fb-115">Ställa in ledtid för transport</span><span class="sxs-lookup"><span data-stu-id="895fb-115">Set up transport lead time</span></span>

<span data-ttu-id="895fb-116">Du måste också ange ledtiden för transport mellan lagerställen på sidan **Transportdagar**.</span><span class="sxs-lookup"><span data-stu-id="895fb-116">You must also set up the transport lead time between the warehouses on the **Transport days** page.</span></span> 
1. <span data-ttu-id="895fb-117">Gå till **Lagerhantering > Inställningar > Distribution > Transport dagar**.</span><span class="sxs-lookup"><span data-stu-id="895fb-117">Go to **Inventory management > Setup > Distribution > Transport days**.</span></span>
2. <span data-ttu-id="895fb-118">I fältet **Mottagningsplats**, välj **Lagerställe**.</span><span class="sxs-lookup"><span data-stu-id="895fb-118">In the **Receiving point** field, select **warehouse**.</span></span>
3. <span data-ttu-id="895fb-119">Välj **speditionslager**, **mottagande lager** och **transportdagar**.</span><span class="sxs-lookup"><span data-stu-id="895fb-119">Select the **Shipping warehouse**, **Receiving warehouse**, and **Transport days**.</span></span> 
4. <span data-ttu-id="895fb-120">(Valfritt) Du kan också ange transporttiden beroende på leveranssätt, under fliken **Transportdagar per leveranssätt**.</span><span class="sxs-lookup"><span data-stu-id="895fb-120">(Optional) You can also set transport time, depending on the mode of delivery, under the **Transport days per mode of delivery** tab.</span></span>
