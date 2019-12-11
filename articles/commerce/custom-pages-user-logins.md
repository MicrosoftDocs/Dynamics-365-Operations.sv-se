---
title: Ställa in anpassade sidor för användarinloggningar
description: I det här avsnittet beskrivs hur du skapar anpassade sidor i Microsoft Dynamics 365 Commerce som hanterar anpassade inloggningsuppgifter för användare av Azure Active Directory (Azure AD) B2C-innehavare (Business-to-Consumer).
author: brianshook
manager: annbe
ms.date: 10/01/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
audience: Application user
ms.reviewer: v-chgri
ms.search.scope: Operations, Retail, Core
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: brshoo
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.openlocfilehash: 644d937ddd3c219ae869f22d977d2846dffc20e1
ms.sourcegitcommit: 295d940a345879b3dfc5991e387b91c7257019ea
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/01/2019
ms.locfileid: "2697576"
---
# <a name="set-up-custom-pages-for-user-logins"></a><span data-ttu-id="df426-103">Ställa in anpassade sidor för användarinloggningar</span><span class="sxs-lookup"><span data-stu-id="df426-103">Set up custom pages for user logins</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="df426-104">I det här avsnittet beskrivs hur du skapar anpassade sidor i Microsoft Dynamics 365 Commerce som hanterar anpassade inloggningsuppgifter för användare av Azure Active Directory (Azure AD) B2C-innehavare (Business-to-Consumer).</span><span class="sxs-lookup"><span data-stu-id="df426-104">This topic describes how to build custom pages in Microsoft Dynamics 365 Commerce that handle customized sign-ins for users of Azure Active Directory (Azure AD) business-to-consumer (B2C) tenants.</span></span>

## <a name="overview"></a><span data-ttu-id="df426-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="df426-105">Overview</span></span>

<span data-ttu-id="df426-106">Om du vill använda anpassade sidor som har skapats i Dynamics 365 Commerce för att hantera användarinloggningsflöden måste du ställa in de Azure AD-policyer som kommer att refereras till i handelsmiljön.</span><span class="sxs-lookup"><span data-stu-id="df426-106">To use custom pages that are authored in Dynamics 365 Commerce to handle user sign-in flows, you must set up the Azure AD policies that will be referenced in the Commerce environment.</span></span> <span data-ttu-id="df426-107">Du kan konfigurera B2C-policyer "Registrera och logga in", "profilredigering" och "lösenordsåterställning" Azure AD B2C-policyer med hjälp av Azure AD B2C-programmet.</span><span class="sxs-lookup"><span data-stu-id="df426-107">You can configure the "Sign up and sign in," "Profile editing," and "Password reset" Azure AD B2C policies by using the Azure AD B2C application.</span></span> <span data-ttu-id="df426-108">Azure AD B2C-innehavare och policynamn kan sedan refereras under etableringsprocessen som utförs för handelsmiljön med hjälp av Microsoft Dynamics Lifecycle Services (LCS).</span><span class="sxs-lookup"><span data-stu-id="df426-108">The Azure AD B2C tenant and policy names can then be referenced during the provisioning process that is done for the Commerce environment by using Microsoft Dynamics Lifecycle Services (LCS).</span></span>

<span data-ttu-id="df426-109">De anpassade handelssidorna kan skapas med hjälp av modulen logga in, registrera, kontoprofil eller återställ lösenord.</span><span class="sxs-lookup"><span data-stu-id="df426-109">The custom Commerce pages can be built by using the sign in, sign up, account profile edit, or password reset module.</span></span> <span data-ttu-id="df426-110">De sid-URL:er som publiceras för dessa anpassade sidor bör sedan refereras i Azure AD B2C policykonfigurationer i Azure-portalen.</span><span class="sxs-lookup"><span data-stu-id="df426-110">The page URLs that are published for these custom pages should then be referenced in Azure AD B2C policy configurations in the Azure portal.</span></span>

## <a name="set-up-b2c-policies"></a><span data-ttu-id="df426-111">Ställ in B2C-policyer</span><span class="sxs-lookup"><span data-stu-id="df426-111">Set up B2C policies</span></span>

<span data-ttu-id="df426-112">När du har ställt in Azure AD B2C-innehavare och associerar den med din handelsmiljö, går du till sidan **Azure AD B2C** i Azure-portalen och väljer i menyn **Policyer** och sedan **Användarflöden (policyer)**.</span><span class="sxs-lookup"><span data-stu-id="df426-112">After you set up your Azure AD B2C tenant and associate it with your Commerce environment, go to the **Azure AD B2C** page in the Azure portal, and then, on the menu, under **Policies**, select **User flows (policies)**.</span></span>

![Kommandot användarflöden (policyer) på menyn](./media/B2C_CustomPage_PoliciesMenu.png)

<span data-ttu-id="df426-114">Du kan nu konfigurera användarinloggningsflöden "registrera och logga in", "profilredigering" och "lösenordsåterställning".</span><span class="sxs-lookup"><span data-stu-id="df426-114">You can now configure the "Sign up and sign in," "Profile editing," and "Password reset" user sign-in flows.</span></span>

### <a name="configure-the-sign-up-and-sign-in-policy"></a><span data-ttu-id="df426-115">Konfigurera policyn "Registrera och logga in"</span><span class="sxs-lookup"><span data-stu-id="df426-115">Configure the "Sign up and sign in" policy</span></span>

<span data-ttu-id="df426-116">För att konfigurera policyn "Registrera och logga in" följ stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="df426-116">To configure the "Sign up and sign in" policy, follow these steps.</span></span>

1. <span data-ttu-id="df426-117">Välj **nytt användarflöde** och välj sedan fliken **rekommenderad**, välj policyn **Logga in**.</span><span class="sxs-lookup"><span data-stu-id="df426-117">Select **New user flow**, and then, on the **Recommended** tab, select the **Sign up and sign in** policy.</span></span>
1. <span data-ttu-id="df426-118">Ange ett namn på policyn (till exempel **B2C\_1\_SignInSignUp**).</span><span class="sxs-lookup"><span data-stu-id="df426-118">Enter a name for the policy (for example, **B2C\_1\_SignInSignUp**).</span></span>
1. <span data-ttu-id="df426-119">I avsnittet **identitetsleverantörer** väljer du vilka identitetsleverantörer som ska användas för policyn.</span><span class="sxs-lookup"><span data-stu-id="df426-119">In the **Identity Providers** section, select the identity providers to use for the policy.</span></span> <span data-ttu-id="df426-120">Åtminstone måste du **välja e-postregistrering**.</span><span class="sxs-lookup"><span data-stu-id="df426-120">At a minimum, **Email signup** must be selected.</span></span>
1. <span data-ttu-id="df426-121">I kolumnen **Samla in attribut** välj kryssrutorna för **e-postadress**, **förnamn** och **efternamn**.</span><span class="sxs-lookup"><span data-stu-id="df426-121">In the **Collect attribute** column, select the check boxes for **Email Address**, **Given Name**, and **Surname**.</span></span>
1. <span data-ttu-id="df426-122">I kolumnen **returanspråk** markerar du kryssrutorna för **e-postadresser**, **förnamn**, **identitetsleverantör**, **efternamn** och **användarens objekt-ID**.</span><span class="sxs-lookup"><span data-stu-id="df426-122">In the **Return claim** column, select the check boxes for **Email Addresses**, **Given Name**, **Identity Provider**, **Surname**, and **User's Object ID**.</span></span>

    ![Valda attribut och anspråk](./media/B2C_SignInSignUp_Attributes.png)

1. <span data-ttu-id="df426-124">Skapa policyn genom att välja **OK**.</span><span class="sxs-lookup"><span data-stu-id="df426-124">Select **OK** to create the policy.</span></span>
1. <span data-ttu-id="df426-125">Dubbelklicka på det nya policynamnet och välj sedan **Egenskaper**i navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="df426-125">Double-click the new policy name, and then, in the navigation pane, select **Properties**.</span></span>
1. <span data-ttu-id="df426-126">Ange alternativet **aktivera JavaScript med tvingad sidlayout (förhandsgranskning)** till **På**.</span><span class="sxs-lookup"><span data-stu-id="df426-126">Set the **Enable JavaScript enforcing page layout (preview)** option to **On**.</span></span>

    ![Egenskapssida för den nya policyn](./media/B2C_SignInSignUp_EnableJavascript.png)

> [!NOTE]
> <span data-ttu-id="df426-128">Policynamnet kommer att refereras till i handelsmiljön.</span><span class="sxs-lookup"><span data-stu-id="df426-128">The policy name will be fully referenced in the Commerce environment.</span></span> <span data-ttu-id="df426-129">(Prefixet **B2C\_1\_** kommer att inkluderas i referensen.) Det går inte att byta namn på policyer när de har skapats.</span><span class="sxs-lookup"><span data-stu-id="df426-129">(The **B2C\_1\_** prefix will be included in the reference.) Policies can't be renamed after they are created.</span></span> <span data-ttu-id="df426-130">Om du ersätter en befintlig policy för din handelsmiljö, kan du ta bort den ursprungliga policyn och bygga en ny policy som har samma namn.</span><span class="sxs-lookup"><span data-stu-id="df426-130">If you're replacing an existing policy for your Commerce environment, you can delete the original policy and build a new policy that has the same name.</span></span> <span data-ttu-id="df426-131">Om miljön redan har etablerats kan du skicka det nya policynamnet via en tjänstbegäran.</span><span class="sxs-lookup"><span data-stu-id="df426-131">Alternatively, if the environment has already been provisioned, you can submit the new policy name through a service request.</span></span>

<span data-ttu-id="df426-132">Du kommer tillbaka till den här policyn för att slutföra installationen när du har byggt de anpassade sidorna.</span><span class="sxs-lookup"><span data-stu-id="df426-132">You will return to this policy to finish the setup after you've built the custom pages.</span></span> <span data-ttu-id="df426-133">Stäng nu policyn för att återgå till sidan **användarflöden (policyer)** i Azure-portalen.</span><span class="sxs-lookup"><span data-stu-id="df426-133">For now, close the policy to return to the **User flows (policies)** page in the Azure portal.</span></span>

### <a name="configure-the-profile-editing-policy"></a><span data-ttu-id="df426-134">Konfigurera policyn för "profilredigering"</span><span class="sxs-lookup"><span data-stu-id="df426-134">Configure the "Profile editing" policy</span></span>

<span data-ttu-id="df426-135">Gör på följande vis för att konfigurera policyn "profilredigering".</span><span class="sxs-lookup"><span data-stu-id="df426-135">To configure the "Profile editing" policy, follow these steps.</span></span>

1. <span data-ttu-id="df426-136">Välj **nytt användarflöde** och välj sedan fliken **rekommenderad**, välj policyn **profilredigering**.</span><span class="sxs-lookup"><span data-stu-id="df426-136">Select **New user flow**, and then, on the **Recommended** tab, select the **Profile editing** policy.</span></span>
1. <span data-ttu-id="df426-137">Ange ett namn på policyn (till exempel **B2C\_1\_EditProfile**).</span><span class="sxs-lookup"><span data-stu-id="df426-137">Enter a name for the policy (for example, **B2C\_1\_EditProfile**).</span></span>
1. <span data-ttu-id="df426-138">I avsnittet **identitetsleverantörer** väljer du vilka identitetsleverantörer som ska användas för policyn.</span><span class="sxs-lookup"><span data-stu-id="df426-138">In the **Identity Providers** section, select the identity providers to use for the policy.</span></span> <span data-ttu-id="df426-139">Åtminstone **Local Account SignIn** måste väljas.</span><span class="sxs-lookup"><span data-stu-id="df426-139">At a minimum, **Local Account SignIn** must be selected.</span></span>
1. <span data-ttu-id="df426-140">I kolumnen **Samla in attribut** välj kryssrutorna för **e-postadresser** och **efternamn**.</span><span class="sxs-lookup"><span data-stu-id="df426-140">In the **Collect attribute** column, select the check boxes for **Email Addresses** and **Surname**.</span></span>
1. <span data-ttu-id="df426-141">I kolumnen **returanspråk** markerar du kryssrutorna för **e-postadresser**, **förnamn**, **identitetsleverantör**, **efternamn** och **användarens objekt-ID**.</span><span class="sxs-lookup"><span data-stu-id="df426-141">In the **Return claim** column, select the check boxes for **Email Addresses**, **Given Name**, **Identity Provider**, **Surname**, and **User's Object ID**.</span></span>
1. <span data-ttu-id="df426-142">Skapa policyn genom att välja **OK**.</span><span class="sxs-lookup"><span data-stu-id="df426-142">Select **OK** to create the policy.</span></span>
1. <span data-ttu-id="df426-143">Dubbelklicka på det nya policynamnet och välj sedan **Egenskaper**i navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="df426-143">Double-click the new policy name, and then, in the navigation pane, select **Properties**.</span></span>
1. <span data-ttu-id="df426-144">Ange alternativet **aktivera JavaScript med tvingad sidlayout (förhandsgranskning)** till **På**.</span><span class="sxs-lookup"><span data-stu-id="df426-144">Set the **Enable JavaScript enforcing page layout (preview)** option to **On**.</span></span>

<span data-ttu-id="df426-145">Du kommer tillbaka till den här policyn för att slutföra installationen när du har byggt de anpassade sidorna.</span><span class="sxs-lookup"><span data-stu-id="df426-145">You will return to this policy to finish the setup after you've built the custom pages.</span></span> <span data-ttu-id="df426-146">Stäng nu policyn för att återgå till sidan **användarflöden (policyer)** i Azure-portalen.</span><span class="sxs-lookup"><span data-stu-id="df426-146">For now, close the policy to return to the **User flows (policies)** page in the Azure portal.</span></span>

### <a name="configure-the-password-reset-policy"></a><span data-ttu-id="df426-147">Konfigurera policyn "Återställ lösenord"</span><span class="sxs-lookup"><span data-stu-id="df426-147">Configure the "Password reset" policy</span></span>

<span data-ttu-id="df426-148">Gör på följande vis för att konfigurera policyn "Lösenordsåterställning".</span><span class="sxs-lookup"><span data-stu-id="df426-148">To configure the "Password reset" policy, follow these steps.</span></span>

1. <span data-ttu-id="df426-149">Välj **nytt användarflöde** och välj sedan fliken **Förhandsgranska**, välj policyn **lösenordsåterställning v1.1**.</span><span class="sxs-lookup"><span data-stu-id="df426-149">Select **New user flow**, and then, on the **Preview** tab, select the **Password reset v1.1** policy.</span></span>

    ![Policyn lösenordsåterställning v1.1 har valts på fliken förhandsgranskning](./media/B2C_ForgetPassword_Menu.png)

1. <span data-ttu-id="df426-151">Ange ett namn på policyn (till exempel **B2C\_1\_ForgetPassword**).</span><span class="sxs-lookup"><span data-stu-id="df426-151">Enter a name for the policy (for example, **B2C\_1\_ForgetPassword**).</span></span>
1. <span data-ttu-id="df426-152">I avsnittet **identitetsleverantörer** väljer du **Återställ lösenord med e-postadress**.</span><span class="sxs-lookup"><span data-stu-id="df426-152">In the **Identity Providers** section, select **Reset password using email address**.</span></span>
1. <span data-ttu-id="df426-153">I kolumnen **returanspråk** markerar du kryssrutorna för **e-postadresser**, **förnamn**, **efternamn** och **användarens objekt-ID**.</span><span class="sxs-lookup"><span data-stu-id="df426-153">In the **Return claim** column, select the check boxes for **Email Addresses**, **Given Name**, **Surname**, and **User's Object ID**.</span></span>

    ![Valda anspråk](./media/B2C_ForgetPassword_Attributes.png)

1. <span data-ttu-id="df426-155">Skapa policyn genom att välja **OK**.</span><span class="sxs-lookup"><span data-stu-id="df426-155">Select **OK** to create the policy.</span></span>
1. <span data-ttu-id="df426-156">Dubbelklicka på det nya policynamnet och välj sedan **Egenskaper**i navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="df426-156">Double-click the new policy name, and then, in the navigation pane, select **Properties**.</span></span>
1. <span data-ttu-id="df426-157">Ange alternativet **aktivera JavaScript med tvingad sidlayout (förhandsgranskning)** till **På**.</span><span class="sxs-lookup"><span data-stu-id="df426-157">Set the **Enable JavaScript enforcing page layout (preview)** option to **On**.</span></span>

<span data-ttu-id="df426-158">Du kommer tillbaka till den här policyn för att slutföra installationen när du har byggt de anpassade sidorna.</span><span class="sxs-lookup"><span data-stu-id="df426-158">You will return to this policy to finish the setup after you've built the custom pages.</span></span> <span data-ttu-id="df426-159">Stäng nu policyn för att återgå till sidan **användarflöden (policyer)** i Azure-portalen.</span><span class="sxs-lookup"><span data-stu-id="df426-159">For now, close the policy to return to the **User flows (policies)** page in the Azure portal.</span></span>

## <a name="build-the-custom-pages"></a><span data-ttu-id="df426-160">Skapa anpassade sidor</span><span class="sxs-lookup"><span data-stu-id="df426-160">Build the custom pages</span></span>

<span data-ttu-id="df426-161">Om du vill skapa de anpassade sidorna för att hantera användarinloggningar följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="df426-161">To build the custom pages to handle user sign-ins, follow these steps.</span></span>

1. <span data-ttu-id="df426-162">I handelsredigeringsverktyg, gå till din webbplats.</span><span class="sxs-lookup"><span data-stu-id="df426-162">In the Commerce authoring tools, go to your site.</span></span>
1. <span data-ttu-id="df426-163">Skapa följande fem mallar och fem sidor:</span><span class="sxs-lookup"><span data-stu-id="df426-163">Build the following five templates and five pages:</span></span>

    - <span data-ttu-id="df426-164">Mallen **Logga in** och sida där inloggningsmodulen används.</span><span class="sxs-lookup"><span data-stu-id="df426-164">A **Sign In** template and page that use the sign in module.</span></span>
    - <span data-ttu-id="df426-165">Mallen **Registrera dig** och sida där registreringsmodulen används.</span><span class="sxs-lookup"><span data-stu-id="df426-165">A **Sign Up** template and page that use the sign up module.</span></span>
    - <span data-ttu-id="df426-166">Mallen **lösenordsåterställning** och sidan med modulen lösenordsåterställning.</span><span class="sxs-lookup"><span data-stu-id="df426-166">A **Password Reset** template and page that use the password reset module.</span></span>
    - <span data-ttu-id="df426-167">Mallen **verifiering av lösenordsåterställning** och sidan med modulen verifiering av lösenordsåterställning.</span><span class="sxs-lookup"><span data-stu-id="df426-167">A **Password Reset verification** template and page that use the password reset verification module.</span></span>
    - <span data-ttu-id="df426-168">Mallen **profilredigering** och sidor som använder redigeringsmodulen för kontoprofilen</span><span class="sxs-lookup"><span data-stu-id="df426-168">A **Profile Edit** template and page that use the account profile edit module</span></span>

<span data-ttu-id="df426-169">Följ de här riktlinjerna när du skapar sidorna:</span><span class="sxs-lookup"><span data-stu-id="df426-169">When you build the pages, follow these guidelines:</span></span>

- <span data-ttu-id="df426-170">För varje sida eller modul använder du layouten och formatet som bäst passar dina affärsbehov.</span><span class="sxs-lookup"><span data-stu-id="df426-170">For each page or module, use the layout and style that best suit your business requirements.</span></span>
- <span data-ttu-id="df426-171">Publicera alla sidor och URL som måste användas i Azure AD B2C-inställningar.</span><span class="sxs-lookup"><span data-stu-id="df426-171">Publish all pages and URLs that must be used in the Azure AD B2C setup.</span></span>
- <span data-ttu-id="df426-172">När sidorna och adresserna har publicerats samlar du in de URL-adresser som måste användas för konfigurationer av Azure AD B2C-policy.</span><span class="sxs-lookup"><span data-stu-id="df426-172">After the pages and URLs are published, collect the URLs that must be used for the Azure AD B2C policy configurations.</span></span> <span data-ttu-id="df426-173">Suffixet **?preloadscripts=true** kommer att läggas till varje URL när det används.</span><span class="sxs-lookup"><span data-stu-id="df426-173">A **?preloadscripts=true** suffix will be added to every URL when it's used.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="df426-174">Återanvänd inte universella sidhuvuden och sidfötter med relativa länkar.</span><span class="sxs-lookup"><span data-stu-id="df426-174">Don't reuse universal headers and footers that have relative links.</span></span> <span data-ttu-id="df426-175">Eftersom dessa sidor kommer att finnas i Azure AD B2C-domänen när de används, ska endast absoluta URL:er användas för alla länkar.</span><span class="sxs-lookup"><span data-stu-id="df426-175">Because these pages will be hosted in the Azure AD B2C domain when they are used, only absolute URLs should be used for all links.</span></span>

## <a name="configure-azure-ad-b2c-policies-with-custom-page-information"></a><span data-ttu-id="df426-176">Konfigurera Azure AD B2C policyer med anpassad sidinformation</span><span class="sxs-lookup"><span data-stu-id="df426-176">Configure Azure AD B2C policies with custom page information</span></span> 

<span data-ttu-id="df426-177">I Azure-portalen, gå tillbaka till sidan **Azure AD B2C** och sedan på menyn under **Policyer**, välj **Användarflöden (policyer)**.</span><span class="sxs-lookup"><span data-stu-id="df426-177">In the Azure portal, return to the **Azure AD B2C** page, and then, on the menu, under **Policies**, select **User flows (policies)**.</span></span>

### <a name="update-the-sign-up-and-sign-in-policy-with-custom-page-information"></a><span data-ttu-id="df426-178">Uppdatera policyn "Registrera och logga in" med anpassad sidinformation</span><span class="sxs-lookup"><span data-stu-id="df426-178">Update the "Sign up and sign in" policy with custom page information</span></span>

<span data-ttu-id="df426-179">För att uppdatera policyn "Registrera och logga in" med anpassad sidinformation, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="df426-179">To update the "Sign up and sign in" policy with custom page information, follow these steps.</span></span>

1. <span data-ttu-id="df426-180">I policyn **Registrera och logga in** som du konfigurerade tidigare, i navigeringsfönstret, välj **Sidlayouter**.</span><span class="sxs-lookup"><span data-stu-id="df426-180">In the **Sign in and sign up** policy that you configured earlier, in the navigation pane, select **Page layouts**.</span></span>
1. <span data-ttu-id="df426-181">Välj layouten **Enhetlig sida för registrera och logga in**.</span><span class="sxs-lookup"><span data-stu-id="df426-181">Select the **Unified sign up or sign in page** layout.</span></span>
1. <span data-ttu-id="df426-182">Ställ in alternativet **Använd anpassat sidinnehåll** till **ja**.</span><span class="sxs-lookup"><span data-stu-id="df426-182">Set the **Use custom page content** option to **Yes**.</span></span>
1. <span data-ttu-id="df426-183">I fältet **Anpassad sid-URI** ange fullständig inloggnings-URL.</span><span class="sxs-lookup"><span data-stu-id="df426-183">In the **Custom page URI** field, enter the full sign-in URL.</span></span> <span data-ttu-id="df426-184">Inkludera suffixet **?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="df426-184">Include the **?preloadscripts=true** suffix.</span></span> <span data-ttu-id="df426-185">Ange till exempel **www.\<my domain\>.com/sign-in?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="df426-185">For example, enter **www.\<my domain\>.com/sign-in?preloadscripts=true**.</span></span>
1. <span data-ttu-id="df426-186">I fältet **Version av sidlayout (förhandsgranskning)**, välj **1.2.0**.</span><span class="sxs-lookup"><span data-stu-id="df426-186">In the **Page Layout Version (Preview)** field, select **1.2.0**.</span></span>
1. <span data-ttu-id="df426-187">Välj layouten **sida för registrering av lokalt konto**.</span><span class="sxs-lookup"><span data-stu-id="df426-187">Select the **Local account sign up page** layout.</span></span>
1. <span data-ttu-id="df426-188">Ställ in alternativet **Använd anpassat sidinnehåll** till **ja**.</span><span class="sxs-lookup"><span data-stu-id="df426-188">Set the **Use custom page content** option to **Yes**.</span></span>
1. <span data-ttu-id="df426-189">I fältet **Anpassad sid-URI** ange fullständig inloggnings-URL.</span><span class="sxs-lookup"><span data-stu-id="df426-189">In the **Custom page URI** field, enter the full sign-in URL.</span></span> <span data-ttu-id="df426-190">Inkludera suffixet **?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="df426-190">Include the **?preloadscripts=true** suffix.</span></span> <span data-ttu-id="df426-191">Ange till exempel **www.\<my domain\>.com/sign-in?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="df426-191">For example, enter **www.\<my domain\>.com/sign-in?preloadscripts=true**.</span></span>
1. <span data-ttu-id="df426-192">I fältet **Version av sidlayout (förhandsgranskning)**, välj **1.2.0**.</span><span class="sxs-lookup"><span data-stu-id="df426-192">In the **Page Layout Version (Preview)** field, select **1.2.0**.</span></span>
1. <span data-ttu-id="df426-193">I avsnittet **Användarattribut** följ dessa steg:</span><span class="sxs-lookup"><span data-stu-id="df426-193">In the **User attributes** section, follow these steps:</span></span>

    1. <span data-ttu-id="df426-194">För attributen **e-postadress**, **förnamn** och **efternamn** väljer du **nej** i fältet **kräver verifiering**.</span><span class="sxs-lookup"><span data-stu-id="df426-194">For the **Email Address**, **Given Name**, and **Surname** attributes, select **No** in the **Requires Verification** field.</span></span>
    1. <span data-ttu-id="df426-195">För attributen **förnamn** och **efternamn** välj **nej** i fältet **valfritt**.</span><span class="sxs-lookup"><span data-stu-id="df426-195">For the **Given Name** and **Surname** attributes, select **No** in the **Optional** field.</span></span>

    ![Konfiguration av policyn sida för registrering av lokalt konto](./media/B2C_SignUp_PageURLConfig.png)

### <a name="update-the-profile-editing-policy-with-custom-page-information"></a><span data-ttu-id="df426-197">Uppdatera policyn "Profilredigering" med anpassad sidinformation</span><span class="sxs-lookup"><span data-stu-id="df426-197">Update the "Profile editing" policy with custom page information</span></span>

<span data-ttu-id="df426-198">För att uppdatera policyn "Profilredigering" med anpassad sidinformation, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="df426-198">To update the "Profile editing" policy with custom page information, follow these steps.</span></span>

1. <span data-ttu-id="df426-199">I policyn **Profilredigering** som du konfigurerade tidigare, i navigeringsfönstret, välj **Sidlayouter**.</span><span class="sxs-lookup"><span data-stu-id="df426-199">In the **Profile Editing** policy that you configured earlier, in the navigation pane, select **Page layouts**.</span></span>
1. <span data-ttu-id="df426-200">Välj layouten **Profilredigeringssida**.</span><span class="sxs-lookup"><span data-stu-id="df426-200">Select the **Profile edit page** layout.</span></span>
1. <span data-ttu-id="df426-201">Ställ in alternativet **Använd anpassat sidinnehåll** till **ja**.</span><span class="sxs-lookup"><span data-stu-id="df426-201">Set the **Use custom page content** option to **Yes**.</span></span>
1. <span data-ttu-id="df426-202">I fältet **Anpassad sid-URI** ange fullständig inloggnings-URL.</span><span class="sxs-lookup"><span data-stu-id="df426-202">In the **Custom page URI** field, enter the full sign-in URL.</span></span> <span data-ttu-id="df426-203">Inkludera suffixet **?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="df426-203">Include the **?preloadscripts=true** suffix.</span></span> <span data-ttu-id="df426-204">Ange till exempel **www.\<my domain\>.com/sign-in?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="df426-204">For example, enter **www.\<my domain\>.com/sign-in?preloadscripts=true**.</span></span>
1. <span data-ttu-id="df426-205">I fältet **Version av sidlayout (förhandsgranskning)**, välj **1.2.0**.</span><span class="sxs-lookup"><span data-stu-id="df426-205">In the **Page Layout Version (Preview)** field, select **1.2.0**.</span></span>
1. <span data-ttu-id="df426-206">I avsnittet **Användarattribut** följ dessa steg:</span><span class="sxs-lookup"><span data-stu-id="df426-206">In the **User attributes** section, follow these steps:</span></span>

    1. <span data-ttu-id="df426-207">För attributen **e-postadress**, **förnamn** väljer du **nej** i fältet **kräver verifiering**.</span><span class="sxs-lookup"><span data-stu-id="df426-207">For the **Email Address**, **Given Name** attributes, select **No** in the **Requires Verification** field.</span></span>
    1. <span data-ttu-id="df426-208">För attributen **förnamn** och **efternamn** välj **nej** i fältet **valfritt**.</span><span class="sxs-lookup"><span data-stu-id="df426-208">For the **Given Name** and **Surname** attributes, select **No** in the **Optional** field.</span></span>

### <a name="update-the-password-reset-policy-with-custom-page-information"></a><span data-ttu-id="df426-209">Uppdatera policyn "Lösenordsåterställning" med anpassad sidinformation</span><span class="sxs-lookup"><span data-stu-id="df426-209">Update the "Password reset" policy with custom page information</span></span>

<span data-ttu-id="df426-210">För att uppdatera policyn "Lösenordsåterställning" med anpassad sidinformation, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="df426-210">To update the "Password reset" policy with custom page information, follow these steps.</span></span>

1. <span data-ttu-id="df426-211">I policyn **Lösenordsåterställning** som du konfigurerade tidigare, i navigeringsfönstret, välj **Sidlayouter**.</span><span class="sxs-lookup"><span data-stu-id="df426-211">In the **Password Reset** policy that you configured earlier, in the navigation pane, select **Page layouts**.</span></span>
1. <span data-ttu-id="df426-212">Välj layouten **Ny lösenordssida**.</span><span class="sxs-lookup"><span data-stu-id="df426-212">Select the **New password page** layout.</span></span>
1. <span data-ttu-id="df426-213">Ställ in alternativet **Använd anpassat sidinnehåll** till **ja**.</span><span class="sxs-lookup"><span data-stu-id="df426-213">Set the **Use custom page content** option to **Yes**.</span></span>
1. <span data-ttu-id="df426-214">I fältet **Anpassad sid-URI** ange fullständig inloggnings-URL.</span><span class="sxs-lookup"><span data-stu-id="df426-214">In the **Custom page URI** field, enter the full sign-in URL.</span></span> <span data-ttu-id="df426-215">Inkludera suffixet **?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="df426-215">Include the **?preloadscripts=true** suffix.</span></span> <span data-ttu-id="df426-216">Ange till exempel **www.\<my domain\>.com/sign-in?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="df426-216">For example, enter **www.\<my domain\>.com/sign-in?preloadscripts=true**.</span></span>
1. <span data-ttu-id="df426-217">I fältet **Version av sidlayout (förhandsgranskning)**, välj **1.2.0**.</span><span class="sxs-lookup"><span data-stu-id="df426-217">In the **Page Layout Version (Preview)** field, select **1.2.0**.</span></span>
1. <span data-ttu-id="df426-218">Välj layouten **sida för kontoverifiering**.</span><span class="sxs-lookup"><span data-stu-id="df426-218">Select the **Account verification page** layout.</span></span>
1. <span data-ttu-id="df426-219">Ställ in alternativet **Använd anpassat sidinnehåll** till **ja**.</span><span class="sxs-lookup"><span data-stu-id="df426-219">Set the **Use custom page content** option to **Yes**.</span></span>
1. <span data-ttu-id="df426-220">I fältet **Anpassad sid-URI** ange fullständig inloggnings-URL.</span><span class="sxs-lookup"><span data-stu-id="df426-220">In the **Custom page URI** field, enter the full sign-in URL.</span></span> <span data-ttu-id="df426-221">Inkludera suffixet **?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="df426-221">Include the **?preloadscripts=true** suffix.</span></span> <span data-ttu-id="df426-222">Ange till exempel **www.\<my domain\>.com/sign-in?preloadscripts=true**.</span><span class="sxs-lookup"><span data-stu-id="df426-222">For example, enter **www.\<my domain\>.com/sign-in?preloadscripts=true**.</span></span>
1. <span data-ttu-id="df426-223">I fältet **Version av sidlayout (förhandsgranskning)**, välj **1.2.0**.</span><span class="sxs-lookup"><span data-stu-id="df426-223">In the **Page Layout Version (Preview)** field, select **1.2.0**.</span></span>

## <a name="customize-default-text-strings-for-labels-and-descriptions"></a><span data-ttu-id="df426-224">Anpassa standardtextsträngar för etiketter och beskrivningar</span><span class="sxs-lookup"><span data-stu-id="df426-224">Customize default text strings for labels and descriptions</span></span>

<span data-ttu-id="df426-225">I startpaketet är inloggningsmoduler förifyllda med standardtextsträngar för etiketterna och beskrivningarna.</span><span class="sxs-lookup"><span data-stu-id="df426-225">In the starter kit, sign in modules are prefilled with default text strings for the labels and descriptions.</span></span> <span data-ttu-id="df426-226">Du kan anpassa dessa strängar i SDK (Software Development Kit) genom att uppdatera värdena i global.json-filen för inloggningsmodulen.</span><span class="sxs-lookup"><span data-stu-id="df426-226">You can customize these strings in the software development kit (SDK) by updating the values in the global.json file for the sign in module.</span></span>

<span data-ttu-id="df426-227">Standardtexten för länken Glömt lösenordet är **glömt lösenord?**.</span><span class="sxs-lookup"><span data-stu-id="df426-227">For example, the default text for the forgotten password link is **Forgotten password?**.</span></span> <span data-ttu-id="df426-228">Nedan visas den här standardtexten på inloggningssidan.</span><span class="sxs-lookup"><span data-stu-id="df426-228">The following shows this default text on the sign-in page.</span></span>

![Standardtext för länken Glömt lösenordet på inloggningssidan](./media/B2C_SignUp_ModuleFace.png)

<span data-ttu-id="df426-230">I global.json-filen för loggen i startpaket kan du emellertid redigera texten till **glömt lösenordet?**, som du ser i bilden nedan.</span><span class="sxs-lookup"><span data-stu-id="df426-230">However, in the global.json file for the starter kit sign in module, you can edit the text to **Forgot Password?**, as shown in the following illustration.</span></span>

![Länktexten uppdaterades i loggen i modulens global.json-fil](./media/B2C_CustomizingStringsForModule.png)

<span data-ttu-id="df426-232">När du har uppdaterat global.json-filen och publicerat ändringarna, visas den nya länktexten i modulen logga in både i handel och på live-inloggningssidan.</span><span class="sxs-lookup"><span data-stu-id="df426-232">After you update the global.json file and publish your changes, the new link text appears in the sign in module in both Commerce and on the live sign-in page.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="df426-233">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="df426-233">Additional resources</span></span>

[<span data-ttu-id="df426-234">Översikt över onlinebutik</span><span class="sxs-lookup"><span data-stu-id="df426-234">Online store overview</span></span>](online-store-overview.md)

[<span data-ttu-id="df426-235">Skapa en näthandelsplats</span><span class="sxs-lookup"><span data-stu-id="df426-235">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="df426-236">Distribuera en ny näthandelsplats</span><span class="sxs-lookup"><span data-stu-id="df426-236">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="df426-237">Associera en online-webbplats med en kanal</span><span class="sxs-lookup"><span data-stu-id="df426-237">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="df426-238">Konfigurera ditt domännamn</span><span class="sxs-lookup"><span data-stu-id="df426-238">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="df426-239">Lägga till stöd för ett innehållsleveransnätverk (CDN)</span><span class="sxs-lookup"><span data-stu-id="df426-239">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="df426-240">Aktivera platsbaserad butiksdetektering</span><span class="sxs-lookup"><span data-stu-id="df426-240">Enable location-based store detection</span></span>](enable-store-detection.md)
