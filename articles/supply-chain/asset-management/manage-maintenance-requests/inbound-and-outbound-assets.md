---
title: Inkommande och avgående tillgångar
description: Det här avsnittet förklarar hur du registrerar inkommande och avgående tillgångar i tillgångshantering.
author: josaw1
manager: AnnBe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: mkirknel
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: 10.0.5
ms.openlocfilehash: bb318c24424c291f08ba7527b2258c0da4cba9a8
ms.sourcegitcommit: d37fb09101c30858bcb975931b3d8f947d72017b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/10/2019
ms.locfileid: "2571678"
---
# <a name="inbound-and-outbound-assets"></a><span data-ttu-id="02591-103">Inkommande och avgående tillgångar</span><span class="sxs-lookup"><span data-stu-id="02591-103">Inbound and outbound assets</span></span>

[!include [banner](../../includes/banner.md)]

 

<span data-ttu-id="02591-104">Om ditt företag utför reparationsjobb eller underhållsjobb på tillgångar som tas emot från andra platser eller kunder, kan tillgångshanteraren spåra både inkommande tillgångar som är på väg till ditt företag och utgående tillgångar som returneras.</span><span class="sxs-lookup"><span data-stu-id="02591-104">If your company does repair jobs or maintenance jobs on assets that are received from other locations or customers, Asset Management can track both inbound assets that are on their way to your company and outbound assets that are being returned.</span></span>

> [!NOTE]
> <span data-ttu-id="02591-105">Om du vill använda inkommande och utgående livscykeltillstånd för att hantera tillgångar som kommer in och som returneras, måste du ställa in livscykeltillstånd och livscykelmodeller för underhållsbegäranden för att stödja dessa åtgärder.</span><span class="sxs-lookup"><span data-stu-id="02591-105">If you want to use inbound and outbound lifecycle states to manage assets that are coming in and being returned, you must set up maintenance request lifecycle states and lifecycle models to support these actions.</span></span> <span data-ttu-id="02591-106">Mer information finns i [Inställning för underhållsbegäran](../setup-for-maintenance-requests/requests.md).</span><span class="sxs-lookup"><span data-stu-id="02591-106">For more information, see [Setup for maintenance requests](../setup-for-maintenance-requests/requests.md).</span></span>

<span data-ttu-id="02591-107">Inställningen av tillgångshantering avgör om du kan arbeta med inkommande och utgående tillgångar.</span><span class="sxs-lookup"><span data-stu-id="02591-107">The setup of Asset Management determines whether you can work with inbound and outbound assets.</span></span>

## <a name="register-assets-as-inbound"></a><span data-ttu-id="02591-108">Registrera tillgångar som inkommande</span><span class="sxs-lookup"><span data-stu-id="02591-108">Register assets as inbound</span></span>

1. <span data-ttu-id="02591-109">Välj **tillgångshantering** \> **allmänt** \> **underhållbegäran** \> **aktiva underhållbegäran**.</span><span class="sxs-lookup"><span data-stu-id="02591-109">Select **Asset management** \> **Common** \> **Maintenance requests** \> **Active maintenance requests**.</span></span>
2. <span data-ttu-id="02591-110">Markera underhållsbegäran.</span><span class="sxs-lookup"><span data-stu-id="02591-110">Select the maintenance request.</span></span>
3. <span data-ttu-id="02591-111">Välj **uppdatera underhållsbegärantillstånd**.</span><span class="sxs-lookup"><span data-stu-id="02591-111">Select **Update maintenance request state**.</span></span>
4. <span data-ttu-id="02591-112">Välj **inkommande** (eller ett annat livscykeltillstånd som du har skapat för inkommande tillgångar) och välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="02591-112">Select **Inbound** (or another lifecycle state that you've created for inbound assets), and then select **OK**.</span></span>

![Registrera tillgångar som inkommande](media/07-manage-maintenance-requests.png)

## <a name="register-inbound-assets-as-received"></a><span data-ttu-id="02591-114">Registrera inkommande tillgångar som inlevererade</span><span class="sxs-lookup"><span data-stu-id="02591-114">Register inbound assets as received</span></span>

1. <span data-ttu-id="02591-115">Välj **tillgångshantering** \> **allmänt** \> **inkommande/utgående** \> **inkommande tillgångar**.</span><span class="sxs-lookup"><span data-stu-id="02591-115">Select **Asset management** \> **Common** \> **Inbound/outbound** \> **Inbound assets**.</span></span>
2. <span data-ttu-id="02591-116">Markera tillgången eller underhållsbegäran.</span><span class="sxs-lookup"><span data-stu-id="02591-116">Select the asset or maintenance request.</span></span>
3. <span data-ttu-id="02591-117">Ta emot **anläggningstillgångar**</span><span class="sxs-lookup"><span data-stu-id="02591-117">Select **Receive assets**.</span></span>
4. <span data-ttu-id="02591-118">I fältet **Inlevererad** ställer du in datum och tid.</span><span class="sxs-lookup"><span data-stu-id="02591-118">In the **Received** field, enter the date and time.</span></span> <span data-ttu-id="02591-119">Välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="02591-119">Then select **OK**.</span></span> <span data-ttu-id="02591-120">Posten tas bort från listsidan **inkommande tillgångar**.</span><span class="sxs-lookup"><span data-stu-id="02591-120">The record is removed from the **Inbound assets** list page.</span></span>

![Registrera inkommande tillgångar som inlevererade](media/08-manage-maintenance-requests.png)

## <a name="register-assets-as-outbound"></a><span data-ttu-id="02591-122">Registrera tillgångar som utgående</span><span class="sxs-lookup"><span data-stu-id="02591-122">Register assets as outbound</span></span>

<span data-ttu-id="02591-123">När du har slutfört underhålls- eller reparationsjobbet kan du registrera tillgången som returnerad.</span><span class="sxs-lookup"><span data-stu-id="02591-123">When you've completed the maintenance or repair job, you can register the asset as returned.</span></span>

1. <span data-ttu-id="02591-124">Välj **tillgångshantering** \> **allmänt** \> **underhållbegäran** \> **aktiva underhållbegäran**.</span><span class="sxs-lookup"><span data-stu-id="02591-124">Select **Asset management** \> **Common** \> **Maintenance requests** \> **Active maintenance requests**.</span></span>
2. <span data-ttu-id="02591-125">Markera underhållsbegäran.</span><span class="sxs-lookup"><span data-stu-id="02591-125">Select the maintenance request.</span></span>
3. <span data-ttu-id="02591-126">Välj **uppdatera underhållsbegärantillstånd**.</span><span class="sxs-lookup"><span data-stu-id="02591-126">Select **Update maintenance request state**.</span></span>
4. <span data-ttu-id="02591-127">Välj **utgående** (eller ett annat livscykeltillstånd som du har skapat för utgående tillgångar) och välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="02591-127">Select **Outbound** (or another lifecycle state that you've created for outbound assets), and then select **OK**.</span></span>

## <a name="register-outbound-assets-as-delivered"></a><span data-ttu-id="02591-128">Registrera utgående tillgångar som levererade</span><span class="sxs-lookup"><span data-stu-id="02591-128">Register outbound assets as delivered</span></span>

1. <span data-ttu-id="02591-129">Välj **tillgångshantering** \> **allmänt** \> **inkommande/utgående** \> **utgående tillgångar**.</span><span class="sxs-lookup"><span data-stu-id="02591-129">Select **Asset management** \> **Common** \> **Inbound/outbound** \> **Outbound assets**.</span></span>
2. <span data-ttu-id="02591-130">Markera tillgången eller underhållsbegäran.</span><span class="sxs-lookup"><span data-stu-id="02591-130">Select the asset or maintenance request.</span></span>
3. <span data-ttu-id="02591-131">Välj **leverera tillgångar**.</span><span class="sxs-lookup"><span data-stu-id="02591-131">Select **Deliver assets**.</span></span>
4. <span data-ttu-id="02591-132">I fältet **Levererad** ställer du in datum och tid.</span><span class="sxs-lookup"><span data-stu-id="02591-132">In the **Delivered** field, enter the date and time.</span></span> <span data-ttu-id="02591-133">Välj sedan **OK**.</span><span class="sxs-lookup"><span data-stu-id="02591-133">Then select **OK**.</span></span> <span data-ttu-id="02591-134">Posten tas bort från listsidan **utgående tillgångar**.</span><span class="sxs-lookup"><span data-stu-id="02591-134">The record is removed from the **Outbound assets** list page.</span></span>
