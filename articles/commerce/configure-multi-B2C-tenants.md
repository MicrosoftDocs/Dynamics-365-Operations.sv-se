---
title: Konfigurera flera B2C-innehavare i en Commerce-miljö
description: Det här avsnittet beskriver när och hur du ställer in flera Microsoft Azure Active Directory (Azure AD) B2C-innehavare för användarautentisering i en dedikerad Dynamics 365 Commerce-miljö.
author: BrianShook
ms.date: 03/17/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: retail
ms.author: brshoo
ms.search.validFrom: 2020-02-12
ms.dyn365.ops.version: ''
ms.openlocfilehash: c813adb79ae1b78a052332e077393f125830633f
ms.sourcegitcommit: cabd991fda2bfcabb55db84c225b24a7bb061631
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "6027732"
---
# <a name="configure-multiple-b2c-tenants-in-a-commerce-environment"></a><span data-ttu-id="5e052-103">Konfigurera flera B2C-innehavare i en Commerce-miljö</span><span class="sxs-lookup"><span data-stu-id="5e052-103">Configure multiple B2C tenants in a Commerce environment</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="5e052-104">Det här avsnittet beskriver när och hur du ställer in flera Microsoft Azure Active Directory (Azure AD) B2C-innehavare per kanal för användarautentisering i en dedikerad Dynamics 365 Commerce-miljö.</span><span class="sxs-lookup"><span data-stu-id="5e052-104">This topic describes when and how to set up multiple Microsoft Azure Active Directory (Azure AD) business-to-consumer (B2C) tenants per channel for user authentication in a dedicated Dynamics 365 Commerce environment.</span></span>

<span data-ttu-id="5e052-105">Dynamics 365 Commerce använder Azure AD B2C molnidentitetstjänst för att stödja autentiseringsuppgifter och verifikationsflöden.</span><span class="sxs-lookup"><span data-stu-id="5e052-105">Dynamics 365 Commerce uses the Azure AD B2C cloud identity service to support user credentials and authentication flows.</span></span> <span data-ttu-id="5e052-106">Användare kan använda verifikationsflöden för att registrera, logga in och återställa sitt lösenord.</span><span class="sxs-lookup"><span data-stu-id="5e052-106">Users can use the authentication flows to sign up, sign in, and reset their password.</span></span> <span data-ttu-id="5e052-107">Azure AD B2C lagrar en användares känsliga autentiseringsinformation, t.ex. användarnamn och lösenord.</span><span class="sxs-lookup"><span data-stu-id="5e052-107">Azure AD B2C stores a user's sensitive authentication information, such as the user name and password.</span></span> <span data-ttu-id="5e052-108">Användarposten är unik för varje B2C-innehavare och använder antingen användarnamn (e-postadress) autentiseringsuppgifter eller autentiseringsuppgifter för social identitet.</span><span class="sxs-lookup"><span data-stu-id="5e052-108">The user record is unique to each B2C tenant, and it uses either user name (email address) credentials or social identity provider credentials.</span></span>

<span data-ttu-id="5e052-109">I de flesta fall används en enda Azure AD B2C-innehavare i en Commerce-miljö.</span><span class="sxs-lookup"><span data-stu-id="5e052-109">In most cases, a single Azure AD B2C tenant is used in a Commerce environment.</span></span> <span data-ttu-id="5e052-110">Commerce-kunder kan sedan skapa och publicera flera webbplatser i samma Commerce-miljö och samma kundautentiseringsuppgifter kommer att användas på dessa webbplatser.</span><span class="sxs-lookup"><span data-stu-id="5e052-110">Commerce customers can then create and publish multiple sites in the same Commerce environment, and the same customer credentials will be used across these sites.</span></span> <span data-ttu-id="5e052-111">Om webbplatserna i miljön ska behandlas som olika varumärken och visas för användarna som separata företag, kan en B2C-innehavare konfigureras för den kanal som används för webbplatsens/varumärkets separation.</span><span class="sxs-lookup"><span data-stu-id="5e052-111">However, if the sites in the environment should be treated as different brands and appear to users as separate businesses, a B2C tenant can be configured for the channel that is used for the site/brand separation.</span></span>

## <a name="considerations-when-multiple-b2c-tenants-are-set-up-per-channel"></a><span data-ttu-id="5e052-112">Att tänka på när flera B2C-innehavare ställs in per kanal</span><span class="sxs-lookup"><span data-stu-id="5e052-112">Considerations when multiple B2C tenants are set up per channel</span></span>

<span data-ttu-id="5e052-113">När varje kanal eller webbplats behandlas som ett separat företag är det bästa alternativet med avseende på användarverifieringsflöden i Commerce att använda separata juridiska enheter.</span><span class="sxs-lookup"><span data-stu-id="5e052-113">Often, when each channel or site is being treated as a separate business, the best option with respect to user authentication flows in Commerce is to use separate legal entities.</span></span> <span data-ttu-id="5e052-114">Om du däremot vill behålla varje kanal/plats i samma miljö och juridisk person, men vill ha separata användarautentisering för varje webbplats, är det viktigt att du tänker på följande saker innan du går vidare:</span><span class="sxs-lookup"><span data-stu-id="5e052-114">However, if you want to keep each channel/site in the same environment and legal entity, but want to have separate user authentication for each site, it's important that you consider the following points before you proceed:</span></span>

- <span data-ttu-id="5e052-115">Användarna får sina egna unika autentiseringsuppgifter för varje kanal/webbplats.</span><span class="sxs-lookup"><span data-stu-id="5e052-115">Users will have their own distinct credentials for each channel/site.</span></span>

    <span data-ttu-id="5e052-116">Samma person kan ha två separata konton per kanal/webbplats, eftersom varje konto är en unik post i en separat B2C-innehavare.</span><span class="sxs-lookup"><span data-stu-id="5e052-116">The same person can have two separate accounts per channel/site, because each account will be a unique entry into a separate B2C tenant.</span></span>

- <span data-ttu-id="5e052-117">I Microsoft Dynamics-miljön kommer separata kundposter att returneras för globala postsökningar.</span><span class="sxs-lookup"><span data-stu-id="5e052-117">In the Microsoft Dynamics environment, separate customer records will be returned for global record searches.</span></span>

    <span data-ttu-id="5e052-118">Om en användare använder samma e-postadress för kanaler/webbplatser returnerar globala kundsökningar resultat för varje kanal/webbplats.</span><span class="sxs-lookup"><span data-stu-id="5e052-118">If a user uses the same email address across channels/sites, global customer searches will return results for each channel/site.</span></span> <span data-ttu-id="5e052-119">(En kanalindikator visas.)</span><span class="sxs-lookup"><span data-stu-id="5e052-119">(A channel indicator will be shown.)</span></span>

- <span data-ttu-id="5e052-120">Adressboken kan användas för att hjälpa till att gruppera användare, så att de kan spåras per kanal.</span><span class="sxs-lookup"><span data-stu-id="5e052-120">The address book can be used to help group users, so that they can be tracked per channel.</span></span>
- <span data-ttu-id="5e052-121">Antalet kundposter per kanal kan öka och denna ökning kan påverka prestandan hos globala kundsökningar.</span><span class="sxs-lookup"><span data-stu-id="5e052-121">The number of customer records per channel might increase, and this increase might affect the performance of global customer searches.</span></span>
- <span data-ttu-id="5e052-122">B2C-innehavare måste mappas omsorgsfullt till en kanal, för att förhindra situationer där kunder registrerar sig för fel innehavare.</span><span class="sxs-lookup"><span data-stu-id="5e052-122">B2C tenants must be carefully mapped to a channel, to help prevent situations where customers sign up for an incorrect tenant.</span></span> <span data-ttu-id="5e052-123">I annat fall kan förvirring och spårningsproblem uppstå.</span><span class="sxs-lookup"><span data-stu-id="5e052-123">Otherwise, confusion or tracking issues can occur.</span></span>

<span data-ttu-id="5e052-124">I bilden nedan visas flera B2C-innehavare i en Commerce-miljö.</span><span class="sxs-lookup"><span data-stu-id="5e052-124">The following illustration shows multiple B2C tenants in a Commerce environment.</span></span>

![Flera B2C-innehavare i en Commerce-miljö](media/MultiB2C_In_Environment.png)

<span data-ttu-id="5e052-126">Om du bestämmer dig för att ditt företag kräver distinkta B2C-innehavare per kanal i samma Commerce-miljö, måste du utföra procedurerna i följande avsnitt för att kunna begära den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="5e052-126">If you decide that your business requires distinct B2C tenants per channel in the same Commerce environment, complete the procedures in the following sections to request this feature.</span></span>

## <a name="configure-b2c-tenants-in-your-environment"></a><span data-ttu-id="5e052-127">Konfigurera B2C-innehavare i miljön</span><span class="sxs-lookup"><span data-stu-id="5e052-127">Configure B2C tenants in your environment</span></span>

<span data-ttu-id="5e052-128">Om du vill konfigurera B2C-innehavare i miljön ska du slutföra de relevanta procedurerna i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="5e052-128">To configure B2C tenants in your environment, complete the relevant procedures in this section.</span></span>

### <a name="add-an-azure-ad-b2c-tenant"></a><span data-ttu-id="5e052-129">Lägg till en Azure AD B2C-innehavare</span><span class="sxs-lookup"><span data-stu-id="5e052-129">Add an Azure AD B2C tenant</span></span>

<span data-ttu-id="5e052-130">Följ stegen nedan för att lägga till en Azure AD B2C-innehavare i din miljö.</span><span class="sxs-lookup"><span data-stu-id="5e052-130">To add an Azure AD B2C tenant to your environment, follow these steps.</span></span>

1. <span data-ttu-id="5e052-131">Logga in på Commerce webbplatsskapare för din miljö som systemadministratör. Om du vill konfigurera Azure AD B2C-innehavare måste du vara systemadministratör för Commerce-miljön.</span><span class="sxs-lookup"><span data-stu-id="5e052-131">Sign in to Commerce site builder for your environment as a system admin. To configure Azure AD B2C tenants, you must be a system admin for the Commerce environment.</span></span>
1. <span data-ttu-id="5e052-132">I det vänstra navigeringsfönstret väljer du **innehavarinställningar** för att expandera den.</span><span class="sxs-lookup"><span data-stu-id="5e052-132">In the left navigation pane, select **Tenant Settings** to expand it.</span></span>
1. <span data-ttu-id="5e052-133">Välj **B2C-inställningar**, och välj sedan **Hantera**.</span><span class="sxs-lookup"><span data-stu-id="5e052-133">Select **B2C Settings**, and then select **Manage**.</span></span>
1. <span data-ttu-id="5e052-134">Välj **Lägg till B2C-program** och ange sedan följande information:</span><span class="sxs-lookup"><span data-stu-id="5e052-134">Select **Add B2C Application**, and then enter the following information:</span></span>

    - <span data-ttu-id="5e052-135">**Programnamn**: Ange namnet som ska användas för programmet i samband med hantering av det i Commerce.</span><span class="sxs-lookup"><span data-stu-id="5e052-135">**Application Name**: Enter the name that should be used for the application in the context of managing it in Commerce.</span></span> <span data-ttu-id="5e052-136">Vi rekommenderar att du använder det programnamn som du väljer när du ställer in Azure AD B2C-programmet i Azure-portalen.</span><span class="sxs-lookup"><span data-stu-id="5e052-136">We recommend that you use the application name that you chose when you set up the Azure AD B2C application in the Azure portal.</span></span> <span data-ttu-id="5e052-137">På det här sättet kan du minska förvirring när du hanterar B2C-innehavare i Commerce.</span><span class="sxs-lookup"><span data-stu-id="5e052-137">In this way, you can help reduce confusion when you manage B2C tenants in Commerce.</span></span>
    - <span data-ttu-id="5e052-138">**Klientnamn**: Ange det B2C-innehavare som det visas i Azure-portalen.</span><span class="sxs-lookup"><span data-stu-id="5e052-138">**Tenant Name**: Enter the B2C tenant name as it appears in the Azure portal.</span></span>
    - <span data-ttu-id="5e052-139">**Glömt lösenordspolicy-ID**: Ange policy-ID (namnet på principen i Azure-portalen).</span><span class="sxs-lookup"><span data-stu-id="5e052-139">**Forget Password Policy ID**: Enter the policy ID (the name of the policy in the Azure portal).</span></span>
    - <span data-ttu-id="5e052-140">**Policy-ID för registrering och inloggning**: Ange policy-ID (namnet på principen i Azure-portalen).</span><span class="sxs-lookup"><span data-stu-id="5e052-140">**Signup Signin Policy ID**: Enter the policy ID (the name of the policy in the Azure portal).</span></span>
    - <span data-ttu-id="5e052-141">**Klient-GUID**: Ange Azure AD B2C innehavar-ID så som det visas i Azure-portalen (inte program-ID för B2C-innehavare).</span><span class="sxs-lookup"><span data-stu-id="5e052-141">**Client GUID**: Enter the Azure AD B2C tenant ID as it appears in the Azure portal (not the application ID for the B2C tenant).</span></span>
    - <span data-ttu-id="5e052-142">**Redigera profil för policy-ID**: Ange policy-ID (namnet på principen i Azure-portalen).</span><span class="sxs-lookup"><span data-stu-id="5e052-142">**Edit Profile Policy ID**: Enter the policy ID (the name of the policy in the Azure portal).</span></span>

1. <span data-ttu-id="5e052-143">När du har angett den här informationen väljer du **OK** för att spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="5e052-143">When you've finished entering this information, select **OK** to save your changes.</span></span> <span data-ttu-id="5e052-144">Den nya Azure AD B2C-innehavaren ska nu visas i listan under **hantera B2C-program**.</span><span class="sxs-lookup"><span data-stu-id="5e052-144">Your new Azure AD B2C tenant should now appear in the list under **Manage B2C Applications**.</span></span>

> [!NOTE]
> <span data-ttu-id="5e052-145">Du bör lämna fält som **Omfattning**, **Icke-interaktivt policy-ID**, **Icke-interaktivt klient-ID**, **Anpassad domän för inloggning** och **Policy-ID för registrering** tomma om inte teamet för Dynamics 365 Commerce uppmanar dig att ställa in dem.</span><span class="sxs-lookup"><span data-stu-id="5e052-145">You should leave fields such as **Scope**, **Non Interactive Policy ID**, **Non Interactive Client ID**, **Login Custom Domain**, and **Sign Up Policy ID** blank unless the Dynamics 365 Commerce team instructs you to set them.</span></span>


### <a name="manage-or-delete-an-azure-ad-b2c-tenant"></a><span data-ttu-id="5e052-146">Hantera eller ta bort Azure AD B2C-innehavare</span><span class="sxs-lookup"><span data-stu-id="5e052-146">Manage or delete an Azure AD B2C tenant</span></span>

1. <span data-ttu-id="5e052-147">Logga in på Commerce webbplatsskapare för din miljö som systemadministratör. Om du vill konfigurera Azure AD B2C-innehavare måste du vara systemadministratör för Commerce-miljön.</span><span class="sxs-lookup"><span data-stu-id="5e052-147">Sign in to Commerce site builder for your environment as a system admin. To configure Azure AD B2C tenants, you must be a system admin for the Commerce environment.</span></span>
1. <span data-ttu-id="5e052-148">I det vänstra navigeringsfönstret väljer du **innehavarinställningar** för att expandera den.</span><span class="sxs-lookup"><span data-stu-id="5e052-148">In the left navigation pane, select **Tenant Settings** to expand it.</span></span>
1. <span data-ttu-id="5e052-149">Välj **B2C-inställningar**, och välj sedan **Hantera**.</span><span class="sxs-lookup"><span data-stu-id="5e052-149">Select **B2C Settings**, and then select **Manage**.</span></span>
1. <span data-ttu-id="5e052-150">Om du vill redigera en B2C-innehavare väljer du pennsymbolen bredvid.</span><span class="sxs-lookup"><span data-stu-id="5e052-150">To edit a B2C tenant, select the pencil symbol next to it.</span></span> <span data-ttu-id="5e052-151">Om du vill ta bort en B2C-innehavare väljer du symbolen bredvid papperskorgen.</span><span class="sxs-lookup"><span data-stu-id="5e052-151">To delete a B2C tenant, select the trash can symbol next to it.</span></span>
1. <span data-ttu-id="5e052-152">Välj **spara** och välj sedan **publicera** för att aktivera ändringarna.</span><span class="sxs-lookup"><span data-stu-id="5e052-152">Select **Save**, and then select **Publish** to activate your changes.</span></span>

> [!WARNING]
> <span data-ttu-id="5e052-153">När en B2C-innehavare har konfigurerats för en pågående/publicerad plats, kan användare ha registrerat sig genom att använda konton som finns på innehavaren.</span><span class="sxs-lookup"><span data-stu-id="5e052-153">When a B2C tenant is configured for a live/published site, users might have signed up by using accounts that are present on the tenant.</span></span> <span data-ttu-id="5e052-154">Om du tar bort en konfigurerad innehavare på menyn **innehavarinställningar \> B2C-innehavare** tar du bort kopplingen till den B2C-innehavare från webbplatser som är associerade med eventuella kanaler hos innehavaren.</span><span class="sxs-lookup"><span data-stu-id="5e052-154">If you delete a configured tenant on the **Tenant Settings \> B2C Tenant** menu, you remove the association of that B2C tenant from sites that are associated with any channels of the tenant.</span></span> <span data-ttu-id="5e052-155">I det här fallet kanske användarna inte längre kan logga in på sina konton.</span><span class="sxs-lookup"><span data-stu-id="5e052-155">In this case, your users might no longer be able to sign in to their accounts.</span></span> <span data-ttu-id="5e052-156">Använd därför yttersta försiktighet när du tar bort en konfigurerad innehavare.</span><span class="sxs-lookup"><span data-stu-id="5e052-156">Therefore, use extreme caution when you delete a configured tenant.</span></span>
>
> <span data-ttu-id="5e052-157">När en konfigurerad innehavare tas bort kommer B2C-innehavaren och posterna att fortsätta underhållas, men systemkonfigurationen för den innehavaren kommer att ändras eller tas bort.</span><span class="sxs-lookup"><span data-stu-id="5e052-157">When a configured tenant is deleted, the B2C tenant and records will continue to be maintained, but the Commerce system configuration of that tenant will be changed or removed.</span></span> <span data-ttu-id="5e052-158">Användare som försöker registrera sig eller logga in på webbplatsen skapar en ny kontopost i den standard- eller B2C-innehavare som har konfigurerats för webbplatsens kanal.</span><span class="sxs-lookup"><span data-stu-id="5e052-158">Users who try to sign up or sign in to the site will create a new account record in the default or newly associated B2C tenant that is configured for the channel of the site.</span></span>

## <a name="configure-your-channel-with-a-b2c-tenant"></a><span data-ttu-id="5e052-159">Konfigurera kanalen med en B2C-innehavare</span><span class="sxs-lookup"><span data-stu-id="5e052-159">Configure your channel with a B2C tenant</span></span>

1. <span data-ttu-id="5e052-160">Logga in på Commerce webbplatsskapare för din miljö som systemadministratör. Om du vill konfigurera Azure AD B2C-innehavare måste du vara systemadministratör för Commerce-miljön.</span><span class="sxs-lookup"><span data-stu-id="5e052-160">Sign in to Commerce site builder for your environment as a system admin. To configure Azure AD B2C tenants, you must be a system admin for the Commerce environment.</span></span>
1. <span data-ttu-id="5e052-161">I det vänstra navigeringsfönstret väljer du **Webbplatsinställningar** för att expandera den.</span><span class="sxs-lookup"><span data-stu-id="5e052-161">In the left navigation pane, select **Site Settings** to expand it.</span></span>
1. <span data-ttu-id="5e052-162">Välj **kanaler** och välj sedan vilken kanal som ska konfigureras.</span><span class="sxs-lookup"><span data-stu-id="5e052-162">Select **Channels**, and then select the channel to configure.</span></span>
1. <span data-ttu-id="5e052-163">I egenskapsfönstret till höger i fältet **Välj B2C-program**, välj konfigurerad Azure AD B2C-innehavare som ska användas för denna kanal.</span><span class="sxs-lookup"><span data-stu-id="5e052-163">In the properties pane on the right, in the **Select B2C Application** field, select the configured Azure AD B2C tenant to use for this channel.</span></span>
1. <span data-ttu-id="5e052-164">I kommandofältet väljer du **spara och publicera** för att bekräfta den nya eller uppdaterade konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="5e052-164">On the command bar, select **Save and Publish** to commit the new or updated configuration.</span></span>

> [!WARNING]
> <span data-ttu-id="5e052-165">Om du ändrar det B2C-program som har tilldelats till kanalen, tar du bort aktuella referenser som har upprättats för användare som redan har registrerat dig i miljön.</span><span class="sxs-lookup"><span data-stu-id="5e052-165">If you change the B2C application that is assigned to the channel, you remove the current references that have been established for any users who have already signed up in the environment.</span></span> <span data-ttu-id="5e052-166">I detta fall kommer eventuella autentiseringsuppgifter som associeras med det B2C programmet inte att vara tillgängliga för användarna.</span><span class="sxs-lookup"><span data-stu-id="5e052-166">In this case, any credentials that are associated with the currently assigned B2C application won't be available to users.</span></span> <span data-ttu-id="5e052-167">Ändra därför bara en kanal Azure AD B2C konfiguration om du ställer in kanalen för första gången och inga användare har kunnat registrera sig.</span><span class="sxs-lookup"><span data-stu-id="5e052-167">Therefore, change a channel Azure AD B2C configuration only if you're setting up the channel for the first time, and no users have been able to sign up.</span></span> <span data-ttu-id="5e052-168">Annars kan användarna behöva registrera sig igen för att upprätta en post i den nya Azure AD B2C-innehavaren.</span><span class="sxs-lookup"><span data-stu-id="5e052-168">Otherwise, users might have to sign up again to establish a record in the new Azure AD B2C tenant.</span></span>
## <a name="additional-resources"></a><span data-ttu-id="5e052-169">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="5e052-169">Additional resources</span></span>

[<span data-ttu-id="5e052-170">Konfigurera ditt domännamn</span><span class="sxs-lookup"><span data-stu-id="5e052-170">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="5e052-171">Distribuera en ny klientorganisation för näthandel</span><span class="sxs-lookup"><span data-stu-id="5e052-171">Deploy a new e-commerce tenant</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="5e052-172">Skapa en näthandelssajt</span><span class="sxs-lookup"><span data-stu-id="5e052-172">Create an e-commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="5e052-173">Associera en Dynamics 365 Commerce-webbplats med en onlinekanal</span><span class="sxs-lookup"><span data-stu-id="5e052-173">Associate a Dynamics 365 Commerce site with an online channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="5e052-174">Hantera robots.txt-filer</span><span class="sxs-lookup"><span data-stu-id="5e052-174">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="5e052-175">Överför URL-omdirigeringar i bulk</span><span class="sxs-lookup"><span data-stu-id="5e052-175">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="5e052-176">Ställa in en B2C-innehavare i Commerce</span><span class="sxs-lookup"><span data-stu-id="5e052-176">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="5e052-177">Ställa in anpassade sidor för användarinloggningar</span><span class="sxs-lookup"><span data-stu-id="5e052-177">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="5e052-178">Lägga till stöd för ett innehållsleveransnätverk (CDN)</span><span class="sxs-lookup"><span data-stu-id="5e052-178">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="5e052-179">Aktivera platsbaserad butiksdetektering</span><span class="sxs-lookup"><span data-stu-id="5e052-179">Enable location-based store detection</span></span>](enable-store-detection.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
