---
title: Inkommande och avgående tillgångar
description: Det här avsnittet förklarar hur du registrerar inkommande och avgående tillgångar i tillgångshantering.
author: josaw1
manager: tfehr
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: EntAssetOutboundObjectsListPage, EntAssetOutboundObjectsDeliver, EntAssetInboundObjectsListPage, EntAssetInboundObjectsRecieve
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: riluan
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: e6dfadf6824c6a3df7be9b3b6f3d9f5dd2749e34
ms.sourcegitcommit: deac22ba5377a912d93fe408c5ae875706378c2d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/16/2021
ms.locfileid: "5018081"
---
# <a name="inbound-and-outbound-assets"></a><span data-ttu-id="0e550-103">Inkommande och avgående tillgångar</span><span class="sxs-lookup"><span data-stu-id="0e550-103">Inbound and outbound assets</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="0e550-104">Om ditt företag utför reparationsjobb eller underhållsjobb på tillgångar som tas emot från andra platser eller kunder, kan tillgångshanteraren spåra både inkommande tillgångar som är på väg till ditt företag och utgående tillgångar som returneras.</span><span class="sxs-lookup"><span data-stu-id="0e550-104">If your company does repair jobs or maintenance jobs on assets that are received from other locations or customers, Asset Management can track both inbound assets that are on their way to your company and outbound assets that are being returned.</span></span>

> [!NOTE]
> <span data-ttu-id="0e550-105">Om du vill använda inkommande och utgående livscykeltillstånd för att hantera tillgångar som kommer in och som returneras, måste du ställa in livscykeltillstånd och livscykelmodeller för underhållsbegäranden för att stödja dessa åtgärder.</span><span class="sxs-lookup"><span data-stu-id="0e550-105">If you want to use inbound and outbound lifecycle states to manage assets that are coming in and being returned, you must set up maintenance request lifecycle states and lifecycle models to support these actions.</span></span> <span data-ttu-id="0e550-106">Mer information finns i [Underhållsbegäran](../setup-for-maintenance-requests/requests.md).</span><span class="sxs-lookup"><span data-stu-id="0e550-106">For more information, see [Maintenance requests](../setup-for-maintenance-requests/requests.md).</span></span>

<span data-ttu-id="0e550-107">Inställningen av tillgångshantering avgör om du kan arbeta med inkommande och utgående tillgångar.</span><span class="sxs-lookup"><span data-stu-id="0e550-107">The setup of Asset Management determines whether you can work with inbound and outbound assets.</span></span>

## <a name="register-assets-as-inbound"></a><span data-ttu-id="0e550-108">Registrera tillgångar som inkommande</span><span class="sxs-lookup"><span data-stu-id="0e550-108">Register assets as inbound</span></span>

1. <span data-ttu-id="0e550-109">Välj **tillgångshantering** \> **allmänt** \> **underhållbegäran** \> **aktiva underhållbegäran**.</span><span class="sxs-lookup"><span data-stu-id="0e550-109">Select **Asset management** \> **Common** \> **Maintenance requests** \> **Active maintenance requests**.</span></span>
2. <span data-ttu-id="0e550-110">Markera underhållsbegäran.</span><span class="sxs-lookup"><span data-stu-id="0e550-110">Select the maintenance request.</span></span>
3. <span data-ttu-id="0e550-111">Välj **uppdatera underhållsbegärantillstånd**.</span><span class="sxs-lookup"><span data-stu-id="0e550-111">Select **Update maintenance request state**.</span></span>
4. <span data-ttu-id="0e550-112">Välj **inkommande** (eller ett annat livscykeltillstånd som du har skapat för inkommande tillgångar) och välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="0e550-112">Select **Inbound** (or another lifecycle state that you've created for inbound assets), and then select **OK**.</span></span>

![Registrera tillgångar som inkommande](media/07-manage-maintenance-requests.png)

## <a name="register-inbound-assets-as-received"></a><span data-ttu-id="0e550-114">Registrera inkommande tillgångar som inlevererade</span><span class="sxs-lookup"><span data-stu-id="0e550-114">Register inbound assets as received</span></span>

1. <span data-ttu-id="0e550-115">Välj **tillgångshantering** \> **allmänt** \> **inkommande/utgående** \> **inkommande tillgångar**.</span><span class="sxs-lookup"><span data-stu-id="0e550-115">Select **Asset management** \> **Common** \> **Inbound/outbound** \> **Inbound assets**.</span></span>
2. <span data-ttu-id="0e550-116">Markera tillgången eller underhållsbegäran.</span><span class="sxs-lookup"><span data-stu-id="0e550-116">Select the asset or maintenance request.</span></span>
3. <span data-ttu-id="0e550-117">Ta emot **anläggningstillgångar**</span><span class="sxs-lookup"><span data-stu-id="0e550-117">Select **Receive assets**.</span></span>
4. <span data-ttu-id="0e550-118">I fältet **Inlevererad** ställer du in datum och tid.</span><span class="sxs-lookup"><span data-stu-id="0e550-118">In the **Received** field, enter the date and time.</span></span> <span data-ttu-id="0e550-119">Välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="0e550-119">Then select **OK**.</span></span> <span data-ttu-id="0e550-120">Posten tas bort från listsidan **inkommande tillgångar**.</span><span class="sxs-lookup"><span data-stu-id="0e550-120">The record is removed from the **Inbound assets** list page.</span></span>

![Registrera inkommande tillgångar som inlevererade](media/08-manage-maintenance-requests.png)

## <a name="register-assets-as-outbound"></a><span data-ttu-id="0e550-122">Registrera tillgångar som utgående</span><span class="sxs-lookup"><span data-stu-id="0e550-122">Register assets as outbound</span></span>

<span data-ttu-id="0e550-123">När du har slutfört underhålls- eller reparationsjobbet kan du registrera tillgången som returnerad.</span><span class="sxs-lookup"><span data-stu-id="0e550-123">When you've completed the maintenance or repair job, you can register the asset as returned.</span></span>

1. <span data-ttu-id="0e550-124">Välj **tillgångshantering** \> **allmänt** \> **underhållbegäran** \> **aktiva underhållbegäran**.</span><span class="sxs-lookup"><span data-stu-id="0e550-124">Select **Asset management** \> **Common** \> **Maintenance requests** \> **Active maintenance requests**.</span></span>
2. <span data-ttu-id="0e550-125">Markera underhållsbegäran.</span><span class="sxs-lookup"><span data-stu-id="0e550-125">Select the maintenance request.</span></span>
3. <span data-ttu-id="0e550-126">Välj **uppdatera underhållsbegärantillstånd**.</span><span class="sxs-lookup"><span data-stu-id="0e550-126">Select **Update maintenance request state**.</span></span>
4. <span data-ttu-id="0e550-127">Välj **utgående** (eller ett annat livscykeltillstånd som du har skapat för utgående tillgångar) och välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="0e550-127">Select **Outbound** (or another lifecycle state that you've created for outbound assets), and then select **OK**.</span></span>

## <a name="register-outbound-assets-as-delivered"></a><span data-ttu-id="0e550-128">Registrera utgående tillgångar som levererade</span><span class="sxs-lookup"><span data-stu-id="0e550-128">Register outbound assets as delivered</span></span>

1. <span data-ttu-id="0e550-129">Välj **tillgångshantering** \> **allmänt** \> **inkommande/utgående** \> **utgående tillgångar**.</span><span class="sxs-lookup"><span data-stu-id="0e550-129">Select **Asset management** \> **Common** \> **Inbound/outbound** \> **Outbound assets**.</span></span>
2. <span data-ttu-id="0e550-130">Markera tillgången eller underhållsbegäran.</span><span class="sxs-lookup"><span data-stu-id="0e550-130">Select the asset or maintenance request.</span></span>
3. <span data-ttu-id="0e550-131">Välj **leverera tillgångar**.</span><span class="sxs-lookup"><span data-stu-id="0e550-131">Select **Deliver assets**.</span></span>
4. <span data-ttu-id="0e550-132">I fältet **Levererad** ställer du in datum och tid.</span><span class="sxs-lookup"><span data-stu-id="0e550-132">In the **Delivered** field, enter the date and time.</span></span> <span data-ttu-id="0e550-133">Välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="0e550-133">Then select **OK**.</span></span> <span data-ttu-id="0e550-134">Posten tas bort från listsidan **utgående tillgångar**.</span><span class="sxs-lookup"><span data-stu-id="0e550-134">The record is removed from the **Outbound assets** list page.</span></span>
