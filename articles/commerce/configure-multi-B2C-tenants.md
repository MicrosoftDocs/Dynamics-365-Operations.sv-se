---
title: Konfigurera flera B2C-innehavare i en Commerce-miljö
description: Det här avsnittet beskriver när och hur du ställer in flera Microsoft Azure Active Directory (Azure AD) B2C-innehavare för användarautentisering i en dedikerad Dynamics 365 Commerce-miljö.
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
ms.author: brshoo
ms.search.validFrom: 2020-02-12
ms.dyn365.ops.version: ''
ms.openlocfilehash: d0b14e0c662af74464768b66c1c86d03d2944014
ms.sourcegitcommit: 708ca25687a4e48271cdcd6d2d22d99fb94cf140
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 10/10/2020
ms.locfileid: "3976026"
---
# <a name="configure-multiple-b2c-tenants-in-a-commerce-environment"></a><span data-ttu-id="12c78-103">Konfigurera flera B2C-innehavare i en Commerce-miljö</span><span class="sxs-lookup"><span data-stu-id="12c78-103">Configure multiple B2C tenants in a Commerce environment</span></span>

[!include [banner](includes/banner.md)]

<span data-ttu-id="12c78-104">Det här avsnittet beskriver när och hur du ställer in flera Microsoft Azure Active Directory (Azure AD) B2C-innehavare per kanal för användarautentisering i en dedikerad Dynamics 365 Commerce-miljö.</span><span class="sxs-lookup"><span data-stu-id="12c78-104">This topic describes when and how to set up multiple Microsoft Azure Active Directory (Azure AD) business-to-consumer (B2C) tenants per channel for user authentication in a dedicated Dynamics 365 Commerce environment.</span></span>

## <a name="overview"></a><span data-ttu-id="12c78-105">Översikt</span><span class="sxs-lookup"><span data-stu-id="12c78-105">Overview</span></span>

<span data-ttu-id="12c78-106">Dynamics 365 Commerce använder Azure AD B2C molnidentitetstjänst för att stödja autentiseringsuppgifter och verifikationsflöden.</span><span class="sxs-lookup"><span data-stu-id="12c78-106">Dynamics 365 Commerce uses the Azure AD B2C cloud identity service to support user credentials and authentication flows.</span></span> <span data-ttu-id="12c78-107">Användare kan använda verifikationsflöden för att registrera, logga in och återställa sitt lösenord.</span><span class="sxs-lookup"><span data-stu-id="12c78-107">Users can use the authentication flows to sign up, sign in, and reset their password.</span></span> <span data-ttu-id="12c78-108">Azure AD B2C lagrar känslig en användares känsliga autentiseringsinformation, t.ex. hans eller hennes namn och lösenord.</span><span class="sxs-lookup"><span data-stu-id="12c78-108">Azure AD B2C stores a user's sensitive authentication information, such as his or her user name and password.</span></span> <span data-ttu-id="12c78-109">Användarposten är unik för varje B2C-innehavare och använder antingen användarnamn (e-postadress) autentiseringsuppgifter eller autentiseringsuppgifter för social identitet.</span><span class="sxs-lookup"><span data-stu-id="12c78-109">The user record is unique to each B2C tenant, and it uses either user name (email address) credentials or social identity provider credentials.</span></span>

<span data-ttu-id="12c78-110">I de flesta fall används en enda Azure AD B2C-innehavare i en Commerce-miljö.</span><span class="sxs-lookup"><span data-stu-id="12c78-110">In most cases, a single Azure AD B2C tenant is used in a Commerce environment.</span></span> <span data-ttu-id="12c78-111">Commerce-kunder kan sedan skapa och publicera flera webbplatser i samma Commerce-miljö och samma kundautentiseringsuppgifter kommer att användas på dessa webbplatser.</span><span class="sxs-lookup"><span data-stu-id="12c78-111">Commerce customers can then create and publish multiple sites in the same Commerce environment, and the same customer credentials will be used across these sites.</span></span> <span data-ttu-id="12c78-112">Om webbplatserna i miljön ska behandlas som olika varumärken och visas för användarna som separata företag, kan en B2C-innehavare konfigureras för den kanal som används för webbplatsens/varumärkets separation.</span><span class="sxs-lookup"><span data-stu-id="12c78-112">However, if the sites in the environment should be treated as different brands and appear to users as separate businesses, a B2C tenant can be configured for the channel that is used for the site/brand separation.</span></span>

## <a name="considerations-when-multiple-b2c-tenants-are-set-up-per-channel"></a><span data-ttu-id="12c78-113">Att tänka på när flera B2C-innehavare ställs in per kanal</span><span class="sxs-lookup"><span data-stu-id="12c78-113">Considerations when multiple B2C tenants are set up per channel</span></span>

<span data-ttu-id="12c78-114">När varje kanal eller webbplats behandlas som ett separat företag är det bästa alternativet med avseende på användarverifieringsflöden i Commerce att använda separata juridiska enheter.</span><span class="sxs-lookup"><span data-stu-id="12c78-114">Often, when each channel or site is being treated as a separate business, the best option with respect to user authentication flows in Commerce is to use separate legal entities.</span></span> <span data-ttu-id="12c78-115">Om du däremot vill behålla varje kanal/plats i samma miljö och juridisk person, men vill ha separata användarautentisering för varje webbplats, är det viktigt att du tänker på följande saker innan du går vidare:</span><span class="sxs-lookup"><span data-stu-id="12c78-115">However, if you want to keep each channel/site in the same environment and legal entity, but want to have separate user authentication for each site, it's important that you consider the following points before you proceed:</span></span>

- <span data-ttu-id="12c78-116">Användarna får sina egna unika autentiseringsuppgifter för varje kanal/webbplats.</span><span class="sxs-lookup"><span data-stu-id="12c78-116">Users will have their own distinct credentials for each channel/site.</span></span>

    <span data-ttu-id="12c78-117">Samma person kan ha två separata konton per kanal/webbplats, eftersom varje konto är en unik post i en separat B2C-innehavare.</span><span class="sxs-lookup"><span data-stu-id="12c78-117">The same person can have two separate accounts per channel/site, because each account will be a unique entry into a separate B2C tenant.</span></span>

- <span data-ttu-id="12c78-118">I Microsoft Dynamics-miljön kommer separata kundposter att returneras för globala postsökningar.</span><span class="sxs-lookup"><span data-stu-id="12c78-118">In the Microsoft Dynamics environment, separate customer records will be returned for global record searches.</span></span>

    <span data-ttu-id="12c78-119">Om en användare använder samma e-postadress för kanaler/webbplatser returnerar globala kundsökningar resultat för varje kanal/webbplats.</span><span class="sxs-lookup"><span data-stu-id="12c78-119">If a user uses the same email address across channels/sites, global customer searches will return results for each channel/site.</span></span> <span data-ttu-id="12c78-120">(En kanalindikator visas.)</span><span class="sxs-lookup"><span data-stu-id="12c78-120">(A channel indicator will be shown.)</span></span>

- <span data-ttu-id="12c78-121">Adressboken kan användas för att hjälpa till att gruppera användare, så att de kan spåras per kanal.</span><span class="sxs-lookup"><span data-stu-id="12c78-121">The address book can be used to help group users, so that they can be tracked per channel.</span></span>
- <span data-ttu-id="12c78-122">Antalet kundposter per kanal kan öka och denna ökning kan påverka prestandan hos globala kundsökningar.</span><span class="sxs-lookup"><span data-stu-id="12c78-122">The number of customer records per channel might increase, and this increase might affect the performance of global customer searches.</span></span>
- <span data-ttu-id="12c78-123">B2C-innehavare måste mappas omsorgsfullt till en kanal, för att förhindra situationer där kunder registrerar sig för fel innehavare.</span><span class="sxs-lookup"><span data-stu-id="12c78-123">B2C tenants must be carefully mapped to a channel, to help prevent situations where customers sign up for an incorrect tenant.</span></span> <span data-ttu-id="12c78-124">I annat fall kan förvirring och spårningsproblem uppstå.</span><span class="sxs-lookup"><span data-stu-id="12c78-124">Otherwise, confusion or tracking issues can occur.</span></span>

<span data-ttu-id="12c78-125">I bilden nedan visas flera B2C-innehavare i en Commerce-miljö.</span><span class="sxs-lookup"><span data-stu-id="12c78-125">The following illustration shows multiple B2C tenants in a Commerce environment.</span></span>

![Flera B2C-innehavare i en Commerce-miljö](media/MultiB2C_In_Environment.png)

<span data-ttu-id="12c78-127">Om du bestämmer dig för att ditt företag kräver distinkta B2C-innehavare per kanal i samma Commerce-miljö, måste du utföra procedurerna i följande avsnitt för att kunna begära den här funktionen.</span><span class="sxs-lookup"><span data-stu-id="12c78-127">If you decide that your business requires distinct B2C tenants per channel in the same Commerce environment, complete the procedures in the following sections to request this feature.</span></span>

## <a name="request-that-b2c-per-channel-be-enabled-in-your-environment"></a><span data-ttu-id="12c78-128">Begär att B2C per kanal aktiveras i din miljö</span><span class="sxs-lookup"><span data-stu-id="12c78-128">Request that B2C per channel be enabled in your environment</span></span>

<span data-ttu-id="12c78-129">För närvarande, om du vill att olika B2C-innehavare per kanal ska vara tillgängliga i samma Commerce-miljö, måste du skicka en begäran till Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="12c78-129">Currently, if you want distinct B2C tenants per channel to be available in the same Commerce environment, you must submit a request to Dynamics 365 Commerce.</span></span> <span data-ttu-id="12c78-130">Mer information finns i [få support för Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md) eller diskutera det här problemet med din kontakt för Commerce-lösningen.</span><span class="sxs-lookup"><span data-stu-id="12c78-130">For more information, see [Get support for Lifecycle Services (LCS)](../fin-ops-core/dev-itpro/lifecycle-services/lcs-support.md), or discuss this issue with your Commerce solutions contact.</span></span>

## <a name="configure-b2c-tenants-in-your-environment"></a><span data-ttu-id="12c78-131">Konfigurera B2C-innehavare i miljön</span><span class="sxs-lookup"><span data-stu-id="12c78-131">Configure B2C tenants in your environment</span></span>

<span data-ttu-id="12c78-132">Om du vill konfigurera B2C-innehavare i miljön ska du slutföra de relevanta procedurerna i det här avsnittet.</span><span class="sxs-lookup"><span data-stu-id="12c78-132">To configure B2C tenants in your environment, complete the relevant procedures in this section.</span></span>

### <a name="add-an-azure-ad-b2c-tenant"></a><span data-ttu-id="12c78-133">Lägg till en Azure AD B2C-innehavare</span><span class="sxs-lookup"><span data-stu-id="12c78-133">Add an Azure AD B2C tenant</span></span>

<span data-ttu-id="12c78-134">Följ stegen nedan för att lägga till en Azure AD B2C-innehavare i din miljö.</span><span class="sxs-lookup"><span data-stu-id="12c78-134">To add an Azure AD B2C tenant to your environment, follow these steps.</span></span>

1. <span data-ttu-id="12c78-135">Logga in på Commerce webbplatsskapare för din miljö som systemadministratör. Om du vill konfigurera Azure AD B2C-innehavare måste du vara systemadministratör för Commerce-miljön.</span><span class="sxs-lookup"><span data-stu-id="12c78-135">Sign in to Commerce site builder for your environment as a system admin. To configure Azure AD B2C tenants, you must be a system admin for the Commerce environment.</span></span>
1. <span data-ttu-id="12c78-136">I det vänstra navigeringsfönstret väljer du **innehavarinställningar** för att expandera den.</span><span class="sxs-lookup"><span data-stu-id="12c78-136">In the left navigation pane, select **Tenant Settings** to expand it.</span></span>
1. <span data-ttu-id="12c78-137">Välj **B2C-inställningar**, och välj sedan **Hantera**.</span><span class="sxs-lookup"><span data-stu-id="12c78-137">Select **B2C Settings**, and then select **Manage**.</span></span>
1. <span data-ttu-id="12c78-138">Välj **Lägg till B2C-program** och ange sedan följande information:</span><span class="sxs-lookup"><span data-stu-id="12c78-138">Select **Add B2C Application**, and then enter the following information:</span></span>

    - <span data-ttu-id="12c78-139">**Programnamn**: Ange namnet som ska användas för programmet i samband med hantering av det i Commerce.</span><span class="sxs-lookup"><span data-stu-id="12c78-139">**Application Name**: Enter the name that should be used for the application in the context of managing it in Commerce.</span></span> <span data-ttu-id="12c78-140">Vi rekommenderar att du använder det programnamn som du väljer när du ställer in Azure AD B2C-programmet i Azure-portalen.</span><span class="sxs-lookup"><span data-stu-id="12c78-140">We recommend that you use the application name that you chose when you set up the Azure AD B2C application in the Azure portal.</span></span> <span data-ttu-id="12c78-141">På det här sättet kan du minska förvirring när du hanterar B2C-innehavare i Commerce.</span><span class="sxs-lookup"><span data-stu-id="12c78-141">In this way, you can help reduce confusion when you manage B2C tenants in Commerce.</span></span>
    - <span data-ttu-id="12c78-142">**Klientnamn**: Ange det B2C-innehavare som det visas i Azure-portalen.</span><span class="sxs-lookup"><span data-stu-id="12c78-142">**Tenant Name**: Enter the B2C tenant name as it appears in the Azure portal.</span></span>
    - <span data-ttu-id="12c78-143">**Glömt lösenordspolicy-ID**: Ange policy-ID (namnet på principen i Azure-portalen).</span><span class="sxs-lookup"><span data-stu-id="12c78-143">**Forget Password Policy ID**: Enter the policy ID (the name of the policy in the Azure portal).</span></span>
    - <span data-ttu-id="12c78-144">**Policy-ID för registrering och inloggning**: Ange policy-ID (namnet på principen i Azure-portalen).</span><span class="sxs-lookup"><span data-stu-id="12c78-144">**Signup Signin Policy ID**: Enter the policy ID (the name of the policy in the Azure portal).</span></span>
    - <span data-ttu-id="12c78-145">**Klient-GUID**: Ange Azure AD B2C innehavar-ID så som det visas i Azure-portalen (inte program-ID för B2C-innehavare).</span><span class="sxs-lookup"><span data-stu-id="12c78-145">**Client GUID**: Enter the Azure AD B2C tenant ID as it appears in the Azure portal (not the application ID for the B2C tenant).</span></span>
    - <span data-ttu-id="12c78-146">**Redigera profil för policy-ID**: Ange policy-ID (namnet på principen i Azure-portalen).</span><span class="sxs-lookup"><span data-stu-id="12c78-146">**Edit Profile Policy ID**: Enter the policy ID (the name of the policy in the Azure portal).</span></span>

1. <span data-ttu-id="12c78-147">När du har angett den här informationen väljer du **OK** för att spara ändringarna.</span><span class="sxs-lookup"><span data-stu-id="12c78-147">When you've finished entering this information, select **OK** to save your changes.</span></span>

> [!NOTE]
> <span data-ttu-id="12c78-148">Du bör lämna fält som **Omfattning**, **Icke-interaktivt policy-ID**, **Icke-interaktivt klient-ID**, **Anpassad domän för inloggning** och **Policy-ID för registrering** tomma om inte teamet för Dynamics 365 Commerce uppmanar dig att ställa in dem.</span><span class="sxs-lookup"><span data-stu-id="12c78-148">You should leave fields such as **Scope**, **Non Interactive Policy ID**, **Non Interactive Client ID**, **Login Custom Domain**, and **Sign Up Policy ID** blank unless the Dynamics 365 Commerce team instructs you to set them.</span></span>
<span data-ttu-id="12c78-149">Den nya Azure AD B2C-innehavaren ska nu visas i listan under **hantera B2C-program**.</span><span class="sxs-lookup"><span data-stu-id="12c78-149">Your new Azure AD B2C tenant should now appear in the list under **Manage B2C Applications**.</span></span>

### <a name="manage-or-delete-an-azure-ad-b2c-tenant"></a><span data-ttu-id="12c78-150">Hantera eller ta bort Azure AD B2C-innehavare</span><span class="sxs-lookup"><span data-stu-id="12c78-150">Manage or delete an Azure AD B2C tenant</span></span>

1. <span data-ttu-id="12c78-151">Logga in på Commerce webbplatsskapare för din miljö som systemadministratör. Om du vill konfigurera Azure AD B2C-innehavare måste du vara systemadministratör för Commerce-miljön.</span><span class="sxs-lookup"><span data-stu-id="12c78-151">Sign in to Commerce site builder for your environment as a system admin. To configure Azure AD B2C tenants, you must be a system admin for the Commerce environment.</span></span>
1. <span data-ttu-id="12c78-152">I det vänstra navigeringsfönstret väljer du **innehavarinställningar** för att expandera den.</span><span class="sxs-lookup"><span data-stu-id="12c78-152">In the left navigation pane, select **Tenant Settings** to expand it.</span></span>
1. <span data-ttu-id="12c78-153">Välj **B2C-inställningar**, och välj sedan **Hantera**.</span><span class="sxs-lookup"><span data-stu-id="12c78-153">Select **B2C Settings**, and then select **Manage**.</span></span>
1. <span data-ttu-id="12c78-154">Om du vill redigera en B2C-innehavare väljer du pennsymbolen bredvid.</span><span class="sxs-lookup"><span data-stu-id="12c78-154">To edit a B2C tenant, select the pencil symbol next to it.</span></span> <span data-ttu-id="12c78-155">Om du vill ta bort en B2C-innehavare väljer du symbolen bredvid papperskorgen.</span><span class="sxs-lookup"><span data-stu-id="12c78-155">To delete a B2C tenant, select the trash can symbol next to it.</span></span>
1. <span data-ttu-id="12c78-156">Välj **spara** och välj sedan **publicera** för att aktivera ändringarna.</span><span class="sxs-lookup"><span data-stu-id="12c78-156">Select **Save**, and then select **Publish** to activate your changes.</span></span>

> [!WARNING]
> <span data-ttu-id="12c78-157">När en B2C-innehavare har konfigurerats för en pågående/publicerad plats, kan användare ha registrerat sig genom att använda konton som finns på innehavaren.</span><span class="sxs-lookup"><span data-stu-id="12c78-157">When a B2C tenant is configured for a live/published site, users might have signed up by using accounts that are present on the tenant.</span></span> <span data-ttu-id="12c78-158">Om du tar bort en konfigurerad innehavare på menyn **innehavarinställningar \> B2C-innehavare** tar du bort kopplingen till den B2C-innehavare från webbplatser som är associerade med eventuella kanaler hos innehavaren.</span><span class="sxs-lookup"><span data-stu-id="12c78-158">If you delete a configured tenant on the **Tenant Settings \> B2C Tenant** menu, you remove the association of that B2C tenant from sites that are associated with any channels of the tenant.</span></span> <span data-ttu-id="12c78-159">I det här fallet kanske användarna inte längre kan logga in på sina konton.</span><span class="sxs-lookup"><span data-stu-id="12c78-159">In this case, your users might no longer be able to sign in to their accounts.</span></span> <span data-ttu-id="12c78-160">Använd därför yttersta försiktighet när du tar bort en konfigurerad innehavare.</span><span class="sxs-lookup"><span data-stu-id="12c78-160">Therefore, use extreme caution when you delete a configured tenant.</span></span>
>
> <span data-ttu-id="12c78-161">När en konfigurerad innehavare tas bort kommer B2C-innehavaren och posterna att fortsätta underhållas, men systemkonfigurationen för den innehavaren kommer att ändras eller tas bort.</span><span class="sxs-lookup"><span data-stu-id="12c78-161">When a configured tenant is deleted, the B2C tenant and records will continue to be maintained, but the Commerce system configuration of that tenant will be changed or removed.</span></span> <span data-ttu-id="12c78-162">Användare som försöker registrera sig eller logga in på webbplatsen skapar en ny kontopost i den standard- eller B2C-innehavare som har konfigurerats för webbplatsens kanal.</span><span class="sxs-lookup"><span data-stu-id="12c78-162">Users who try to sign up or sign in to the site will create a new account record in the default or newly associated B2C tenant that is configured for the channel of the site.</span></span>
## <a name="configure-your-channel-with-a-b2c-tenant"></a><span data-ttu-id="12c78-163">Konfigurera kanalen med en B2C-innehavare</span><span class="sxs-lookup"><span data-stu-id="12c78-163">Configure your channel with a B2C tenant</span></span>

1. <span data-ttu-id="12c78-164">Logga in på Commerce webbplatsskapare för din miljö som systemadministratör. Om du vill konfigurera Azure AD B2C-innehavare måste du vara systemadministratör för Commerce-miljön.</span><span class="sxs-lookup"><span data-stu-id="12c78-164">Sign in to Commerce site builder for your environment as a system admin. To configure Azure AD B2C tenants, you must be a system admin for the Commerce environment.</span></span>
1. <span data-ttu-id="12c78-165">I det vänstra navigeringsfönstret väljer du **Webbplatsinställningar** för att expandera den.</span><span class="sxs-lookup"><span data-stu-id="12c78-165">In the left navigation pane, select **Site Settings** to expand it.</span></span>
1. <span data-ttu-id="12c78-166">Välj **kanaler** och välj sedan vilken kanal som ska konfigureras.</span><span class="sxs-lookup"><span data-stu-id="12c78-166">Select **Channels**, and then select the channel to configure.</span></span>
1. <span data-ttu-id="12c78-167">I egenskapsfönstret till höger i fältet **Välj B2C-program**, välj konfigurerad Azure AD B2C-innehavare som ska användas för denna kanal.</span><span class="sxs-lookup"><span data-stu-id="12c78-167">In the properties pane on the right, in the **Select B2C Application** field, select the configured Azure AD B2C tenant to use for this channel.</span></span>
1. <span data-ttu-id="12c78-168">I kommandofältet väljer du **spara och publicera** för att bekräfta den nya eller uppdaterade konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="12c78-168">On the command bar, select **Save and Publish** to commit the new or updated configuration.</span></span>

> [!WARNING]
> <span data-ttu-id="12c78-169">Om du ändrar det B2C-program som har tilldelats till kanalen, tar du bort aktuella referenser som har upprättats för användare som redan har registrerat dig i miljön.</span><span class="sxs-lookup"><span data-stu-id="12c78-169">If you change the B2C application that is assigned to the channel, you remove the current references that have been established for any users who have already signed up in the environment.</span></span> <span data-ttu-id="12c78-170">I detta fall kommer eventuella autentiseringsuppgifter som associeras med det B2C programmet inte att vara tillgängliga för användarna.</span><span class="sxs-lookup"><span data-stu-id="12c78-170">In this case, any credentials that are associated with the currently assigned B2C application won't be available to users.</span></span> <span data-ttu-id="12c78-171">Ändra därför bara en kanal Azure AD B2C konfiguration om du ställer in kanalen för första gången och inga användare har kunnat registrera sig.</span><span class="sxs-lookup"><span data-stu-id="12c78-171">Therefore, change a channel Azure AD B2C configuration only if you're setting up the channel for the first time, and no users have been able to sign up.</span></span> <span data-ttu-id="12c78-172">Annars kan användarna behöva registrera sig igen för att upprätta en post i den nya Azure AD B2C-innehavaren.</span><span class="sxs-lookup"><span data-stu-id="12c78-172">Otherwise, users might have to sign up again to establish a record in the new Azure AD B2C tenant.</span></span>
## <a name="additional-resources"></a><span data-ttu-id="12c78-173">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="12c78-173">Additional resources</span></span>

[<span data-ttu-id="12c78-174">Konfigurera ditt domännamn</span><span class="sxs-lookup"><span data-stu-id="12c78-174">Configure your domain name</span></span>](configure-your-domain-name.md)

[<span data-ttu-id="12c78-175">Distribuera en ny näthandelsplats</span><span class="sxs-lookup"><span data-stu-id="12c78-175">Deploy a new e-Commerce site</span></span>](deploy-ecommerce-site.md)

[<span data-ttu-id="12c78-176">Skapa en e-handelsplats</span><span class="sxs-lookup"><span data-stu-id="12c78-176">Create an e-Commerce site</span></span>](create-ecommerce-site.md)

[<span data-ttu-id="12c78-177">Associera en online-webbplats med en kanal</span><span class="sxs-lookup"><span data-stu-id="12c78-177">Associate an online site with a channel</span></span>](associate-site-online-store.md)

[<span data-ttu-id="12c78-178">Hantera robots.txt-filer</span><span class="sxs-lookup"><span data-stu-id="12c78-178">Manage robots.txt files</span></span>](manage-robots-txt-files.md)

[<span data-ttu-id="12c78-179">Överföring av URL-omdirigeringar i bulk</span><span class="sxs-lookup"><span data-stu-id="12c78-179">Upload URL redirects in bulk</span></span>](upload-bulk-redirects.md)

[<span data-ttu-id="12c78-180">Ställa in en B2C-innehavare i Commerce</span><span class="sxs-lookup"><span data-stu-id="12c78-180">Set up a B2C tenant in Commerce</span></span>](set-up-B2C-tenant.md)

[<span data-ttu-id="12c78-181">Ställa in anpassade sidor för användarinloggningar</span><span class="sxs-lookup"><span data-stu-id="12c78-181">Set up custom pages for user logins</span></span>](custom-pages-user-logins.md)

[<span data-ttu-id="12c78-182">Lägga till stöd för ett innehållsleveransnätverk (CDN)</span><span class="sxs-lookup"><span data-stu-id="12c78-182">Add support for a content delivery network (CDN)</span></span>](add-cdn-support.md)

[<span data-ttu-id="12c78-183">Aktivera platsbaserad butiksdetektering</span><span class="sxs-lookup"><span data-stu-id="12c78-183">Enable location-based store detection</span></span>](enable-store-detection.md)
