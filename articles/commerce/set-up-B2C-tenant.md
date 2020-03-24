---
title: Ställa in en B2C-innehavare i Commerce
description: I det här avsnittet beskrivs hur du ställer in din Azure Active Directory (Azure AD) B2C-innehavare (Business-to-Consumer) för autentisering av användarplats i Dynamics 365 Commerce.
author: BrianShook
manager: annbe
ms.date: 03/02/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.scope: ''
ms.search.region: Global
ms.search.industry: retail
ms.author: BriShoo
ms.search.validFrom: 2020-02-13
ms.dyn365.ops.version: ''
ms.openlocfilehash: a5fca37fb89c723273ef753b102092e2cfb26563
ms.sourcegitcommit: 236672932ffd0a758012ebb7b2df9bc51249c126
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/03/2020
ms.locfileid: "3096527"
---
# <a name="set-up-a-b2c-tenant-in-commerce"></a><span data-ttu-id="7d9ce-103">Ställa in en B2C-innehavare i Commerce</span><span class="sxs-lookup"><span data-stu-id="7d9ce-103">Set up a B2C tenant in Commerce</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="7d9ce-104">I det här avsnittet beskrivs hur du ställer in din Azure Active Directory (Azure AD) B2C-innehavare (Business-to-Consumer) för autentisering av användarplats i Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-104">This topic describes how to set up your Azure Active Directory (Azure AD) business-to-consumer (B2C) tenants for user site authentication in Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="7d9ce-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="7d9ce-105">Overview</span></span>

<span data-ttu-id="7d9ce-106">Dynamics 365 Commerce använder Azure AD B2C för att stödja autentiseringsuppgifter för användare och verifikationsflöden.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-106">Dynamics 365 Commerce uses Azure AD B2C to support user credential and authentication flows.</span></span> <span data-ttu-id="7d9ce-107">En användare kan registrera sig, logga in och återställa sitt lösenord genom dessa flöden.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-107">A user can sign up, sign in, and reset their password through these flows.</span></span> <span data-ttu-id="7d9ce-108">Azure AD B2C lagrar känslig information om användarautentisering, t.ex. användarnamn och lösenord.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-108">Azure AD B2C stores sensitive user authentication information, such as username and password.</span></span> <span data-ttu-id="7d9ce-109">Användarposten i B2C-innehavaren kommer att lagra antingen en B2C lokal kontopost eller en post för en B2C social identitetsleverantör.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-109">The user record in the B2C tenant will store either a B2C local account record or a B2C social identity provider record.</span></span> <span data-ttu-id="7d9ce-110">Dessa B2C-poster kommer att länkas tillbaka till kundposten i Commerce-miljön.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-110">These B2C records will link back to the customer record in the Commerce environment.</span></span>

## <a name="create-or-link-to-an-existing-aad-b2c-tenant-in-the-azure-portal"></a><span data-ttu-id="7d9ce-111">Skapa eller länka till en befintlig AAD B2C-klientorganisation i Azure-portalen</span><span class="sxs-lookup"><span data-stu-id="7d9ce-111">Create or link to an existing AAD B2C tenant in the Azure portal</span></span>

1. <span data-ttu-id="7d9ce-112">Logga in på [Azure-portal](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="7d9ce-112">Sign in to the [Azure portal](https://portal.azure.com/).</span></span>
1. <span data-ttu-id="7d9ce-113">Från Azure-portal menyn, välj **skapa en resurs**.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-113">From the Azure portal menu, select **Create a resource**.</span></span> <span data-ttu-id="7d9ce-114">Se till att använda den prenumeration och katalog som kommer att vara ansluten till din Commerce-miljö.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-114">Be sure to use the subscription and directory that will be connected with your Commerce environment.</span></span>

    ![Skapa en resurs i Azure-portalen](./media/B2CImage_1.png)

1. <span data-ttu-id="7d9ce-116">Gå till **identitet \>Azure Active Directory B2C**.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-116">Go to **Identity \> Azure Active Directory B2C**.</span></span>
1. <span data-ttu-id="7d9ce-117">På sidan **Skapa ny B2C-klient eller länk till befintlig klient** använder du ett av alternativen nedan som bäst passar ditt företags behov:</span><span class="sxs-lookup"><span data-stu-id="7d9ce-117">Once on the **Create New B2C Tenant or Link to existing Tenant** page, use one of the options below that best suits your company's needs:</span></span>

    - <span data-ttu-id="7d9ce-118">**Skapa en ny Azure AD B2C-innehavare**: Använd det här alternativet om du vill skapa en ny AAD B2C-innehavare.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-118">**Create a new Azure AD B2C Tenant**: Use this option to create a new AAD B2C tenant.</span></span>
        1. <span data-ttu-id="7d9ce-119">Välj **Skapa ett nytt Azure AD B2C-innehavare**.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-119">Select **Create a new Azure AD B2C Tenant**.</span></span>
        1. <span data-ttu-id="7d9ce-120">Ange **organisationsnamnet** under organisationsnamn.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-120">Under **Organization name**, enter the organization name.</span></span>
        1. <span data-ttu-id="7d9ce-121">Under **Initialt domännamn**, ange initialt domännamn.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-121">Under **Initial domain name**, enter the initial domain name.</span></span>
        1. <span data-ttu-id="7d9ce-122">För **land eller region** välj land eller region.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-122">For **Country or region**, select the country or region.</span></span>
        1. <span data-ttu-id="7d9ce-123">Välj **skapa** om du vill skapa innehavaren.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-123">Select **Create** to create the tenant.</span></span>

     ![Skapa en ny Azure AD innehavare](./media/B2CImage_2.png)

     - <span data-ttu-id="7d9ce-125">**Länka en befintlig Azure AD B2C-innehavare till min Azure-prenumeration**: Använd det här alternativet om du redan har en Azure AD B2C innehavare som du vill länka till.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-125">**Link an existing Azure AD B2C Tenant to my Azure subscription**: Use this option if you already have an Azure AD B2C tenant you want to link to.</span></span>
        1. <span data-ttu-id="7d9ce-126">Välj **länka en befintlig Azure AD B2C-klient till mitt Azure-abonnemang**.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-126">Select **Link an existing Azure AD B2C Tenant to my Azure subscription**.</span></span>
        1. <span data-ttu-id="7d9ce-127">Välj **Azure AD B2C innehavare** välj för B2C-innehavaren.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-127">For **Azure AD B2C Tenant**, select the appropriate B2C tenant.</span></span> <span data-ttu-id="7d9ce-128">Om meddelandet "inga bidragsberättigande B2C-innehavare hittades" visas i urvalsrutan har du inte en giltig B2C klientorganisation och behöver skapa en ny.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-128">If the message "No eligible B2C Tenants found" appears in the selection box, you do not have an existing eligible B2C tenant and will need to create a new one.</span></span>
        1. <span data-ttu-id="7d9ce-129">För **Resursgrupp**, välj **Skapa nya**.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-129">For **Resource group**, select **Create new**.</span></span> <span data-ttu-id="7d9ce-130">Ange ett **namn** på den resursgrupp som ska innehålla innehavaren, välj **Välj resursgruppens plats** och välj **sedan skapa**.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-130">Enter a **Name** for the resource group that will contain the tenant, select the **Resource group location**, and then select **Create**.</span></span>

    ![Länka en befintlig Azure AD B2C innehavare till Azure abonnemang](./media/B2CImage_3.png)

1. <span data-ttu-id="7d9ce-132">När den nya Azure AD B2C skapas (detta kan ta en stund) visas en länk till den nya katalogen på instrumentpanelen.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-132">Once the new Azure AD B2C directory is created (this may take a few moments), a link to the new directory will appear on the dashboard.</span></span> <span data-ttu-id="7d9ce-133">Länken leder till sidan "Välkommen till Azure Active Directory B2C".</span><span class="sxs-lookup"><span data-stu-id="7d9ce-133">This link will direct you to the "Welcome to Azure Active Directory B2C" page.</span></span>

    ![Länk till ny AAD-katalog](./media/B2CImage_4.png)

> [!NOTE]
> <span data-ttu-id="7d9ce-135">Om du har flera prenumerationer inom ditt Azure-konto eller har ställt in B2C-klienten utan att länka till en aktiv **prenumeration**, kommer en felsökningsannons att leda till att du kopplar klienten till en prenumeration.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-135">If you have multiple subscriptions within your Azure account or have set up the B2C tenant without linking to an active subscription, a **Troubleshoot** banner will direct you to link the tenant to a subscription.</span></span> <span data-ttu-id="7d9ce-136">Markera felsökningsmeddelandet och följ instruktionerna för att lösa prenumerationsproblemet.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-136">Select the troubleshooting message and follow the instructions to resolve the subscription issue.</span></span>

<span data-ttu-id="7d9ce-137">Följande bild visar ett exempel på en Azure AD B2C **felsökning** banderoll.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-137">The following image shows an example of an Azure AD B2C **Troubleshoot** banner.</span></span>

![Varnings visar av katalog har ingen aktiv prenumeration](./media/B2CImage_5.png)

## <a name="create-the-b2c-application"></a><span data-ttu-id="7d9ce-139">Skapa B2C-applikationen</span><span class="sxs-lookup"><span data-stu-id="7d9ce-139">Create the B2C application</span></span>

<span data-ttu-id="7d9ce-140">När B2C-innehavaren har skapats kommer du att skapa ett B2C-program inom innehavaren för att samverka med Commerce-åtgärderna.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-140">Once the B2C tenant has been created, you will create a B2C application within the tenant to interact with the Commerce actions.</span></span>

<span data-ttu-id="7d9ce-141">Gör så här om du vill skapa ett B2C-applikation.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-141">To create the B2C application, follow these steps.</span></span>

1. <span data-ttu-id="7d9ce-142">Markera **Program** och välj **Lägg till** i Azure-portalen.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-142">In the Azure portal, select **Applications** and then select **Add**.</span></span>
1. <span data-ttu-id="7d9ce-143">Under **namn** anger du namnet på det önskade AAD B2C-programmet.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-143">Under **Name**, enter the name of the desired AAD B2C application.</span></span>
1. <span data-ttu-id="7d9ce-144">Under **Webbapp/Webb-API**, för **Inkludera webbapp/webb-API**, välj **Ja**.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-144">Under **Web App/Web API**, for **Include web app / web API**, select **Yes**.</span></span>
1. <span data-ttu-id="7d9ce-145">För **Tillåt implicit flöde**, välj **Ja** (standardvärde).</span><span class="sxs-lookup"><span data-stu-id="7d9ce-145">For **Allow implicit flow**, select **Yes** (the default value).</span></span>
1. <span data-ttu-id="7d9ce-146">Ange **Svars-URL** för svar under svars-URL.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-146">Under **Reply URL**, enter your dedicated reply URLs.</span></span> <span data-ttu-id="7d9ce-147">Se [besvara URL](#reply-urls) nedan för information om svars-URL:er och hur du formaterar dem.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-147">See [Reply URLs](#reply-urls) below for information on reply URLs and how to format them here.</span></span>
1. <span data-ttu-id="7d9ce-148">För **Inkludera inhemsk klient**, välj **Nej** (standardvärdet).</span><span class="sxs-lookup"><span data-stu-id="7d9ce-148">For **Include native client**, select **No** (the default value).</span></span>
1. <span data-ttu-id="7d9ce-149">Markera **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-149">Select **Create**.</span></span>

### <a name="reply-urls"></a><span data-ttu-id="7d9ce-150">Svars-URL</span><span class="sxs-lookup"><span data-stu-id="7d9ce-150">Reply URLs</span></span>

<span data-ttu-id="7d9ce-151">Svars-URL är viktiga eftersom de tillåter en vitlista av returdomänerna när platsen anropar Azure AD B2C för autentisering av en användare.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-151">Reply URLs are important as they allow a whitelist of the return domains when your site calls Azure AD B2C to authenticate a user.</span></span> <span data-ttu-id="7d9ce-152">På så sätt kan den autentiserade användaren returnera tillbaka till den domän som de loggar in på (din webbplatsdomän).</span><span class="sxs-lookup"><span data-stu-id="7d9ce-152">This allows the return of the authenticated user back to the domain from which they are signing into (your site domain).</span></span> 

<span data-ttu-id="7d9ce-153">I rutan **Svars-URL** på skärmen **Azure AD B2C - program \> Ny program** måste du lägga till separata rader för både din webbplatsdomän och (när din miljö har etablerats) den URL som genereras av Commerce.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-153">In the **Reply URL** box on the **Azure AD B2c - Applications \> New application** screen, you need to add separate lines for both your site domain and (once your environment is provisioned) the Commerce-generated URL.</span></span> <span data-ttu-id="7d9ce-154">URL-adresserna får alltid använda ett giltigt URL-format och måste bara vara bas-URL:er (inga snedstreck eller sökvägar kan avslutas).</span><span class="sxs-lookup"><span data-stu-id="7d9ce-154">These URLs must always use a valid URL format and must be base URLs only (no trailing forward slashes or paths).</span></span> <span data-ttu-id="7d9ce-155">Strängen ``/_msdyn365/authresp`` måste läggas till i bas-URL:erna, som i följande exempel.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-155">The string ``/_msdyn365/authresp`` then needs to be appended to the base URLs, as in the following examples.</span></span>

- ``https://fabrikam.com/_msdyn365/authresp``
- ``https://fabrikam-prod.commerce.dynamics.com/_msdyn365/authresp``

## <a name="create-user-flow-policies"></a><span data-ttu-id="7d9ce-156">Skapa policyer för användarflöden</span><span class="sxs-lookup"><span data-stu-id="7d9ce-156">Create user flow policies</span></span>

<span data-ttu-id="7d9ce-157">Användarflöden är de policyer Azure AD B2C använder för att tillhandahålla säker inloggning, registrera, redigera profil och glömma användarupplevelser för lösenord.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-157">User flows are the policies Azure AD B2C uses to provide secure sign in, sign up, edit profile, and forget password user experiences.</span></span> <span data-ttu-id="7d9ce-158">Dynamics 365 Commerce använder dessa flöden för att utföra policyåtgärder för samverkan med Azure AD B2C-innehavaren.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-158">Dynamics 365 Commerce uses these flows to perform the policy actions to interact with the Azure AD B2C tenant.</span></span> <span data-ttu-id="7d9ce-159">När en användare interagerar med dessa principer, omdirigeras de till Azure AD B2C-innehavaren för att utföra åtgärderna.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-159">When a user interacts with these policies, they are redirected to the Azure AD B2C tenant to perform the actions.</span></span>

<span data-ttu-id="7d9ce-160">Azure AD B2C har tre grundläggande användarflödestyper:</span><span class="sxs-lookup"><span data-stu-id="7d9ce-160">Azure AD B2C provides three basic user flow types:</span></span>
- <span data-ttu-id="7d9ce-161">Registrera dig och logga in</span><span class="sxs-lookup"><span data-stu-id="7d9ce-161">Sign up and sign in</span></span>
- <span data-ttu-id="7d9ce-162">Profilredigering</span><span class="sxs-lookup"><span data-stu-id="7d9ce-162">Profile editing</span></span>
- <span data-ttu-id="7d9ce-163">Återställ lösenord</span><span class="sxs-lookup"><span data-stu-id="7d9ce-163">Password reset</span></span>

<span data-ttu-id="7d9ce-164">Du kan välja att använda standard användarflöden som tillhandahålls av Azure AD, vilket visar en sida som finns i AAD B2C.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-164">You can choose to use the default user flows provided by Azure AD, which will display a page hosted by AAD B2C.</span></span> <span data-ttu-id="7d9ce-165">Du kan också skapa en HTML-sida för att kontrollera hur dessa användarflödesupplevelser ser ut och fungerar.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-165">Alternately, you can create an HTML page to control the look and feel of these user flow experiences.</span></span> 

<span data-ttu-id="7d9ce-166">Information om hur du anpassar sidorna för Dynamics 365 Commerce finns i [Konfigurera användarsidor för användarinloggningar](custom-pages-user-logins.md).</span><span class="sxs-lookup"><span data-stu-id="7d9ce-166">To customize the user policy pages for Dynamics 365 Commerce, see [Set up custom pages for user logins](custom-pages-user-logins.md).</span></span> <span data-ttu-id="7d9ce-167">Mer information finns i [Anpassa gränssnittet för användarupplevelser i Azure Active Directory B2C](https://docs.microsoft.com/azure/active-directory-b2c/tutorial-customize-ui).</span><span class="sxs-lookup"><span data-stu-id="7d9ce-167">For additional information, see [Customize the interface of user experiences in Azure Active Directory B2C](https://docs.microsoft.com/azure/active-directory-b2c/tutorial-customize-ui).</span></span>

### <a name="create-a-sign-up-and-sign-in-user-flow-policy"></a><span data-ttu-id="7d9ce-168">Skapa en policy för användarflöde för registrering och inloggning</span><span class="sxs-lookup"><span data-stu-id="7d9ce-168">Create a sign up and sign in user flow policy</span></span>

<span data-ttu-id="7d9ce-169">För att skapa en inloggning och policy för användarflöde följ stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-169">To create a sign up and sign in user flow policy, follow these steps.</span></span>

1. <span data-ttu-id="7d9ce-170">I Azure-portalen väljer du **Användarflöden (policyer)** i det vänstra navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-170">In the Azure portal, select **User flows (policies)** in the left navigation pane.</span></span>
1. <span data-ttu-id="7d9ce-171">På sidan **Azure AD B2C – användarflöden (policyer)** väljer du **Nytt användarflöde**.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-171">On the **Azure AD B2C – User flows (policies)** page, select **New User Flow**.</span></span>
1. <span data-ttu-id="7d9ce-172">På fliken **Rekommenderad** välj **registrera dig och logga in**.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-172">On the **Recommended** tab, select **Sign up and sign in**.</span></span>
1. <span data-ttu-id="7d9ce-173">Under **Namn**, ange ett policynamn.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-173">Under **Name**, enter a policy name.</span></span> <span data-ttu-id="7d9ce-174">Det här namnet visas efteråt med ett prefix som portalen tilldelar (t.ex. "B2C_1_").</span><span class="sxs-lookup"><span data-stu-id="7d9ce-174">This name will display afterwards with a prefix the portal assigns (for example, "B2C_1_").</span></span>
1. <span data-ttu-id="7d9ce-175">Under **identitetsleverantörer**, välj lämplig kryssruta.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-175">Under **Identity providers**, select the appropriate check box.</span></span>
1. <span data-ttu-id="7d9ce-176">Under **Flerfaktorautentisering** väljer du lämpligt val för ditt företag.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-176">Under **Multifactor Authentication**, select the appropriate choice for your company.</span></span> 
1. <span data-ttu-id="7d9ce-177">Under **användarattribut och anspråk** väljer du alternativ för att samla in attribut eller returnera anspråk efter behov.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-177">Under **User attributes and claims**, select options to collect attributes or return claims as appropriate.</span></span> <span data-ttu-id="7d9ce-178">Commerce kräver följande standardalternativ:</span><span class="sxs-lookup"><span data-stu-id="7d9ce-178">Commerce requires the following default options:</span></span>

    | <span data-ttu-id="7d9ce-179">**Samla in attribut**</span><span class="sxs-lookup"><span data-stu-id="7d9ce-179">**Collect  attribute**</span></span> | <span data-ttu-id="7d9ce-180">**Returnera anspråk**</span><span class="sxs-lookup"><span data-stu-id="7d9ce-180">**Return  claim**</span></span> |
    | ---------------------- | ----------------- |
    |                        | <span data-ttu-id="7d9ce-181">E-postadresser</span><span class="sxs-lookup"><span data-stu-id="7d9ce-181">Email Addresses</span></span>   |
    | <span data-ttu-id="7d9ce-182">Angivet namn</span><span class="sxs-lookup"><span data-stu-id="7d9ce-182">Given Name</span></span>             | <span data-ttu-id="7d9ce-183">Angivet namn</span><span class="sxs-lookup"><span data-stu-id="7d9ce-183">Given Name</span></span>        |
    |                        | <span data-ttu-id="7d9ce-184">Identitetsprovider</span><span class="sxs-lookup"><span data-stu-id="7d9ce-184">Identity Provider</span></span> |
    | <span data-ttu-id="7d9ce-185">Efternamn</span><span class="sxs-lookup"><span data-stu-id="7d9ce-185">Surname</span></span>                | <span data-ttu-id="7d9ce-186">Efternamn</span><span class="sxs-lookup"><span data-stu-id="7d9ce-186">Surname</span></span>           |
    |                        | <span data-ttu-id="7d9ce-187">Användarens objekt-ID</span><span class="sxs-lookup"><span data-stu-id="7d9ce-187">User’s Object ID</span></span>  |

1. <span data-ttu-id="7d9ce-188">Markera **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-188">Select **Create**.</span></span>

<span data-ttu-id="7d9ce-189">Följande bild är ett exempel på Azure AD B2C registrering och inloggning i användarflödet.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-189">The following image is an example of the Azure AD B2C sign up and sign in user flow.</span></span>

![Inställningar av policyn Registrera och logga in](./media/B2CImage_11.png)

<span data-ttu-id="7d9ce-191">I bilden nedan visas alternativet **kör användarflöde** i Azure AD B2C för att registrera och logga in i användarflödet.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-191">The following image shows the **Run user flow** option in the Azure AD B2C sign up and sign in user flow.</span></span>

![Kör användarflödesalternativ i policyflöde](./media/B2CImage_23.png)
   
### <a name="create-a-profile-editing-user-flow-policy"></a><span data-ttu-id="7d9ce-193">Skapa en profil genom att redigera användarflödespolicy</span><span class="sxs-lookup"><span data-stu-id="7d9ce-193">Create a profile editing user flow policy</span></span>

<span data-ttu-id="7d9ce-194">För att en profilredigering för policy för användarflöde följ stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-194">To create a profile editing user flow policy, follow these steps.</span></span>

1. <span data-ttu-id="7d9ce-195">I Azure-portalen väljer du **Användarflöden (policyer)** i det vänstra navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-195">In the Azure portal, select **User flows (policies)** in the left navigation pane.</span></span>
1. <span data-ttu-id="7d9ce-196">På sidan **Azure AD B2C – användarflöden (policyer)** väljer du **Nytt användarflöde**.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-196">On the **Azure AD B2C – User flows (policies)** page, select **New User Flow**.</span></span>
1. <span data-ttu-id="7d9ce-197">På fliken **Rekommenderad**, välj **Profilredigering**.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-197">On the **Recommended** tab, select **Profile editing**.</span></span>
1. <span data-ttu-id="7d9ce-198">Under **namn** anger du användarflödet för profilredigering.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-198">Under **Name**, enter the profile editing user flow.</span></span> <span data-ttu-id="7d9ce-199">Det här namnet visas efteråt med ett prefix som portalen tilldelar (t.ex. "B2C_1_").</span><span class="sxs-lookup"><span data-stu-id="7d9ce-199">This name will display afterwards with a prefix the portal assigns (for example, "B2C_1_").</span></span>
1. <span data-ttu-id="7d9ce-200">Under **identitetsleverantörer**, välj **Inloggning på lokalt konto**.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-200">Under **Identity providers**, select **Local Account SignIn**.</span></span>
1. <span data-ttu-id="7d9ce-201">Markera en eller flera av följande kryssrutor under **Användarattribut**:</span><span class="sxs-lookup"><span data-stu-id="7d9ce-201">Under **User attributes**, select the following check boxes:</span></span>
    - <span data-ttu-id="7d9ce-202">**E-postadresser** (endast **returanspråk**)</span><span class="sxs-lookup"><span data-stu-id="7d9ce-202">**Email Addresses** (**Return claim** only)</span></span>
    - <span data-ttu-id="7d9ce-203">**Angivet namn** (**Samla in attribut** och **returanspråk**)</span><span class="sxs-lookup"><span data-stu-id="7d9ce-203">**Given Name** (**Collect attribute** and **Return claim**)</span></span>
    - <span data-ttu-id="7d9ce-204">**Identitetsleverantör** (endast **returanspråk**)</span><span class="sxs-lookup"><span data-stu-id="7d9ce-204">**Identity Provider** (**Return claim** only)</span></span>
    - <span data-ttu-id="7d9ce-205">**Efternamn** (**Samla in attribut** och **returanspråk**)</span><span class="sxs-lookup"><span data-stu-id="7d9ce-205">**Surname** (**Collect attribute** and **Return claim**)</span></span>
    - <span data-ttu-id="7d9ce-206">**Användarens objekt-ID** (endast **returanspråk**)</span><span class="sxs-lookup"><span data-stu-id="7d9ce-206">**User's Object ID** (**Return claim** only)</span></span>
1. <span data-ttu-id="7d9ce-207">Markera **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-207">Select **Create**.</span></span>

<span data-ttu-id="7d9ce-208">Följande bild visar ett exempel på Azure AD B2C-profil som redigerar användarflödet.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-208">The following image shows an example of the Azure AD B2C profile editing user flow.</span></span>

![Skapa en användarflödet profilredigering](./media/B2CImage_12.png)

### <a name="create-a-password-reset-user-flow-policy"></a><span data-ttu-id="7d9ce-210">Skapa en lösenordsåterställning för användarflödespolicy</span><span class="sxs-lookup"><span data-stu-id="7d9ce-210">Create a password reset user flow policy</span></span>

<span data-ttu-id="7d9ce-211">För att en lösenordsåterställning för policy för användarflöde följ stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-211">To create a password reset user flow policy, follow these steps.</span></span>

1. <span data-ttu-id="7d9ce-212">I Azure-portalen väljer du **Användarflöden (policyer)** i det vänstra navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-212">In the Azure portal, select **User flows (policies)** in the left navigation pane.</span></span>
1. <span data-ttu-id="7d9ce-213">På sidan **Azure AD B2C – användarflöden (policyer)** väljer du **Nytt användarflöde**.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-213">On the **Azure AD B2C – User flows (policies)** page, select **New User Flow**.</span></span>
1. <span data-ttu-id="7d9ce-214">På fliken **Rekommenderad**, välj **lösenordsåterställning**.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-214">On the **Recommended** tab, select **Password Reset**.</span></span>
1. <span data-ttu-id="7d9ce-215">Under **namn** anger du ett namn på användarflödet för återställning av lösenord.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-215">Under **Name**, enter a name for the password reset user flow.</span></span>
1. <span data-ttu-id="7d9ce-216">Under **identitetsleverantörer** väljer du **Återställ lösenord med e-postadress**.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-216">Under **Identity providers**, select **Reset password using email address**.</span></span>
1. <span data-ttu-id="7d9ce-217">Markera **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-217">Select **Create**.</span></span>
1. <span data-ttu-id="7d9ce-218">Markera en eller flera av följande kryssrutor under **Programanspråk**:</span><span class="sxs-lookup"><span data-stu-id="7d9ce-218">Under **Application claims**, select the following check boxes:</span></span>
    - <span data-ttu-id="7d9ce-219">**E-postadress**</span><span class="sxs-lookup"><span data-stu-id="7d9ce-219">**Email**</span></span>
    - <span data-ttu-id="7d9ce-220">**Adresser**</span><span class="sxs-lookup"><span data-stu-id="7d9ce-220">**Addresses**</span></span>
    - <span data-ttu-id="7d9ce-221">**Angivet namn**</span><span class="sxs-lookup"><span data-stu-id="7d9ce-221">**Given Name**</span></span>
    - <span data-ttu-id="7d9ce-222">**Efternamn**</span><span class="sxs-lookup"><span data-stu-id="7d9ce-222">**Surname**</span></span>
    - <span data-ttu-id="7d9ce-223">**Användarens objekt-ID**</span><span class="sxs-lookup"><span data-stu-id="7d9ce-223">**User's Object ID**</span></span>
1. <span data-ttu-id="7d9ce-224">Markera **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-224">Select **Create**.</span></span>

<span data-ttu-id="7d9ce-225">I följande bild visas var du ska ange **Återställ lösenord med e-postadress** i Azure AD B2C lösenordsåterställning för användarflöde.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-225">The following image shows where to set **Reset Password using mail address** in the Azure AD B2C password reset user flow.</span></span>

![Ange "Återställ lösenord med e-postadress" i policyn för lösenordsåterställning](./media/B2CImage_13.png)

## <a name="add-social-identity-providers-optional"></a><span data-ttu-id="7d9ce-227">Lägg till sociala identitetsleverantör (valfritt)</span><span class="sxs-lookup"><span data-stu-id="7d9ce-227">Add social identity providers (Optional)</span></span>

<span data-ttu-id="7d9ce-228">Med sociala identitetsleverantör kan användarna använda sina sociala konton för autentisering.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-228">Social identity providers allow users to use their social accounts for authentication.</span></span> <span data-ttu-id="7d9ce-229">Att lägga till sociala identitetsleverantör är valfritt i Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-229">Adding social identity provider authentication is optional in Dynamics 365 Commerce.</span></span> 

<span data-ttu-id="7d9ce-230">Om autentiseringen av sociala identitetsleverantör inte läggs till blir Azure AD B2C standard-profiler huvudprofilerna för användarbasen.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-230">If social identity provider authentication is not added, the default Azure AD B2C profiles will be the main profiles for your user base.</span></span> <span data-ttu-id="7d9ce-231">Användarna väljer sina egna användarnamn (deras standard-e-postadress) och anger ett lösenord.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-231">Users will select their own username (their preferred email address) and set a password.</span></span> <span data-ttu-id="7d9ce-232">Azure AD B2C kommer att autentisera användare direkt.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-232">Azure AD B2C will authenticate users directly.</span></span> 

<span data-ttu-id="7d9ce-233">Om autentisering av sociala identitetsleverantörer läggs till och en användare väljer en av de tillgängliga leverantörerna av sociala identiteter, skapas en entitet fortfarande i Azure AD B2C-innehavaren.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-233">If social identity provider authentication is added and a user chooses one of the social identity providers offered, an entity is still created in the Azure AD B2C tenant.</span></span> <span data-ttu-id="7d9ce-234">Azure AD B2C kommer sedan att autentisera användarens uppgifter hos den sociala identitetsleverantören.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-234">Azure AD B2C will then authenticate the user's credentials with the social identity provider.</span></span>

> [!NOTE]
> <span data-ttu-id="7d9ce-235">Identitetsleverantörens inloggning skapar en post i B2C-innehavaren, men i ett annat format än lokala konton eftersom den ska anropa den externa referensen för social identitetsleverantör för autentisering.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-235">The identity provider sign in creates a record in the B2C tenant, but in a different format than local accounts since it will call the external social identity provider reference for authentication.</span></span> <span data-ttu-id="7d9ce-236">Användaren kan använda samma e-postadress för sociala identitetsleverantör, vilket innebär att e-postnamnet som används för autentisering kanske inte är unikt för innehavaren.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-236">The user can use the same email address across social identity providers, meaning that the email username used for authentication may not be unique to the tenant.</span></span> <span data-ttu-id="7d9ce-237">Azure AD B2C kommer bara att säkerställa att användarna har en unik e-postadress på lokala B2C-konton.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-237">Azure AD B2C will only enforce that users have a unique email address on local B2C accounts.</span></span>

<span data-ttu-id="7d9ce-238">Innan du kan lägga till en social identitetsleverantör för autentisering måste du gå till identitetsleverantörens portal och ställa in ett program för identitetsleverantör enligt anvisningarna i Azure AD B2C-dokumentationen.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-238">Before you can add a social identity provider for authentication, you must go to the identity provider's portal and set up an identity provider application as instructed in the Azure AD B2C documentation.</span></span> <span data-ttu-id="7d9ce-239">Nedan finns en lista med länkar till dokumentationen.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-239">A list of links to the documentation is provided below.</span></span>

- [<span data-ttu-id="7d9ce-240">Amazon</span><span class="sxs-lookup"><span data-stu-id="7d9ce-240">Amazon</span></span>](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-amzn-app)
- [<span data-ttu-id="7d9ce-241">Azure AD (En innehavare)</span><span class="sxs-lookup"><span data-stu-id="7d9ce-241">Azure AD (Single Tenant)</span></span>](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-oidc-azure-active-directory)
- [<span data-ttu-id="7d9ce-242">Microsoft-konto</span><span class="sxs-lookup"><span data-stu-id="7d9ce-242">Microsoft Account</span></span>](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-msa-app)
- [<span data-ttu-id="7d9ce-243">Facebook</span><span class="sxs-lookup"><span data-stu-id="7d9ce-243">Facebook</span></span>](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-fb-app)
- [<span data-ttu-id="7d9ce-244">GitHub</span><span class="sxs-lookup"><span data-stu-id="7d9ce-244">GitHub</span></span>](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-github-app)
- [<span data-ttu-id="7d9ce-245">Google</span><span class="sxs-lookup"><span data-stu-id="7d9ce-245">Google</span></span>](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-goog-app)
- [<span data-ttu-id="7d9ce-246">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="7d9ce-246">LinkedIn</span></span>](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-li-app)
- [<span data-ttu-id="7d9ce-247">OpenID Connect</span><span class="sxs-lookup"><span data-stu-id="7d9ce-247">OpenID Connect</span></span>](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-oidc-idp)
- [<span data-ttu-id="7d9ce-248">Twitter</span><span class="sxs-lookup"><span data-stu-id="7d9ce-248">Twitter</span></span>](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-twitter-app)

### <a name="add-and-set-up-a-social-identity-provider"></a><span data-ttu-id="7d9ce-249">Lägga till och ställa in en leverantör av sociala identiteter</span><span class="sxs-lookup"><span data-stu-id="7d9ce-249">Add and set up a social identity provider</span></span>

<span data-ttu-id="7d9ce-250">Lägg till och ställ in en leverantör av sociala identiteter enligt följande instruktioner.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-250">To add and set up a social identity provider, follow these steps.</span></span>  

1. <span data-ttu-id="7d9ce-251">I Azure-portal, navigera till **identitetsleverantörer**.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-251">In the Azure portal, navigate to **Identity Providers**.</span></span>
1. <span data-ttu-id="7d9ce-252">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-252">Select **Add**.</span></span> <span data-ttu-id="7d9ce-253">Skärmen **Lägg till identitetsleverantör** visas.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-253">The **Add identity provider** screen appears.</span></span>
1. <span data-ttu-id="7d9ce-254">Under **namn** anger du det namn som ska visas för användarna i inloggningsskärmen.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-254">Under **Name**, enter the name to be displayed to users on your sign in screen.</span></span>
1. <span data-ttu-id="7d9ce-255">Under **Typ av identitetsleverantör**, välj en identitetsleverantör från listan.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-255">Under **Identity provider type**, select an identity provider from the list.</span></span>
1. <span data-ttu-id="7d9ce-256">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-256">Select **OK**.</span></span>
1. <span data-ttu-id="7d9ce-257">Välj **konfigurera den här identitetsleverantören** för åtkomst till skärmen **Ställ in till fönstret för social identitetsleverantör**.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-257">Select **Set up this identity provider** to access the **Set up the social identity provider** screen.</span></span>
1. <span data-ttu-id="7d9ce-258">Under **klient-ID**, ange det klient-ID som hämtas från programinställningar för identitetsleverantör.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-258">Under **Client ID**, enter the client ID as obtained from the identity provider application setup.</span></span>
1. <span data-ttu-id="7d9ce-259">Under **klienthemlighet**, ange den klienthemlighet som hämtas från programinställningar för identitetsleverantör.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-259">Under **Client secret**, enter the client secret as obtained from the identity provider application setup.</span></span>
1. <span data-ttu-id="7d9ce-260">Koppla användarflöde för inloggningsprinciper för inloggning:</span><span class="sxs-lookup"><span data-stu-id="7d9ce-260">Attach user flow for sign in sign up policies:</span></span>
1. <span data-ttu-id="7d9ce-261">Gå till **Azure AD B2C – användarflöden (principer)\> {din policy för registrering och inloggning} \> identitetsleverantörer**.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-261">Go to **Azure AD B2C – User flows (policies) \> {your sign-in sign-up policy} \> Identity providers**.</span></span>
1. <span data-ttu-id="7d9ce-262">Om du vill koppla användarflödespolicyn för inloggning/registrering markerar du varje identitetsleverantör som du har skapat för ditt konto.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-262">To attach the sign in/sign up user flow policy, select each identity provider you have set up for your account.</span></span> <span data-ttu-id="7d9ce-263">Om du vill testa dessa väljer du **kör användarflöde** för varje identitetsleverantör.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-263">To test these, select **Run user flow** for each identity provider.</span></span> <span data-ttu-id="7d9ce-264">På en ny flik visas inloggningssidan med den nya valrutan för identitetsleverantörer.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-264">A new tab will display the sign-in page displaying the new identity provider selection box.</span></span>

<span data-ttu-id="7d9ce-265">Följande bild illustrerar exempel på skärmarna **lägga till identitetsleverantören** och **ställer in social identitetsleverantören** i Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-265">The following image shows examples of the **Add identity provider** and **Set up the social identity provider** screens in Azure AD B2C.</span></span>

![Lägga till en social identitetsleverantör i ditt program](./media/B2CImage_14.png)

<span data-ttu-id="7d9ce-267">I följande bild visas ett exempel på hur du väljer identitetsleverantörer på sidan Azure AD B2C **identitetsleverantörer**.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-267">The following image shows an example of how to select identity providers on the Azure AD B2C **Identity Providers** page.</span></span>

![Välj varje social identitetsleverantör som ska aktiveras för din policy](./media/B2CImage_16.png)

<span data-ttu-id="7d9ce-269">I bilden nedan visas ett exempel på en standard inloggningsskärm med knappen för inloggning med sociala identitetsleverantörer som visas.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-269">The following image shows an example of a default sign-in screen with a social identity provider sign-in button displayed.</span></span>

![Exempel på standard inloggningsskärm när inloggningsknappen för sociala identitetsleverantörer visas](./media/B2CImage_17.png)

## <a name="update-commerce-headquarters-with-the-new-azure-ad-b2c-information"></a><span data-ttu-id="7d9ce-271">Uppdatera Commerce-administration med den nya Azure AD B2C-informationen</span><span class="sxs-lookup"><span data-stu-id="7d9ce-271">Update Commerce headquarters with the new Azure AD B2C information</span></span>

<span data-ttu-id="7d9ce-272">När Azure AD B2C etableringsstegen ovan har slutförts måste Azure AD B2C-programmet vara registrerat i din Dynamics 365 Commerce-miljö.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-272">Once the Azure AD B2C provisioning steps above are completed, the Azure AD B2C application must be registered in your Dynamics 365 Commerce environment.</span></span>

<span data-ttu-id="7d9ce-273">Om du vill uppdatera huvud kontoret med den nya Azure AD B2C-informationen följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-273">To update headquarters with the new Azure AD B2C information, follow these steps.</span></span>

1. <span data-ttu-id="7d9ce-274">I Commerce går du till **delade Commerce-parametrar** och väljer **identitetsleverantörer** på den vänstra menyn.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-274">In Commerce, go to **Commerce Shared Parameters** and select **Identity Providers** in the left menu.</span></span>
1. <span data-ttu-id="7d9ce-275">Under **identitetsleverantörer** gör du följande:</span><span class="sxs-lookup"><span data-stu-id="7d9ce-275">Under **Identity Providers**, do the following:</span></span>
    1. <span data-ttu-id="7d9ce-276">I rutan **utfärdare** anger du URL för identitetsleverantörens utfärdare.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-276">In the **Issuer** box, enter the identity provider issuer URL.</span></span> <span data-ttu-id="7d9ce-277">Information om hur du hittar din utfärdar-URL, se [Hämta utfärdar-URL](#obtain-issuer-url) nedan.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-277">To find your issuer URL, see [Obtain issuer URL](#obtain-issuer-url) below.</span></span>
    1. <span data-ttu-id="7d9ce-278">I rutan **Namn**, ange ett namn för din utfärdarpost.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-278">In the **Name** box, enter a name for your issuer record.</span></span>
    1. <span data-ttu-id="7d9ce-279">I rutan **Typ**, ange **Azure AD B2C (id_token)**.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-279">In the **Type** box, enter **Azure AD B2C (id_token)**.</span></span>
1. <span data-ttu-id="7d9ce-280">Under **Förlitande parter**, med ovanstående B2C för identitetsleverantör:</span><span class="sxs-lookup"><span data-stu-id="7d9ce-280">Under **Relying Parties**, with the above B2C identity provider item selected, do the following:</span></span>
    1. <span data-ttu-id="7d9ce-281">I rutan **ClientID**, ange ditt B2C program-ID.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-281">In the **ClientID** box, enter your B2C application ID.</span></span> <span data-ttu-id="7d9ce-282">Du hittar detta i rutan **Program-ID** på egenskapssida B2C-program.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-282">You can find this in the **Application ID** box of your B2C application's properties page.</span></span>
    1. <span data-ttu-id="7d9ce-283">I rutan **Typ** ange **Offentlig**.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-283">In the **Type** box, enter **Public**.</span></span>
    1. <span data-ttu-id="7d9ce-284">I rutan **Användartyp** ange **Kund**.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-284">In the **User Type** box, enter **Customer**.</span></span>
1. <span data-ttu-id="7d9ce-285">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-285">On the action pane, select **Save**.</span></span>
1. <span data-ttu-id="7d9ce-286">I Commerce-sökrutan, sök efter **nummerserier** (organisationsadministration > nummerserier).</span><span class="sxs-lookup"><span data-stu-id="7d9ce-286">In the Commerce search box, search for **Number sequences** (Organization administration > Number sequences).</span></span>
1. <span data-ttu-id="7d9ce-287">Under åtgärdsfönstret, välj **redigera** under **underhåll**.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-287">Under the action pane, select **Edit** under **Maintain**.</span></span>
1. <span data-ttu-id="7d9ce-288">På snabbfliken **allmänt** väljer du **Nej** för **Manuell**.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-288">On the **General** fast tab, select **No** for **Manual**.</span></span>
1. <span data-ttu-id="7d9ce-289">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-289">On the action pane, select **Save**.</span></span> 
1. <span data-ttu-id="7d9ce-290">I Commerce-sökrutan, sök efter **Distributionsschema**</span><span class="sxs-lookup"><span data-stu-id="7d9ce-290">In the Commerce search box, search for **Distribution schedule**</span></span>
1. <span data-ttu-id="7d9ce-291">I den vänstra navigeringsmenyn på sidan **distributionsscheman** väljer du **1110 Global konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-291">In the left navigation menu of the **Distribution schedules** page, select job **1110 Global configuration**.</span></span>
1. <span data-ttu-id="7d9ce-292">I åtgärdsfönstret, klicka på **Kör nu**.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-292">On the action pane, select **Run Now**.</span></span>

### <a name="obtain-issuer-url"></a><span data-ttu-id="7d9ce-293">Hämta utfärdar-URL</span><span class="sxs-lookup"><span data-stu-id="7d9ce-293">Obtain issuer URL</span></span>

<span data-ttu-id="7d9ce-294">Om du vill ha en utfärdar-URL för identitetsleverantören följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-294">To obtain your identity provider issuer URL, follow these steps.</span></span>

1. <span data-ttu-id="7d9ce-295">Skapa en URL för en metadataadress i följande format med hjälp av din B2C-klient och policy: ``https://<B2CTENANTNAME>.b2clogin.com/<B2CTENANTNAME>.onmicrosoft.com/v2.0/.well-known/openid-configuration?p=<B2CSIGN-INPOLICY>``</span><span class="sxs-lookup"><span data-stu-id="7d9ce-295">Create a metadata address URL in the following format using your B2C tenant and policy: ``https://<B2CTENANTNAME>.b2clogin.com/<B2CTENANTNAME>.onmicrosoft.com/v2.0/.well-known/openid-configuration?p=<B2CSIGN-INPOLICY>``</span></span>
    - <span data-ttu-id="7d9ce-296">Exempel: ``https://d365plc.b2clogin.com/d365plc.onmicrosoft.com/v2.0/.well-known/openid-configuration?p=B2C_1_signinup``.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-296">Example: ``https://d365plc.b2clogin.com/d365plc.onmicrosoft.com/v2.0/.well-known/openid-configuration?p=B2C_1_signinup``.</span></span>
1. <span data-ttu-id="7d9ce-297">Ange URL-adressen för metadata i webbläsarens adressfält.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-297">Enter the metadata address URL into a browser address bar.</span></span>
1. <span data-ttu-id="7d9ce-298">I metadata kopierar du URL:en för identitetsleverantören (värdet för **"utfärdare"**).</span><span class="sxs-lookup"><span data-stu-id="7d9ce-298">In the metadata, copy the identity provider issuer URL (the value for **"issuer"**).</span></span>
    - <span data-ttu-id="7d9ce-299">Exempel: ``https://login.fabrikam.com/073405c3-0113-4f43-b5e2-df01266e24ae/v2.0/``.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-299">Example: ``https://login.fabrikam.com/073405c3-0113-4f43-b5e2-df01266e24ae/v2.0/``.</span></span>

## <a name="configure-your-b2c-tenant-in-commerce-site-builder"></a><span data-ttu-id="7d9ce-300">Konfigurera din B2C-innehavare i Commerce webbplatsskaparen</span><span class="sxs-lookup"><span data-stu-id="7d9ce-300">Configure your B2C tenant in Commerce site builder</span></span>

<span data-ttu-id="7d9ce-301">När installationen av din Azure AD B2C-innehavare har slutförts måste du konfigurera B2C-innehavaren i Commerce webbplatsskaparen.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-301">Once setup of your Azure AD B2C tenant is completed, you must configure the B2C tenant in Commerce site builder.</span></span> <span data-ttu-id="7d9ce-302">Konfigurationsstegen omfattar insamling av B2C programinformation från Azure-portalen, ange B2C programinformation till webbplatsskaparen och sedan associera B2C-programmet med din webbplats och kanal.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-302">Configuration steps include collecting B2C application information from the Azure portal, entering that B2C application information into site builder, and then associating the B2C application with your site and channel.</span></span>

### <a name="collect-the-required-application-information"></a><span data-ttu-id="7d9ce-303">Samla in nödvändig programinformation</span><span class="sxs-lookup"><span data-stu-id="7d9ce-303">Collect the required application information</span></span>

<span data-ttu-id="7d9ce-304">Gör så här för att samla in den nödvändiga programinformationen.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-304">To collect the required application information, follow these steps.</span></span>

1. <span data-ttu-id="7d9ce-305">I Azure-portal, gå till **Start \> Azure AD B2C - program**.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-305">In the Azure portal, go to **Home \> Azure AD B2C - Applications**.</span></span>
1. <span data-ttu-id="7d9ce-306">Markera programmet och välj sedan i vänstra navigeringsfönstret **Egenskaper** för att hämta programinformationen.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-306">Select your application, and then in the left navigation pane select **Properties** to obtain the application details.</span></span>
1. <span data-ttu-id="7d9ce-307">Från rutan **program-ID**, samla in program-ID för B2C-programmet som har skapats i B2C-innehavaren.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-307">From the **Application ID** box, collect the application ID of the B2C application created in your B2C tenant.</span></span> <span data-ttu-id="7d9ce-308">Detta kommer senare att anges som **klient-GUID** i webbplatsskaparen.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-308">This will later be entered as the **Client GUID** in site builder.</span></span>
1. <span data-ttu-id="7d9ce-309">Under **Svars-URL**, samla svars-URL.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-309">Under **Reply URL**, collect the reply URL.</span></span>
1. <span data-ttu-id="7d9ce-310">Gå till **Start \> Azure AD B2C – användarflöden (policyer)** och samla sedan in namnen på varje användarflödespolicy.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-310">Go to **Home \> Azure AD B2C – User flows (policies)**, and then collect the names of each user flow policy.</span></span>

<span data-ttu-id="7d9ce-311">Följande bild visar ett exempel på sidan **Azure AD B2C-program**.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-311">The following image shows an example of the **Azure AD B2C - Applications** page.</span></span>

![Navigera till B2C-programmet inom din klientorganisation](./media/B2CImage_19.png)

<span data-ttu-id="7d9ce-313">Följande bild visar ett exempel på en programsida **egenskaper** i Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-313">The following image shows an example of an application **Properties** page in Azure AD B2C.</span></span> 

![Kopiera program-ID från B2C programegenskaper](./media/B2CImage_21.png)

<span data-ttu-id="7d9ce-315">Följande bild visar ett exempel på användarflödespolicyer på sidan **Azure AD B2C – användarflöden (policy)**.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-315">The following image shows an example of user flow policies on the **Azure AD B2C – User flows (policies)** page.</span></span>

![Samla in namnen på varje B2C policyflöde](./media/B2CImage_22.png)

### <a name="enter-your-aad-b2c-tenant-application-information-into-commerce"></a><span data-ttu-id="7d9ce-317">Ange din AAD B2C-information för klientprogram i Commerce</span><span class="sxs-lookup"><span data-stu-id="7d9ce-317">Enter your AAD B2C tenant application information into Commerce</span></span>

<span data-ttu-id="7d9ce-318">Du måste ange information om Azure AD B2C-innehavaren i Commerce webbplatsskaparen innan du kopplar B2C-innehavaren till dina webbplatser.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-318">You must enter details of the Azure AD B2C tenant into Commerce site builder before associating the B2C tenant with your site(s).</span></span>

<span data-ttu-id="7d9ce-319">Följ stegen nedan om du vill lägga till din AAD B2C-information till Commerce.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-319">To add your AAD B2C tenant application information to Commerce, follow these steps.</span></span>

1. <span data-ttu-id="7d9ce-320">Logga in som administratör på Commerce webbplatsskaparen för din miljö.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-320">Sign in as an administrator to Commerce site builder for your environment.</span></span>
1. <span data-ttu-id="7d9ce-321">I det vänstra navigeringsfönstret väljer du **innehavarinställningar** för att expandera den.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-321">In the left navigation pane, select **Tenant Settings**  to expand it.</span></span>
1. <span data-ttu-id="7d9ce-322">Under **innehavarinställningar** väljer du **B2C-inställningar**.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-322">Under **Tenant Settings**, select **B2C Settings**.</span></span> 
1. <span data-ttu-id="7d9ce-323">I huvudfönstret bredvid **B2C-program**, välj **Hantera**.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-323">In the main window next **B2C Applications**, select **Manage**.</span></span> <span data-ttu-id="7d9ce-324">(Om din klientorganisation visas i listan B2C-program, har den redan lagts till av en administratör.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-324">(If your tenant appears in the B2C Applications list, then it was already added by an administrator.</span></span> <span data-ttu-id="7d9ce-325">Kontrollera att artiklarna i steg 6 nedan matchar ditt B2C-program.)</span><span class="sxs-lookup"><span data-stu-id="7d9ce-325">Verify that the items in step 6 below match your B2C Application.)</span></span>
1. <span data-ttu-id="7d9ce-326">Välj **Lägg till B2C-program**.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-326">Select **Add B2C Application**.</span></span>
1. <span data-ttu-id="7d9ce-327">Ange följande obligatoriska objekt i formuläret som visas med värden från din B2C-innehavare och programmet.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-327">Enter the following required items in the form displayed, using values from your B2C tenant and application.</span></span> <span data-ttu-id="7d9ce-328">Fält som inte är obligatoriska (sådana som saknar asterisk) kan lämnas tomma.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-328">Fields that are not required (those without an asterisk) may be left blank.</span></span>

    - <span data-ttu-id="7d9ce-329">**Programnamn**: namnet på ditt B2C-program, t.ex. "Fabrikam B2C".</span><span class="sxs-lookup"><span data-stu-id="7d9ce-329">**Application Name**: The name for your B2C Application, for example "Fabrikam B2C".</span></span>
    - <span data-ttu-id="7d9ce-330">**Klientorganisationens namn**: namnet på din B2C-innehavare, t.ex. "Fabrikam".</span><span class="sxs-lookup"><span data-stu-id="7d9ce-330">**Tenant Name**: The name of your B2C Tenant, for example "Fabrikam".</span></span>
    - <span data-ttu-id="7d9ce-331">**Glömt lösenordspolicy-ID**: glöm lösenord användarflödespolicy-ID, t.ex. "B2C_1_PasswordReset".</span><span class="sxs-lookup"><span data-stu-id="7d9ce-331">**Forget Password Policy ID**: The forget password user flow policy ID, for example "B2C_1_PasswordReset".</span></span>
    - <span data-ttu-id="7d9ce-332">**Policy-ID för registrering och inloggning**: användarflödespolicy-ID för registrering och inloggning, t.ex. "B2C_1_signup_signin".</span><span class="sxs-lookup"><span data-stu-id="7d9ce-332">**Signup Signin Policy ID**: The sign up and sign in user flow policy ID, for example "B2C_1_signup_signin".</span></span>
    - <span data-ttu-id="7d9ce-333">**Klient-GUID**: B2C program-ID, till exempel "22290eb2-c52e-42e9-8b35-a2b0a3bcb9e6".</span><span class="sxs-lookup"><span data-stu-id="7d9ce-333">**Client GUID**: The B2C application ID, for example "22290eb2-c52e-42e9-8b35-a2b0a3bcb9e6".</span></span>
    - <span data-ttu-id="7d9ce-334">**Redigera profilpolicy-ID-**: profil som redigerar användarflödespolicy-ID, till exempel "B2C_1A_ProfileEdit".</span><span class="sxs-lookup"><span data-stu-id="7d9ce-334">**Edit Profile Policy ID**: The profile editing user flow policy ID, for example "B2C_1A_ProfileEdit".</span></span>

1. <span data-ttu-id="7d9ce-335">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-335">Select **OK**.</span></span> <span data-ttu-id="7d9ce-336">Nu ska nu se att namnet på ditt B2C-program visas i listan.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-336">You should now see the name of your B2C application appear in the list.</span></span>

### <a name="associate-the-b2c-application-to-your-site-and-channel"></a><span data-ttu-id="7d9ce-337">Associera B2C program till din webbplats och kanal</span><span class="sxs-lookup"><span data-stu-id="7d9ce-337">Associate the B2C application to your site and channel</span></span>

> [!WARNING]
> <span data-ttu-id="7d9ce-338">Om webbplatsen redan är associerad med ett B2C-program tas aktuella referenser för användare som redan registrerats i den här miljön bort när du byter till ett annat B2C-program.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-338">If your site is already associated with a B2C application, changing to a different B2C application will remove the current references established for users already signed up in this environment.</span></span> <span data-ttu-id="7d9ce-339">Om det ändras kommer inga autentiseringsuppgifter som associeras med det B2C programmet att vara tillgängliga för användarna.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-339">If changed, any credentials associated with the currently-assigned B2C application will not be available to users.</span></span> 
> 
> <span data-ttu-id="7d9ce-340">Uppdatera endast B2C-programmet om du ställer in kanalens B2C-program för första gången eller om du vill att användarna ska registrera dig igen med nya autentiseringsuppgifter för den här kanalen med det nya B2C-programmet.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-340">Only update the B2C application if you are setting up the channel's B2C application for the first time or if you intend to have users re-sign up with new credentials to this channel with the new B2C application.</span></span> <span data-ttu-id="7d9ce-341">Var försiktig när du kopplar kanaler till B2C-program och namnge program tydligt.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-341">Take caution when associating channels to B2C applications, and name applications clearly.</span></span> <span data-ttu-id="7d9ce-342">Om en kanal inte är associerad med ett B2C program i stegen nedan, kommer användare som loggar in på den kanalen för din webbplats att anges i B2C-program som visas **standard** i **innehavarinställningar \> B2C-inställningar** för B2C-program.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-342">If a channel is not associated to a B2C application in the steps below, users signing into that channel for your site will be entered into the B2C application showing as **default** in the **Tenant Settings \> B2C Settings** list of B2C applications.</span></span>

<span data-ttu-id="7d9ce-343">För att associera B2C-program till din webbplats och kanal, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-343">To associate the B2C application to your site and channel, follow these steps.</span></span>

1. <span data-ttu-id="7d9ce-344">Navigera till webbplatsen i Commerce webbplatsskaparen.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-344">Navigate to your site in Commerce site builder.</span></span>
1. <span data-ttu-id="7d9ce-345">I det vänstra navigeringsfönstret väljer du **Webbplatsinställningar** för att expandera den.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-345">In the left navigation pane, select **Site Settings** to expand it.</span></span>
1. <span data-ttu-id="7d9ce-346">Under **webbplatsinställningar**, välj **kanaler**.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-346">Below **Site Settings**, select **Channels**.</span></span>
1. <span data-ttu-id="7d9ce-347">I huvudfönstret under **kanaler**, välj din kanal.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-347">In the main window under **Channels**, select your channel.</span></span>
1. <span data-ttu-id="7d9ce-348">I rutan kanal egenskaper till höger väljer du B2C-programnamnet från nedrullningsbara menyn **Välj B2C-program**.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-348">In the channel properties pane on the right, select your B2C application name from the **Select B2C Application** drop down menu.</span></span>
1. <span data-ttu-id="7d9ce-349">Välj **Stäng** och välj sedan **Spara och publicera**.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-349">Select **Close**, and then select **Save and Publish**.</span></span>

## <a name="additional-b2c-information"></a><span data-ttu-id="7d9ce-350">Ytterligare B2C-information</span><span class="sxs-lookup"><span data-stu-id="7d9ce-350">Additional B2C information</span></span>

### <a name="customer-migration"></a><span data-ttu-id="7d9ce-351">Kundmigrering</span><span class="sxs-lookup"><span data-stu-id="7d9ce-351">Customer migration</span></span>

<span data-ttu-id="7d9ce-352">Om du funderar på att flytta kundposter från en tidigare plattform för identitetsleverantörer, arbeta med Dynamics 365 Commerce för att granska behovet av kundmigrering.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-352">If you are considering migrating customer records from a previous identity provider platform, please work with the Dynamics 365 Commerce team to review your customer migration needs.</span></span>

<span data-ttu-id="7d9ce-353">För ytterligare Azure AD B2C-dokumentation om kundmigrering, se [Migrera användare till Azure Active Directory B2C](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-user-migration).</span><span class="sxs-lookup"><span data-stu-id="7d9ce-353">For additional Azure AD B2C documentation on customer migration, see [Migrate users to Azure Active Directory B2C](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-user-migration).</span></span>

### <a name="custom-policies"></a><span data-ttu-id="7d9ce-354">Anpassade principer</span><span class="sxs-lookup"><span data-stu-id="7d9ce-354">Custom policies</span></span>

<span data-ttu-id="7d9ce-355">Mer information om hur du anpassar Azure AD-interaktioner och policyflöden utöver vad som erbjuds av B2C, se [Anpassa policyer i Azure Active Directory B2C](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-overview-custom).</span><span class="sxs-lookup"><span data-stu-id="7d9ce-355">For additional information regarding customizing Azure AD B2C interactions and policy flows beyond what is offered by B2C standard policies, see [Custom policies in Azure Active Directory B2C](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-overview-custom).</span></span> 

### <a name="secondary-admin"></a><span data-ttu-id="7d9ce-356">Sekundär administration</span><span class="sxs-lookup"><span data-stu-id="7d9ce-356">Secondary admin</span></span>

<span data-ttu-id="7d9ce-357">Ett valfritt, sekundärt administratörskonto kan läggas till i avsnittet **användare** på din B2C-innehavare.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-357">An optional, secondary administrator account can be added in the **Users** section of your B2C tenant.</span></span> <span data-ttu-id="7d9ce-358">Det kan vara ett direkt konto eller ett allmänt konto.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-358">This can be a direct account or a general account.</span></span> <span data-ttu-id="7d9ce-359">Om du behöver dela ett konto mellan teamresurser kan du även skapa ett gemensamt konto.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-359">If you need to share an account across team resources, a common account can also be created.</span></span> <span data-ttu-id="7d9ce-360">På grund av känsligheten hos de data som lagras i Azure AD B2C, bör ett gemensamt konto övervakas i ett nära samarbete per ditt företags säkerhetspolicyer.</span><span class="sxs-lookup"><span data-stu-id="7d9ce-360">Due to the sensitivity of the data stored in Azure AD B2C, a common account should be monitored closely per your company's security practices.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="7d9ce-361">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="7d9ce-361">Additional resources</span></span>

[<span data-ttu-id="7d9ce-362">Konfigurera ditt domännamn</span><span class="sxs-lookup"><span data-stu-id="7d9ce-362">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="7d9ce-363">Distribuera en ny näthandelsplats</span><span class="sxs-lookup"><span data-stu-id="7d9ce-363">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="7d9ce-364">Skapa en e-handelsplats</span><span class="sxs-lookup"><span data-stu-id="7d9ce-364">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="7d9ce-365">Associera en online-webbplats med en kanal</span><span class="sxs-lookup"><span data-stu-id="7d9ce-365">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="7d9ce-366">Hantera robots.txt-filer</span><span class="sxs-lookup"><span data-stu-id="7d9ce-366">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="7d9ce-367">Överföring av URL-omdirigeringar i bulk</span><span class="sxs-lookup"><span data-stu-id="7d9ce-367">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="7d9ce-368">Ställa in anpassade sidor för användarinloggningar</span><span class="sxs-lookup"><span data-stu-id="7d9ce-368">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="7d9ce-369">Konfigurera flera B2C-innehavare i en Commerce-miljö</span><span class="sxs-lookup"><span data-stu-id="7d9ce-369">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="7d9ce-370">Lägga till stöd för ett innehållsleveransnätverk (CDN)</span><span class="sxs-lookup"><span data-stu-id="7d9ce-370">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="7d9ce-371">Aktivera platsbaserad butiksdetektering</span><span class="sxs-lookup"><span data-stu-id="7d9ce-371">Enable location-based store detection</span></span>](enable-store-detection.md)
