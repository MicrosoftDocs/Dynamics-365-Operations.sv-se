---
title: Ställa in en B2C-innehavare i Commerce
description: I det här avsnittet beskrivs hur du ställer in din Azure Active Directory (Azure AD) B2C-innehavare (Business-to-Consumer) för autentisering av användarplats i Dynamics 365 Commerce.
author: BrianShook
manager: annbe
ms.date: 06/22/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-commerce
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: brshoo
ms.search.validFrom: 2020-02-13
ms.dyn365.ops.version: ''
ms.openlocfilehash: 68e72bc17005c11f28f572114357f906098cc045
ms.sourcegitcommit: 38d40c331c8894acb7b119c5073e3088b54776c1
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/15/2021
ms.locfileid: "4993354"
---
# <a name="set-up-a-b2c-tenant-in-commerce"></a><span data-ttu-id="02f47-103">Ställa in en B2C-innehavare i Commerce</span><span class="sxs-lookup"><span data-stu-id="02f47-103">Set up a B2C tenant in Commerce</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="02f47-104">I det här avsnittet beskrivs hur du ställer in din Azure Active Directory (Azure AD) B2C-innehavare (Business-to-Consumer) för autentisering av användarplats i Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="02f47-104">This topic describes how to set up your Azure Active Directory (Azure AD) business-to-consumer (B2C) tenants for user site authentication in Dynamics 365 Commerce.</span></span>

## <a name="overview"></a><span data-ttu-id="02f47-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="02f47-105">Overview</span></span>

<span data-ttu-id="02f47-106">Dynamics 365 Commerce använder Azure AD B2C för att stödja autentiseringsuppgifter för användare och verifikationsflöden.</span><span class="sxs-lookup"><span data-stu-id="02f47-106">Dynamics 365 Commerce uses Azure AD B2C to support user credential and authentication flows.</span></span> <span data-ttu-id="02f47-107">En användare kan registrera sig, logga in och återställa sitt lösenord genom dessa flöden.</span><span class="sxs-lookup"><span data-stu-id="02f47-107">A user can sign up, sign in, and reset their password through these flows.</span></span> <span data-ttu-id="02f47-108">Azure AD B2C lagrar känslig information om användarautentisering, t.ex. användarnamn och lösenord.</span><span class="sxs-lookup"><span data-stu-id="02f47-108">Azure AD B2C stores sensitive user authentication information, such as username and password.</span></span> <span data-ttu-id="02f47-109">Användarposten i B2C-innehavaren kommer att lagra antingen en B2C lokal kontopost eller en post för en B2C social identitetsleverantör.</span><span class="sxs-lookup"><span data-stu-id="02f47-109">The user record in the B2C tenant will store either a B2C local account record or a B2C social identity provider record.</span></span> <span data-ttu-id="02f47-110">Dessa B2C-poster kommer att länkas tillbaka till kundposten i Commerce-miljön.</span><span class="sxs-lookup"><span data-stu-id="02f47-110">These B2C records will link back to the customer record in the Commerce environment.</span></span>

## <a name="create-or-link-to-an-existing-aad-b2c-tenant-in-the-azure-portal"></a><span data-ttu-id="02f47-111">Skapa eller länka till en befintlig AAD B2C-klientorganisation i Azure-portalen</span><span class="sxs-lookup"><span data-stu-id="02f47-111">Create or link to an existing AAD B2C tenant in the Azure portal</span></span>

1. <span data-ttu-id="02f47-112">Logga in på [Azure-portal](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="02f47-112">Sign in to the [Azure portal](https://portal.azure.com/).</span></span>
1. <span data-ttu-id="02f47-113">Från Azure-portal menyn, välj **skapa en resurs**.</span><span class="sxs-lookup"><span data-stu-id="02f47-113">From the Azure portal menu, select **Create a resource**.</span></span> <span data-ttu-id="02f47-114">Se till att använda den prenumeration och katalog som kommer att vara ansluten till din Commerce-miljö.</span><span class="sxs-lookup"><span data-stu-id="02f47-114">Be sure to use the subscription and directory that will be connected with your Commerce environment.</span></span>

    ![Skapa en resurs i Azure-portalen](./media/B2CImage_1.png)

1. <span data-ttu-id="02f47-116">Gå till **identitet \>Azure Active Directory B2C**.</span><span class="sxs-lookup"><span data-stu-id="02f47-116">Go to **Identity \> Azure Active Directory B2C**.</span></span>
1. <span data-ttu-id="02f47-117">På sidan **Skapa ny B2C-klient eller länk till befintlig klient** använder du ett av alternativen nedan som bäst passar ditt företags behov:</span><span class="sxs-lookup"><span data-stu-id="02f47-117">Once on the **Create New B2C Tenant or Link to existing Tenant** page, use one of the options below that best suits your company's needs:</span></span>

    - <span data-ttu-id="02f47-118">**Skapa en ny Azure AD B2C-innehavare**: Använd det här alternativet om du vill skapa en ny AAD B2C-innehavare.</span><span class="sxs-lookup"><span data-stu-id="02f47-118">**Create a new Azure AD B2C Tenant**: Use this option to create a new AAD B2C tenant.</span></span>
        1. <span data-ttu-id="02f47-119">Välj **Skapa ett nytt Azure AD B2C-innehavare**.</span><span class="sxs-lookup"><span data-stu-id="02f47-119">Select **Create a new Azure AD B2C Tenant**.</span></span>
        1. <span data-ttu-id="02f47-120">Ange **organisationsnamnet** under organisationsnamn.</span><span class="sxs-lookup"><span data-stu-id="02f47-120">Under **Organization name**, enter the organization name.</span></span>
        1. <span data-ttu-id="02f47-121">Under **Initialt domännamn**, ange initialt domännamn.</span><span class="sxs-lookup"><span data-stu-id="02f47-121">Under **Initial domain name**, enter the initial domain name.</span></span>
        1. <span data-ttu-id="02f47-122">För **land eller region** välj land eller region.</span><span class="sxs-lookup"><span data-stu-id="02f47-122">For **Country or region**, select the country or region.</span></span>
        1. <span data-ttu-id="02f47-123">Välj **skapa** om du vill skapa innehavaren.</span><span class="sxs-lookup"><span data-stu-id="02f47-123">Select **Create** to create the tenant.</span></span>

     ![Skapa en ny Azure AD innehavare](./media/B2CImage_2.png)

     - <span data-ttu-id="02f47-125">**Länka en befintlig Azure AD B2C-innehavare till min Azure-prenumeration**: Använd det här alternativet om du redan har en Azure AD B2C innehavare som du vill länka till.</span><span class="sxs-lookup"><span data-stu-id="02f47-125">**Link an existing Azure AD B2C Tenant to my Azure subscription**: Use this option if you already have an Azure AD B2C tenant you want to link to.</span></span>
        1. <span data-ttu-id="02f47-126">Välj **länka en befintlig Azure AD B2C-klient till mitt Azure-abonnemang**.</span><span class="sxs-lookup"><span data-stu-id="02f47-126">Select **Link an existing Azure AD B2C Tenant to my Azure subscription**.</span></span>
        1. <span data-ttu-id="02f47-127">Välj **Azure AD B2C innehavare** välj för B2C-innehavaren.</span><span class="sxs-lookup"><span data-stu-id="02f47-127">For **Azure AD B2C Tenant**, select the appropriate B2C tenant.</span></span> <span data-ttu-id="02f47-128">Om meddelandet "inga bidragsberättigande B2C-innehavare hittades" visas i urvalsrutan har du inte en giltig B2C klientorganisation och behöver skapa en ny.</span><span class="sxs-lookup"><span data-stu-id="02f47-128">If the message "No eligible B2C Tenants found" appears in the selection box, you do not have an existing eligible B2C tenant and will need to create a new one.</span></span>
        1. <span data-ttu-id="02f47-129">För **Resursgrupp**, välj **Skapa nya**.</span><span class="sxs-lookup"><span data-stu-id="02f47-129">For **Resource group**, select **Create new**.</span></span> <span data-ttu-id="02f47-130">Ange ett **namn** på den resursgrupp som ska innehålla innehavaren, välj **Välj resursgruppens plats** och välj **sedan skapa**.</span><span class="sxs-lookup"><span data-stu-id="02f47-130">Enter a **Name** for the resource group that will contain the tenant, select the **Resource group location**, and then select **Create**.</span></span>

    ![Länka en befintlig Azure AD B2C innehavare till Azure abonnemang](./media/B2CImage_3.png)

1. <span data-ttu-id="02f47-132">När den nya Azure AD B2C skapas (detta kan ta en stund) visas en länk till den nya katalogen på instrumentpanelen.</span><span class="sxs-lookup"><span data-stu-id="02f47-132">Once the new Azure AD B2C directory is created (this may take a few moments), a link to the new directory will appear on the dashboard.</span></span> <span data-ttu-id="02f47-133">Länken leder till sidan "Välkommen till Azure Active Directory B2C".</span><span class="sxs-lookup"><span data-stu-id="02f47-133">This link will direct you to the "Welcome to Azure Active Directory B2C" page.</span></span>

    ![Länk till ny AAD-katalog](./media/B2CImage_4.png)

> [!NOTE]
> <span data-ttu-id="02f47-135">Om du har flera prenumerationer inom ditt Azure-konto eller har ställt in B2C-klienten utan att länka till en aktiv **prenumeration**, kommer en felsökningsannons att leda till att du kopplar klienten till en prenumeration.</span><span class="sxs-lookup"><span data-stu-id="02f47-135">If you have multiple subscriptions within your Azure account or have set up the B2C tenant without linking to an active subscription, a **Troubleshoot** banner will direct you to link the tenant to a subscription.</span></span> <span data-ttu-id="02f47-136">Markera felsökningsmeddelandet och följ instruktionerna för att lösa prenumerationsproblemet.</span><span class="sxs-lookup"><span data-stu-id="02f47-136">Select the troubleshooting message and follow the instructions to resolve the subscription issue.</span></span>

<span data-ttu-id="02f47-137">Följande bild visar ett exempel på en Azure AD B2C **felsökning** banderoll.</span><span class="sxs-lookup"><span data-stu-id="02f47-137">The following image shows an example of an Azure AD B2C **Troubleshoot** banner.</span></span>

![Varnings visar av katalog har ingen aktiv prenumeration](./media/B2CImage_5.png)

## <a name="create-the-b2c-application"></a><span data-ttu-id="02f47-139">Skapa B2C-applikationen</span><span class="sxs-lookup"><span data-stu-id="02f47-139">Create the B2C application</span></span>

<span data-ttu-id="02f47-140">När B2C-innehavaren har skapats kommer du att skapa ett B2C-program inom innehavaren för att samverka med Commerce-åtgärderna.</span><span class="sxs-lookup"><span data-stu-id="02f47-140">Once the B2C tenant has been created, you will create a B2C application within the tenant to interact with the Commerce actions.</span></span>

<span data-ttu-id="02f47-141">Gör så här om du vill skapa ett B2C-applikation.</span><span class="sxs-lookup"><span data-stu-id="02f47-141">To create the B2C application, follow these steps.</span></span>

1. <span data-ttu-id="02f47-142">Markera **Program (äldre)** och välj **Lägg till** i Azure-portalen.</span><span class="sxs-lookup"><span data-stu-id="02f47-142">In the Azure portal, select **Applications(Legacy)** and then select **Add**.</span></span>
1. <span data-ttu-id="02f47-143">Under **namn** anger du namnet på det önskade AAD B2C-programmet.</span><span class="sxs-lookup"><span data-stu-id="02f47-143">Under **Name**, enter the name of the desired AAD B2C application.</span></span>
1. <span data-ttu-id="02f47-144">Under **Webbapp/Webb-API**, för **Inkludera webbapp/webb-API**, välj **Ja**.</span><span class="sxs-lookup"><span data-stu-id="02f47-144">Under **Web App/Web API**, for **Include web app / web API**, select **Yes**.</span></span>
1. <span data-ttu-id="02f47-145">För **Tillåt implicit flöde**, välj **Ja** (standardvärde).</span><span class="sxs-lookup"><span data-stu-id="02f47-145">For **Allow implicit flow**, select **Yes** (the default value).</span></span>
1. <span data-ttu-id="02f47-146">Ange **Svars-URL** för svar under svars-URL.</span><span class="sxs-lookup"><span data-stu-id="02f47-146">Under **Reply URL**, enter your dedicated reply URLs.</span></span> <span data-ttu-id="02f47-147">Se [besvara URL](#reply-urls) nedan för information om svars-URL:er och hur du formaterar dem.</span><span class="sxs-lookup"><span data-stu-id="02f47-147">See [Reply URLs](#reply-urls) below for information on reply URLs and how to format them here.</span></span>
1. <span data-ttu-id="02f47-148">För **Inkludera inhemsk klient**, välj **Nej** (standardvärdet).</span><span class="sxs-lookup"><span data-stu-id="02f47-148">For **Include native client**, select **No** (the default value).</span></span>
1. <span data-ttu-id="02f47-149">Markera **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="02f47-149">Select **Create**.</span></span>

### <a name="reply-urls"></a><span data-ttu-id="02f47-150">Svars-URL</span><span class="sxs-lookup"><span data-stu-id="02f47-150">Reply URLs</span></span>

<span data-ttu-id="02f47-151">Svars-URL är viktiga eftersom de ger en tillåten-lista med returdomänerna när platsen anropar Azure AD B2C för autentisering av en användare.</span><span class="sxs-lookup"><span data-stu-id="02f47-151">Reply URLs are important as they provide an allow list of the return domains when your site calls Azure AD B2C to authenticate a user.</span></span> <span data-ttu-id="02f47-152">På så sätt tillåts den autentiserade användaren returnera tillbaka till den domän som de loggar in på (din webbplatsdomän).</span><span class="sxs-lookup"><span data-stu-id="02f47-152">This permits the return of the authenticated user back to the domain from which they are signing into (your site domain).</span></span> 

<span data-ttu-id="02f47-153">I rutan **Svars-URL** på skärmen **Azure AD B2C – program \> Ny program** måste du lägga till separata rader för både din webbplatsdomän och (när din miljö har etablerats) den URL som genereras av Commerce.</span><span class="sxs-lookup"><span data-stu-id="02f47-153">In the **Reply URL** box on the **Azure AD B2c - Applications \> New application** screen, you need to add separate lines for both your site domain and (once your environment is provisioned) the Commerce-generated URL.</span></span> <span data-ttu-id="02f47-154">URL-adresserna får alltid använda ett giltigt URL-format och måste bara vara bas-URL:er (inga snedstreck eller sökvägar kan avslutas).</span><span class="sxs-lookup"><span data-stu-id="02f47-154">These URLs must always use a valid URL format and must be base URLs only (no trailing forward slashes or paths).</span></span> <span data-ttu-id="02f47-155">Strängen ``/_msdyn365/authresp`` måste läggas till i bas-URL:erna, som i följande exempel.</span><span class="sxs-lookup"><span data-stu-id="02f47-155">The string ``/_msdyn365/authresp`` then needs to be appended to the base URLs, as in the following examples.</span></span>

- <span data-ttu-id="02f47-156">``https://www.fabrikam.com/_msdyn365/authresp`` (Domänen ska matcha näthandelsdomänen helt.</span><span class="sxs-lookup"><span data-stu-id="02f47-156">``https://www.fabrikam.com/_msdyn365/authresp`` (The domain should match the e-commerce domain completely.</span></span> <span data-ttu-id="02f47-157">Om du har flera domäner måste du lägga till denna URL för varje domän.)</span><span class="sxs-lookup"><span data-stu-id="02f47-157">If you have multiple domains, you need to add this URL for each domain.)</span></span>
- ``https://fabrikam-prod.commerce.dynamics.com/_msdyn365/authresp``

## <a name="create-user-flow-policies"></a><span data-ttu-id="02f47-158">Skapa policyer för användarflöden</span><span class="sxs-lookup"><span data-stu-id="02f47-158">Create user flow policies</span></span>

<span data-ttu-id="02f47-159">Användarflöden är de policyer Azure AD B2C använder för att tillhandahålla säker inloggning, registrera, redigera profil och glömma användarupplevelser för lösenord.</span><span class="sxs-lookup"><span data-stu-id="02f47-159">User flows are the policies Azure AD B2C uses to provide secure sign in, sign up, edit profile, and forget password user experiences.</span></span> <span data-ttu-id="02f47-160">Dynamics 365 Commerce använder dessa flöden för att utföra policyåtgärder för samverkan med Azure AD B2C-innehavaren.</span><span class="sxs-lookup"><span data-stu-id="02f47-160">Dynamics 365 Commerce uses these flows to perform the policy actions to interact with the Azure AD B2C tenant.</span></span> <span data-ttu-id="02f47-161">När en användare interagerar med dessa principer, omdirigeras de till Azure AD B2C-innehavaren för att utföra åtgärderna.</span><span class="sxs-lookup"><span data-stu-id="02f47-161">When a user interacts with these policies, they are redirected to the Azure AD B2C tenant to perform the actions.</span></span>

<span data-ttu-id="02f47-162">Azure AD B2C har tre grundläggande användarflödestyper:</span><span class="sxs-lookup"><span data-stu-id="02f47-162">Azure AD B2C provides three basic user flow types:</span></span>
- <span data-ttu-id="02f47-163">Registrera dig och logga in</span><span class="sxs-lookup"><span data-stu-id="02f47-163">Sign up and sign in</span></span>
- <span data-ttu-id="02f47-164">Profilredigering</span><span class="sxs-lookup"><span data-stu-id="02f47-164">Profile editing</span></span>
- <span data-ttu-id="02f47-165">Återställ lösenord</span><span class="sxs-lookup"><span data-stu-id="02f47-165">Password reset</span></span>

<span data-ttu-id="02f47-166">Du kan välja att använda standard användarflöden som tillhandahålls av Azure AD, vilket visar en sida som finns i AAD B2C.</span><span class="sxs-lookup"><span data-stu-id="02f47-166">You can choose to use the default user flows provided by Azure AD, which will display a page hosted by AAD B2C.</span></span> <span data-ttu-id="02f47-167">Du kan också skapa en HTML-sida för att kontrollera hur dessa användarflödesupplevelser ser ut och fungerar.</span><span class="sxs-lookup"><span data-stu-id="02f47-167">Alternately, you can create an HTML page to control the look and feel of these user flow experiences.</span></span> 

<span data-ttu-id="02f47-168">Information om hur du anpassar sidorna för Dynamics 365 Commerce finns i [Konfigurera användarsidor för användarinloggningar](custom-pages-user-logins.md).</span><span class="sxs-lookup"><span data-stu-id="02f47-168">To customize the user policy pages for Dynamics 365 Commerce, see [Set up custom pages for user logins](custom-pages-user-logins.md).</span></span> <span data-ttu-id="02f47-169">Mer information finns i [Anpassa gränssnittet för användarupplevelser i Azure Active Directory B2C](https://docs.microsoft.com/azure/active-directory-b2c/tutorial-customize-ui).</span><span class="sxs-lookup"><span data-stu-id="02f47-169">For additional information, see [Customize the interface of user experiences in Azure Active Directory B2C](https://docs.microsoft.com/azure/active-directory-b2c/tutorial-customize-ui).</span></span>

### <a name="create-a-sign-up-and-sign-in-user-flow-policy"></a><span data-ttu-id="02f47-170">Skapa en policy för användarflöde för registrering och inloggning</span><span class="sxs-lookup"><span data-stu-id="02f47-170">Create a sign up and sign in user flow policy</span></span>

<span data-ttu-id="02f47-171">För att skapa en inloggning och policy för användarflöde följ stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="02f47-171">To create a sign up and sign in user flow policy, follow these steps.</span></span>

1. <span data-ttu-id="02f47-172">I Azure-portalen väljer du **Användarflöden (policyer)** i det vänstra navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="02f47-172">In the Azure portal, select **User flows (policies)** in the left navigation pane.</span></span>
1. <span data-ttu-id="02f47-173">På sidan **Azure AD B2C – användarflöden (policyer)** väljer du **Nytt användarflöde**.</span><span class="sxs-lookup"><span data-stu-id="02f47-173">On the **Azure AD B2C – User flows (policies)** page, select **New User Flow**.</span></span>
1. <span data-ttu-id="02f47-174">På fliken **Rekommenderad** välj **registrera dig och logga in**.</span><span class="sxs-lookup"><span data-stu-id="02f47-174">On the **Recommended** tab, select **Sign up and sign in**.</span></span>
1. <span data-ttu-id="02f47-175">Under **Namn**, ange ett policynamn.</span><span class="sxs-lookup"><span data-stu-id="02f47-175">Under **Name**, enter a policy name.</span></span> <span data-ttu-id="02f47-176">Det här namnet visas efteråt med ett prefix som portalen tilldelar (t.ex. "B2C_1_").</span><span class="sxs-lookup"><span data-stu-id="02f47-176">This name will display afterwards with a prefix the portal assigns (for example, "B2C_1_").</span></span>
1. <span data-ttu-id="02f47-177">Under **identitetsleverantörer**, välj lämplig kryssruta.</span><span class="sxs-lookup"><span data-stu-id="02f47-177">Under **Identity providers**, select the appropriate check box.</span></span>
1. <span data-ttu-id="02f47-178">Under **Flerfaktorautentisering** väljer du lämpligt val för ditt företag.</span><span class="sxs-lookup"><span data-stu-id="02f47-178">Under **Multifactor Authentication**, select the appropriate choice for your company.</span></span> 
1. <span data-ttu-id="02f47-179">Under **användarattribut och anspråk** väljer du alternativ för att samla in attribut eller returnera anspråk efter behov.</span><span class="sxs-lookup"><span data-stu-id="02f47-179">Under **User attributes and claims**, select options to collect attributes or return claims as appropriate.</span></span> <span data-ttu-id="02f47-180">Commerce kräver följande standardalternativ:</span><span class="sxs-lookup"><span data-stu-id="02f47-180">Commerce requires the following default options:</span></span>

    | <span data-ttu-id="02f47-181">**Samla in attribut**</span><span class="sxs-lookup"><span data-stu-id="02f47-181">**Collect  attribute**</span></span> | <span data-ttu-id="02f47-182">**Returnera anspråk**</span><span class="sxs-lookup"><span data-stu-id="02f47-182">**Return  claim**</span></span> |
    | ---------------------- | ----------------- |
    | <span data-ttu-id="02f47-183">E-postadress</span><span class="sxs-lookup"><span data-stu-id="02f47-183">Email Address</span></span>          | <span data-ttu-id="02f47-184">E-postadresser</span><span class="sxs-lookup"><span data-stu-id="02f47-184">Email Addresses</span></span>   |
    | <span data-ttu-id="02f47-185">Angivet namn</span><span class="sxs-lookup"><span data-stu-id="02f47-185">Given Name</span></span>             | <span data-ttu-id="02f47-186">Angivet namn</span><span class="sxs-lookup"><span data-stu-id="02f47-186">Given Name</span></span>        |
    |                        | <span data-ttu-id="02f47-187">Identitetsprovider</span><span class="sxs-lookup"><span data-stu-id="02f47-187">Identity Provider</span></span> |
    | <span data-ttu-id="02f47-188">Efternamn</span><span class="sxs-lookup"><span data-stu-id="02f47-188">Surname</span></span>                | <span data-ttu-id="02f47-189">Efternamn</span><span class="sxs-lookup"><span data-stu-id="02f47-189">Surname</span></span>           |
    |                        | <span data-ttu-id="02f47-190">Användarens objekt-ID</span><span class="sxs-lookup"><span data-stu-id="02f47-190">User’s Object ID</span></span>  |

1. <span data-ttu-id="02f47-191">Markera **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="02f47-191">Select **Create**.</span></span>

<span data-ttu-id="02f47-192">Följande bild är ett exempel på Azure AD B2C registrering och inloggning i användarflödet.</span><span class="sxs-lookup"><span data-stu-id="02f47-192">The following image is an example of the Azure AD B2C sign up and sign in user flow.</span></span>

![Inställningar av policyn Registrera och logga in](./media/B2CImage_11.png)

<span data-ttu-id="02f47-194">I bilden nedan visas alternativet **kör användarflöde** i Azure AD B2C för att registrera och logga in i användarflödet.</span><span class="sxs-lookup"><span data-stu-id="02f47-194">The following image shows the **Run user flow** option in the Azure AD B2C sign up and sign in user flow.</span></span>

![Kör användarflödesalternativ i policyflöde](./media/B2CImage_23.png)
   
### <a name="create-a-profile-editing-user-flow-policy"></a><span data-ttu-id="02f47-196">Skapa en profil genom att redigera användarflödespolicy</span><span class="sxs-lookup"><span data-stu-id="02f47-196">Create a profile editing user flow policy</span></span>

<span data-ttu-id="02f47-197">För att en profilredigering för policy för användarflöde följ stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="02f47-197">To create a profile editing user flow policy, follow these steps.</span></span>

1. <span data-ttu-id="02f47-198">I Azure-portalen väljer du **Användarflöden (policyer)** i det vänstra navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="02f47-198">In the Azure portal, select **User flows (policies)** in the left navigation pane.</span></span>
1. <span data-ttu-id="02f47-199">På sidan **Azure AD B2C – användarflöden (policyer)** väljer du **Nytt användarflöde**.</span><span class="sxs-lookup"><span data-stu-id="02f47-199">On the **Azure AD B2C – User flows (policies)** page, select **New User Flow**.</span></span>
1. <span data-ttu-id="02f47-200">På fliken **Rekommenderad**, välj **Profilredigering**.</span><span class="sxs-lookup"><span data-stu-id="02f47-200">On the **Recommended** tab, select **Profile editing**.</span></span>
1. <span data-ttu-id="02f47-201">Under **namn** anger du användarflödet för profilredigering.</span><span class="sxs-lookup"><span data-stu-id="02f47-201">Under **Name**, enter the profile editing user flow.</span></span> <span data-ttu-id="02f47-202">Det här namnet visas efteråt med ett prefix som portalen tilldelar (t.ex. "B2C_1_").</span><span class="sxs-lookup"><span data-stu-id="02f47-202">This name will display afterwards with a prefix the portal assigns (for example, "B2C_1_").</span></span>
1. <span data-ttu-id="02f47-203">Under **identitetsleverantörer**, välj **Inloggning på lokalt konto**.</span><span class="sxs-lookup"><span data-stu-id="02f47-203">Under **Identity providers**, select **Local Account SignIn**.</span></span>
1. <span data-ttu-id="02f47-204">Markera en eller flera av följande kryssrutor under **Användarattribut**:</span><span class="sxs-lookup"><span data-stu-id="02f47-204">Under **User attributes**, select the following check boxes:</span></span>
    - <span data-ttu-id="02f47-205">**E-postadresser** (endast **returanspråk**)</span><span class="sxs-lookup"><span data-stu-id="02f47-205">**Email Addresses** (**Return claim** only)</span></span>
    - <span data-ttu-id="02f47-206">**Angivet namn** (**Samla in attribut** och **returanspråk**)</span><span class="sxs-lookup"><span data-stu-id="02f47-206">**Given Name** (**Collect attribute** and **Return claim**)</span></span>
    - <span data-ttu-id="02f47-207">**Identitetsleverantör** (endast **returanspråk**)</span><span class="sxs-lookup"><span data-stu-id="02f47-207">**Identity Provider** (**Return claim** only)</span></span>
    - <span data-ttu-id="02f47-208">**Efternamn** (**Samla in attribut** och **returanspråk**)</span><span class="sxs-lookup"><span data-stu-id="02f47-208">**Surname** (**Collect attribute** and **Return claim**)</span></span>
    - <span data-ttu-id="02f47-209">**Användarens objekt-ID** (endast **returanspråk**)</span><span class="sxs-lookup"><span data-stu-id="02f47-209">**User's Object ID** (**Return claim** only)</span></span>
1. <span data-ttu-id="02f47-210">Markera **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="02f47-210">Select **Create**.</span></span>

<span data-ttu-id="02f47-211">Följande bild visar ett exempel på Azure AD B2C-profil som redigerar användarflödet.</span><span class="sxs-lookup"><span data-stu-id="02f47-211">The following image shows an example of the Azure AD B2C profile editing user flow.</span></span>

![Skapa en användarflödet profilredigering](./media/B2CImage_12.png)

### <a name="create-a-password-reset-user-flow-policy"></a><span data-ttu-id="02f47-213">Skapa en lösenordsåterställning för användarflödespolicy</span><span class="sxs-lookup"><span data-stu-id="02f47-213">Create a password reset user flow policy</span></span>

<span data-ttu-id="02f47-214">För att en lösenordsåterställning för policy för användarflöde följ stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="02f47-214">To create a password reset user flow policy, follow these steps.</span></span>

1. <span data-ttu-id="02f47-215">I Azure-portalen väljer du **Användarflöden (policyer)** i det vänstra navigeringsfönstret.</span><span class="sxs-lookup"><span data-stu-id="02f47-215">In the Azure portal, select **User flows (policies)** in the left navigation pane.</span></span>
1. <span data-ttu-id="02f47-216">På sidan **Azure AD B2C – användarflöden (policyer)** väljer du **Nytt användarflöde**.</span><span class="sxs-lookup"><span data-stu-id="02f47-216">On the **Azure AD B2C – User flows (policies)** page, select **New User Flow**.</span></span>
1. <span data-ttu-id="02f47-217">På fliken **Rekommenderad**, välj **lösenordsåterställning**.</span><span class="sxs-lookup"><span data-stu-id="02f47-217">On the **Recommended** tab, select **Password Reset**.</span></span>
1. <span data-ttu-id="02f47-218">Under **namn** anger du ett namn på användarflödet för återställning av lösenord.</span><span class="sxs-lookup"><span data-stu-id="02f47-218">Under **Name**, enter a name for the password reset user flow.</span></span>
1. <span data-ttu-id="02f47-219">Under **identitetsleverantörer** väljer du **Återställ lösenord med e-postadress**.</span><span class="sxs-lookup"><span data-stu-id="02f47-219">Under **Identity providers**, select **Reset password using email address**.</span></span>
1. <span data-ttu-id="02f47-220">Markera **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="02f47-220">Select **Create**.</span></span>
1. <span data-ttu-id="02f47-221">Markera en eller flera av följande kryssrutor under **Programanspråk**:</span><span class="sxs-lookup"><span data-stu-id="02f47-221">Under **Application claims**, select the following check boxes:</span></span>
    - <span data-ttu-id="02f47-222">**E-postadresser**</span><span class="sxs-lookup"><span data-stu-id="02f47-222">**Email addresses**</span></span>
    - <span data-ttu-id="02f47-223">**Angivet namn**</span><span class="sxs-lookup"><span data-stu-id="02f47-223">**Given Name**</span></span>
    - <span data-ttu-id="02f47-224">**Efternamn**</span><span class="sxs-lookup"><span data-stu-id="02f47-224">**Surname**</span></span>
    - <span data-ttu-id="02f47-225">**Användarens objekt-ID**</span><span class="sxs-lookup"><span data-stu-id="02f47-225">**User's Object ID**</span></span>
1. <span data-ttu-id="02f47-226">Markera **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="02f47-226">Select **Create**.</span></span>

<span data-ttu-id="02f47-227">I följande bild visas var du ska ange **Återställ lösenord med e-postadress** i Azure AD B2C lösenordsåterställning för användarflöde.</span><span class="sxs-lookup"><span data-stu-id="02f47-227">The following image shows where to set **Reset Password using mail address** in the Azure AD B2C password reset user flow.</span></span>

![Ange "Återställ lösenord med e-postadress" i policyn för lösenordsåterställning](./media/B2CImage_13.png)

## <a name="add-social-identity-providers-optional"></a><span data-ttu-id="02f47-229">Lägg till sociala identitetsleverantör (valfritt)</span><span class="sxs-lookup"><span data-stu-id="02f47-229">Add social identity providers (Optional)</span></span>

<span data-ttu-id="02f47-230">Med sociala identitetsleverantör kan användarna använda sina sociala konton för autentisering.</span><span class="sxs-lookup"><span data-stu-id="02f47-230">Social identity providers allow users to use their social accounts for authentication.</span></span> <span data-ttu-id="02f47-231">Att lägga till sociala identitetsleverantör är valfritt i Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="02f47-231">Adding social identity provider authentication is optional in Dynamics 365 Commerce.</span></span> 

<span data-ttu-id="02f47-232">Om autentiseringen av sociala identitetsleverantör inte läggs till blir Azure AD B2C standard-profiler huvudprofilerna för användarbasen.</span><span class="sxs-lookup"><span data-stu-id="02f47-232">If social identity provider authentication is not added, the default Azure AD B2C profiles will be the main profiles for your user base.</span></span> <span data-ttu-id="02f47-233">Användarna väljer sina egna användarnamn (deras standard-e-postadress) och anger ett lösenord.</span><span class="sxs-lookup"><span data-stu-id="02f47-233">Users will select their own username (their preferred email address) and set a password.</span></span> <span data-ttu-id="02f47-234">Azure AD B2C kommer att autentisera användare direkt.</span><span class="sxs-lookup"><span data-stu-id="02f47-234">Azure AD B2C will authenticate users directly.</span></span> 

<span data-ttu-id="02f47-235">Om autentisering av sociala identitetsleverantörer läggs till och en användare väljer en av de tillgängliga leverantörerna av sociala identiteter, skapas en entitet fortfarande i Azure AD B2C-innehavaren.</span><span class="sxs-lookup"><span data-stu-id="02f47-235">If social identity provider authentication is added and a user chooses one of the social identity providers offered, an entity is still created in the Azure AD B2C tenant.</span></span> <span data-ttu-id="02f47-236">Azure AD B2C kommer sedan att autentisera användarens uppgifter hos den sociala identitetsleverantören.</span><span class="sxs-lookup"><span data-stu-id="02f47-236">Azure AD B2C will then authenticate the user's credentials with the social identity provider.</span></span>

> [!NOTE]
> <span data-ttu-id="02f47-237">Identitetsleverantörens inloggning skapar en post i B2C-innehavaren, men i ett annat format än lokala konton eftersom den ska anropa den externa referensen för social identitetsleverantör för autentisering.</span><span class="sxs-lookup"><span data-stu-id="02f47-237">The identity provider sign in creates a record in the B2C tenant, but in a different format than local accounts since it will call the external social identity provider reference for authentication.</span></span> <span data-ttu-id="02f47-238">Användaren kan använda samma e-postadress för sociala identitetsleverantör, vilket innebär att e-postnamnet som används för autentisering kanske inte är unikt för innehavaren.</span><span class="sxs-lookup"><span data-stu-id="02f47-238">The user can use the same email address across social identity providers, meaning that the email username used for authentication may not be unique to the tenant.</span></span> <span data-ttu-id="02f47-239">Azure AD B2C kommer bara att säkerställa att användarna har en unik e-postadress på lokala B2C-konton.</span><span class="sxs-lookup"><span data-stu-id="02f47-239">Azure AD B2C will only enforce that users have a unique email address on local B2C accounts.</span></span>

<span data-ttu-id="02f47-240">Innan du kan lägga till en social identitetsleverantör för autentisering måste du gå till identitetsleverantörens portal och ställa in ett program för identitetsleverantör enligt anvisningarna i Azure AD B2C-dokumentationen.</span><span class="sxs-lookup"><span data-stu-id="02f47-240">Before you can add a social identity provider for authentication, you must go to the identity provider's portal and set up an identity provider application as instructed in the Azure AD B2C documentation.</span></span> <span data-ttu-id="02f47-241">Nedan finns en lista med länkar till dokumentationen.</span><span class="sxs-lookup"><span data-stu-id="02f47-241">A list of links to the documentation is provided below.</span></span>

- [<span data-ttu-id="02f47-242">Amazon</span><span class="sxs-lookup"><span data-stu-id="02f47-242">Amazon</span></span>](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-amzn-app)
- [<span data-ttu-id="02f47-243">Azure AD (En innehavare)</span><span class="sxs-lookup"><span data-stu-id="02f47-243">Azure AD (Single Tenant)</span></span>](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-oidc-azure-active-directory)
- [<span data-ttu-id="02f47-244">Microsoft-konto</span><span class="sxs-lookup"><span data-stu-id="02f47-244">Microsoft Account</span></span>](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-msa-app)
- [<span data-ttu-id="02f47-245">Facebook</span><span class="sxs-lookup"><span data-stu-id="02f47-245">Facebook</span></span>](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-fb-app)
- [<span data-ttu-id="02f47-246">GitHub</span><span class="sxs-lookup"><span data-stu-id="02f47-246">GitHub</span></span>](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-github-app)
- [<span data-ttu-id="02f47-247">Google</span><span class="sxs-lookup"><span data-stu-id="02f47-247">Google</span></span>](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-goog-app)
- [<span data-ttu-id="02f47-248">LinkedIn</span><span class="sxs-lookup"><span data-stu-id="02f47-248">LinkedIn</span></span>](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-li-app)
- [<span data-ttu-id="02f47-249">OpenID Connect</span><span class="sxs-lookup"><span data-stu-id="02f47-249">OpenID Connect</span></span>](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-oidc-idp)
- [<span data-ttu-id="02f47-250">Twitter</span><span class="sxs-lookup"><span data-stu-id="02f47-250">Twitter</span></span>](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-setup-twitter-app)

### <a name="add-and-set-up-a-social-identity-provider"></a><span data-ttu-id="02f47-251">Lägga till och ställa in en leverantör av sociala identiteter</span><span class="sxs-lookup"><span data-stu-id="02f47-251">Add and set up a social identity provider</span></span>

<span data-ttu-id="02f47-252">Lägg till och ställ in en leverantör av sociala identiteter enligt följande instruktioner.</span><span class="sxs-lookup"><span data-stu-id="02f47-252">To add and set up a social identity provider, follow these steps.</span></span>  

1. <span data-ttu-id="02f47-253">I Azure-portal, navigera till **identitetsleverantörer**.</span><span class="sxs-lookup"><span data-stu-id="02f47-253">In the Azure portal, navigate to **Identity Providers**.</span></span>
1. <span data-ttu-id="02f47-254">Markera **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="02f47-254">Select **Add**.</span></span> <span data-ttu-id="02f47-255">Skärmen **Lägg till identitetsleverantör** visas.</span><span class="sxs-lookup"><span data-stu-id="02f47-255">The **Add identity provider** screen appears.</span></span>
1. <span data-ttu-id="02f47-256">Under **namn** anger du det namn som ska visas för användarna i inloggningsskärmen.</span><span class="sxs-lookup"><span data-stu-id="02f47-256">Under **Name**, enter the name to be displayed to users on your sign in screen.</span></span>
1. <span data-ttu-id="02f47-257">Under **Typ av identitetsleverantör**, välj en identitetsleverantör från listan.</span><span class="sxs-lookup"><span data-stu-id="02f47-257">Under **Identity provider type**, select an identity provider from the list.</span></span>
1. <span data-ttu-id="02f47-258">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="02f47-258">Select **OK**.</span></span>
1. <span data-ttu-id="02f47-259">Välj **konfigurera den här identitetsleverantören** för åtkomst till skärmen **Ställ in till fönstret för social identitetsleverantör**.</span><span class="sxs-lookup"><span data-stu-id="02f47-259">Select **Set up this identity provider** to access the **Set up the social identity provider** screen.</span></span>
1. <span data-ttu-id="02f47-260">Under **klient-ID**, ange det klient-ID som hämtas från programinställningar för identitetsleverantör.</span><span class="sxs-lookup"><span data-stu-id="02f47-260">Under **Client ID**, enter the client ID as obtained from the identity provider application setup.</span></span>
1. <span data-ttu-id="02f47-261">Under **klienthemlighet**, ange den klienthemlighet som hämtas från programinställningar för identitetsleverantör.</span><span class="sxs-lookup"><span data-stu-id="02f47-261">Under **Client secret**, enter the client secret as obtained from the identity provider application setup.</span></span>
1. <span data-ttu-id="02f47-262">Koppla användarflöde för inloggningsprinciper för inloggning:</span><span class="sxs-lookup"><span data-stu-id="02f47-262">Attach user flow for sign in sign up policies:</span></span>
1. <span data-ttu-id="02f47-263">Gå till **Azure AD B2C – användarflöden (principer)\> {din policy för registrering och inloggning} \> identitetsleverantörer**.</span><span class="sxs-lookup"><span data-stu-id="02f47-263">Go to **Azure AD B2C – User flows (policies) \> {your sign-in sign-up policy} \> Identity providers**.</span></span>
1. <span data-ttu-id="02f47-264">Om du vill koppla användarflödespolicyn för inloggning/registrering markerar du varje identitetsleverantör som du har skapat för ditt konto.</span><span class="sxs-lookup"><span data-stu-id="02f47-264">To attach the sign in/sign up user flow policy, select each identity provider you have set up for your account.</span></span> <span data-ttu-id="02f47-265">Om du vill testa dessa väljer du **kör användarflöde** för varje identitetsleverantör.</span><span class="sxs-lookup"><span data-stu-id="02f47-265">To test these, select **Run user flow** for each identity provider.</span></span> <span data-ttu-id="02f47-266">På en ny flik visas inloggningssidan med den nya valrutan för identitetsleverantörer.</span><span class="sxs-lookup"><span data-stu-id="02f47-266">A new tab will display the sign-in page displaying the new identity provider selection box.</span></span>

<span data-ttu-id="02f47-267">Följande bild illustrerar exempel på skärmarna **lägga till identitetsleverantören** och **ställer in social identitetsleverantören** i Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="02f47-267">The following image shows examples of the **Add identity provider** and **Set up the social identity provider** screens in Azure AD B2C.</span></span>

![Lägga till en social identitetsleverantör i ditt program](./media/B2CImage_14.png)

<span data-ttu-id="02f47-269">I följande bild visas ett exempel på hur du väljer identitetsleverantörer på sidan Azure AD B2C **identitetsleverantörer**.</span><span class="sxs-lookup"><span data-stu-id="02f47-269">The following image shows an example of how to select identity providers on the Azure AD B2C **Identity Providers** page.</span></span>

![Välj varje social identitetsleverantör som ska aktiveras för din policy](./media/B2CImage_16.png)

<span data-ttu-id="02f47-271">I bilden nedan visas ett exempel på en standard inloggningsskärm med knappen för inloggning med sociala identitetsleverantörer som visas.</span><span class="sxs-lookup"><span data-stu-id="02f47-271">The following image shows an example of a default sign-in screen with a social identity provider sign-in button displayed.</span></span>

![Exempel på standard inloggningsskärm när inloggningsknappen för sociala identitetsleverantörer visas](./media/B2CImage_17.png)

## <a name="update-commerce-headquarters-with-the-new-azure-ad-b2c-information"></a><span data-ttu-id="02f47-273">Uppdatera Commerce-administration med den nya Azure AD B2C-informationen</span><span class="sxs-lookup"><span data-stu-id="02f47-273">Update Commerce headquarters with the new Azure AD B2C information</span></span>

<span data-ttu-id="02f47-274">När Azure AD B2C etableringsstegen ovan har slutförts måste Azure AD B2C-programmet vara registrerat i din Dynamics 365 Commerce-miljö.</span><span class="sxs-lookup"><span data-stu-id="02f47-274">Once the Azure AD B2C provisioning steps above are completed, the Azure AD B2C application must be registered in your Dynamics 365 Commerce environment.</span></span>

<span data-ttu-id="02f47-275">Om du vill uppdatera huvud kontoret med den nya Azure AD B2C-informationen följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="02f47-275">To update headquarters with the new Azure AD B2C information, follow these steps.</span></span>

1. <span data-ttu-id="02f47-276">I Commerce går du till **delade Commerce-parametrar** och väljer **identitetsleverantörer** på den vänstra menyn.</span><span class="sxs-lookup"><span data-stu-id="02f47-276">In Commerce, go to **Commerce Shared Parameters** and select **Identity Providers** in the left menu.</span></span>
1. <span data-ttu-id="02f47-277">Under **identitetsleverantörer** gör du följande:</span><span class="sxs-lookup"><span data-stu-id="02f47-277">Under **Identity Providers**, do the following:</span></span>
    1. <span data-ttu-id="02f47-278">I rutan **utfärdare** anger du URL för identitetsleverantörens utfärdare.</span><span class="sxs-lookup"><span data-stu-id="02f47-278">In the **Issuer** box, enter the identity provider issuer URL.</span></span> <span data-ttu-id="02f47-279">Information om hur du hittar din utfärdar-URL, se [Hämta utfärdar-URL](#obtain-issuer-url) nedan.</span><span class="sxs-lookup"><span data-stu-id="02f47-279">To find your issuer URL, see [Obtain issuer URL](#obtain-issuer-url) below.</span></span>
    1. <span data-ttu-id="02f47-280">I rutan **Namn**, ange ett namn för din utfärdarpost.</span><span class="sxs-lookup"><span data-stu-id="02f47-280">In the **Name** box, enter a name for your issuer record.</span></span>
    1. <span data-ttu-id="02f47-281">I rutan **Typ**, ange **Azure AD B2C (id_token)**.</span><span class="sxs-lookup"><span data-stu-id="02f47-281">In the **Type** box, enter **Azure AD B2C (id_token)**.</span></span>
1. <span data-ttu-id="02f47-282">Under **Förlitande parter**, med ovanstående B2C för identitetsleverantör:</span><span class="sxs-lookup"><span data-stu-id="02f47-282">Under **Relying Parties**, with the above B2C identity provider item selected, do the following:</span></span>
    1. <span data-ttu-id="02f47-283">I rutan **ClientID**, ange ditt B2C program-ID.</span><span class="sxs-lookup"><span data-stu-id="02f47-283">In the **ClientID** box, enter your B2C application ID.</span></span> <span data-ttu-id="02f47-284">Du hittar detta i rutan **Program-ID** på egenskapssida B2C-program.</span><span class="sxs-lookup"><span data-stu-id="02f47-284">You can find this in the **Application ID** box of your B2C application's properties page.</span></span>
    1. <span data-ttu-id="02f47-285">I rutan **Typ** ange **Offentlig**.</span><span class="sxs-lookup"><span data-stu-id="02f47-285">In the **Type** box, enter **Public**.</span></span>
    1. <span data-ttu-id="02f47-286">I rutan **Användartyp** ange **Kund**.</span><span class="sxs-lookup"><span data-stu-id="02f47-286">In the **User Type** box, enter **Customer**.</span></span>
1. <span data-ttu-id="02f47-287">Klicka på **Spara** i åtgärdsfönstret.</span><span class="sxs-lookup"><span data-stu-id="02f47-287">On the action pane, select **Save**.</span></span>
1. <span data-ttu-id="02f47-288">I Commerce-sökrutan, sök efter **Distributionsschema**</span><span class="sxs-lookup"><span data-stu-id="02f47-288">In the Commerce search box, search for **Distribution schedule**</span></span>
1. <span data-ttu-id="02f47-289">I den vänstra navigeringsmenyn på sidan **distributionsscheman** väljer du **1110 Global konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="02f47-289">In the left navigation menu of the **Distribution schedules** page, select job **1110 Global configuration**.</span></span>
1. <span data-ttu-id="02f47-290">I åtgärdsfönstret, klicka på **Kör nu**.</span><span class="sxs-lookup"><span data-stu-id="02f47-290">On the action pane, select **Run Now**.</span></span>

### <a name="obtain-issuer-url"></a><span data-ttu-id="02f47-291">Hämta utfärdar-URL</span><span class="sxs-lookup"><span data-stu-id="02f47-291">Obtain issuer URL</span></span>

<span data-ttu-id="02f47-292">Om du vill ha en utfärdar-URL för identitetsleverantören följer du stegen nedan.</span><span class="sxs-lookup"><span data-stu-id="02f47-292">To obtain your identity provider issuer URL, follow these steps.</span></span>

1. <span data-ttu-id="02f47-293">Skapa en URL för en metadataadress i följande format med hjälp av din B2C-klient och policy: ``https://<B2CTENANTNAME>.b2clogin.com/<B2CTENANTNAME>.onmicrosoft.com/v2.0/.well-known/openid-configuration?p=<B2CSIGN-INPOLICY>``</span><span class="sxs-lookup"><span data-stu-id="02f47-293">Create a metadata address URL in the following format using your B2C tenant and policy: ``https://<B2CTENANTNAME>.b2clogin.com/<B2CTENANTNAME>.onmicrosoft.com/v2.0/.well-known/openid-configuration?p=<B2CSIGN-INPOLICY>``</span></span>
    - <span data-ttu-id="02f47-294">Exempel: ``https://d365plc.b2clogin.com/d365plc.onmicrosoft.com/v2.0/.well-known/openid-configuration?p=B2C_1_signinup``.</span><span class="sxs-lookup"><span data-stu-id="02f47-294">Example: ``https://d365plc.b2clogin.com/d365plc.onmicrosoft.com/v2.0/.well-known/openid-configuration?p=B2C_1_signinup``.</span></span>
1. <span data-ttu-id="02f47-295">Ange URL-adressen för metadata i webbläsarens adressfält.</span><span class="sxs-lookup"><span data-stu-id="02f47-295">Enter the metadata address URL into a browser address bar.</span></span>
1. <span data-ttu-id="02f47-296">I metadata kopierar du URL:en för identitetsleverantören (värdet för **"utfärdare"**).</span><span class="sxs-lookup"><span data-stu-id="02f47-296">In the metadata, copy the identity provider issuer URL (the value for **"issuer"**).</span></span>
    - <span data-ttu-id="02f47-297">Exempel: ``https://login.fabrikam.com/073405c3-0113-4f43-b5e2-df01266e24ae/v2.0/``.</span><span class="sxs-lookup"><span data-stu-id="02f47-297">Example: ``https://login.fabrikam.com/073405c3-0113-4f43-b5e2-df01266e24ae/v2.0/``.</span></span>

## <a name="configure-your-b2c-tenant-in-commerce-site-builder"></a><span data-ttu-id="02f47-298">Konfigurera din B2C-innehavare i Commerce webbplatsskaparen</span><span class="sxs-lookup"><span data-stu-id="02f47-298">Configure your B2C tenant in Commerce site builder</span></span>

<span data-ttu-id="02f47-299">När installationen av din Azure AD B2C-innehavare har slutförts måste du konfigurera B2C-innehavaren i Commerce webbplatsskaparen.</span><span class="sxs-lookup"><span data-stu-id="02f47-299">Once setup of your Azure AD B2C tenant is completed, you must configure the B2C tenant in Commerce site builder.</span></span> <span data-ttu-id="02f47-300">Konfigurationsstegen omfattar insamling av B2C programinformation från Azure-portalen, ange B2C programinformation till webbplatsskaparen och sedan associera B2C-programmet med din webbplats och kanal.</span><span class="sxs-lookup"><span data-stu-id="02f47-300">Configuration steps include collecting B2C application information from the Azure portal, entering that B2C application information into site builder, and then associating the B2C application with your site and channel.</span></span>

### <a name="collect-the-required-application-information"></a><span data-ttu-id="02f47-301">Samla in nödvändig programinformation</span><span class="sxs-lookup"><span data-stu-id="02f47-301">Collect the required application information</span></span>

<span data-ttu-id="02f47-302">Gör så här för att samla in den nödvändiga programinformationen.</span><span class="sxs-lookup"><span data-stu-id="02f47-302">To collect the required application information, follow these steps.</span></span>

1. <span data-ttu-id="02f47-303">I Azure-portal, gå till **Start \> Azure AD B2C – program**.</span><span class="sxs-lookup"><span data-stu-id="02f47-303">In the Azure portal, go to **Home \> Azure AD B2C - Applications**.</span></span>
1. <span data-ttu-id="02f47-304">Markera programmet och välj sedan i vänstra navigeringsfönstret **Egenskaper** för att hämta programinformationen.</span><span class="sxs-lookup"><span data-stu-id="02f47-304">Select your application, and then in the left navigation pane select **Properties** to obtain the application details.</span></span>
1. <span data-ttu-id="02f47-305">Från rutan **program-ID**, samla in program-ID för B2C-programmet som har skapats i B2C-innehavaren.</span><span class="sxs-lookup"><span data-stu-id="02f47-305">From the **Application ID** box, collect the application ID of the B2C application created in your B2C tenant.</span></span> <span data-ttu-id="02f47-306">Detta kommer senare att anges som **klient-GUID** i webbplatsskaparen.</span><span class="sxs-lookup"><span data-stu-id="02f47-306">This will later be entered as the **Client GUID** in site builder.</span></span>
1. <span data-ttu-id="02f47-307">Under **Svars-URL**, samla svars-URL.</span><span class="sxs-lookup"><span data-stu-id="02f47-307">Under **Reply URL**, collect the reply URL.</span></span>
1. <span data-ttu-id="02f47-308">Gå till **Start \> Azure AD B2C – användarflöden (policyer)** och samla sedan in namnen på varje användarflödespolicy.</span><span class="sxs-lookup"><span data-stu-id="02f47-308">Go to **Home \> Azure AD B2C – User flows (policies)**, and then collect the names of each user flow policy.</span></span>

<span data-ttu-id="02f47-309">Följande bild visar ett exempel på sidan **Azure AD B2C-program**.</span><span class="sxs-lookup"><span data-stu-id="02f47-309">The following image shows an example of the **Azure AD B2C - Applications** page.</span></span>

![Navigera till B2C-programmet inom din klientorganisation](./media/B2CImage_19.png)

<span data-ttu-id="02f47-311">Följande bild visar ett exempel på en programsida **egenskaper** i Azure AD B2C.</span><span class="sxs-lookup"><span data-stu-id="02f47-311">The following image shows an example of an application **Properties** page in Azure AD B2C.</span></span> 

![Kopiera program-ID från B2C programegenskaper](./media/B2CImage_21.png)

<span data-ttu-id="02f47-313">Följande bild visar ett exempel på användarflödespolicyer på sidan **Azure AD B2C – användarflöden (policy)**.</span><span class="sxs-lookup"><span data-stu-id="02f47-313">The following image shows an example of user flow policies on the **Azure AD B2C – User flows (policies)** page.</span></span>

![Samla in namnen på varje B2C policyflöde](./media/B2CImage_22.png)

### <a name="enter-your-aad-b2c-tenant-application-information-into-commerce"></a><span data-ttu-id="02f47-315">Ange din AAD B2C-information för klientprogram i Commerce</span><span class="sxs-lookup"><span data-stu-id="02f47-315">Enter your AAD B2C tenant application information into Commerce</span></span>

<span data-ttu-id="02f47-316">Du måste ange information om Azure AD B2C-innehavaren i Commerce webbplatsskaparen innan du kopplar B2C-innehavaren till dina webbplatser.</span><span class="sxs-lookup"><span data-stu-id="02f47-316">You must enter details of the Azure AD B2C tenant into Commerce site builder before associating the B2C tenant with your site(s).</span></span>

<span data-ttu-id="02f47-317">Följ stegen nedan om du vill lägga till din AAD B2C-information till Commerce.</span><span class="sxs-lookup"><span data-stu-id="02f47-317">To add your AAD B2C tenant application information to Commerce, follow these steps.</span></span>

1. <span data-ttu-id="02f47-318">Logga in som administratör på Commerce webbplatsskaparen för din miljö.</span><span class="sxs-lookup"><span data-stu-id="02f47-318">Sign in as an administrator to Commerce site builder for your environment.</span></span>
1. <span data-ttu-id="02f47-319">I det vänstra navigeringsfönstret väljer du **innehavarinställningar** för att expandera den.</span><span class="sxs-lookup"><span data-stu-id="02f47-319">In the left navigation pane, select **Tenant Settings**  to expand it.</span></span>
1. <span data-ttu-id="02f47-320">Under **innehavarinställningar** väljer du **B2C-inställningar**.</span><span class="sxs-lookup"><span data-stu-id="02f47-320">Under **Tenant Settings**, select **B2C Settings**.</span></span> 
1. <span data-ttu-id="02f47-321">I huvudfönstret bredvid **B2C-program**, välj **Hantera**.</span><span class="sxs-lookup"><span data-stu-id="02f47-321">In the main window next **B2C Applications**, select **Manage**.</span></span> <span data-ttu-id="02f47-322">(Om din klientorganisation visas i listan B2C-program, har den redan lagts till av en administratör.</span><span class="sxs-lookup"><span data-stu-id="02f47-322">(If your tenant appears in the B2C Applications list, then it was already added by an administrator.</span></span> <span data-ttu-id="02f47-323">Kontrollera att artiklarna i steg 6 nedan matchar ditt B2C-program.)</span><span class="sxs-lookup"><span data-stu-id="02f47-323">Verify that the items in step 6 below match your B2C Application.)</span></span>
1. <span data-ttu-id="02f47-324">Välj **Lägg till B2C-program**.</span><span class="sxs-lookup"><span data-stu-id="02f47-324">Select **Add B2C Application**.</span></span>
1. <span data-ttu-id="02f47-325">Ange följande obligatoriska objekt i formuläret som visas med värden från din B2C-innehavare och programmet.</span><span class="sxs-lookup"><span data-stu-id="02f47-325">Enter the following required items in the form displayed, using values from your B2C tenant and application.</span></span> <span data-ttu-id="02f47-326">Fält som inte är obligatoriska (sådana som saknar asterisk) kan lämnas tomma.</span><span class="sxs-lookup"><span data-stu-id="02f47-326">Fields that are not required (those without an asterisk) may be left blank.</span></span>

    - <span data-ttu-id="02f47-327">**Programnamn**: namnet på ditt B2C-program, t.ex. "Fabrikam B2C".</span><span class="sxs-lookup"><span data-stu-id="02f47-327">**Application Name**: The name for your B2C Application, for example "Fabrikam B2C".</span></span>
    - <span data-ttu-id="02f47-328">**Klientnamn**: Namnet på din B2C-klient (Använd till exempel "fabrikam" om domänen visas som "fabrikam.onmicrosoft.com" för B2C-klienten).</span><span class="sxs-lookup"><span data-stu-id="02f47-328">**Tenant Name**: The name of your B2C tenant (for example, use "fabrikam" if the domain appears as "fabrikam.onmicrosoft.com" for the B2C tenant).</span></span> 
    - <span data-ttu-id="02f47-329">**Glömt lösenordspolicy-ID**: glöm lösenord användarflödespolicy-ID, t.ex. "B2C_1_PasswordReset".</span><span class="sxs-lookup"><span data-stu-id="02f47-329">**Forget Password Policy ID**: The forget password user flow policy ID, for example "B2C_1_PasswordReset".</span></span>
    - <span data-ttu-id="02f47-330">**Policy-ID för registrering och inloggning**: användarflödespolicy-ID för registrering och inloggning, t.ex. "B2C_1_signup_signin".</span><span class="sxs-lookup"><span data-stu-id="02f47-330">**Signup Signin Policy ID**: The sign up and sign in user flow policy ID, for example "B2C_1_signup_signin".</span></span>
    - <span data-ttu-id="02f47-331">**Klient-GUID**: B2C program-ID, till exempel "22290eb2-c52e-42e9-8b35-a2b0a3bcb9e6".</span><span class="sxs-lookup"><span data-stu-id="02f47-331">**Client GUID**: The B2C application ID, for example "22290eb2-c52e-42e9-8b35-a2b0a3bcb9e6".</span></span>
    - <span data-ttu-id="02f47-332">**Redigera profilpolicy-ID-**: profil som redigerar användarflödespolicy-ID, till exempel "B2C_1A_ProfileEdit".</span><span class="sxs-lookup"><span data-stu-id="02f47-332">**Edit Profile Policy ID**: The profile editing user flow policy ID, for example "B2C_1A_ProfileEdit".</span></span>

1. <span data-ttu-id="02f47-333">Välj **OK**.</span><span class="sxs-lookup"><span data-stu-id="02f47-333">Select **OK**.</span></span> <span data-ttu-id="02f47-334">Nu ska nu se att namnet på ditt B2C-program visas i listan.</span><span class="sxs-lookup"><span data-stu-id="02f47-334">You should now see the name of your B2C application appear in the list.</span></span>
1. <span data-ttu-id="02f47-335">Spara ändringarna genom att klicka på **Spara**.</span><span class="sxs-lookup"><span data-stu-id="02f47-335">Select **Save** to save your changes.</span></span>

### <a name="associate-the-b2c-application-to-your-site-and-channel"></a><span data-ttu-id="02f47-336">Associera B2C program till din webbplats och kanal</span><span class="sxs-lookup"><span data-stu-id="02f47-336">Associate the B2C application to your site and channel</span></span>

> [!WARNING]
> <span data-ttu-id="02f47-337">Om webbplatsen redan är associerad med ett B2C-program tas aktuella referenser för användare som redan registrerats i den här miljön bort när du byter till ett annat B2C-program.</span><span class="sxs-lookup"><span data-stu-id="02f47-337">If your site is already associated with a B2C application, changing to a different B2C application will remove the current references established for users already signed up in this environment.</span></span> <span data-ttu-id="02f47-338">Om det ändras kommer inga autentiseringsuppgifter som associeras med det B2C programmet att vara tillgängliga för användarna.</span><span class="sxs-lookup"><span data-stu-id="02f47-338">If changed, any credentials associated with the currently-assigned B2C application will not be available to users.</span></span> 
> 
> <span data-ttu-id="02f47-339">Uppdatera endast B2C-programmet om du ställer in kanalens B2C-program för första gången eller om du vill att användarna ska registrera dig igen med nya autentiseringsuppgifter för den här kanalen med det nya B2C-programmet.</span><span class="sxs-lookup"><span data-stu-id="02f47-339">Only update the B2C application if you are setting up the channel's B2C application for the first time or if you intend to have users re-sign up with new credentials to this channel with the new B2C application.</span></span> <span data-ttu-id="02f47-340">Var försiktig när du kopplar kanaler till B2C-program och namnge program tydligt.</span><span class="sxs-lookup"><span data-stu-id="02f47-340">Take caution when associating channels to B2C applications, and name applications clearly.</span></span> <span data-ttu-id="02f47-341">Om en kanal inte är associerad med ett B2C program i stegen nedan, kommer användare som loggar in på den kanalen för din webbplats att anges i B2C-program som visas **standard** i **innehavarinställningar \> B2C-inställningar** för B2C-program.</span><span class="sxs-lookup"><span data-stu-id="02f47-341">If a channel is not associated to a B2C application in the steps below, users signing into that channel for your site will be entered into the B2C application showing as **default** in the **Tenant Settings \> B2C Settings** list of B2C applications.</span></span>

<span data-ttu-id="02f47-342">För att associera B2C-program till din webbplats och kanal, följ dessa steg.</span><span class="sxs-lookup"><span data-stu-id="02f47-342">To associate the B2C application to your site and channel, follow these steps.</span></span>

1. <span data-ttu-id="02f47-343">Navigera till webbplatsen i Commerce webbplatsskaparen.</span><span class="sxs-lookup"><span data-stu-id="02f47-343">Navigate to your site in Commerce site builder.</span></span>
1. <span data-ttu-id="02f47-344">I det vänstra navigeringsfönstret väljer du **Webbplatsinställningar** för att expandera den.</span><span class="sxs-lookup"><span data-stu-id="02f47-344">In the left navigation pane, select **Site Settings** to expand it.</span></span>
1. <span data-ttu-id="02f47-345">Under **webbplatsinställningar**, välj **kanaler**.</span><span class="sxs-lookup"><span data-stu-id="02f47-345">Below **Site Settings**, select **Channels**.</span></span>
1. <span data-ttu-id="02f47-346">I huvudfönstret under **kanaler**, välj din kanal.</span><span class="sxs-lookup"><span data-stu-id="02f47-346">In the main window under **Channels**, select your channel.</span></span>
1. <span data-ttu-id="02f47-347">I rutan kanal egenskaper till höger väljer du B2C-programnamnet från nedrullningsbara menyn **Välj B2C-program**.</span><span class="sxs-lookup"><span data-stu-id="02f47-347">In the channel properties pane on the right, select your B2C application name from the **Select B2C Application** drop down menu.</span></span>
1. <span data-ttu-id="02f47-348">Välj **Stäng** och välj sedan **Spara och publicera**.</span><span class="sxs-lookup"><span data-stu-id="02f47-348">Select **Close**, and then select **Save and Publish**.</span></span>

## <a name="additional-b2c-information"></a><span data-ttu-id="02f47-349">Ytterligare B2C-information</span><span class="sxs-lookup"><span data-stu-id="02f47-349">Additional B2C information</span></span>

### <a name="customer-migration"></a><span data-ttu-id="02f47-350">Kundmigrering</span><span class="sxs-lookup"><span data-stu-id="02f47-350">Customer migration</span></span>

<span data-ttu-id="02f47-351">Om du funderar på att flytta kundposter från en tidigare plattform för identitetsleverantörer, arbeta med Dynamics 365 Commerce för att granska behovet av kundmigrering.</span><span class="sxs-lookup"><span data-stu-id="02f47-351">If you are considering migrating customer records from a previous identity provider platform, please work with the Dynamics 365 Commerce team to review your customer migration needs.</span></span>

<span data-ttu-id="02f47-352">För ytterligare Azure AD B2C-dokumentation om kundmigrering, se [Migrera användare till Azure Active Directory B2C](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-user-migration).</span><span class="sxs-lookup"><span data-stu-id="02f47-352">For additional Azure AD B2C documentation on customer migration, see [Migrate users to Azure Active Directory B2C](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-user-migration).</span></span>

### <a name="custom-policies"></a><span data-ttu-id="02f47-353">Anpassade principer</span><span class="sxs-lookup"><span data-stu-id="02f47-353">Custom policies</span></span>

<span data-ttu-id="02f47-354">Mer information om hur du anpassar Azure AD-interaktioner och policyflöden utöver vad som erbjuds av B2C, se [Anpassa policyer i Azure Active Directory B2C](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-overview-custom).</span><span class="sxs-lookup"><span data-stu-id="02f47-354">For additional information regarding customizing Azure AD B2C interactions and policy flows beyond what is offered by B2C standard policies, see [Custom policies in Azure Active Directory B2C](https://docs.microsoft.com/azure/active-directory-b2c/active-directory-b2c-overview-custom).</span></span> 

### <a name="secondary-admin"></a><span data-ttu-id="02f47-355">Sekundär administration</span><span class="sxs-lookup"><span data-stu-id="02f47-355">Secondary admin</span></span>

<span data-ttu-id="02f47-356">Ett valfritt, sekundärt administratörskonto kan läggas till i avsnittet **användare** på din B2C-innehavare.</span><span class="sxs-lookup"><span data-stu-id="02f47-356">An optional, secondary administrator account can be added in the **Users** section of your B2C tenant.</span></span> <span data-ttu-id="02f47-357">Det kan vara ett direkt konto eller ett allmänt konto.</span><span class="sxs-lookup"><span data-stu-id="02f47-357">This can be a direct account or a general account.</span></span> <span data-ttu-id="02f47-358">Om du behöver dela ett konto mellan teamresurser kan du även skapa ett gemensamt konto.</span><span class="sxs-lookup"><span data-stu-id="02f47-358">If you need to share an account across team resources, a common account can also be created.</span></span> <span data-ttu-id="02f47-359">På grund av känsligheten hos de data som lagras i Azure AD B2C, bör ett gemensamt konto övervakas i ett nära samarbete per ditt företags säkerhetspolicyer.</span><span class="sxs-lookup"><span data-stu-id="02f47-359">Due to the sensitivity of the data stored in Azure AD B2C, a common account should be monitored closely per your company's security practices.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="02f47-360">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="02f47-360">Additional resources</span></span>

[<span data-ttu-id="02f47-361">Konfigurera ditt domännamn</span><span class="sxs-lookup"><span data-stu-id="02f47-361">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="02f47-362">Distribuera en ny klientorganisation för näthandel</span><span class="sxs-lookup"><span data-stu-id="02f47-362">Deploy a new e-commerce tenant</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="02f47-363">Skapa en näthandelssajt</span><span class="sxs-lookup"><span data-stu-id="02f47-363">Create an e-commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="02f47-364">Associera en Dynamics 365 Commerce-webbplats med en onlinekanal</span><span class="sxs-lookup"><span data-stu-id="02f47-364">Associate a Dynamics 365 Commerce site with an online channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="02f47-365">Hantera robots.txt-filer</span><span class="sxs-lookup"><span data-stu-id="02f47-365">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

<span data-ttu-id="02f47-366">[Ladda upp URL-omdirigeringar i bulk](upload-bulk-redirects.md)Associera en Dynamics 365 Commerce-webbplats med en onlinekanal</span><span class="sxs-lookup"><span data-stu-id="02f47-366">[Upload URL redirects in bulk](upload-bulk-redirects.md)Associate a Dynamics 365 Commerce site with an online channel</span></span>

[<span data-ttu-id="02f47-367">Ställa in anpassade sidor för användarinloggningar</span><span class="sxs-lookup"><span data-stu-id="02f47-367">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="02f47-368">Konfigurera flera B2C-klientorganisationer i en Commerce-miljö</span><span class="sxs-lookup"><span data-stu-id="02f47-368">Configure multiple B2C tenants in a Commerce environment</span></span>](configure-multi-B2C-tenants.md)

[<span data-ttu-id="02f47-369">Lägga till stöd för ett innehållsleveransnätverk (CDN)</span><span class="sxs-lookup"><span data-stu-id="02f47-369">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="02f47-370">Aktivera platsbaserad butiksdetektering</span><span class="sxs-lookup"><span data-stu-id="02f47-370">Enable location-based store detection</span></span>](enable-store-detection.md)
