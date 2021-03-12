---
title: Välj att använda omdömen och recensioner
description: Det här avsnittet innehåller information om hur du väljer att använda värderingar och recensioner på din Microsoft Dynamics 365 Commerce-webbplats.
author: gvrmohanreddy
manager: annbe
ms.date: 01/30/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 481a8750b2333d5dd5de2c05e175569804a6046f
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4985846"
---
# <a name="opt-in-to-use-ratings-and-reviews"></a><span data-ttu-id="4b5f8-103">Välj att använda omdömen och recensioner</span><span class="sxs-lookup"><span data-stu-id="4b5f8-103">Opt in to use ratings and reviews</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="4b5f8-104">Det här avsnittet innehåller information om hur du väljer att använda värderingar och recensioner på din Microsoft Dynamics 365 Commerce-webbplats.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-104">This topic explains how to opt in to use ratings and reviews on your Microsoft Dynamics 365 Commerce site.</span></span>

## <a name="overview"></a><span data-ttu-id="4b5f8-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="4b5f8-105">Overview</span></span>

<span data-ttu-id="4b5f8-106">Klassificerings- och granskningslösningen är en flerkanalslösning som du kan göra tillgänglig i Dynamics 365 Commerce genom att använda Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="4b5f8-106">The ratings and reviews solution is an omni-channel solution that you can make available in Dynamics 365 Commerce by using Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="4b5f8-107">LCS är en administrationsportal som används av detaljhandlare för att hantera sina miljöer från etablering till avställning.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-107">LCS is an administration portal that retailers use to manage their environments from provisioning to decommissioning.</span></span>

<span data-ttu-id="4b5f8-108">Om du vill använda klassificeringen och granska lösningen på din handelswebbplats, måste du välja om du vill ha omdömen och recensioner under distributionen av din näthandelssajt på Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-108">If you want to use the ratings and reviews solution on your Commerce website, you must opt in for ratings and reviews during deployment of your e-Commerce site on Dynamics 365 Commerce.</span></span>

## <a name="opt-in-to-use-ratings-and-reviews"></a><span data-ttu-id="4b5f8-109">Välj att använda omdömen och recensioner</span><span class="sxs-lookup"><span data-stu-id="4b5f8-109">Opt in to use ratings and reviews</span></span>

<span data-ttu-id="4b5f8-110">Om du vill använda värderingar och recensioner på webbplatsen följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-110">To opt in to use ratings and reviews on your site, follow these steps.</span></span>

1. <span data-ttu-id="4b5f8-111">Följ stegen i [distribuera en ny näthandelssajt](deploy-ecommerce-site.md).</span><span class="sxs-lookup"><span data-stu-id="4b5f8-111">Follow the steps in [Deploy a new e-Commerce site](deploy-ecommerce-site.md).</span></span>
1. <span data-ttu-id="4b5f8-112">När du fortfarande är i LCS går du till **Inställning av butiksdistribution \> Övriga inställningar**.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-112">While you're still in LCS, go to **Retail deployment setup \> Other settings**.</span></span>
1. <span data-ttu-id="4b5f8-113">Ange alternativet **tjänsten aktivera klassificering och granska** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-113">Set the **Enable ratings and reviews service** option to **Yes**.</span></span>
1. <span data-ttu-id="4b5f8-114">I fältet **AAD-säkerhetsgruppen för moderator för omdömen och recensioner (ojekt-ID för säkerhetsgrupp)** ange ID för den Microsoft Azure Active Directory (Azure AD) äkerhetsgrupp som inkluderar moderatorer för omdömen och recensioner.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-114">In the **AAD security group for ratings and review moderator (security group object id)** field, enter the ID of the Microsoft Azure Active Directory (Azure AD) security group that includes the ratings and reviews moderators.</span></span>

    ![Välj att använda omdömen och recensioner](media/LCS_RnR_Preference.png)

1. <span data-ttu-id="4b5f8-116">Slutför initieringsprocessen för näthandel.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-116">Complete the e-Commerce initialization process.</span></span>

> [!NOTE] 
> <span data-ttu-id="4b5f8-117">Om du är en befintlig Dynamics 365 Commerce-kund som redan har distribuerat en näthandelssajt utan att ha valt värderingar och recensioner och nu vill använda omdömen och recensioner från Dynamics 365 Commerce-paketet, måste du skicka en servicebegäran.</span><span class="sxs-lookup"><span data-stu-id="4b5f8-117">If you are an existing Dynamics 365 Commerce customer who has already deployed an e-Commerce site without having opted in for ratings and reviews and now want to use ratings and reviews from the Dynamics 365 Commerce package, please submit a service request.</span></span> <span data-ttu-id="4b5f8-118">Mer information om hur du skickar en servicebegäran finns i [skicka bearbeta serviceförfrågningar](../fin-ops-core/dev-itpro/lifecycle-services/submit-request-dynamics-service-engineering-team.md?toc=/dynamics365/commerce/toc.json).</span><span class="sxs-lookup"><span data-stu-id="4b5f8-118">For information about how to submit a service request, see [Submit service requests process](../fin-ops-core/dev-itpro/lifecycle-services/submit-request-dynamics-service-engineering-team.md?toc=/dynamics365/commerce/toc.json).</span></span> 

## <a name="additional-resources"></a><span data-ttu-id="4b5f8-119">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="4b5f8-119">Additional resources</span></span>

[<span data-ttu-id="4b5f8-120">Översikt över omdömen och recensioner</span><span class="sxs-lookup"><span data-stu-id="4b5f8-120">Ratings and reviews overview</span></span>](ratings-reviews-overview.md)

[<span data-ttu-id="4b5f8-121">Hantera omdömen och recensioner</span><span class="sxs-lookup"><span data-stu-id="4b5f8-121">Manage ratings and reviews</span></span>](manage-reviews.md)

[<span data-ttu-id="4b5f8-122">Konfigurera omdömen och recensioner</span><span class="sxs-lookup"><span data-stu-id="4b5f8-122">Configure ratings and reviews</span></span>](configure-ratings-reviews.md)

[<span data-ttu-id="4b5f8-123">Synkronisera produktklassificeringar i Dynamics 365 Commerce</span><span class="sxs-lookup"><span data-stu-id="4b5f8-123">Sync product ratings in Dynamics 365 Commerce</span></span>](sync-product-ratings.md)


