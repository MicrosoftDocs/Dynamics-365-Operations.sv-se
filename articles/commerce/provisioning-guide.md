---
title: Etablera en förhandsversionsmiljö för Commerce
description: Det här avsnittet förklarar hur du etablerar en förhandsversionsmiljö för Microsoft Dynamics 365 Commerce.
author: psimolin
manager: annbe
ms.date: 01/06/2020
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
ms.author: psimolin
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: ''
ms.openlocfilehash: b77d2cbbc100aeae5dcd53ddbe69ff2e4435da13
ms.sourcegitcommit: 4d77d06a07ec9e7a3fcbd508afdffaa406fd3dd8
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/06/2020
ms.locfileid: "2934758"
---
# <a name="provision-a-commerce-preview-environment"></a><span data-ttu-id="13184-103">Etablera en förhandsversionsmiljö för Commerce</span><span class="sxs-lookup"><span data-stu-id="13184-103">Provision a Commerce preview environment</span></span>

[!include [banner](includes/preview-banner.md)]
[!include [banner](includes/banner.md)]

<span data-ttu-id="13184-104">Det här avsnittet förklarar hur du etablerar en förhandsversionsmiljö för Microsoft Dynamics 365 Commerce.</span><span class="sxs-lookup"><span data-stu-id="13184-104">This topic explains how to provision a Microsoft Dynamics 365 Commerce preview environment.</span></span>

<span data-ttu-id="13184-105">Innan du börjar rekommenderar vi att du åtminstone läser igenom hela ämnet för att få en uppfattning om vad processen medför och vad ämnet innehåller.</span><span class="sxs-lookup"><span data-stu-id="13184-105">Before you begin, we recommend that you at least skim through this whole topic to get an idea of what the process entails and what this topic contains.</span></span>

> [!NOTE]
> <span data-ttu-id="13184-106">Obs! Om du inte har beviljats åtkomst till förhandsgranskning för Dynamics 365 Commerce kan du begära förhandsgranskningsåtkomst [Commerce-webbplats](https://aka.ms/Dynamics365CommerceWebsite).</span><span class="sxs-lookup"><span data-stu-id="13184-106">If you haven't yet been granted access to the Dynamics 365 Commerce preview, you can request preview access from the [Commerce website](https://aka.ms/Dynamics365CommerceWebsite).</span></span>

## <a name="overview"></a><span data-ttu-id="13184-107">Översikt</span><span class="sxs-lookup"><span data-stu-id="13184-107">Overview</span></span>

<span data-ttu-id="13184-108">För att kunna etablera din förhandsversionsmiljö för Commerce måste du skapa ett projekt som har ett specifikt produktnamn och en viss typ.</span><span class="sxs-lookup"><span data-stu-id="13184-108">To successfully provision your Commerce preview environment, you must create a project that has a specific product name and type.</span></span> <span data-ttu-id="13184-109">Miljön och Retail Cloud Scale Unit (RCSU) har även del specifika parametrar som du måste använda för att kunna etablera e-handel senare.</span><span class="sxs-lookup"><span data-stu-id="13184-109">The environment and Retail Cloud Scale Unit (RCSU) also have some specific parameters that you must use when you provision e-Commerce later.</span></span> <span data-ttu-id="13184-110">Instruktionerna i det här avsnittet beskriver alla nödvändiga steg som du måste utföra och de parametrar som du måste använda.</span><span class="sxs-lookup"><span data-stu-id="13184-110">The instructions in this topic describe all the required steps that you must complete and the parameters that you must use.</span></span>

<span data-ttu-id="13184-111">När du har tillhandahållit din förhandsversionsmiljö för Commerce måste du slutföra några steg efter etablering för att förbereda den.</span><span class="sxs-lookup"><span data-stu-id="13184-111">After you successfully provision your Commerce preview environment, you must complete a few post-provisioning steps to prepare it.</span></span> <span data-ttu-id="13184-112">Vissa steg är valfria, beroende på vilka delar av systemet du vill utvärdera.</span><span class="sxs-lookup"><span data-stu-id="13184-112">Some steps are optional, depending on the aspects of the system that you want to evaluate.</span></span> <span data-ttu-id="13184-113">Du kan alltid slutföra de valfria stegen senare.</span><span class="sxs-lookup"><span data-stu-id="13184-113">You can always complete the optional steps later.</span></span>

<span data-ttu-id="13184-114">Information om hur du konfigurerar förhandsversionsmiljö för Commerce efter att du har konfigurerat den finns i [Konfigurera en förhandsversionsmiljö för Commerce](cpe-post-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="13184-114">For information about how to configure your Commerce preview environment after you provision it, see [Configure a Commerce preview environment](cpe-post-provisioning.md).</span></span> <span data-ttu-id="13184-115">Information om hur du konfigurerar valfria funktioner för Commerce efter att du har konfigurerat den finns i [Konfigurera valfria funktioner för förhandsversionsmiljö för Commerce](cpe-optional-features.md).</span><span class="sxs-lookup"><span data-stu-id="13184-115">For information about how to configure optional features for your Commerce preview environment, see [Configure optional features for a Commerce preview environment](cpe-optional-features.md).</span></span>

<span data-ttu-id="13184-116">Om du har frågor om etableringsstegen eller om du stöter på problem ska du tala om för Microsoft i [Microsoft Dynamics 365 Commerce förhandsgranskning Yammer-grupp](https://aka.ms/Dynamics365CommercePreviewYammer).</span><span class="sxs-lookup"><span data-stu-id="13184-116">If you have any questions about the provisioning steps, or if you encounter any issues, let Microsoft know in the [Microsoft Dynamics 365 Commerce Preview Yammer group](https://aka.ms/Dynamics365CommercePreviewYammer).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="13184-117">Förutsättningar</span><span class="sxs-lookup"><span data-stu-id="13184-117">Prerequisites</span></span>

<span data-ttu-id="13184-118">Följande förutsättningar måste vara på plats innan du kan etablera din förhandsversionsmiljö för Commerce:</span><span class="sxs-lookup"><span data-stu-id="13184-118">The following prerequisites must be in place before you can provision your Commerce preview environment:</span></span>

- <span data-ttu-id="13184-119">Du har åtkomst till Microsoft Dynamics Lifecycle Services-portal (LCS).</span><span class="sxs-lookup"><span data-stu-id="13184-119">You have access to the Microsoft Dynamics Lifecycle Services (LCS) portal.</span></span>
- <span data-ttu-id="13184-120">Du har accepterats i Dynamics 365 Commerce förhandsgranskningsprogrammet.</span><span class="sxs-lookup"><span data-stu-id="13184-120">You've been accepted into the Dynamics 365 Commerce Preview program.</span></span>
- <span data-ttu-id="13184-121">Du har de behörigheter som krävs för att skapa ett **projekt för potentiell försäljning** eller **migrera, skapa lösningar och lära dig**.</span><span class="sxs-lookup"><span data-stu-id="13184-121">You have the required permissions to create a project for **Prospective presales** or **Migrate, create solutions, and learn**.</span></span>
- <span data-ttu-id="13184-122">Du är rollen **Miljöhanterare** eller **Projektägare** i projektet där du ska etablera miljön</span><span class="sxs-lookup"><span data-stu-id="13184-122">You're a member of the **Environment manager** or **Project owner** role in the project where you will provision the environment.</span></span>
- <span data-ttu-id="13184-123">Du har administratörsåtkomst till din Microsoft Azure-prenumeration eller kontakta en prenumerationsadministratör som kan slutföra de två steg som kräver administratörsbehörighet för din räkning</span><span class="sxs-lookup"><span data-stu-id="13184-123">You have admin access to your Microsoft Azure subscription, or you're in contact with a subscription admin who can complete the two steps that require admin permissions on your behalf.</span></span>
- <span data-ttu-id="13184-124">Du har ditt Azure Active Directory (Azure AD) innehavar-ID tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="13184-124">You have your Azure Active Directory (Azure AD) tenant ID available.</span></span>
- <span data-ttu-id="13184-125">Du har skapat en Azure AD-säkerhetsgrupp som kan användas som en systemadministratörsgrupp för e-handel och du har dess ID tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="13184-125">You've created an Azure AD security group that can be used as an e-Commerce system admin group, and you have its ID available.</span></span>
- <span data-ttu-id="13184-126">Du har skapat en Azure AD-säkerhetsgrupp som kan användas som gruppen moderator för omdömen och recensioner och du har dess ID tillgängligt.</span><span class="sxs-lookup"><span data-stu-id="13184-126">You've created an Azure AD security group that can be used as a Ratings and Reviews moderator group, and you have its ID available.</span></span> <span data-ttu-id="13184-127">(Den här säkerhetsgruppen kan vara samma som administratörsgruppen för e-handelssystem.)</span><span class="sxs-lookup"><span data-stu-id="13184-127">(This security group can be the same as the e-Commerce system admin group.)</span></span>

### <a name="find-your-azure-ad-tenant-id"></a><span data-ttu-id="13184-128">Hitta ditt Azure AD innehavar-ID</span><span class="sxs-lookup"><span data-stu-id="13184-128">Find your Azure AD tenant ID</span></span>

<span data-ttu-id="13184-129">Ditt Azure AD innehavar-ID är en globalt unik identifierare (GUID) som liknar det här exemplet: **72f988bf-86f1-41af-91ab-2d7cd011db47**.</span><span class="sxs-lookup"><span data-stu-id="13184-129">Your Azure AD tenant ID is a globally unique identifier (GUID) that resembles this example: **72f988bf-86f1-41af-91ab-2d7cd011db47**.</span></span>

#### <a name="find-your-azure-ad-tenant-id-by-using-the-azure-portal"></a><span data-ttu-id="13184-130">Hitta ditt Azure AD innehavar-ID med hjälp av Azure-portal</span><span class="sxs-lookup"><span data-stu-id="13184-130">Find your Azure AD tenant ID by using the Azure portal</span></span>

1. <span data-ttu-id="13184-131">Logga in på [Azure-portal](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="13184-131">Sign in to the [Azure portal](https://portal.azure.com/).</span></span>
1. <span data-ttu-id="13184-132">Kontrollera att du har valt rätt katalog.</span><span class="sxs-lookup"><span data-stu-id="13184-132">Make sure that the correct directory is selected.</span></span>
1. <span data-ttu-id="13184-133">I menyn till vänster, välj **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="13184-133">On the menu on the left, select **Azure Active Directory**.</span></span>
1. <span data-ttu-id="13184-134">Under **egenskaper** under **egenskaper**.</span><span class="sxs-lookup"><span data-stu-id="13184-134">Under **Manage**, select **Properties**.</span></span> <span data-ttu-id="13184-135">Ditt Azure AD innehavar-ID visas under **katalog-ID**.</span><span class="sxs-lookup"><span data-stu-id="13184-135">Your Azure AD tenant ID appears under **Directory ID**.</span></span>

#### <a name="find-your-azure-ad-tenant-id-by-using-openid-connect-metadata"></a><span data-ttu-id="13184-136">Hitta ditt Azure AD innehavar-ID med hjälp av OpenID Connect metadata</span><span class="sxs-lookup"><span data-stu-id="13184-136">Find your Azure AD tenant ID by using OpenID Connect metadata</span></span>

<span data-ttu-id="13184-137">Skapa en OpenID URL genom ersätta **\{YOUR\_DOMAIN\}** med din domän, t.ex. `microsoft.com`.</span><span class="sxs-lookup"><span data-stu-id="13184-137">Create an OpenID URL by replacing **\{YOUR\_DOMAIN\}** with your domain, such as `microsoft.com`.</span></span> <span data-ttu-id="13184-138">Till exempel, `https://login.microsoftonline.com/{YOUR_DOMAIN}/.well-known/openid-configuration` kommer att bli `https://login.microsoftonline.com/microsoft.com/.well-known/openid-configuration`.</span><span class="sxs-lookup"><span data-stu-id="13184-138">For example, `https://login.microsoftonline.com/{YOUR_DOMAIN}/.well-known/openid-configuration` will become `https://login.microsoftonline.com/microsoft.com/.well-known/openid-configuration`.</span></span>

1. <span data-ttu-id="13184-139">Gå till den OpenID-URL som innehåller din domän.</span><span class="sxs-lookup"><span data-stu-id="13184-139">Go to the OpenID URL that contains your domain.</span></span>

    <span data-ttu-id="13184-140">Du hittar ditt Azure AD innehavar-ID i flera egenskapsvärden.</span><span class="sxs-lookup"><span data-stu-id="13184-140">You can find you Azure AD tenant ID in multiple property values.</span></span>

1. <span data-ttu-id="13184-141">Hitta **authorization\_endpoint** och extrahera GUID som visas omedelbart efter `login.microsoftonline.com/`.</span><span class="sxs-lookup"><span data-stu-id="13184-141">Find **authorization\_endpoint**, and extract the GUID that appears immediately after `login.microsoftonline.com/`.</span></span>

### <a name="find-your-azure-ad-security-group-id"></a><span data-ttu-id="13184-142">Hitta ditt Azure AD säkerhetsgrupp-ID</span><span class="sxs-lookup"><span data-stu-id="13184-142">Find your Azure AD security group ID</span></span>

<span data-ttu-id="13184-143">ID för din Azure AD säkerhetsgrupp är ett GUID som liknar det här exemplet: **436ea7f5-ee6c-40c1-9f08-825c5811066a**.</span><span class="sxs-lookup"><span data-stu-id="13184-143">The ID of your Azure AD security group is a GUID that resembles this example: **436ea7f5-ee6c-40c1-9f08-825c5811066a**.</span></span>

<span data-ttu-id="13184-144">Den här proceduren förutsätter att du är medlem i gruppen som du försöker hitta ID för.</span><span class="sxs-lookup"><span data-stu-id="13184-144">This procedure assumes that you're a member of the group that you're trying to find the ID for.</span></span>

1. <span data-ttu-id="13184-145">Öppna [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer#).</span><span class="sxs-lookup"><span data-stu-id="13184-145">Open the [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer#).</span></span>
1. <span data-ttu-id="13184-146">Välj **Logga in med Microsoft** och logga in med dina autentiseringsuppgifter.</span><span class="sxs-lookup"><span data-stu-id="13184-146">Select **Sign In with Microsoft**, and sign in by using your credentials.</span></span>
1. <span data-ttu-id="13184-147">Till vänster väljer du **Visa fler exempel**.</span><span class="sxs-lookup"><span data-stu-id="13184-147">On the left, select **show more samples**.</span></span>
1. <span data-ttu-id="13184-148">Aktivera **grupper** från högra fönstret.</span><span class="sxs-lookup"><span data-stu-id="13184-148">In the right pane, enable **Groups**.</span></span>
1. <span data-ttu-id="13184-149">Stäng den högra rutan.</span><span class="sxs-lookup"><span data-stu-id="13184-149">Close the right pane.</span></span>
1. <span data-ttu-id="13184-150">Klicka på **Alla grupper jag tillhör**.</span><span class="sxs-lookup"><span data-stu-id="13184-150">Select **all groups I belong to**.</span></span>
1. <span data-ttu-id="13184-151">I fältet **Förhandsgranskning av svar** hitta din grupp</span><span class="sxs-lookup"><span data-stu-id="13184-151">In the **Response Preview** field, find your group.</span></span> <span data-ttu-id="13184-152">Säkerhetsgrupp-ID visas under den egenskapen **ID**.</span><span class="sxs-lookup"><span data-stu-id="13184-152">The security group ID appears under the **id** property.</span></span>

## <a name="provision-your-commerce-preview-environment"></a><span data-ttu-id="13184-153">Etablera en förhandsversionsmiljö för Commerce</span><span class="sxs-lookup"><span data-stu-id="13184-153">Provision your Commerce preview environment</span></span>

<span data-ttu-id="13184-154">Dessa procedurer förklarar hur du etablerar en förhandsversionsmiljö för Commerce.</span><span class="sxs-lookup"><span data-stu-id="13184-154">These procedures explain how to provision a Commerce preview environment.</span></span> <span data-ttu-id="13184-155">När du har slutfört dem kommer förhandsversionsmiljö för Commerce att vara redo för konfigurering.</span><span class="sxs-lookup"><span data-stu-id="13184-155">After you successfully complete them, the Commerce preview environment will be ready for configuration.</span></span> <span data-ttu-id="13184-156">Alla aktiviteter som beskrivs här utförs i LCS-portalen.</span><span class="sxs-lookup"><span data-stu-id="13184-156">All the activities that are described here occur in the LCS portal.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="13184-157">Förhandsgranskningsåtkomsten är knuten till LCS-kontot och organisationen som du angav i förhandsgranskningsprogrammet.</span><span class="sxs-lookup"><span data-stu-id="13184-157">Preview access is tied to the LCS account and organization that you specified in your preview application.</span></span> <span data-ttu-id="13184-158">Du måste använda samma konto för att etablera förhandsversionsmiljö för Commerce.</span><span class="sxs-lookup"><span data-stu-id="13184-158">You must use the same account to provision the Commerce preview environment.</span></span> <span data-ttu-id="13184-159">Om du måste använda ett annat LCS-konto eller en innehavare för förhandsversionsmiljö för Commerce måste du ange dessa uppgifter för Microsoft.</span><span class="sxs-lookup"><span data-stu-id="13184-159">If you must use a different LCS account or tenant for the Commerce preview environment, you must provide those details to Microsoft.</span></span> <span data-ttu-id="13184-160">Kontaktinformation finns i avsnittet [Förhandsversionsmiljö för Commerce](#commerce-preview-environment-support) senare i det här ämnet.</span><span class="sxs-lookup"><span data-stu-id="13184-160">For contact information, see the [Commerce preview environment support](#commerce-preview-environment-support) section later in this topic.</span></span>

### <a name="grant-access-to-e-commerce-applications"></a><span data-ttu-id="13184-161">Bevilja åtkomst till e-handelsprogram</span><span class="sxs-lookup"><span data-stu-id="13184-161">Grant access to e-Commerce applications</span></span>

> [!IMPORTANT]
> <span data-ttu-id="13184-162">Den person som loggar in måste vara en Azure AD innehavaradministratören som har Azure AD klient-ID.</span><span class="sxs-lookup"><span data-stu-id="13184-162">The person who signs in must be an Azure AD tenant admin who has the Azure AD tenant ID.</span></span> <span data-ttu-id="13184-163">Om det här steget inte har slutförts, kommer resterande etableringssteg att misslyckas.</span><span class="sxs-lookup"><span data-stu-id="13184-163">If this step isn't successfully completed, the remaining provisioning steps will fail.</span></span>

<span data-ttu-id="13184-164">Gör så här om du vill auktorisera e-handelsprogram åtkomst till din Azure-prenumeration.</span><span class="sxs-lookup"><span data-stu-id="13184-164">To authorize e-Commerce applications to access your Azure subscription, follow these steps.</span></span>

1. <span data-ttu-id="13184-165">Montera en URL i följande format:</span><span class="sxs-lookup"><span data-stu-id="13184-165">Assemble a URL in the following format:</span></span>

    `https://login.windows.net/{AAD_TENANT_ID}/oauth2/authorize?client_id=fbcbf727-cd18-4422-a723-f8274075331a&response_type=code&redirect_uri=https://sb.manage.commerce.dynamics.com/_commerce/Consent&response_mode=query&prompt=admin_consent&state=12345`

1. <span data-ttu-id="13184-166">Kopiera och klistra in URL:en i din webbläsare eller textredigerare och **\{AAD\_TENANT\_ID\}** med ditt Azure AD innehavar-ID.</span><span class="sxs-lookup"><span data-stu-id="13184-166">Copy and paste the URL into your browser or text editor, and replace **\{AAD\_TENANT\_ID\}** with your Azure AD tenant ID.</span></span> <span data-ttu-id="13184-167">Öppna sedan URL:en.</span><span class="sxs-lookup"><span data-stu-id="13184-167">Then open the URL.</span></span>
1. <span data-ttu-id="13184-168">I dialogrutan Azure AD-inloggning, logga in och bekräfta att du vill bevilja **Dynamics 365 Commerce (förhandsversion)** åtkomst till din prenumeration.</span><span class="sxs-lookup"><span data-stu-id="13184-168">In the Azure AD sign-in dialog box, sign in, and confirm that you want to grant **Dynamics 365 Commerce (Preview)** access to your subscription.</span></span> <span data-ttu-id="13184-169">Du omdirigeras till en sida som anger om åtgärden har lyckats.</span><span class="sxs-lookup"><span data-stu-id="13184-169">You're redirected to a page that indicates whether the operation was successful.</span></span>

### <a name="confirm-that-preview-features-are-available-and-turned-on-in-lcs"></a><span data-ttu-id="13184-170">Bekräfta att förhandsgranskningsfunktioner är tillgängliga och aktiverade i LCS</span><span class="sxs-lookup"><span data-stu-id="13184-170">Confirm that preview features are available and turned on in LCS</span></span>

<span data-ttu-id="13184-171">För att bekräfta att förhandsgranskningsfunktioner är tillgängliga och aktiverade i LCS.</span><span class="sxs-lookup"><span data-stu-id="13184-171">To confirm that preview features are available and turned on in LCS, follow these steps.</span></span>

1. <span data-ttu-id="13184-172">Logga in på [LCS-portalen](https://lcs.dynamics.com) med hjälp av samma LCS-konto som du använde för att begära åtkomst till förhandsgranskningen.</span><span class="sxs-lookup"><span data-stu-id="13184-172">Sign in to the [LCS portal](https://lcs.dynamics.com) by using the same LCS account that you used to request access to the preview.</span></span>
1. <span data-ttu-id="13184-173">Rulla hela vägen till höger på LCS-startsida och klicka på panelen för **Hantering av förhandsgranskningsfunktioner**.</span><span class="sxs-lookup"><span data-stu-id="13184-173">On the LCS home page, scroll all the way to the right, and select the **Preview feature management** tile.</span></span>

    ![Panel för förhandsgranskningsfunktion](./media/preview1.png)

1. <span data-ttu-id="13184-175">Rulla ned till **Privata förhandsgranskningsfunktioner** och se till att följande funktioner är tillgängliga och aktiverade:</span><span class="sxs-lookup"><span data-stu-id="13184-175">Scroll down to **Private preview features**, and confirm that the following features are available and turned on:</span></span>

    - <span data-ttu-id="13184-176">Utvärdering av e-handel</span><span class="sxs-lookup"><span data-stu-id="13184-176">e-Commerce Evaluation</span></span>
    - <span data-ttu-id="13184-177">Miljöer för förhandsgranskningsprogram</span><span class="sxs-lookup"><span data-stu-id="13184-177">Commerce Preview Program Environments</span></span>

    ![Privata förhandsgranskningsfunktioner](./media/preview2.png)

1. <span data-ttu-id="13184-179">Om dessa funktioner inte visas i listan kan du kontakta Microsoft och ange din e-postadress för arbete, LCS-konto och klientinformation.</span><span class="sxs-lookup"><span data-stu-id="13184-179">If those features don't appear in the list, contact Microsoft, and provide your work email address, LCS account, and tenant details.</span></span> <span data-ttu-id="13184-180">Kontaktinformation finns i avsnittet [Förhandsversionsmiljö för Commerce](#commerce-preview-environment-support) senare.</span><span class="sxs-lookup"><span data-stu-id="13184-180">For contact information, see the [Commerce preview environment support](#commerce-preview-environment-support) section.</span></span>

### <a name="create-a-new-project"></a><span data-ttu-id="13184-181">Skapa ett nytt projekt</span><span class="sxs-lookup"><span data-stu-id="13184-181">Create a new project</span></span>

<span data-ttu-id="13184-182">Om du vill skapa ett nytt projekt i LCS, följ dessa steg:</span><span class="sxs-lookup"><span data-stu-id="13184-182">To create a new project in LCS, follow these steps.</span></span>

1. <span data-ttu-id="13184-183">På LCS-startsidan väljer du plustecknet (**+**) för att skapa ett projekt.</span><span class="sxs-lookup"><span data-stu-id="13184-183">On the LCS home page, select the plus sign (**+**) to create a project.</span></span>
1. <span data-ttu-id="13184-184">I den högra rutan följer du något av följande steg:</span><span class="sxs-lookup"><span data-stu-id="13184-184">In the right pane, follow one of these steps:</span></span>

    - <span data-ttu-id="13184-185">Om du är partner väljer du **Migrera, skapa lösningar och lär dig**.</span><span class="sxs-lookup"><span data-stu-id="13184-185">If you're a partner, select **Migrate, create solutions, and learn**.</span></span>
    - <span data-ttu-id="13184-186">Om du är kund väljer du **Potentiella försäljningar**.</span><span class="sxs-lookup"><span data-stu-id="13184-186">If you're a customer, select **Prospective presales**.</span></span>

1. <span data-ttu-id="13184-187">Ange ett namn, beskrivning och bransch.</span><span class="sxs-lookup"><span data-stu-id="13184-187">Enter a name, description, and industry.</span></span>
1. <span data-ttu-id="13184-188">I fältet **Produktnamn** välj **Dynamics 365 Retail**.</span><span class="sxs-lookup"><span data-stu-id="13184-188">In the **Product name** field, select **Dynamics 365 Retail**.</span></span>
1. <span data-ttu-id="13184-189">I fältet **Produktversion** välj **Dynamics 365 Retail**.</span><span class="sxs-lookup"><span data-stu-id="13184-189">In the **Product version** field, select **Dynamics 365 Retail**.</span></span>
1. <span data-ttu-id="13184-190">Fältet **Metod**, välj **Dynamics Retail implementeringsmetod**.</span><span class="sxs-lookup"><span data-stu-id="13184-190">In the **Methodology** field, select **Dynamics Retail implementation methodology**.</span></span>
1. <span data-ttu-id="13184-191">Valfritt: Du kan importera roller och användare från ett befintligt projekt.</span><span class="sxs-lookup"><span data-stu-id="13184-191">Optional: You can import roles and users from an existing project.</span></span>
1. <span data-ttu-id="13184-192">Markera **Skapa**.</span><span class="sxs-lookup"><span data-stu-id="13184-192">Select **Create**.</span></span> <span data-ttu-id="13184-193">Projektvyn visas.</span><span class="sxs-lookup"><span data-stu-id="13184-193">The project view appears.</span></span>

### <a name="add-the-azure-connector"></a><span data-ttu-id="13184-194">Lägg till Azure-koppling</span><span class="sxs-lookup"><span data-stu-id="13184-194">Add the Azure Connector</span></span>

<span data-ttu-id="13184-195">Så här lägger du till Azure Connector i ditt LCS-projekt.</span><span class="sxs-lookup"><span data-stu-id="13184-195">To add the Azure Connector to your LCS project, follow these steps.</span></span>

1. <span data-ttu-id="13184-196">Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="13184-196">Follow one of these steps:</span></span>

    - <span data-ttu-id="13184-197">Om du är en partner väljer du panelen **Projektinställningar** längst till höger.</span><span class="sxs-lookup"><span data-stu-id="13184-197">If you're a partner, select the **Project settings** tile on the far right.</span></span>
    - <span data-ttu-id="13184-198">Om du är kund väljer du **projektinställningar** på huvudmenyn.</span><span class="sxs-lookup"><span data-stu-id="13184-198">If you're a customer, select **Project settings** on the top menu.</span></span>

1. <span data-ttu-id="13184-199">Välj **Azure-kopplingar**.</span><span class="sxs-lookup"><span data-stu-id="13184-199">Select **Azure connectors**.</span></span>
1. <span data-ttu-id="13184-200">Klicka på **+ Lägg till** om du vill lägga till Azure-koppling.</span><span class="sxs-lookup"><span data-stu-id="13184-200">Select **Add** to add the Azure Connector.</span></span>
1. <span data-ttu-id="13184-201">Ange ett namn.</span><span class="sxs-lookup"><span data-stu-id="13184-201">Enter a name.</span></span>
1. <span data-ttu-id="13184-202">Ange ditt Azure prenumerations-ID.</span><span class="sxs-lookup"><span data-stu-id="13184-202">Enter your Azure subscription ID.</span></span>
1. <span data-ttu-id="13184-203">Aktivera alternativet **Konfigurera för att använda Azure Resource Manager (ARM)**.</span><span class="sxs-lookup"><span data-stu-id="13184-203">Turn on the **Configure to use Azure Resource Manager (ARM)** option.</span></span>
1. <span data-ttu-id="13184-204">Kontrollera att värdet **Azure-abonnemangets AAD-innehavardomän (eller ID)** är korrekt.</span><span class="sxs-lookup"><span data-stu-id="13184-204">Verify that the **Azure subscription AAD Tenant Domain (or ID)** value is correct.</span></span> <span data-ttu-id="13184-205">Kontakta din Azure abonnemangsadministratör om det behövs.</span><span class="sxs-lookup"><span data-stu-id="13184-205">Consult your Azure subscription admin as required.</span></span>
1. <span data-ttu-id="13184-206">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="13184-206">Select **Next**.</span></span>
1. <span data-ttu-id="13184-207">Följ instruktionerna på sidan och ge de program som krävs åtkomst till din prenumeration.</span><span class="sxs-lookup"><span data-stu-id="13184-207">Follow the instructions on the page to grant the required applications access to your subscription.</span></span> <span data-ttu-id="13184-208">Kontakta din Azure abonnemangsadministratör om det behövs.</span><span class="sxs-lookup"><span data-stu-id="13184-208">Consult your Azure subscription admin as required.</span></span>

    1. <span data-ttu-id="13184-209">Logga in på [Azure-portal](https://portal.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="13184-209">Sign in to the [Azure portal](https://portal.azure.com/).</span></span>
    1. <span data-ttu-id="13184-210">Kontrollera att rätt katalog är markerad och välj sedan **prenumerationer** på menyn till vänster.</span><span class="sxs-lookup"><span data-stu-id="13184-210">Make sure that the correct directory is selected, and then, on the menu on the left, select **Subscriptions**.</span></span>
    1. <span data-ttu-id="13184-211">Leta rätt på den korrekta prenumerationen i listan och markera den.</span><span class="sxs-lookup"><span data-stu-id="13184-211">Find the correct subscription in the list, and select it.</span></span> <span data-ttu-id="13184-212">Använd sökfunktionen efter behov.</span><span class="sxs-lookup"><span data-stu-id="13184-212">Use the search functionality as required.</span></span>
    1. <span data-ttu-id="13184-213">Välj **åtkomstkontroll (IAM)** på menyn.</span><span class="sxs-lookup"><span data-stu-id="13184-213">On the menu, select **Access control (IAM)**.</span></span>
    1. <span data-ttu-id="13184-214">Till höger under **Lägg till** välj **Lägg till**.</span><span class="sxs-lookup"><span data-stu-id="13184-214">On the right, under **Add a role assignment**, select **Add**.</span></span> <span data-ttu-id="13184-215">Fönstret **Lägg till rolltilldelning** visas.</span><span class="sxs-lookup"><span data-stu-id="13184-215">The **Add role assignment** pane appears.</span></span>
    1. <span data-ttu-id="13184-216">I fältet **Roll**, välj **Deltagare**.</span><span class="sxs-lookup"><span data-stu-id="13184-216">In the **Role** field, select **Contributor**.</span></span>
    1. <span data-ttu-id="13184-217">I fältet **Tilldela åtkomst till**, lämna standardvärdet **Azure AD användare, grupp eller Service Principals**.</span><span class="sxs-lookup"><span data-stu-id="13184-217">In the **Assign access to** field, leave the default value, **Azure AD user, group, or service principal**.</span></span>
    1. <span data-ttu-id="13184-218">Under **Välj**, anger du **b96b7e94-b82e-4e71-99a0-cf7fb188acea**.</span><span class="sxs-lookup"><span data-stu-id="13184-218">Under **Select**, enter **b96b7e94-b82e-4e71-99a0-cf7fb188acea**.</span></span>
    1. <span data-ttu-id="13184-219">Välj **Dynamics distributionstjänst \[wsfed-enabled\]** i listan.</span><span class="sxs-lookup"><span data-stu-id="13184-219">Select **Dynamics Deployment Services \[wsfed-enabled\]** in the list.</span></span>
    1. <span data-ttu-id="13184-220">Välj **Spara**.</span><span class="sxs-lookup"><span data-stu-id="13184-220">Select **Save**.</span></span>

1. <span data-ttu-id="13184-221">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="13184-221">Select **Next**.</span></span>
1. <span data-ttu-id="13184-222">Följ instruktionerna på sidan och ge de program som krävs åtkomst till din prenumeration.</span><span class="sxs-lookup"><span data-stu-id="13184-222">Follow the instructions on the page to grant the required applications access to your subscription.</span></span> <span data-ttu-id="13184-223">Kontakta din Azure abonnemangsadministratör om det behövs.</span><span class="sxs-lookup"><span data-stu-id="13184-223">Consult your Azure subscription admin as required.</span></span>
1. <span data-ttu-id="13184-224">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="13184-224">Select **Next**.</span></span>
1. <span data-ttu-id="13184-225">I fältet **Azure-region**, väljer du antingen **östra US**, **östra US 2**, **västra US** eller **västra US 2**.</span><span class="sxs-lookup"><span data-stu-id="13184-225">In the **Azure region** field, select **East US**, **East US 2**, **West US**, or **West US 2**.</span></span>
1. <span data-ttu-id="13184-226">Välj **Anslut**.</span><span class="sxs-lookup"><span data-stu-id="13184-226">Select **Connect**.</span></span> <span data-ttu-id="13184-227">Din Azure-koppling ska visas i listan.</span><span class="sxs-lookup"><span data-stu-id="13184-227">Your Azure Connector should appear in the list.</span></span>

### <a name="import-the-commerce-preview-demo-base-extension"></a><span data-ttu-id="13184-228">Importera Commerce-förhandsgranskning demo bastillägg</span><span class="sxs-lookup"><span data-stu-id="13184-228">Import the Commerce Preview Demo Base Extension</span></span>

<span data-ttu-id="13184-229">Så här importerar du Commerce-förhandsgranskning demo bastillägg till ditt projekt.</span><span class="sxs-lookup"><span data-stu-id="13184-229">To import the Commerce Preview Demo Base Extension into your project, follow these steps.</span></span>

1. <span data-ttu-id="13184-230">Öppna projektets startsida genom att välja projektnamnet överst.</span><span class="sxs-lookup"><span data-stu-id="13184-230">Open the home page for your project by selecting the project name at the top.</span></span>
1. <span data-ttu-id="13184-231">Gör något av följande:</span><span class="sxs-lookup"><span data-stu-id="13184-231">Follow one of these steps:</span></span>

    - <span data-ttu-id="13184-232">Om du är en partner väljer du panelen **Tillgångsbibliotek** längst till höger.</span><span class="sxs-lookup"><span data-stu-id="13184-232">If you're a partner, select the **Asset library** tile on the far right.</span></span>
    - <span data-ttu-id="13184-233">Om du är kund väljer du **Tillgångsbibliotek** på huvudmenyn.</span><span class="sxs-lookup"><span data-stu-id="13184-233">If you're a customer, select **Asset library** on the top menu.</span></span>

1. <span data-ttu-id="13184-234">I listan till vänster, välj **Distribuerbart programpaket**.</span><span class="sxs-lookup"><span data-stu-id="13184-234">In the list on the left, select **Software deployable package**.</span></span>
1. <span data-ttu-id="13184-235">Välj **Importera**.</span><span class="sxs-lookup"><span data-stu-id="13184-235">Select **Import**.</span></span>
1. <span data-ttu-id="13184-236">Under **Delat tillgångsbibliotek**, välj **Commerce-förhandsgranskning demo bastillägg** från listan med tillgångar.</span><span class="sxs-lookup"><span data-stu-id="13184-236">Under **Shared asset library**, select **Commerce Preview Demo Base Extension** in the list of assets.</span></span>
1. <span data-ttu-id="13184-237">Välj **Plocka**.</span><span class="sxs-lookup"><span data-stu-id="13184-237">Select **Pick**.</span></span> <span data-ttu-id="13184-238">Du kommer att returneras till tillgångsbiblioteket och du bör se filnamnstillägget i listan.</span><span class="sxs-lookup"><span data-stu-id="13184-238">You're returned to the Asset library, and you should see the extension in the list.</span></span>

<span data-ttu-id="13184-239">Följande illustration visar de åtgärder som måste vidtas på sidan LCS **tillgångsbibliotek**.</span><span class="sxs-lookup"><span data-stu-id="13184-239">The following illustration shows the actions that must be taken on the LCS **Asset library** page.</span></span>

![Importera Commerce-förhandsgranskning demo bastillägg](./media/import.png)

### <a name="deploy-the-environment"></a><span data-ttu-id="13184-241">Distribuera miljö</span><span class="sxs-lookup"><span data-stu-id="13184-241">Deploy the environment</span></span>

<span data-ttu-id="13184-242">Följ dessa steg för att distribuera miljön.</span><span class="sxs-lookup"><span data-stu-id="13184-242">To deploy the environment, follow these steps.</span></span>

> [!NOTE]
> <span data-ttu-id="13184-243">Du kanske inte behöver slutföra steg 6, 7 och/eller 8, eftersom sidor som har ett enda alternativ hoppas över.</span><span class="sxs-lookup"><span data-stu-id="13184-243">You might not have to complete steps 6, 7, and/or 8, because pages that have a single option are skipped.</span></span> <span data-ttu-id="13184-244">När du är i vyn **Miljöparametrar** bekräfta att texten **Dynamics 365 Commerce (förhandsversion) - Demo (10.0.6 med plattformsuppdatering 30)** visas direkt ovanför fältet **Miljönamn**.</span><span class="sxs-lookup"><span data-stu-id="13184-244">When you're in the **Environment parameters** view, confirm that the text **Dynamics 365 Commerce (Preview) - Demo (10.0.6 with Platform update 30)** appears directly above the **Environment name** field.</span></span> <span data-ttu-id="13184-245">Se illustrationen som visas efter steg 8.</span><span class="sxs-lookup"><span data-stu-id="13184-245">See the illustration that appears after step 8.</span></span>

1. <span data-ttu-id="13184-246">På huvudmenyn väljer du miljön **Molnstyrda miljöer**.</span><span class="sxs-lookup"><span data-stu-id="13184-246">On the top menu, select **Cloud-hosted environments**.</span></span>
1. <span data-ttu-id="13184-247">Klicka på **Lägg till** om du vill lägga till en miljö.</span><span class="sxs-lookup"><span data-stu-id="13184-247">Select **Add** to add an environment.</span></span>
1. <span data-ttu-id="13184-248">I fältet **Programversion**, välj **10.0.6**.</span><span class="sxs-lookup"><span data-stu-id="13184-248">In the **Application version** field, select **10.0.6**.</span></span>
1. <span data-ttu-id="13184-249">I fältet **plattformsversion**, väljer du **plattformsuppdatering 30**.</span><span class="sxs-lookup"><span data-stu-id="13184-249">In the **Platform version** field, select **Platform Update 30**.</span></span>

    ![Välj program- och plattformsversioner](./media/project1.png)

1. <span data-ttu-id="13184-251">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="13184-251">Select **Next**.</span></span>
1. <span data-ttu-id="13184-252">Välj **Demo** som miljötopologi.</span><span class="sxs-lookup"><span data-stu-id="13184-252">Select **Demo** as the environment topology.</span></span>

    ![Välja miljötopologi 1](./media/project2.png)

1. <span data-ttu-id="13184-254">Välj **Dynamics 365 Commerce (förhandsversion) - Demo** som miljötopologi.</span><span class="sxs-lookup"><span data-stu-id="13184-254">Select **Dynamics 365 Commerce (Preview) - Demo** as the environment topology.</span></span> <span data-ttu-id="13184-255">Om du konfigurerade en enda Azure-koppling tidigare kommer den att användas i den här miljön.</span><span class="sxs-lookup"><span data-stu-id="13184-255">If you configured a single Azure Connector earlier, it will be used for this environment.</span></span> <span data-ttu-id="13184-256">Om du har konfigurerat flera Azure-kopplingar kan du välja vilken koppling som: **Östra USA**, **Östra USA 2**, **Västra USA** eller **Västra USA 2**.</span><span class="sxs-lookup"><span data-stu-id="13184-256">If you configured multiple Azure Connectors, you can select which connector to use: **East US**, **East US 2**, **West US**, or **West US 2**.</span></span> <span data-ttu-id="13184-257">(För bästa slutpunkt till slutpunkt-prestanda rekommenderar vi att du väljer **Västra USA 2**.)</span><span class="sxs-lookup"><span data-stu-id="13184-257">(For the best end-to-end performance, we recommend that you select **West US 2**.)</span></span>

    ![Välja miljötopologi 2](./media/project3.png)

1. <span data-ttu-id="13184-259">Ange ett **miljönamn** på sidan distribuera miljö.</span><span class="sxs-lookup"><span data-stu-id="13184-259">On the **Deploy environment** page, enter an environment name.</span></span> <span data-ttu-id="13184-260">Lämna Avancerade inställningar som de är.</span><span class="sxs-lookup"><span data-stu-id="13184-260">Leave the advanced settings as they are.</span></span>

    ![Sidan Distribuera miljö](./media/project4.png)

1. <span data-ttu-id="13184-262">Justera VM-storlek som krävs.</span><span class="sxs-lookup"><span data-stu-id="13184-262">Adjust the VM size as required.</span></span> <span data-ttu-id="13184-263">(Vi rekommenderar VM lagerhållningsenhet \[SKU\]**D13 v2**.)</span><span class="sxs-lookup"><span data-stu-id="13184-263">(We recommend VM stock keeping unit \[SKU\] **D13 v2**.)</span></span>
1. <span data-ttu-id="13184-264">Granska prissättnings- och licensvillkoren och markera sedan kryssrutan för att ange att du godkänner dem.</span><span class="sxs-lookup"><span data-stu-id="13184-264">Review the pricing and licensing terms, and then select the check box to indicate that you agree to them.</span></span>
1. <span data-ttu-id="13184-265">Välj **Nästa**.</span><span class="sxs-lookup"><span data-stu-id="13184-265">Select **Next**.</span></span>
1. <span data-ttu-id="13184-266">På sidan för distributions bekräftelse, när du har kontrollerat att informationen är korrekt, klickar du på **distribuera**.</span><span class="sxs-lookup"><span data-stu-id="13184-266">On the deployment confirmation page, verify that the details are correct, and then select **Deploy**.</span></span> <span data-ttu-id="13184-267">Du kommer tillbaka till vyn **Molnstyrda miljöer** och din miljö bör visas i listan.</span><span class="sxs-lookup"><span data-stu-id="13184-267">You're returned to the **Cloud-hosted environments** view, and your environment should appear in the list.</span></span>

    <span data-ttu-id="13184-268">Den begärda miljön visas som en kö och distribueras sedan.</span><span class="sxs-lookup"><span data-stu-id="13184-268">Your requested environment will appear as queued and then deploying.</span></span> <span data-ttu-id="13184-269">Miljöarbetsflödena kommer att ta lite tid att slutföras.</span><span class="sxs-lookup"><span data-stu-id="13184-269">The environment workflows will take some time to be completed.</span></span> <span data-ttu-id="13184-270">Kontrollera därför tillbaka efter ungefär sex till nio timmar.</span><span class="sxs-lookup"><span data-stu-id="13184-270">Therefore, check back after approximately six to nine hours.</span></span>

1. <span data-ttu-id="13184-271">Innan du fortsätter bör du kontrollera att miljöstatus är **distribuerad**.</span><span class="sxs-lookup"><span data-stu-id="13184-271">Before you continue, make sure that the status of your environment is **Deployed**.</span></span>

### <a name="initialize-rcsu"></a><span data-ttu-id="13184-272">Initiera RCSU</span><span class="sxs-lookup"><span data-stu-id="13184-272">Initialize RCSU</span></span>

<span data-ttu-id="13184-273">Gör så här om du vill initiera en RCSU.</span><span class="sxs-lookup"><span data-stu-id="13184-273">To initialize RCSU, follow these steps.</span></span>

1. <span data-ttu-id="13184-274">Välj din miljö i listan **Molnstyrda miljöer**.</span><span class="sxs-lookup"><span data-stu-id="13184-274">In the **Cloud-hosted environments** view, select your environment in the list.</span></span>
1. <span data-ttu-id="13184-275">Välj i miljövyn till höger **Fullständig information**.</span><span class="sxs-lookup"><span data-stu-id="13184-275">In the environment view on the right, select **Full details**.</span></span> <span data-ttu-id="13184-276">Vyn miljöinformation visas.</span><span class="sxs-lookup"><span data-stu-id="13184-276">The environment details view appears.</span></span>
1. <span data-ttu-id="13184-277">Under **Miljöfunktioner**, välj **hantera**.</span><span class="sxs-lookup"><span data-stu-id="13184-277">Under **Environment features**, select **Manage**.</span></span>
1. <span data-ttu-id="13184-278">På fliken **Butik**, välj **Initiera**.</span><span class="sxs-lookup"><span data-stu-id="13184-278">On the **Retail** tab, select **Initialize**.</span></span> <span data-ttu-id="13184-279">Parametervyn RCSU-initiering visas.</span><span class="sxs-lookup"><span data-stu-id="13184-279">The RCSU initialization parameters view appears.</span></span>
1. <span data-ttu-id="13184-280">I fältet **Region**, väljer du antingen **östra US**, **östra US 2**, **västra US** eller **västra US 2**.</span><span class="sxs-lookup"><span data-stu-id="13184-280">In the **Region** field, select **East US**, **East US 2**, **West US**, or **West US 2**.</span></span>
1. <span data-ttu-id="13184-281">I fältet **version** väljer du **ange en version** i listan och anger sedan **9.16.19262.5** i fältet som visas.</span><span class="sxs-lookup"><span data-stu-id="13184-281">In the **Version** field, select **Specify a version** in the list, and then specify **9.16.19262.5** in the field that appears.</span></span> <span data-ttu-id="13184-282">Var noga med att ange den exakta versionen som anges här.</span><span class="sxs-lookup"><span data-stu-id="13184-282">Be sure to specify the exact version that is indicated here.</span></span> <span data-ttu-id="13184-283">I annat fall måste du uppdatera RCSU till rätt version senare.</span><span class="sxs-lookup"><span data-stu-id="13184-283">Otherwise, you will have to update RCSU to the correct version later.</span></span>
1. <span data-ttu-id="13184-284">Aktivera alternativet **Använd tillägg**.</span><span class="sxs-lookup"><span data-stu-id="13184-284">Turn on the **Apply extension** option.</span></span>
1. <span data-ttu-id="13184-285">Från listan över tillägg, välj **Handelsförhandsgranskning demobastillägg**.</span><span class="sxs-lookup"><span data-stu-id="13184-285">In the list of extensions, select **Commerce Preview Demo Base Extension**.</span></span>
1. <span data-ttu-id="13184-286">Välj **initiera**.</span><span class="sxs-lookup"><span data-stu-id="13184-286">Select **Initialize**.</span></span>
1. <span data-ttu-id="13184-287">På sidan för distributions bekräftelse, när du har kontrollerat att informationen är korrekt, klickar du på **Ja**.</span><span class="sxs-lookup"><span data-stu-id="13184-287">On the deployment confirmation page, verify that the details are correct, and then select **Yes**.</span></span> <span data-ttu-id="13184-288">Du återgår till vyn **Butikshantering** med fliken **Butik** är vald.</span><span class="sxs-lookup"><span data-stu-id="13184-288">You're returned to the **Retail management** view, where the **Retail** tab is selected.</span></span> <span data-ttu-id="13184-289">Din RCSU har ställts i kö för etablering.</span><span class="sxs-lookup"><span data-stu-id="13184-289">Your RCSU has been queued for provisioning.</span></span>
1. <span data-ttu-id="13184-290">Innan du fortsätter bör du kontrollera att status för din RCSU är **Lyckades**.</span><span class="sxs-lookup"><span data-stu-id="13184-290">Before you continue, make sure that the status of your RCSU is **Success**.</span></span> <span data-ttu-id="13184-291">Initieringen tar ungefär två till fem timmar.</span><span class="sxs-lookup"><span data-stu-id="13184-291">Initialization takes approximately two to five hours.</span></span>

### <a name="initialize-e-commerce"></a><span data-ttu-id="13184-292">Initiera e-handelsplattform</span><span class="sxs-lookup"><span data-stu-id="13184-292">Initialize e-Commerce</span></span>

<span data-ttu-id="13184-293">Gör så här om du vill initiera e-handel.</span><span class="sxs-lookup"><span data-stu-id="13184-293">To initialize e-Commerce, follow these steps.</span></span>

1. <span data-ttu-id="13184-294">Granska medgivande för förhandsversion på fliken **e-handel (förhandsversion)** -handel (förhandsversion) och välj sedan **inställningar**.</span><span class="sxs-lookup"><span data-stu-id="13184-294">On the **e-Commerce (Preview)** tab, review the preview consent, and then select **Setup**.</span></span>
1. <span data-ttu-id="13184-295">I fältet **E-handelsinnehavarens namn**, ange ett namn.</span><span class="sxs-lookup"><span data-stu-id="13184-295">In the **e-Commerce tenant name** field, enter a name.</span></span> <span data-ttu-id="13184-296">Tänk dock på att det här namnet kommer att visas i några av webbadresserna som pekar på din e-handelsinstans.</span><span class="sxs-lookup"><span data-stu-id="13184-296">However, be aware that this name will appear in some of the URLs that point to your e-Commerce instance.</span></span>
1. <span data-ttu-id="13184-297">I fältet **Namn på Retail Cloud Scale Unit** välj din RCSU i listan.</span><span class="sxs-lookup"><span data-stu-id="13184-297">In the **Retail cloud scale unit name** field, select your RCSU in the list.</span></span> <span data-ttu-id="13184-298">(Listan bör bara ha ett alternativ.)</span><span class="sxs-lookup"><span data-stu-id="13184-298">(The list should have only one option.)</span></span>

    <span data-ttu-id="13184-299">Fältet **e-handelsgeografi** ställs in automatiskt och värdet kan inte ändras.</span><span class="sxs-lookup"><span data-stu-id="13184-299">The **e-Commerce geography** field is set automatically, and the value can't be changed.</span></span>

1. <span data-ttu-id="13184-300">Klicka på **Nästa** när du vill fortsätta.</span><span class="sxs-lookup"><span data-stu-id="13184-300">Select **Next** to continue.</span></span>
1. <span data-ttu-id="13184-301">I fältet **Värdnamn som stöds** ange en giltig domän, t.ex. `www.fabrikam.com`.</span><span class="sxs-lookup"><span data-stu-id="13184-301">In the **Supported host names** field, enter any valid domain, such as `www.fabrikam.com`.</span></span>
1.  <span data-ttu-id="13184-302">I fältet **AAD säkerhetsgrupp för systemadministration**, ange de första bokstäverna i namnet på säkerhetsgruppen du vill använda.</span><span class="sxs-lookup"><span data-stu-id="13184-302">In the **AAD security group for system admin** field, enter the first few letters of the name of the security group that you want to use.</span></span> <span data-ttu-id="13184-303">Välj ikonen förstoringsglas för att visa sökresultaten.</span><span class="sxs-lookup"><span data-stu-id="13184-303">Select the magnifying class icon to display the search results.</span></span> <span data-ttu-id="13184-304">Välj en säkerhetsgrupp i listan.</span><span class="sxs-lookup"><span data-stu-id="13184-304">Select a security group from the list.</span></span>
2.  <span data-ttu-id="13184-305">I fältet **AAD-säkerhetsgruppen för moderator för omdömen och recensioner**, ange de första bokstäverna i namnet på säkerhetsgruppen du vill använda.</span><span class="sxs-lookup"><span data-stu-id="13184-305">In the **AAD security group for ratings and review moderator** field, enter the first few letters of the name of the security group that you want to use.</span></span> <span data-ttu-id="13184-306">Välj ikonen förstoringsglas för att visa sökresultaten.</span><span class="sxs-lookup"><span data-stu-id="13184-306">Select the magnifying class icon to display the search results.</span></span> <span data-ttu-id="13184-307">Välj en säkerhetsgrupp i listan.</span><span class="sxs-lookup"><span data-stu-id="13184-307">Select a security group from the list.</span></span>
1. <span data-ttu-id="13184-308">Lämna alternativet **tjänsten aktivera klassificering** aktiverat.</span><span class="sxs-lookup"><span data-stu-id="13184-308">Leave the **Enable ratings and review service** option turned on.</span></span>
1. <span data-ttu-id="13184-309">Om du redan har slutfört Microsoft Azure Active Directory (Azure AD) medgivandesteget enligt beskrivningen i avsnittet "bevilja åtkomst till e-handelsprogram" markerar du kryssrutan för att bekräfta ditt medgivande.</span><span class="sxs-lookup"><span data-stu-id="13184-309">If you have already completed the Microsoft Azure Active Directory (Azure AD) consent step as described in the "Grant access to e-Commerce applications" section, select the check box to confirm your consent.</span></span> <span data-ttu-id="13184-310">Om du ännu inte har slutfört det här steget måste du göra det innan du fortsätter med initieringen.</span><span class="sxs-lookup"><span data-stu-id="13184-310">If you have not yet completed this step, you need to do that before proceeding with the initialization.</span></span> <span data-ttu-id="13184-311">Markera länken i texten bredvid kryssrutan för att öppna dialogrutan medgivande och slutför steget.</span><span class="sxs-lookup"><span data-stu-id="13184-311">Select the link within the text next to the check box to open the consent dialog box and complete the step.</span></span>
1. <span data-ttu-id="13184-312">Välj **initiera**.</span><span class="sxs-lookup"><span data-stu-id="13184-312">Select **Initialize**.</span></span> <span data-ttu-id="13184-313">Du återgår till vyn **Butikshantering** med fliken **e-handel (förhandsgranskning)** väljs.</span><span class="sxs-lookup"><span data-stu-id="13184-313">You're returned to the **Retail management** view, where the **e-Commerce (Preview)** tab is selected.</span></span> <span data-ttu-id="13184-314">Initieringen av e-handel har påbörjats.</span><span class="sxs-lookup"><span data-stu-id="13184-314">E-Commerce initialization has started.</span></span>
1. <span data-ttu-id="13184-315">Innan du fortsätter väntar du tills initieringsstatus för e-handel är **initialisering har slutförts**.</span><span class="sxs-lookup"><span data-stu-id="13184-315">Before you continue, wait until the status of e-Commerce initialization is **Initialization successful**.</span></span>
1. <span data-ttu-id="13184-316">Under **länkar** längst ned till höger, anteckna webbadresserna för följande länkar:</span><span class="sxs-lookup"><span data-stu-id="13184-316">Under **Links** in the lower right, make a note of the URLs for the following links:</span></span>

    * <span data-ttu-id="13184-317">**e-handelsplats** – länken till roten på din e-handelsplats.</span><span class="sxs-lookup"><span data-stu-id="13184-317">**e-Commerce site** – The link to the root of your e-Commerce site.</span></span>
    * <span data-ttu-id="13184-318">**e-handelsplats hanteringsverktyg** – länken till webbplatshanteringsverktyget.</span><span class="sxs-lookup"><span data-stu-id="13184-318">**e-Commerce site management tool** – The link to the site management tool.</span></span>

## <a name="commerce-preview-environment-support"></a><span data-ttu-id="13184-319">Support för förhandsversionsmiljö för Commerce</span><span class="sxs-lookup"><span data-stu-id="13184-319">Commerce preview environment support</span></span>

<span data-ttu-id="13184-320">Om du får problem när du slutför etableringsstegen kan du gå till [Microsoft Dynamics 365 Commerce förhandsversion Yammer-gruppen](https://aka.ms/Dynamics365CommercePreviewYammer) och be om hjälp.</span><span class="sxs-lookup"><span data-stu-id="13184-320">If you experience issues while you're completing the provisioning steps, visit the [Microsoft Dynamics 365 Commerce Preview Yammer group](https://aka.ms/Dynamics365CommercePreviewYammer) for help.</span></span>

<span data-ttu-id="13184-321">Om du får problem när du försöker komma åt Yammer-gruppen kan du kontakta Microsoft via e-post på <Dynamics365Commerce@microsoft.com>.</span><span class="sxs-lookup"><span data-stu-id="13184-321">If you experience issues when you try to access the Yammer group, you can contact Microsoft by email at <Dynamics365Commerce@microsoft.com>.</span></span> <span data-ttu-id="13184-322">Den här e-postadressen övervakas inte aktivt.</span><span class="sxs-lookup"><span data-stu-id="13184-322">This email address isn't actively monitored.</span></span> <span data-ttu-id="13184-323">Förvänta dig därför en fördröjning i svaret.</span><span class="sxs-lookup"><span data-stu-id="13184-323">Therefore, expect a delay in the response.</span></span>

## <a name="next-steps"></a><span data-ttu-id="13184-324">Nästa steg</span><span class="sxs-lookup"><span data-stu-id="13184-324">Next steps</span></span>

<span data-ttu-id="13184-325">För att fortsätta processen med att tillhandahålla och konfigurera din förhandsgranskningsmiljö för Commerce, se [Konfigurera en förhandsversionsmiljö för Commerce](cpe-post-provisioning.md).</span><span class="sxs-lookup"><span data-stu-id="13184-325">To continue the process of provisioning and configuring your Commerce preview environment, see [Configure a Commerce preview environment](cpe-post-provisioning.md).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="13184-326">Ytterligare resurser</span><span class="sxs-lookup"><span data-stu-id="13184-326">Additional resources</span></span>

[<span data-ttu-id="13184-327">Förhandsversionsmiljö för Commerce – översikt</span><span class="sxs-lookup"><span data-stu-id="13184-327">Commerce preview environment overview</span></span>](cpe-overview.md)

[<span data-ttu-id="13184-328">Konfigurera en förhandsversionsmiljö för Commerce</span><span class="sxs-lookup"><span data-stu-id="13184-328">Configure a Commerce preview environment</span></span>](cpe-post-provisioning.md)

[<span data-ttu-id="13184-329">Konfigurera valfria funktioner för en förhandsversionsmiljö för Commerce</span><span class="sxs-lookup"><span data-stu-id="13184-329">Configure optional features for a Commerce preview environment</span></span>](cpe-optional-features.md)

[<span data-ttu-id="13184-330">Förhandsversionsmiljö för Commerce – vanliga frågor och svar</span><span class="sxs-lookup"><span data-stu-id="13184-330">Commerce preview environment FAQ</span></span>](cpe-faq.md)

[<span data-ttu-id="13184-331">Microsoft Lifecycle Services (LCS)</span><span class="sxs-lookup"><span data-stu-id="13184-331">Microsoft Lifecycle Services (LCS)</span></span>](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/lifecycle-services/lcs-user-guide)

[<span data-ttu-id="13184-332">Retail Cloud Scale Unit (RCSU)</span><span class="sxs-lookup"><span data-stu-id="13184-332">Retail Cloud Scale Unit (RCSU)</span></span>](https://docs.microsoft.com/business-applications-release-notes/october18/dynamics365-retail/retail-cloud-scale-unit)

[<span data-ttu-id="13184-333">Microsoft Azure-portal</span><span class="sxs-lookup"><span data-stu-id="13184-333">Microsoft Azure portal</span></span>](https://azure.microsoft.com/features/azure-portal)

[<span data-ttu-id="13184-334">Dynamics 365 Commerce webbplatsen</span><span class="sxs-lookup"><span data-stu-id="13184-334">Dynamics 365 Commerce website</span></span>](https://aka.ms/Dynamics365CommerceWebsite)

[<span data-ttu-id="13184-335">Hjälpresurser för Dynamics 365 Retail</span><span class="sxs-lookup"><span data-stu-id="13184-335">Help resources for Dynamics 365 Retail</span></span>](../retail/index.md)
