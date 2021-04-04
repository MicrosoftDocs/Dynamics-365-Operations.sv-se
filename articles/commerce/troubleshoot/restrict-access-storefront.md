---
title: Begränsa åtkomsten till en butiksbutik under testning eller utveckling
description: I det här avsnittet beskrivs hur du begränsar åtkomsten Microsoft Dynamics 365 Commerce till en butik medan intern testning eller utveckling sker.
author: Reza-Assadi
manager: AnnBe
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
ms.service: dynamics-365-retail
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.search.industry: Retail
ms.author: rassadi
ms.search.validFrom: 2021-01-31
ms.dyn365.ops.version: 10.0.18
ms.openlocfilehash: 2cdf131048e0fac940475322294ed99e76c0a53b
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585541"
---
# <a name="restrict-access-to-a-storefront-during-testing-or-development"></a><span data-ttu-id="971a3-103">Begränsa åtkomsten till en butiksbutik under testning eller utveckling</span><span class="sxs-lookup"><span data-stu-id="971a3-103">Restrict access to a storefront during testing or development</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="971a3-104">I det här avsnittet beskrivs hur du begränsar åtkomsten Microsoft Dynamics 365 Commerce till en butik medan intern testning eller utveckling sker.</span><span class="sxs-lookup"><span data-stu-id="971a3-104">This topic explains how to restrict access to a Microsoft Dynamics 365 Commerce storefront while internal testing or development is occurring.</span></span>

## <a name="description"></a><span data-ttu-id="971a3-105">beskrivning</span><span class="sxs-lookup"><span data-stu-id="971a3-105">Description</span></span>

<span data-ttu-id="971a3-106">Under den interna testningen eller den aktiva utvecklingen kan du begränsa åtkomsten till webbplatsen så att externa användare inte kommer åt de publicerade butikssidorna.</span><span class="sxs-lookup"><span data-stu-id="971a3-106">During internal testing or active development, you might want to restrict access to your site to prevent external users from accessing the published storefront pages.</span></span>

## <a name="resolution"></a><span data-ttu-id="971a3-107">Upplösning</span><span class="sxs-lookup"><span data-stu-id="971a3-107">Resolution</span></span>

### <a name="set-up-azure-ad-b2c-by-using-standard-user-flows"></a><span data-ttu-id="971a3-108">Ställa in Azure AD B2C med hjälp av standardanvändarflöden</span><span class="sxs-lookup"><span data-stu-id="971a3-108">Set up Azure AD B2C by using standard user flows</span></span>

<span data-ttu-id="971a3-109">Mer information om hur du konfigurerar Azure Active Directory B2C (Azure AD B2C) för din e-handelsplats finns i [Ställa in en B2C-innehavare i Commerce](../set-up-b2c-tenant.md).</span><span class="sxs-lookup"><span data-stu-id="971a3-109">For information about how to configure Azure Active Directory B2C (Azure AD B2C) for your e-commerce site, see [Set up a B2C tenant in Commerce](../set-up-b2c-tenant.md).</span></span>

### <a name="restrict-user-access-to-storefront-pages-and-block-the-creation-of-new-users"></a><span data-ttu-id="971a3-110">Begränsa användarnas åtkomst till butikssidor och blockera skapandet av nya användare</span><span class="sxs-lookup"><span data-stu-id="971a3-110">Restrict user access to storefront pages and block the creation of new users</span></span>

<span data-ttu-id="971a3-111">Om du vill begränsa användarens åtkomst till butikssidor i Commerce-webbplatsbyggaren gör du så här.</span><span class="sxs-lookup"><span data-stu-id="971a3-111">To restrict user access to storefront pages in Commerce site builder, follow these steps.</span></span>

1. <span data-ttu-id="971a3-112">Gå till webbplatsen.</span><span class="sxs-lookup"><span data-stu-id="971a3-112">Go to your site.</span></span>
1. <span data-ttu-id="971a3-113">Välj **sidor** och välj sedan den sida som du vill begränsa användaråtkomsten för.</span><span class="sxs-lookup"><span data-stu-id="971a3-113">Select **Pages**, and then select the page to restrict user access for.</span></span>
1. <span data-ttu-id="971a3-114">Markera modulen eller fragmentplatsen och välj **redigera**.</span><span class="sxs-lookup"><span data-stu-id="971a3-114">Select the module or fragment slot, and then select **Edit**.</span></span>
1. <span data-ttu-id="971a3-115">I egenskapsfönstret, välj **Kräver inloggning?** och välj **Slutför redigering**.</span><span class="sxs-lookup"><span data-stu-id="971a3-115">In the properties pane, select **Requires sign-in?**, and then select **Finish editing**.</span></span>
1. <span data-ttu-id="971a3-116">Markera **Publicera**.</span><span class="sxs-lookup"><span data-stu-id="971a3-116">Select **Publish**.</span></span>

<span data-ttu-id="971a3-117">Om du vill spärra skapandet av nya användare i Azure AD gör du så här.</span><span class="sxs-lookup"><span data-stu-id="971a3-117">To block the creation of new users in Azure AD, follow these steps.</span></span>

1. <span data-ttu-id="971a3-118">Gå till [Azure-portal](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="971a3-118">Go to the [Azure portal](https://portal.azure.com/).</span></span>
1. <span data-ttu-id="971a3-119">Välj det Azure AD B2C-program som du skapat för din webbplatsåtkomst.</span><span class="sxs-lookup"><span data-stu-id="971a3-119">Select the Azure AD B2C application that you created for your site access.</span></span>
1. <span data-ttu-id="971a3-120">I navigeringsfönstret till vänster, välj **Användarflöden**.</span><span class="sxs-lookup"><span data-stu-id="971a3-120">In the left navigation, select **User flows**.</span></span>
1. <span data-ttu-id="971a3-121">Längst upp på sidan **användarflöden** väljer du **Nytt användarflöde**.</span><span class="sxs-lookup"><span data-stu-id="971a3-121">At the top of the **User Flows** page, select **New user flow**.</span></span>
1. <span data-ttu-id="971a3-122">På sidan **Välj en typ av användarflöde** välj **Förhandsgranskning**.</span><span class="sxs-lookup"><span data-stu-id="971a3-122">On the **Select a user flow type** page, select **Preview**.</span></span>
1. <span data-ttu-id="971a3-123">I mitten av sidan väljer du **inloggning v2**.</span><span class="sxs-lookup"><span data-stu-id="971a3-123">In the middle of the page, select **Sign in v2**.</span></span> <span data-ttu-id="971a3-124">Följ stegen i [Ställa in en B2C-innehavare i Commerce](../set-up-b2c-tenant.md) om du vill konfigurera flödet som webbplatsens standardanvändarflöde för Azure AD B2C under testning eller utveckling.</span><span class="sxs-lookup"><span data-stu-id="971a3-124">Then follow the steps in [Set up a B2C tenant in Commerce](../set-up-b2c-tenant.md) to configure the flow as your site's standard user flow for Azure AD B2C during testing or development.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="971a3-125">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="971a3-125">Additional resources</span></span>

[<span data-ttu-id="971a3-126">Ställa in en B2C-klientorganisation i Commerce</span><span class="sxs-lookup"><span data-stu-id="971a3-126">Set up a B2C tenant in Commerce</span></span>](../set-up-b2c-tenant.md)

[<span data-ttu-id="971a3-127">Ställa in anpassade sidor för användarinloggningar</span><span class="sxs-lookup"><span data-stu-id="971a3-127">Set up custom pages for user sign-ins</span></span>](../custom-pages-user-logins.md)
