---
title: Välj att använda omdömen och recensioner
description: Det här avsnittet innehåller information om hur du väljer att använda värderingar och recensioner på din Microsoft Dynamics 365 Commerce-webbplats.
author: gvrmohanreddy
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: Retail, Core, Operations
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: ''
ms.author: gmohanv
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 10e3c33af232fa46df09a103b2e73eae09a909eb
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697990"
---
# <a name="opt-in-to-use-ratings-and-reviews"></a><span data-ttu-id="14d52-103">Välj att använda omdömen och recensioner</span><span class="sxs-lookup"><span data-stu-id="14d52-103">Opt in to use ratings and reviews</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="14d52-104">Det här avsnittet innehåller information om hur du väljer att använda värderingar och recensioner på din Microsoft Dynamics 365 Commerce-webbplats.</span><span class="sxs-lookup"><span data-stu-id="14d52-104">This topic explains how to opt in to use ratings and reviews on your Microsoft Dynamics 365 Commerce site.</span></span>

## <a name="overview"></a><span data-ttu-id="14d52-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="14d52-105">Overview</span></span>

<span data-ttu-id="14d52-106">Klassificerings- och granskningslösningen är en flerkanalslösning som du kan göra tillgänglig i Dynamics 365 Commerce genom att använda Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="14d52-106">The ratings and reviews solution is an omnichannel solution that you can make available in Dynamics 365 Commerce by using Microsoft Dynamics Lifecycle Services (LCS).</span></span> <span data-ttu-id="14d52-107">LCS är en administrationsportal som används av detaljhandlare för att hantera sina miljöer från etablering till avställning.</span><span class="sxs-lookup"><span data-stu-id="14d52-107">LCS is an administration portal that retailers use to manage their environments from provisioning to decommissioning.</span></span>

<span data-ttu-id="14d52-108">Om du vill använda klassificeringen och granska lösningen på din näthandelsplats måste du först anmäla den.</span><span class="sxs-lookup"><span data-stu-id="14d52-108">If you want to use the ratings and reviews solution on your Commerce website, you must first opt in.</span></span>

## <a name="opt-in-to-use-ratings-and-reviews"></a><span data-ttu-id="14d52-109">Välj att använda omdömen och recensioner</span><span class="sxs-lookup"><span data-stu-id="14d52-109">Opt in to use ratings and reviews</span></span>

<span data-ttu-id="14d52-110">Om du vill använda värderingar och recensioner på webbplatsen följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="14d52-110">To opt in to use ratings and reviews on your site, follow these steps.</span></span>

1. <span data-ttu-id="14d52-111">Följ stegen i [distribuera en ny näthandelsplats](deploy-ecommerce-site.md).</span><span class="sxs-lookup"><span data-stu-id="14d52-111">Follow the steps in [Deploy a new e-Commerce site](deploy-ecommerce-site.md).</span></span>
1. <span data-ttu-id="14d52-112">När du fortfarande är i LCS går du till **Inställning av butiksdistribution \> Övriga inställningar**.</span><span class="sxs-lookup"><span data-stu-id="14d52-112">While you're still in LCS, go to **Retail deployment setup \> Other settings**.</span></span>
1. <span data-ttu-id="14d52-113">Ange alternativet **tjänsten aktivera klassificering och granska** till **Ja**.</span><span class="sxs-lookup"><span data-stu-id="14d52-113">Set the **Enable ratings and reviews service** option to **Yes**.</span></span>
1. <span data-ttu-id="14d52-114">I fältet **AAD-säkerhetsgruppen för moderator för omdömen och recensioner (ojekt-ID för säkerhetsgrupp)** ange ID för den Microsoft Azure Active Directory (Azure AD) äkerhetsgrupp som inkluderar moderatorer för omdömen och recensioner.</span><span class="sxs-lookup"><span data-stu-id="14d52-114">In the **AAD security group for ratings and review moderator (security group object id)** field, enter the ID of the Microsoft Azure Active Directory (Azure AD) security group that includes the ratings and reviews moderators.</span></span>

    ![Välj att använda omdömen och recensioner](media/LCS_RnR_Preference.png)

1. <span data-ttu-id="14d52-116">Slutför initieringsprocessen för e-handel.</span><span class="sxs-lookup"><span data-stu-id="14d52-116">Complete the e-Commerce initialization process.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="14d52-117">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="14d52-117">Additional resources</span></span>

[<span data-ttu-id="14d52-118">Översikt över omdömen och recensioner</span><span class="sxs-lookup"><span data-stu-id="14d52-118">Ratings and reviews overview</span></span>](ratings-reviews-overview.md)

[<span data-ttu-id="14d52-119">Hantera omdömen och recensioner</span><span class="sxs-lookup"><span data-stu-id="14d52-119">Manage ratings and reviews</span></span>](manage-reviews.md)

[<span data-ttu-id="14d52-120">Konfigurera omdömen och recensioner</span><span class="sxs-lookup"><span data-stu-id="14d52-120">Configure ratings and reviews</span></span>](configure-ratings-reviews.md)

[<span data-ttu-id="14d52-121">Synkronisera produktklassificeringar i Dynamics 365 Retail</span><span class="sxs-lookup"><span data-stu-id="14d52-121">Sync product ratings in Dynamics 365 Retail</span></span>](sync-product-ratings.md)
