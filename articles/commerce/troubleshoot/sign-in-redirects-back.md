---
title: Inloggningslänken omdirigerar tillbaka till en e-handelsplats
description: Det här avsnittet innehåller felsökningsvägledning som kan vara till hjälp när en inloggningslänk omdirigeras tillbaka till e-handelsplatsen istället för att gå till inloggningssidan.
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
ms.openlocfilehash: 36f10c9f68570a6c67da6b4b6e4155f4634f633a
ms.sourcegitcommit: 6c108be3378b365e6ec596a1a8666d59b758db25
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/12/2021
ms.locfileid: "5585529"
---
# <a name="sign-in-link-redirects-back-to-an-e-commerce-site"></a><span data-ttu-id="a506e-103">Inloggningslänken omdirigerar tillbaka till en e-handelsplats</span><span class="sxs-lookup"><span data-stu-id="a506e-103">Sign-in link redirects back to an e-commerce site</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="a506e-104">Det här avsnittet innehåller felsökningsvägledning som kan vara till hjälp när en inloggningslänk omdirigeras tillbaka till e-handelsplatsen istället för att gå till inloggningssidan.</span><span class="sxs-lookup"><span data-stu-id="a506e-104">This topic provides troubleshooting guidance that can help when a sign-in link redirects back to the e-commerce site instead of going to the sign-in page.</span></span>

## <a name="description"></a><span data-ttu-id="a506e-105">beskrivning</span><span class="sxs-lookup"><span data-stu-id="a506e-105">Description</span></span>

<span data-ttu-id="a506e-106">När du har konfigurerat en ny Microsoft Azure Active Directory B2C (Azure AD B2C) innehavare i Commerce-webbplatsbyggaren, användare som väljer länkar **Inloggning** omdirigeras tillbaka till huvudsidan för e-handel utan att gå till inloggningssidan.</span><span class="sxs-lookup"><span data-stu-id="a506e-106">After you configure a new Microsoft Azure Active Directory B2C (Azure AD B2C) tenant in Commerce site builder, users who select the **Sign in** link are redirected back to the main e-commerce landing page without going to the sign-in page.</span></span>

## <a name="resolution"></a><span data-ttu-id="a506e-107">Upplösning</span><span class="sxs-lookup"><span data-stu-id="a506e-107">Resolution</span></span>

### <a name="confirm-that-the-reply-url-is-correctly-configured-in-the-azure-ad-b2c-application"></a><span data-ttu-id="a506e-108">Bekräfta att svars-URL är korrekt konfigurerat i Azure AD B2C-programmet</span><span class="sxs-lookup"><span data-stu-id="a506e-108">Confirm that the reply URL is correctly configured in the Azure AD B2C application</span></span>

<span data-ttu-id="a506e-109">Bekräfta att svars-URL är korrekt konfigurerat i Azure AD B2C-programmet med dessa steg.</span><span class="sxs-lookup"><span data-stu-id="a506e-109">To confirm that the reply URL is correctly configured in the Azure AD B2C application, follow these steps.</span></span>

1. <span data-ttu-id="a506e-110">Gå till [Azure-portal](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="a506e-110">Go to the [Azure portal](https://portal.azure.com/).</span></span>
1. <span data-ttu-id="a506e-111">Välj det Azure AD B2C-program som du skapat för din webbplatsåtkomst.</span><span class="sxs-lookup"><span data-stu-id="a506e-111">Select the Azure AD B2C application that you created for your site access.</span></span>
1. <span data-ttu-id="a506e-112">Välj det program som du skapade under Azure AD B2C-inställningen.</span><span class="sxs-lookup"><span data-stu-id="a506e-112">Select the application that you created during the Azure AD B2C setup.</span></span>
1. <span data-ttu-id="a506e-113">Under **Svars-URL** ska du se till att listan innehåller poster för både URL-adressen och URL-adressen som genereras av e-handel, enligt exemplet i följande illustration.</span><span class="sxs-lookup"><span data-stu-id="a506e-113">Under **Reply URL**, make sure that the list includes entries for both the site domain URL and the e-commerce-generated URL, as shown in the example in the following illustration.</span></span>

    ![URL-poster för Azure AD B2C-svar](media/aad-b2c-reply-url.jpg)

> [!NOTE]
> <span data-ttu-id="a506e-115">Både webbadressen och URL-adressen som genereras av e-handel måste vara i ett giltigt URL-format som inte innehåller inledande eller avslutande snedstreck.</span><span class="sxs-lookup"><span data-stu-id="a506e-115">Both the site domain URL and the e-commerce-generated URL must be in a valid URL format that doesn't include leading or trailing slashes.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a506e-116">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="a506e-116">Additional resources</span></span>

[<span data-ttu-id="a506e-117">Registrera en webbapp i Azure Active Directory B2C</span><span class="sxs-lookup"><span data-stu-id="a506e-117">Register a web application in Azure Active Directory B2C</span></span>](https://docs.microsoft.com/azure/active-directory-b2c/tutorial-register-applications?tabs=app-reg-ga#register-a-web-application)

[<span data-ttu-id="a506e-118">Ställa in en B2C-klientorganisation i Commerce</span><span class="sxs-lookup"><span data-stu-id="a506e-118">Set up a B2C tenant in Commerce</span></span>](../set-up-b2c-tenant.md)
