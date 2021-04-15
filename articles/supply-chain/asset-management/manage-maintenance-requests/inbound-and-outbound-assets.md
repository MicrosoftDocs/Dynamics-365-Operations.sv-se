---
title: Inkommande och avgående tillgångar
description: Det här avsnittet förklarar hur du registrerar inkommande och avgående tillgångar i tillgångshantering.
author: johanhoffmann
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: EntAssetOutboundObjectsListPage, EntAssetOutboundObjectsDeliver, EntAssetInboundObjectsListPage, EntAssetInboundObjectsRecieve
audience: Application User
ms.reviewer: kamaybac
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: johanho
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: 1a2bac914330058400a7e4d7d355bd4a00a4522f
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/01/2021
ms.locfileid: "5816806"
---
# <a name="inbound-and-outbound-assets"></a><span data-ttu-id="40f68-103">Inkommande och avgående tillgångar</span><span class="sxs-lookup"><span data-stu-id="40f68-103">Inbound and outbound assets</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="40f68-104">Om ditt företag utför reparationsjobb eller underhållsjobb på tillgångar som tas emot från andra platser eller kunder, kan tillgångshanteraren spåra både inkommande tillgångar som är på väg till ditt företag och utgående tillgångar som returneras.</span><span class="sxs-lookup"><span data-stu-id="40f68-104">If your company does repair jobs or maintenance jobs on assets that are received from other locations or customers, Asset Management can track both inbound assets that are on their way to your company and outbound assets that are being returned.</span></span>

> [!NOTE]
> <span data-ttu-id="40f68-105">Om du vill använda inkommande och utgående livscykeltillstånd för att hantera tillgångar som kommer in och som returneras, måste du ställa in livscykeltillstånd och livscykelmodeller för underhållsbegäranden för att stödja dessa åtgärder.</span><span class="sxs-lookup"><span data-stu-id="40f68-105">If you want to use inbound and outbound lifecycle states to manage assets that are coming in and being returned, you must set up maintenance request lifecycle states and lifecycle models to support these actions.</span></span> <span data-ttu-id="40f68-106">Mer information finns i [Underhållsbegäran](../setup-for-maintenance-requests/requests.md).</span><span class="sxs-lookup"><span data-stu-id="40f68-106">For more information, see [Maintenance requests](../setup-for-maintenance-requests/requests.md).</span></span>

<span data-ttu-id="40f68-107">Inställningen av tillgångshantering avgör om du kan arbeta med inkommande och utgående tillgångar.</span><span class="sxs-lookup"><span data-stu-id="40f68-107">The setup of Asset Management determines whether you can work with inbound and outbound assets.</span></span>

## <a name="register-assets-as-inbound"></a><span data-ttu-id="40f68-108">Registrera tillgångar som inkommande</span><span class="sxs-lookup"><span data-stu-id="40f68-108">Register assets as inbound</span></span>

1. <span data-ttu-id="40f68-109">Välj **tillgångshantering** \> **allmänt** \> **underhållbegäran** \> **aktiva underhållbegäran**.</span><span class="sxs-lookup"><span data-stu-id="40f68-109">Select **Asset management** \> **Common** \> **Maintenance requests** \> **Active maintenance requests**.</span></span>
2. <span data-ttu-id="40f68-110">Markera underhållsbegäran.</span><span class="sxs-lookup"><span data-stu-id="40f68-110">Select the maintenance request.</span></span>
3. <span data-ttu-id="40f68-111">Välj **uppdatera underhållsbegärantillstånd**.</span><span class="sxs-lookup"><span data-stu-id="40f68-111">Select **Update maintenance request state**.</span></span>
4. <span data-ttu-id="40f68-112">Välj **inkommande** (eller ett annat livscykeltillstånd som du har skapat för inkommande tillgångar) och välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="40f68-112">Select **Inbound** (or another lifecycle state that you've created for inbound assets), and then select **OK**.</span></span>

![Registrera tillgångar som inkommande](media/07-manage-maintenance-requests.png)

## <a name="register-inbound-assets-as-received"></a><span data-ttu-id="40f68-114">Registrera inkommande tillgångar som inlevererade</span><span class="sxs-lookup"><span data-stu-id="40f68-114">Register inbound assets as received</span></span>

1. <span data-ttu-id="40f68-115">Välj **tillgångshantering** \> **allmänt** \> **inkommande/utgående** \> **inkommande tillgångar**.</span><span class="sxs-lookup"><span data-stu-id="40f68-115">Select **Asset management** \> **Common** \> **Inbound/outbound** \> **Inbound assets**.</span></span>
2. <span data-ttu-id="40f68-116">Markera tillgången eller underhållsbegäran.</span><span class="sxs-lookup"><span data-stu-id="40f68-116">Select the asset or maintenance request.</span></span>
3. <span data-ttu-id="40f68-117">Ta emot **anläggningstillgångar**</span><span class="sxs-lookup"><span data-stu-id="40f68-117">Select **Receive assets**.</span></span>
4. <span data-ttu-id="40f68-118">I fältet **Inlevererad** ställer du in datum och tid.</span><span class="sxs-lookup"><span data-stu-id="40f68-118">In the **Received** field, enter the date and time.</span></span> <span data-ttu-id="40f68-119">Välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="40f68-119">Then select **OK**.</span></span> <span data-ttu-id="40f68-120">Posten tas bort från listsidan **inkommande tillgångar**.</span><span class="sxs-lookup"><span data-stu-id="40f68-120">The record is removed from the **Inbound assets** list page.</span></span>

![Registrera inkommande tillgångar som inlevererade](media/08-manage-maintenance-requests.png)

## <a name="register-assets-as-outbound"></a><span data-ttu-id="40f68-122">Registrera tillgångar som utgående</span><span class="sxs-lookup"><span data-stu-id="40f68-122">Register assets as outbound</span></span>

<span data-ttu-id="40f68-123">När du har slutfört underhålls- eller reparationsjobbet kan du registrera tillgången som returnerad.</span><span class="sxs-lookup"><span data-stu-id="40f68-123">When you've completed the maintenance or repair job, you can register the asset as returned.</span></span>

1. <span data-ttu-id="40f68-124">Välj **tillgångshantering** \> **allmänt** \> **underhållbegäran** \> **aktiva underhållbegäran**.</span><span class="sxs-lookup"><span data-stu-id="40f68-124">Select **Asset management** \> **Common** \> **Maintenance requests** \> **Active maintenance requests**.</span></span>
2. <span data-ttu-id="40f68-125">Markera underhållsbegäran.</span><span class="sxs-lookup"><span data-stu-id="40f68-125">Select the maintenance request.</span></span>
3. <span data-ttu-id="40f68-126">Välj **uppdatera underhållsbegärantillstånd**.</span><span class="sxs-lookup"><span data-stu-id="40f68-126">Select **Update maintenance request state**.</span></span>
4. <span data-ttu-id="40f68-127">Välj **utgående** (eller ett annat livscykeltillstånd som du har skapat för utgående tillgångar) och välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="40f68-127">Select **Outbound** (or another lifecycle state that you've created for outbound assets), and then select **OK**.</span></span>

## <a name="register-outbound-assets-as-delivered"></a><span data-ttu-id="40f68-128">Registrera utgående tillgångar som levererade</span><span class="sxs-lookup"><span data-stu-id="40f68-128">Register outbound assets as delivered</span></span>

1. <span data-ttu-id="40f68-129">Välj **tillgångshantering** \> **allmänt** \> **inkommande/utgående** \> **utgående tillgångar**.</span><span class="sxs-lookup"><span data-stu-id="40f68-129">Select **Asset management** \> **Common** \> **Inbound/outbound** \> **Outbound assets**.</span></span>
2. <span data-ttu-id="40f68-130">Markera tillgången eller underhållsbegäran.</span><span class="sxs-lookup"><span data-stu-id="40f68-130">Select the asset or maintenance request.</span></span>
3. <span data-ttu-id="40f68-131">Välj **leverera tillgångar**.</span><span class="sxs-lookup"><span data-stu-id="40f68-131">Select **Deliver assets**.</span></span>
4. <span data-ttu-id="40f68-132">I fältet **Levererad** ställer du in datum och tid.</span><span class="sxs-lookup"><span data-stu-id="40f68-132">In the **Delivered** field, enter the date and time.</span></span> <span data-ttu-id="40f68-133">Välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="40f68-133">Then select **OK**.</span></span> <span data-ttu-id="40f68-134">Posten tas bort från listsidan **utgående tillgångar**.</span><span class="sxs-lookup"><span data-stu-id="40f68-134">The record is removed from the **Outbound assets** list page.</span></span>


[!INCLUDE[footer-include](../../../includes/footer-banner.md)]