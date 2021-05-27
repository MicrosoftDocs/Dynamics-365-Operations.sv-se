---
title: Inloggningslänken omdirigerar tillbaka till en e-handelsplats
description: Det här avsnittet innehåller felsökningsvägledning som kan vara till hjälp när en inloggningslänk omdirigeras tillbaka till e-handelsplatsen istället för att gå till inloggningssidan.
author: Reza-Assadi
ms.date: 03/11/2021
ms.topic: Troubleshooting
ms.prod: ''
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
ms.openlocfilehash: a1d0ae4e487c391020947c607d5d7cb5d1ba6af4
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/11/2021
ms.locfileid: "6020613"
---
# <a name="sign-in-link-redirects-back-to-an-e-commerce-site"></a><span data-ttu-id="d0991-103">Inloggningslänken omdirigerar tillbaka till en e-handelsplats</span><span class="sxs-lookup"><span data-stu-id="d0991-103">Sign-in link redirects back to an e-commerce site</span></span>

[!include [banner](../../includes/banner.md)]

<span data-ttu-id="d0991-104">Det här avsnittet innehåller felsökningsvägledning som kan vara till hjälp när en inloggningslänk omdirigeras tillbaka till e-handelsplatsen istället för att gå till inloggningssidan.</span><span class="sxs-lookup"><span data-stu-id="d0991-104">This topic provides troubleshooting guidance that can help when a sign-in link redirects back to the e-commerce site instead of going to the sign-in page.</span></span>

## <a name="description"></a><span data-ttu-id="d0991-105">beskrivning</span><span class="sxs-lookup"><span data-stu-id="d0991-105">Description</span></span>

<span data-ttu-id="d0991-106">När du har konfigurerat en ny Microsoft Azure Active Directory B2C (Azure AD B2C) innehavare i Commerce-webbplatsbyggaren, användare som väljer länkar **Inloggning** omdirigeras tillbaka till huvudsidan för e-handel utan att gå till inloggningssidan.</span><span class="sxs-lookup"><span data-stu-id="d0991-106">After you configure a new Microsoft Azure Active Directory B2C (Azure AD B2C) tenant in Commerce site builder, users who select the **Sign in** link are redirected back to the main e-commerce landing page without going to the sign-in page.</span></span>

## <a name="resolution"></a><span data-ttu-id="d0991-107">Upplösning</span><span class="sxs-lookup"><span data-stu-id="d0991-107">Resolution</span></span>

### <a name="confirm-that-the-reply-url-is-correctly-configured-in-the-azure-ad-b2c-application"></a><span data-ttu-id="d0991-108">Bekräfta att svars-URL är korrekt konfigurerat i Azure AD B2C-programmet</span><span class="sxs-lookup"><span data-stu-id="d0991-108">Confirm that the reply URL is correctly configured in the Azure AD B2C application</span></span>

<span data-ttu-id="d0991-109">Bekräfta att svars-URL är korrekt konfigurerat i Azure AD B2C-programmet med dessa steg.</span><span class="sxs-lookup"><span data-stu-id="d0991-109">To confirm that the reply URL is correctly configured in the Azure AD B2C application, follow these steps.</span></span>

1. <span data-ttu-id="d0991-110">Gå till [Azure-portal](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="d0991-110">Go to the [Azure portal](https://portal.azure.com/).</span></span>
1. <span data-ttu-id="d0991-111">Välj det Azure AD B2C-program som du skapat för din webbplatsåtkomst.</span><span class="sxs-lookup"><span data-stu-id="d0991-111">Select the Azure AD B2C application that you created for your site access.</span></span>
1. <span data-ttu-id="d0991-112">Välj det program som du skapade under Azure AD B2C-inställningen.</span><span class="sxs-lookup"><span data-stu-id="d0991-112">Select the application that you created during the Azure AD B2C setup.</span></span>
1. <span data-ttu-id="d0991-113">Under **Svars-URL** ska du se till att listan innehåller poster för både URL-adressen och URL-adressen som genereras av e-handel, enligt exemplet i följande illustration.</span><span class="sxs-lookup"><span data-stu-id="d0991-113">Under **Reply URL**, make sure that the list includes entries for both the site domain URL and the e-commerce-generated URL, as shown in the example in the following illustration.</span></span>

    ![URL-poster för Azure AD B2C-svar](media/aad-b2c-reply-url.jpg)

> [!NOTE]
> <span data-ttu-id="d0991-115">Både webbadressen och URL-adressen som genereras av e-handel måste vara i ett giltigt URL-format som inte innehåller inledande eller avslutande snedstreck.</span><span class="sxs-lookup"><span data-stu-id="d0991-115">Both the site domain URL and the e-commerce-generated URL must be in a valid URL format that doesn't include leading or trailing slashes.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="d0991-116">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="d0991-116">Additional resources</span></span>

[<span data-ttu-id="d0991-117">Registrera en webbapp i Azure Active Directory B2C</span><span class="sxs-lookup"><span data-stu-id="d0991-117">Register a web application in Azure Active Directory B2C</span></span>](/azure/active-directory-b2c/tutorial-register-applications?tabs=app-reg-ga#register-a-web-application)

[<span data-ttu-id="d0991-118">Ställa in en B2C-klientorganisation i Commerce</span><span class="sxs-lookup"><span data-stu-id="d0991-118">Set up a B2C tenant in Commerce</span></span>](../set-up-b2c-tenant.md)