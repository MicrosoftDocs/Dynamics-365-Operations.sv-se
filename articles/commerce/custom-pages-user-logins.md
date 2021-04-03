---
title: Ställa in anpassade sidor för användarinloggningar
description: I det här avsnittet beskrivs hur du skapar anpassade sidor i Microsoft Dynamics 365 Commerce som hanterar anpassade inloggningsuppgifter för användare av Azure Active Directory (Azure AD) B2C-innehavare (Business-to-Consumer).
author: brianshook
manager: annbe
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 3328fad5328ae1954a6749f9a5eebcb71c723698
ms.sourcegitcommit: c88b54ba13a4dfe39b844ffaced4dc435560c47d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/19/2021
ms.locfileid: "5477958"
---
# <a name="set-up-custom-pages-for-user-sign-ins"></a><span data-ttu-id="dd781-103">Ställa in anpassade sidor för användarinloggningar</span><span class="sxs-lookup"><span data-stu-id="dd781-103">Set up custom pages for user sign-ins</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="dd781-104">I det här avsnittet beskrivs hur du skapar anpassade sidor i Microsoft Dynamics 365 Commerce som hanterar anpassade inloggningsuppgifter för användare av Azure Active Directory (Azure AD) B2C-innehavare (Business-to-Consumer).</span><span class="sxs-lookup"><span data-stu-id="dd781-104">This topic describes how to build custom pages in Microsoft Dynamics 365 Commerce that handle customized sign-ins for users of Azure Active Directory (Azure AD) business-to-consumer (B2C) tenants.</span></span>

<span data-ttu-id="dd781-105">Om du vill använda anpassade sidor som har skapats i Dynamics 365 Commerce för att hantera användarinloggningsflöden måste du ställa in de Azure AD-policyer som kommer att refereras till i handelsmiljön.</span><span class="sxs-lookup"><span data-stu-id="dd781-105">To use custom pages that are authored in Dynamics 365 Commerce to handle user sign-in flows, you must set up the Azure AD policies that will be referenced in the Commerce environment.</span></span> <span data-ttu-id="dd781-106">Du kan konfigurera B2C-policyer "Registrera och logga in", "profilredigering" och "lösenordsåterställning" Azure AD B2C-policyer med hjälp av Azure AD B2C-programmet.</span><span class="sxs-lookup"><span data-stu-id="dd781-106">You can configure the "Sign up and sign in," "Profile editing," and "Password reset" Azure AD B2C policies by using the Azure AD B2C application.</span></span> <span data-ttu-id="dd781-107">Azure AD B2C-innehavare och policynamn kan sedan refereras under etableringsprocessen som utförs för handelsmiljön med hjälp av Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="dd781-107">The Azure AD B2C tenant and policy names can then be referenced during the provisioning process that is done for the Commerce environment by using Microsoft Dynamics Lifecycle Services (LCS).</span></span>

<span data-ttu-id="dd781-108">De anpassade handelssidorna kan skapas med hjälp av modulen logga in, registrera, kontoprofil eller återställ lösenord.</span><span class="sxs-lookup"><span data-stu-id="dd781-108">The custom Commerce pages can be built by using the sign in, sign up, account profile edit, or password reset module.</span></span> <span data-ttu-id="dd781-109">De sid-URL:er som publiceras för dessa anpassade sidor bör sedan refereras i Azure AD B2C policykonfigurationer i Azure-portalen.</span><span class="sxs-lookup"><span data-stu-id="dd781-109">The page URLs that are published for these custom pages should then be referenced in Azure AD B2C policy configurations in the Azure portal.</span></span>

## <a name="set-up-b2c-policies"></a><span data-ttu-id="dd781-110">Ställ in B2C-policyer</span><span class="sxs-lookup"><span data-stu-id="dd781-110">Set up B2C policies</span></span>

<span data-ttu-id="dd781-111">När du har ställt in Azure AD B2C-innehavare och associerar den med din handelsmiljö, går du till sidan **Azure AD B2C** i Azure-portalen och väljer i menyn **Policyer** och sedan **Användarflöden (policyer)**.</span><span class="sxs-lookup"><span data-stu-id="dd781-111">After you set up your Azure AD B2C tenant and associate it with your Commerce environment, go to the **Azure AD B2C** page in the Azure portal, and then, on the menu, under **Policies**, select **User flows (policies)**.</span></span>

![Kommandot användarflöden (policyer) på menyn](./media/B2C_CustomPage_PoliciesMenu.png)

<span data-ttu-id="dd781-113">Du kan nu konfigurera användarinloggningsflöden "registrera och logga in", "profilredigering" och "lösenordsåterställning".</span><span class="sxs-lookup"><span data-stu-id="dd781-113">You can now configure the "Sign up and sign in," "Profile editing," and "Password reset" user sign-in flows.</span></span>

### <a name="configure-the-sign-up-and-sign-in-policy"></a><span data-ttu-id="dd781-114">Konfigurera policyn "Registrera och logga in"</span><span class="sxs-lookup"><span data-stu-id="dd781-114">Configure the "Sign up and sign in" policy</span></span>

<span data-ttu-id="dd781-115">För att konfigurera policyn "Registrera och logga in" följ stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="dd781-115">To configure the "Sign up and sign in" policy, follow these steps.</span></span>

1. <span data-ttu-id="dd781-116">Välj **nytt användarflöde** och välj sedan fliken **rekommenderad**, välj policyn **Logga in**.</span><span class="sxs-lookup"><span data-stu-id="dd781-116">Select **New user flow**, and then, on the **Recommended** tab, select the **Sign up and sign in** policy.</span></span>
1. <span data-ttu-id="dd781-117">Ange ett namn på policyn (till exempel **B2C\_1\_SignInSignUp**).</span><span class="sxs-lookup"><span data-stu-id="dd781-117">Enter a name for the policy (for example, **B2C\_1\_SignInSignUp**).</span></span>
1. <span data-ttu-id="dd781-118">I avsnittet **identitetsleverantörer** väljer du vilka identitetsleverantörer som ska användas för policyn.</span><span class="sxs-lookup"><span data-stu-id="dd781-118">In the **Identity Providers** section, select the identity providers to use for the policy.</span></span> <span data-ttu-id="dd781-119">Åtminstone måste du **välja e-postregistrering**.</span><span class="sxs-lookup"><span data-stu-id="dd781-119">At a minimum, **Email signup** must be selected.</span></span>
1. <span data-ttu-id="dd781-120">I kolumnen **Samla in attribut** välj kryssrutorna för **e-postadress**, **förnamn** och **efternamn**.</span><span class="sxs-lookup"><span data-stu-id="dd781-120">In the **Collect attribute** column, select the check boxes for **Email Address**, **Given Name**, and **Surname**.</span></span>
1. <span data-ttu-id="dd781-121">I kolumnen **returanspråk** markerar du kryssrutorna för **e-postadresser**, **förnamn**, **identitetsleverantör**, **efternamn** och **användarens objekt-ID**.</span><span class="sxs-lookup"><span data-stu-id="dd781-121">In the **Return claim** column, select the check boxes for **Email Addresses**, **Given Name**, **Identity Provider**, **Surname**, and **User's Object ID**.</span></span>

    ![Valda attribut och anspråk](./media/B2C_SignInSignUp_Attributes.png)

1. <span data-ttu-id="dd781-123">Skapa policyn genom att välja **OK**.</span><span class="sxs-lookup"><span data-stu-id="dd781-123">Select **OK** to create the policy.</span></span>
1. <span data-ttu-id="dd781-124">Dubbelklicka på det nya policynamnet och välj sedan **Egenskaper** i navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="dd781-124">Double-click the new policy name, and then, in the navigation pane, select **Properties**.</span></span>
1. <span data-ttu-id="dd781-125">Ange alternativet **aktivera JavaScript med tvingad sidlayout (förhandsgranskning)** till **På**.</span><span class="sxs-lookup"><span data-stu-id="dd781-125">Set the **Enable JavaScript enforcing page layout (preview)** option to **On**.</span></span>

    ![Egenskapssida för den nya policyn](./media/B2C_SignInSignUp_EnableJavascript.png)

> [!NOTE]
> <span data-ttu-id="dd781-127">Policynamnet kommer att refereras till i handelsmiljön.</span><span class="sxs-lookup"><span data-stu-id="dd781-127">The policy name will be fully referenced in the Commerce environment.</span></span> <span data-ttu-id="dd781-128">(Prefixet **B2C\_1\_** kommer att inkluderas i referensen.) Det går inte att byta namn på policyer när de har skapats.</span><span class="sxs-lookup"><span data-stu-id="dd781-128">(The **B2C\_1\_** prefix will be included in the reference.) Policies can't be renamed after they are created.</span></span> <span data-ttu-id="dd781-129">Om du ersätter en befintlig policy för din handelsmiljö, kan du ta bort den ursprungliga policyn och bygga en ny policy som har samma namn.</span><span class="sxs-lookup"><span data-stu-id="dd781-129">If you're replacing an existing policy for your Commerce environment, you can delete the original policy and build a new policy that has the same name.</span></span> <span data-ttu-id="dd781-130">Om miljön redan har etablerats kan du skicka det nya policynamnet via en tjänstbegäran.</span><span class="sxs-lookup"><span data-stu-id="dd781-130">Alternatively, if the environment has already been provisioned, you can submit the new policy name through a service request.</span></span>

<span data-ttu-id="dd781-131">Du kommer tillbaka till den här policyn för att slutföra installationen när du har byggt de anpassade sidorna.</span><span class="sxs-lookup"><span data-stu-id="dd781-131">You will return to this policy to finish the setup after you've built the custom pages.</span></span> <span data-ttu-id="dd781-132">Stäng nu policyn för att återgå till sidan **användarflöden (policyer)** i Azure-portalen.</span><span class="sxs-lookup"><span data-stu-id="dd781-132">For now, close the policy to return to the **User flows (policies)** page in the Azure portal.</span></span>

### <a name="configure-the-profile-editing-policy"></a><span data-ttu-id="dd781-133">Konfigurera policyn för "profilredigering"</span><span class="sxs-lookup"><span data-stu-id="dd781-133">Configure the "Profile editing" policy</span></span>

<span data-ttu-id="dd781-134">Gör på följande vis för att konfigurera policyn "profilredigering".</span><span class="sxs-lookup"><span data-stu-id="dd781-134">To configure the "Profile editing" policy, follow these steps.</span></span>

1. <span data-ttu-id="dd781-135">Välj **nytt användarflöde** och välj sedan fliken **rekommenderad**, välj policyn **profilredigering**.</span><span class="sxs-lookup"><span data-stu-id="dd781-135">Select **New user flow**, and then, on the **Recommended** tab, select the **Profile editing** policy.</span></span>
1. <span data-ttu-id="dd781-136">Ange ett namn på policyn (till exempel **B2C\_1\_EditProfile**).</span><span class="sxs-lookup"><span data-stu-id="dd781-136">Enter a name for the policy (for example, **B2C\_1\_EditProfile**).</span></span>
1. <span data-ttu-id="dd781-137">I avsnittet **identitetsleverantörer** väljer du vilka identitetsleverantörer som ska användas för policyn.</span><span class="sxs-lookup"><span data-stu-id="dd781-137">In the **Identity Providers** section, select the identity providers to use for the policy.</span></span> <span data-ttu-id="dd781-138">Åtminstone **Local Account SignIn** måste väljas.</span><span class="sxs-lookup"><span data-stu-id="dd781-138">At a minimum, **Local Account SignIn** must be selected.</span></span>
1. <span data-ttu-id="dd781-139">I kolumnen **Samla in attribut** välj kryssrutorna för **e-postadresser** och **efternamn**.</span><span class="sxs-lookup"><span data-stu-id="dd781-139">In the **Collect attribute** column, select the check boxes for **Email Addresses** and **Surname**.</span></span>
1. <span data-ttu-id="dd781-140">I kolumnen **returanspråk** markerar du kryssrutorna för **e-postadresser**, **förnamn**, **identitetsleverantör**, **efternamn** och **användarens objekt-ID**.</span><span class="sxs-lookup"><span data-stu-id="dd781-140">In the **Return claim** column, select the check boxes for **Email Addresses**, **Given Name**, **Identity Provider**, **Surname**, and **User's Object ID**.</span></span>
1. <span data-ttu-id="dd781-141">Skapa policyn genom att välja **OK**.</span><span class="sxs-lookup"><span data-stu-id="dd781-141">Select **OK** to create the policy.</span></span>
1. <span data-ttu-id="dd781-142">Dubbelklicka på det nya policynamnet och välj sedan **Egenskaper** i navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="dd781-142">Double-click the new policy name, and then, in the navigation pane, select **Properties**.</span></span>
1. <span data-ttu-id="dd781-143">Ange alternativet **aktivera JavaScript med tvingad sidlayout (förhandsgranskning)** till **På**.</span><span class="sxs-lookup"><span data-stu-id="dd781-143">Set the **Enable JavaScript enforcing page layout (preview)** option to **On**.</span></span>

<span data-ttu-id="dd781-144">Du kommer tillbaka till den här policyn för att slutföra installationen när du har byggt de anpassade sidorna.</span><span class="sxs-lookup"><span data-stu-id="dd781-144">You will return to this policy to finish the setup after you've built the custom pages.</span></span> <span data-ttu-id="dd781-145">Stäng nu policyn för att återgå till sidan **användarflöden (policyer)** i Azure-portalen.</span><span class="sxs-lookup"><span data-stu-id="dd781-145">For now, close the policy to return to the **User flows (policies)** page in the Azure portal.</span></span>

### <a name="configure-the-password-reset-policy"></a><span data-ttu-id="dd781-146">Konfigurera policyn "Återställ lösenord"</span><span class="sxs-lookup"><span data-stu-id="dd781-146">Configure the "Password reset" policy</span></span>

<span data-ttu-id="dd781-147">Gör på följande vis för att konfigurera policyn "Lösenordsåterställning".</span><span class="sxs-lookup"><span data-stu-id="dd781-147">To configure the "Password reset" policy, follow these steps.</span></span>

1. <span data-ttu-id="dd781-148">Välj **nytt användarflöde** och välj sedan fliken **Förhandsgranska**, välj policyn **lösenordsåterställning v1.1**.</span><span class="sxs-lookup"><span data-stu-id="dd781-148">Select **New user flow**, and then, on the **Preview** tab, select the **Password reset v1.1** policy.</span></span>

    ![Policyn lösenordsåterställning v1.1 har valts på fliken förhandsgranskning](./media/B2C_ForgetPassword_Menu.png)

1. <span data-ttu-id="dd781-150">Ange ett namn på policyn (till exempel **B2C\_1\_ForgetPassword**).</span><span class="sxs-lookup"><span data-stu-id="dd781-150">Enter a name for the policy (for example, **B2C\_1\_ForgetPassword**).</span></span>
1. <span data-ttu-id="dd781-151">I avsnittet **identitetsleverantörer** väljer du **Återställ lösenord med e-postadress**.</span><span class="sxs-lookup"><span data-stu-id="dd781-151">In the **Identity Providers** section, select **Reset password using email address**.</span></span>
1. <span data-ttu-id="dd781-152">I kolumnen **returanspråk** markerar du kryssrutorna för **e-postadresser**, **förnamn**, **efternamn** och **användarens objekt-ID**.</span><span class="sxs-lookup"><span data-stu-id="dd781-152">In the **Return claim** column, select the check boxes for **Email Addresses**, **Given Name**, **Surname**, and **User's Object ID**.</span></span>

    ![Valda anspråk](./media/B2C_ForgetPassword_Attributes.png)

1. <span data-ttu-id="dd781-154">Skapa policyn genom att välja **OK**.</span><span class="sxs-lookup"><span data-stu-id="dd781-154">Select **OK** to create the policy.</span></span>
1. <span data-ttu-id="dd781-155">Dubbelklicka på det nya policynamnet och välj sedan **Egenskaper** i navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="dd781-155">Double-click the new policy name, and then, in the navigation pane, select **Properties**.</span></span>
1. <span data-ttu-id="dd781-156">Ange alternativet **aktivera JavaScript med tvingad sidlayout (förhandsgranskning)** till **På**.</span><span class="sxs-lookup"><span data-stu-id="dd781-156">Set the **Enable JavaScript enforcing page layout (preview)** option to **On**.</span></span>

<span data-ttu-id="dd781-157">Du kommer tillbaka till den här policyn för att slutföra installationen när du har byggt de anpassade sidorna.</span><span class="sxs-lookup"><span data-stu-id="dd781-157">You will return to this policy to finish the setup after you've built the custom pages.</span></span> <span data-ttu-id="dd781-158">Stäng nu policyn för att återgå till sidan **användarflöden (policyer)** i Azure-portalen.</span><span class="sxs-lookup"><span data-stu-id="dd781-158">For now, close the policy to return to the **User flows (policies)** page in the Azure portal.</span></span>

## <a name="build-the-custom-pages"></a><span data-ttu-id="dd781-159">Skapa anpassade sidor</span><span class="sxs-lookup"><span data-stu-id="dd781-159">Build the custom pages</span></span>

<span data-ttu-id="dd781-160">Om du vill skapa de anpassade sidorna för att hantera användarinloggningar följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="dd781-160">To build the custom pages to handle user sign-ins, follow these steps.</span></span>

1. <span data-ttu-id="dd781-161">I handelsredigeringsverktyg, gå till din webbplats.</span><span class="sxs-lookup"><span data-stu-id="dd781-161">In the Commerce authoring tools, go to your site.</span></span>
1. <span data-ttu-id="dd781-162">Skapa följande fem mallar och fem sidor:</span><span class="sxs-lookup"><span data-stu-id="dd781-162">Build the following five templates and five pages:</span></span>

    - <span data-ttu-id="dd781-163">Mallen **Logga in** och sida där inloggningsmodulen används.</span><span class="sxs-lookup"><span data-stu-id="dd781-163">A **Sign In** template and page that use the sign in module.</span></span>
    - <span data-ttu-id="dd781-164">Mallen **Registrera dig** och sida där registreringsmodulen används.</span><span class="sxs-lookup"><span data-stu-id="dd781-164">A **Sign Up** template and page that use the sign up module.</span></span>
    - <span data-ttu-id="dd781-165">Mallen **lösenordsåterställning** och sidan med modulen lösenordsåterställning.</span><span class="sxs-lookup"><span data-stu-id="dd781-165">A **Password Reset** template and page that use the password reset module.</span></span>
    - <span data-ttu-id="dd781-166">Mallen **verifiering av lösenordsåterställning** och sidan med modulen verifiering av lösenordsåterställning.</span><span class="sxs-lookup"><span data-stu-id="dd781-166">A **Password Reset verification** template and page that use the password reset verification module.</span></span>
    - <span data-ttu-id="dd781-167">Mallen **profilredigering** och sidor som använder redigeringsmodulen för kontoprofilen</span><span class="sxs-lookup"><span data-stu-id="dd781-167">A **Profile Edit** template and page that use the account profile edit module</span></span>

<span data-ttu-id="dd781-168">Följ de här riktlinjerna när du skapar sidorna:</span><span class="sxs-lookup"><span data-stu-id="dd781-168">When you build the pages, follow these guidelines:</span></span>

- <span data-ttu-id="dd781-169">För varje sida eller modul använder du layouten och formatet som bäst passar dina affärsbehov.</span><span class="sxs-lookup"><span data-stu-id="dd781-169">For each page or module, use the layout and style that best suit your business requirements.</span></span>
- <span data-ttu-id="dd781-170">Publicera alla sidor och URL som måste användas i Azure AD B2C-inställningar.</span><span class="sxs-lookup"><span data-stu-id="dd781-170">Publish all pages and URLs that must be used in the Azure AD B2C setup.</span></span>
- <span data-ttu-id="dd781-171">När sidorna och adresserna har publicerats samlar du in de URL-adresser som måste användas för konfigurationer av Azure AD B2C-policy.</span><span class="sxs-lookup"><span data-stu-id="dd781-171">After the pages and URLs are published, collect the URLs that must be used for the Azure AD B2C policy configurations.</span></span> <span data-ttu-id="dd781-172">Suffixet **?preloadscripts=true** kommer att läggas till varje URL när det används.</span><span class="sxs-lookup"><span data-stu-id="dd781-172">A **?preloadscripts=true** suffix will be added to every URL when it's used.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dd781-173">Återanvänd inte universella sidhuvuden och sidfötter med relativa länkar.</span><span class="sxs-lookup"><span data-stu-id="dd781-173">Don't reuse universal headers and footers that have relative links.</span></span> <span data-ttu-id="dd781-174">Eftersom dessa sidor kommer att finnas i Azure AD B2C-domänen när de används, ska endast absoluta URL:er användas för alla länkar.</span><span class="sxs-lookup"><span data-stu-id="dd781-174">Because these pages will be hosted in the Azure AD B2C domain when they are used, only absolute URLs should be used for all links.</span></span>

## <a name="configure-azure-ad-b2c-policies-with-custom-page-information"></a><span data-ttu-id="dd781-175">Konfigurera Azure AD B2C policyer med anpassad sidinformation</span><span class="sxs-lookup"><span data-stu-id="dd781-175">Configure Azure AD B2C policies with custom page information</span></span> 

<span data-ttu-id="dd781-176">I Azure-portalen, gå tillbaka till sidan **Azure AD B2C** och sedan på menyn under **Policyer**, välj **Användarflöden (policyer)**.</span><span class="sxs-lookup"><span data-stu-id="dd781-176">In the Azure portal, return to the **Azure AD B2C** page, and then, on the menu, under **Policies**, select **User flows (policies)**.</span></span>

### <a name="update-the-sign-up-and-sign-in-policy-with-custom-page-information"></a><span data-ttu-id="dd781-177">Uppdatera policyn "Registrera och logga in" med anpassad sidinformation</span><span class="sxs-lookup"><span data-stu-id="dd781-177">Update the "Sign up and sign in" policy with custom page information</span></span>

<span data-ttu-id="dd781-178">För att uppdatera policyn "Registrera och logga in" med anpassad sidinformation, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="dd781-178">To update the "Sign up and sign in" policy with custom page information, follow these steps.</span></span>

1. <span data-ttu-id="dd781-179">I policyn **Registrera och logga in** som du konfigurerade tidigare, i navigeringsfönstret, välj **Sidlayouter**.</span><span class="sxs-lookup"><span data-stu-id="dd781-179">In the **Sign in and sign up** policy that you configured earlier, in the navigation pane, select **Page layouts**.</span></span>
1. <span data-ttu-id="dd781-180">Välj layouten **Enhetlig sida för registrera och logga in**.</span><span class="sxs-lookup"><span data-stu-id="dd781-180">Select the **Unified sign up or sign in page** layout.</span></span>
1. <span data-ttu-id="dd781-181">Ställ in alternativet **Använd anpassat sidinnehåll** till **ja**.</span><span class="sxs-lookup"><span data-stu-id="dd781-181">Set the **Use custom page content** option to **Yes**.</span></span>
1. <span data-ttu-id="dd781-182">I fältet **Anpassad sid-URI** ange fullständig inloggnings-URL.</span><span class="sxs-lookup"><span data-stu-id="dd781-182">In the **Custom page URI** field, enter the full sign-in URL.</span></span> <span data-ttu-id="dd781-183">Inkludera suffixet **?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="dd781-183">Include the **?preloadscripts=true** suffix.</span></span> <span data-ttu-id="dd781-184">Ange exempelvis ``www.<my domain>.com/sign-in?preloadscripts=true``.</span><span class="sxs-lookup"><span data-stu-id="dd781-184">For example, enter ``www.<my domain>.com/sign-in?preloadscripts=true``.</span></span>
1. <span data-ttu-id="dd781-185">I fältet **Version av sidlayout (förhandsgranskning)**, välj **1.2.0**.</span><span class="sxs-lookup"><span data-stu-id="dd781-185">In the **Page Layout Version (Preview)** field, select **1.2.0**.</span></span>
1. <span data-ttu-id="dd781-186">Välj layouten **sida för registrering av lokalt konto**.</span><span class="sxs-lookup"><span data-stu-id="dd781-186">Select the **Local account sign up page** layout.</span></span>
1. <span data-ttu-id="dd781-187">Ställ in alternativet **Använd anpassat sidinnehåll** till **ja**.</span><span class="sxs-lookup"><span data-stu-id="dd781-187">Set the **Use custom page content** option to **Yes**.</span></span>
1. <span data-ttu-id="dd781-188">I fältet **Anpassad sid-URI** ange fullständig inloggnings-URL.</span><span class="sxs-lookup"><span data-stu-id="dd781-188">In the **Custom page URI** field, enter the full sign-up URL.</span></span> <span data-ttu-id="dd781-189">Inkludera suffixet **?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="dd781-189">Include the **?preloadscripts=true** suffix.</span></span> <span data-ttu-id="dd781-190">Ange exempelvis ``www.<my domain>.com/sign-up?preloadscripts=true``.</span><span class="sxs-lookup"><span data-stu-id="dd781-190">For example, enter ``www.<my domain>.com/sign-up?preloadscripts=true``.</span></span>
1. <span data-ttu-id="dd781-191">I fältet **Version av sidlayout (förhandsgranskning)**, välj **1.2.0**.</span><span class="sxs-lookup"><span data-stu-id="dd781-191">In the **Page Layout Version (Preview)** field, select **1.2.0**.</span></span>
1. <span data-ttu-id="dd781-192">I avsnittet **Användarattribut** följ dessa steg:</span><span class="sxs-lookup"><span data-stu-id="dd781-192">In the **User attributes** section, follow these steps:</span></span>

    1. <span data-ttu-id="dd781-193">För attributen **e-postadress**, **förnamn** och **efternamn** väljer du **nej** i fältet **kräver verifiering**.</span><span class="sxs-lookup"><span data-stu-id="dd781-193">For the **Email Address**, **Given Name**, and **Surname** attributes, select **No** in the **Requires Verification** field.</span></span>
    1. <span data-ttu-id="dd781-194">För attributen **förnamn** och **efternamn** välj **nej** i fältet **valfritt**.</span><span class="sxs-lookup"><span data-stu-id="dd781-194">For the **Given Name** and **Surname** attributes, select **No** in the **Optional** field.</span></span>

    ![Konfiguration av policyn sida för registrering av lokalt konto](./media/B2C_SignUp_PageURLConfig.png)

### <a name="update-the-profile-editing-policy-with-custom-page-information"></a><span data-ttu-id="dd781-196">Uppdatera policyn "Profilredigering" med anpassad sidinformation</span><span class="sxs-lookup"><span data-stu-id="dd781-196">Update the "Profile editing" policy with custom page information</span></span>

<span data-ttu-id="dd781-197">För att uppdatera policyn "Profilredigering" med anpassad sidinformation, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="dd781-197">To update the "Profile editing" policy with custom page information, follow these steps.</span></span>

1. <span data-ttu-id="dd781-198">I policyn **Profilredigering** som du konfigurerade tidigare, i navigeringsfönstret, välj **Sidlayouter**.</span><span class="sxs-lookup"><span data-stu-id="dd781-198">In the **Profile Editing** policy that you configured earlier, in the navigation pane, select **Page layouts**.</span></span>
1. <span data-ttu-id="dd781-199">Välj layouten **Profilredigeringssida**.</span><span class="sxs-lookup"><span data-stu-id="dd781-199">Select the **Profile edit page** layout.</span></span>
1. <span data-ttu-id="dd781-200">Ställ in alternativet **Använd anpassat sidinnehåll** till **ja**.</span><span class="sxs-lookup"><span data-stu-id="dd781-200">Set the **Use custom page content** option to **Yes**.</span></span>
1. <span data-ttu-id="dd781-201">I fältet **Anpassad sid-URI** ange fullständig profil redigerings-URL.</span><span class="sxs-lookup"><span data-stu-id="dd781-201">In the **Custom page URI** field, enter the full profile edit URL.</span></span> <span data-ttu-id="dd781-202">Inkludera suffixet **?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="dd781-202">Include the **?preloadscripts=true** suffix.</span></span> <span data-ttu-id="dd781-203">Ange exempelvis ``www.<my domain>.com/profile-edit?preloadscripts=true``.</span><span class="sxs-lookup"><span data-stu-id="dd781-203">For example, enter ``www.<my domain>.com/profile-edit?preloadscripts=true``.</span></span>
1. <span data-ttu-id="dd781-204">I fältet **Version av sidlayout (förhandsgranskning)**, välj **1.2.0**.</span><span class="sxs-lookup"><span data-stu-id="dd781-204">In the **Page Layout Version (Preview)** field, select **1.2.0**.</span></span>
1. <span data-ttu-id="dd781-205">I avsnittet **Användarattribut** följ dessa steg:</span><span class="sxs-lookup"><span data-stu-id="dd781-205">In the **User attributes** section, follow these steps:</span></span>

    1. <span data-ttu-id="dd781-206">För attributen **e-postadress**, **förnamn** väljer du **nej** i fältet **kräver verifiering**.</span><span class="sxs-lookup"><span data-stu-id="dd781-206">For the **Email Address**, **Given Name** attributes, select **No** in the **Requires Verification** field.</span></span>
    1. <span data-ttu-id="dd781-207">För attributen **förnamn** och **efternamn** välj **nej** i fältet **valfritt**.</span><span class="sxs-lookup"><span data-stu-id="dd781-207">For the **Given Name** and **Surname** attributes, select **No** in the **Optional** field.</span></span>

### <a name="update-the-password-reset-policy-with-custom-page-information"></a><span data-ttu-id="dd781-208">Uppdatera policyn "Lösenordsåterställning" med anpassad sidinformation</span><span class="sxs-lookup"><span data-stu-id="dd781-208">Update the "Password reset" policy with custom page information</span></span>

<span data-ttu-id="dd781-209">För att uppdatera policyn "Lösenordsåterställning" med anpassad sidinformation, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="dd781-209">To update the "Password reset" policy with custom page information, follow these steps.</span></span>

1. <span data-ttu-id="dd781-210">I policyn **Lösenordsåterställning** som du konfigurerade tidigare, i navigeringsfönstret, välj **Sidlayouter**.</span><span class="sxs-lookup"><span data-stu-id="dd781-210">In the **Password Reset** policy that you configured earlier, in the navigation pane, select **Page layouts**.</span></span>
1. <span data-ttu-id="dd781-211">Välj layouten **Ny lösenordssida**.</span><span class="sxs-lookup"><span data-stu-id="dd781-211">Select the **New password page** layout.</span></span>
1. <span data-ttu-id="dd781-212">Ställ in alternativet **Använd anpassat sidinnehåll** till **ja**.</span><span class="sxs-lookup"><span data-stu-id="dd781-212">Set the **Use custom page content** option to **Yes**.</span></span>
1. <span data-ttu-id="dd781-213">I fältet **Anpassad sid-URI** ange fullständig lösenordsåterställnings-URL.</span><span class="sxs-lookup"><span data-stu-id="dd781-213">In the **Custom page URI** field, enter the full password reset URL.</span></span> <span data-ttu-id="dd781-214">Inkludera suffixet **?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="dd781-214">Include the **?preloadscripts=true** suffix.</span></span> <span data-ttu-id="dd781-215">Ange exempelvis ``www.<my domain>.com/passwordreset?preloadscripts=true``.</span><span class="sxs-lookup"><span data-stu-id="dd781-215">For example, enter ``www.<my domain>.com/passwordreset?preloadscripts=true``.</span></span>
1. <span data-ttu-id="dd781-216">I fältet **Version av sidlayout (förhandsgranskning)**, välj **1.2.0**.</span><span class="sxs-lookup"><span data-stu-id="dd781-216">In the **Page Layout Version (Preview)** field, select **1.2.0**.</span></span>
1. <span data-ttu-id="dd781-217">Välj layouten **sida för kontoverifiering**.</span><span class="sxs-lookup"><span data-stu-id="dd781-217">Select the **Account verification page** layout.</span></span>
1. <span data-ttu-id="dd781-218">Ställ in alternativet **Använd anpassat sidinnehåll** till **ja**.</span><span class="sxs-lookup"><span data-stu-id="dd781-218">Set the **Use custom page content** option to **Yes**.</span></span>
1. <span data-ttu-id="dd781-219">I fältet **Anpassad sid-URI** ange fullständig lösenordsåterställning verifierings-URL.</span><span class="sxs-lookup"><span data-stu-id="dd781-219">In the **Custom page URI** field, enter the full password reset verification URL.</span></span> <span data-ttu-id="dd781-220">Inkludera suffixet **?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="dd781-220">Include the **?preloadscripts=true** suffix.</span></span> <span data-ttu-id="dd781-221">Ange exempelvis ``www.<my domain>.com/passwordreset-verification?preloadscripts=true``.</span><span class="sxs-lookup"><span data-stu-id="dd781-221">For example, enter ``www.<my domain>.com/passwordreset-verification?preloadscripts=true``.</span></span>
1. <span data-ttu-id="dd781-222">I fältet **Version av sidlayout (förhandsgranskning)**, välj **1.2.0**.</span><span class="sxs-lookup"><span data-stu-id="dd781-222">In the **Page Layout Version (Preview)** field, select **1.2.0**.</span></span>



## <a name="customize-default-text-strings-for-labels-and-descriptions"></a><span data-ttu-id="dd781-223">Anpassa standardtextsträngar för etiketter och beskrivningar</span><span class="sxs-lookup"><span data-stu-id="dd781-223">Customize default text strings for labels and descriptions</span></span>

<span data-ttu-id="dd781-224">I modulbiblioteket är inloggningsmoduler förifyllda med standardtextsträngar för etiketterna och beskrivningarna.</span><span class="sxs-lookup"><span data-stu-id="dd781-224">In the module library, sign-in modules are prefilled with default text strings for the labels and descriptions.</span></span> <span data-ttu-id="dd781-225">Du kan anpassa dessa strängar i SDK (Software Development Kit) genom att uppdatera värdena i global.json-filen för inloggningsmodulen.</span><span class="sxs-lookup"><span data-stu-id="dd781-225">You can customize these strings in the software development kit (SDK) by updating the values in the global.json file for the sign in module.</span></span>

<span data-ttu-id="dd781-226">Standardtexten för länken Glömt lösenordet är **glömt lösenord?**.</span><span class="sxs-lookup"><span data-stu-id="dd781-226">For example, the default text for the forgotten password link is **Forgotten password?**.</span></span> <span data-ttu-id="dd781-227">Nedan visas den här standardtexten på inloggningssidan.</span><span class="sxs-lookup"><span data-stu-id="dd781-227">The following shows this default text on the sign-in page.</span></span>

![Standardtext för länken Glömt lösenordet på inloggningssidan](./media/B2C_SignUp_ModuleFace.png)

<span data-ttu-id="dd781-229">I global.json-filen för modulen modulbibliotek kan du emellertid redigera texten till **glömt lösenordet?**, som du ser i bilden nedan.</span><span class="sxs-lookup"><span data-stu-id="dd781-229">However, in the global.json file for the module library sign-in module, you can edit the text to **Forgot Password?**, as shown in the following illustration.</span></span>

![Länktexten uppdaterades i loggen i modulens global.json-fil](./media/B2C_CustomizingStringsForModule.png)

<span data-ttu-id="dd781-231">När du har uppdaterat global.json-filen och publicerat ändringarna, visas den nya länktexten i modulen logga in både i handel och på live-inloggningssidan.</span><span class="sxs-lookup"><span data-stu-id="dd781-231">After you update the global.json file and publish your changes, the new link text appears in the sign-in module in both Commerce and on the live sign-in page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="dd781-232">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="dd781-232">Additional resources</span></span>

[<span data-ttu-id="dd781-233">Konfigurera ditt domännamn</span><span class="sxs-lookup"><span data-stu-id="dd781-233">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="dd781-234">Distribuera en ny klientorganisation för näthandel</span><span class="sxs-lookup"><span data-stu-id="dd781-234">Deploy a new e-commerce tenant</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="dd781-235">Skapa en näthandelssajt</span><span class="sxs-lookup"><span data-stu-id="dd781-235">Create an e-commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="dd781-236">Associera en Dynamics 365 Commerce-webbplats med en onlinekanal</span><span class="sxs-lookup"><span data-stu-id="dd781-236">Associate a Dynamics 365 Commerce site with an online channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="dd781-237">Hantera robots.txt-filer</span><span class="sxs-lookup"><span data-stu-id="dd781-237">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="dd781-238">Överför URL-omdirigeringar i bulk</span><span class="sxs-lookup"><span data-stu-id="dd781-238">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="dd781-239">Ställa in en B2C-innehavare i Commerce</span><span class="sxs-lookup"><span data-stu-id="dd781-239">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="dd781-240">Konfigurera flera B2C-innehavare i en Commerce-miljö</span><span class="sxs-lookup"><span data-stu-id="dd781-240">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="dd781-241">Lägga till stöd för ett innehållsleveransnätverk (CDN)</span><span class="sxs-lookup"><span data-stu-id="dd781-241">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="dd781-242">Aktivera platsbaserad butiksdetektering</span><span class="sxs-lookup"><span data-stu-id="dd781-242">Enable location-based store detection</span></span>](enable-store-detection.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
